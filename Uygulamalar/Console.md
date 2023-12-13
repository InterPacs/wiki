---
title: Console
description: Uygulama kısa açıklama
published: true
date: 2023-12-11T12:47:06.432Z
tags: 
editor: markdown
dateCreated: 2023-12-09T13:34:52.649Z
---

Console uygulaması ImageServer web uygulamasının yeni versiyonudur. 
ImageServerHelper uygulamasındaki KOS takip ekranı bu uygulamaya taşınmıştır.

# Tabs {.tabset}
## Sürüm Notları
### v1.0.0
>  - Study ekranında KOS gönderim ve worklist durumlarının görülmesi sağlanmıştır. KOS gönderimi yapılmış ise çekim silme ve güncelleme yapması engellenmiştir.
>  - "Teletıp" ekranı eklenmiştir.
>  - Teletip yardımcı servisleri eklenmiştir.
>  - "Workqueue" ekranı eklenmiştir.
>  - "PACS Log" ekranı eklenmiştir.
>  - "Raporlar" eklenmiştir.
>  - Sık kullanılan SQL komutlarının çalıştırıldığı "Çoklu Komutlar" eklenmiştir.
>  - "Cihazlar" ekranı eklenmiştir.
>  - "Sunucu Bölümleri" ekranı eklenmiştir.
>  - "Dosya Sistemleri" ekranı eklenmiştir.
> 
{.is-info}



## Kurulum

### Gereksinimler
> [App Server](/Uygulamalar/AppServer) kurulu ve erişilebilir olmak zorundadır.
{.is-warning}

> InterPacs.Logs veritabanı kurulu ve erişilebilir olmak zorundadır.
{.is-warning}

### Kurulum Adımları
1. InterPacs.Console klasörü C:\inetpub ya da C:\ITP içerisine kopyalayın.
2. IIS üzerinde "Default Website" altında yeni bir uygulama oluşturularak bu klasöre bağlayın.
3. Webconfig dosyasındaki 3 adet veritabanı bağlantı bilgilerini güncelleyin.
4. ***"Create_NonClustered_Index_for_worklist.sql"*** script dosyasını çalıştırın.
5. InterPacs.Console veritabanındaki "Institutions" tablosunu KOS gönderimi yapacak tüm partition'lar için doldurun. 
6. ImageServerHelper uygulamasındaki kullanıcıları Console uygulamasında tanımlayın.
7. SQL Reporting Servis kurulumunu yapın.


### Notlar
- Console uygulamasının kullanımı ile birlikte aşağıdaki uygulamaların kullanımı devre dışı kalacaktır.
1. InterPacs.TeletipService
2. ImageServerHelper
3. InterPacs.RMS veritabanın da yer alan "Institution" tablosu

## Kullanım
> - Rapor modülünün çalışması için URL içinde Host değil bilgisayar adı kullanılır. 
{.is-warning}

## Bakım

## Hata Çözümleri

### Uygulama Hataları

### Uygulama Dışı Hatalar

#

[Geliştirme Notları](/Gelistirme/Uygulama-Adi)