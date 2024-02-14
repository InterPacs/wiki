---
title: Application Selector
description: Web uygulamaları tarafından gelen istekleri InterPacs uygulamalarına gönderir
published: true
date: 2023-11-18T17:56:50.978Z
tags: 
editor: markdown
dateCreated: 2023-11-16T10:53:30.317Z
---

Web uygulamalarının InterPacs uygulamalarına entegre olarak istek ve veri gönderebilmesini sağlar. Kurulum sonraı windows üzerinde itp:// protokolü aktif hale gelir.

# Tabs {.tabset}

## Sürüm Notları
### v1.5.6
- Bir görüntü açılmak istendiğinde Windows üzerinde oturum açmış olan kullanıcı adı ve açmak istediği görüntü bilgilerinin InterPacs.Viewer uygulamasının Log servisine gönderilmesi sağlandı. Bu özelliğin çalışması için Viewer uygulamasında kullanıcı adı: log şifresi: log4net olan bir kullanıcı açılması gerekiyor. Daha sonra uygulama üzerinden Log yaz seçeneği seçilerek sunucu adresinin aşağıdakine benzer şekilde girilmesi gerekiyor.
![001.png](/appsel/001.png =600x)
- Uygulamaya tanımladığımız sunucu ve partition listesinin InterPacs Dicom Viewer'ın sunucu listesini güncellemesi sağlandı. Sunucular ve bölümler ekranında aşağıda kalan "Viewer'ın sunucularınıda güncelle" seçeneği seçildiği zaman bu listedeki bilgiler Viewer'ın listesine otomatik eklenecek.
![002.png](/appsel/002.png =300x)
- Ayrıca bu eklenen kayıtlar Application Selector üzerinden değiştirildiğinde Viewer üzerinde de değişiklik gerçekleşiyor fakat bu takibin yapılabilmesi için Viewer üzerinde Location kısmının kurcalanmamış olması gerekiyor. Location kısmına sunucuları takip etmek için bir numara yazıyoruz. Bu silinirse takip edilemiyor. Sunucu isimleri Viewer'a SunucuAdı.BölümAdı şeklinde geliyor.
![003.png](/appsel/003.png =300x)
### v1.4.1
- Uygulamanın birden fazla partition'a baktığında birden fazla çekim bulursa ekrana bir pencere çıkartıp hangisini açmak istediğini kullanıcıya sorması sağlandı. Açılan pencerede çekimlerin hangi sunucuda olduğuda gözükmekte. Dolayısıyla kullanıcı kendisine yakın olanı da seçebilir hale geldi.
### v1.3.0
- Uygulamaya çeşitli uygulama entegrasyon ve tetikleme işlemlerini test edebilmek için bir sekme eklendi.
##### v1.3.0.1
- Gönderilen accession number'a ait çekim bulunamadığında hastanın 20 çalışmasını açma özelliği eklendi.
##### v1.3.0.2
- Önceki versiyonda tespit edilen bir hata düzeltildi.
### v1.2.3
- Viewer'da ekli olan birden fazla sunucuda arama yapabilmesi için AE Title alanına virgül ile ayırarak birden fazla giriş yapabilme özelliği eklendi.
- Sadece PatientId ile hastanın tüm çekimlerinin açılması sağlandı.
### v1.2.2
- "Yönetici olarak çalıştır" seçeneği eklendi.
##### v1.2.2.1
- Domain ortamında uygulama çalışırken kullanıcı adı ve parola istemesinden dolayı yaşanan sıkıntıları çözmek için kurulum sihirbazına ClearCanvas'ın WCF servisinin URL yetkisi verilecek kullanıcı veya grup adı sayfası eklendi. Domain olmayan bir ortamda bu sayfada değişiklik yapmadan devam edebilirsiniz. Domain ortamında ise isteğe göre bu sayfada uygulamayı kullanacak kişinin kullanıcı adı veya bir grup adı (Users veya DomainUsers gibi) belirtilebilir.
##### v1.2.2.2
- Ayarların tüm kullanıcılar tarafından ortak kullanılması sağlandı. Yönetici olarak çalıştır varsayılan olarak kapalı yapıldı. Kurulumun tüm kullanıcılara yapılması varsayılan olarak ayarlandı.
##### v1.2.2.3
- URLAclForXP paketi kuruluma dahil edildi.
- Ayarların tüm kullanıcılar tarafından ortak kullanılması ile ilgili bir sorun giderildi.
### v1.2.1
- Yeni ClearCanvas Viewer versiyonu için değişiklik yapıldı. Bu versiyondan sonra eski viewer açılmayacak sadece yeni viewer açılacak.
##### v.1.2.1.1
- Viewer açık olduğu halde yeni bir viewer açılması sorunu düzeltildi.
### v1.2.0
- URL ile verilen MP3 dosyasını C:\ITP\ITPPlayer\ITPPlayer.exe ile açma özelliği eklendi.
Örnek: `itp:Type=MP3&URL=http://www.interpacs.com.tr:1983/video/000_3/Rihana.mp3`



## Kurulum
1. Setup dosyasından kurulum başlatılır.
2. Eğer bilgisayar bir Active Directory Domainine bağlı ise kurulum esnasında sorulan URL yetkisi alanına yetki verilecek domain kullanıcı adı veya grubu yazılır.
3. Kurulum tamamlanır.

Not: Eğer URL yetkisi verme işlemi bir şekilde başarısız oluyorsa [Uygulamanın açılması çok uzun sürdü](/Hatalar/AppSel001) hatasına bakınız.

### Gereksinimler


### v1.0.0 - Kurulum notları
- Talimat 1
- Talimat 2

## Kullanım

## Bakım

## Hata Çözümleri

### Uygulama Hataları
- [AppSel001 *Uygulamanın açılması çok uzun sürdü.*](/Hatalar/AppSel001)
{.links-list}

### Uygulama Dışı Hatalar

#
[Geliştirme Notları](/Gelistirme/Uygulama-Adi)