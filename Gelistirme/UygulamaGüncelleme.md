---
title: Uygulama Güncelleme
description: Uygulamaları güncelleme sunucusuna entegre etme
published: true
date: 2024-01-31T11:48:06.353Z
tags: dev, update
editor: markdown
dateCreated: 2024-01-30T14:10:06.659Z
---

Geliştirilen uygulamalara kurulum ve güncelleme paketleri oluşturarak güncelleme sunucusuna entegre etmek için aşağıdaki konuları okuyunuz.

# Tabs {.tabset}
## Entegrasyon
- Nuget üzerinden squirrel.windows paketini uygulamanıza yükleyin
- Uygulamanızın uygun yerine güncellemenin kontrol edileceği kod bloğunu yerleştirin
- Sunucuda çalışan uygulamalar için güncelleme sunucusunun localhost üzerinde var olduğu varsayılır
- Sunucuda çalışmayan yada farklı sunucuda çalışan uygulamalar için kod içindeki URL güncelleme sunucusunu işaret etmelidir
- URL'nin uygulama ayarlarından değiştirilebilir olması faydalı olur
- Kodun yerini uygulamanın açılışını yavaşlatmayacak şekilde konumlandırmanız faydalı olur

```
using (var mgr = new UpdateManager("https://localhost/UpdateServer/Releases"))
{
   await mgr.UpdateApp();
}
```
- Uygulamanızın kurulum, güncelleştirme ve kaldrırılma esnasında tetiklenmesini istiyorsanız aşağıdaki adımları da uygulayın
- `AssemblyInfo.cs` dosyasına aşağıdaki satırı ekleyin
```
[assembly: AssemblyMetadata("SquirrelAwareVersion", "1")]
```
- Uygulamanızda erken bir safhada çalışmak üzere aşağıdaki kodu ekleyerek istenilen olaylarda istediğiniz şekilde kod çalıştırabilirsiniz
```
static bool ShowTheWelcomeWizard;
static int Main(string[] args) 
{
    // NB: Note here that HandleEvents is being called as early in startup
    // as possible in the app. This is very important! Do _not_ call this
    // method as part of your app's "check for updates" code.

    using (var mgr = new UpdateManager(updateUrl))
    {
        // Note, in most of these scenarios, the app exits after this method
        // completes!
        SquirrelAwareApp.HandleEvents(
          onInitialInstall: v => mgr.CreateShortcutForThisExe(),
          onAppUpdate: v => mgr.CreateShortcutForThisExe(),
          onAppUninstall: v => mgr.RemoveShortcutForThisExe(),
          onFirstRun: () => ShowTheWelcomeWizard = true);
    }
}
```


## Paketleme

Paketleme işlemi hem kurulum paketi oluşturmak için hemde güncelleme paketi oluşturmak için kullanılabiliyor.

### Build
- Uygulama versiyonunuzu sağ tuş Properties yada `Properties\AssemblyInfo.cs` dosyasından belirleyin
```
[assembly: AssemblyVersion("1.0.0")]
[assembly: AssemblyFileVersion("1.0.0")]
```
- Uygulamanızı Release modunda build edin

### İlk Paketleme (kurulum paketi)
- [Nuget Package Explorer](https://www.microsoft.com/store/apps/9wzdncrdmdm3) uygulamasını kuruyoruz
- Uygulama üzerinden yeni bir nuget paketi oluşturuyoruz
![nugetpackageexplorer.png](/gelistirme/nugetpackageexplorer.png)
- Edit Metadata ile uygulamamızın temel bilgilerini giriyoruz
- Id kısmına boşluksuz uygulama adını yazıyoruz (örnek: InterPacs.AppServer)
- Version kısmına uygulamanın versiyonununu yazıyoruz
- Package contents kısmına önce `lib` klasörünü ekliyoruz altına ise uygulamanız hangi .net versiyonunu kullanırsa kullansın `net45` klasörünü ekliyoruz
- Uygulamanızın release edilmiş halindeki gerekli tüm dosyaları `net45` klasörünün altına ekliyoruz
- Son olarak nuget paketini uygulamamızın .sln dosyasının yanına kaydediyoruz

## Dağıtma

- Package Manager Console kullanarak aşağıdaki komut ile uygulamayı paketliyoruz
```
Squirrel --releasify MyApp.1.0.0.nupkg
```
- Komuta parametre olarak uygulamamızın nuget paketinin adını veriyoruz
- Komutu çalıştırdığınızda Setup dosyalarını `Releases` klasörüne oluşturarak yanına `-full` isimli nuget paketini koyacaktır
- Full bu paket ile direk kurulum yapılabileceği anlamına gelir
- Komut bir sonraki versiyon için çalıştırıldığında ise bir önceki versiyon ile aradaki farkları bularak `-delta` isimli bir güncelleme paketi ve aynı zamanda yeni versiyonun da `-full` isimli kurulabilir paketini ekleyecektir


## Yükleme

## Güncelleme