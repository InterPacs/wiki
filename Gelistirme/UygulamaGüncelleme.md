---
title: Uygulama Güncelleme
description: Uygulamaları güncelleme sunucusuna entegre etme
published: true
date: 2024-01-30T14:10:06.659Z
tags: update
editor: markdown
dateCreated: 2024-01-30T14:10:06.659Z
---

Geliştirilen uygulamaları güncelleme sunucusuna entegre etmek için aşağıdaki konuları okuyunuz.

# Tabs {.tabset}
## Entegrasyon
- Uygulamanızın solution klasörünün içine Releases isimli bir klasör açın (.sln dosyasının yanına)
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

## Paketleme


## Dağıtma

## Yükleme

## Güncelleme