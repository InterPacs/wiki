---
title: CaptureDevice
description: Uygulama kısa açıklama
published: true
date: 2024-04-02T09:44:59.857Z
tags: 
editor: markdown
dateCreated: 2024-01-29T08:13:49.234Z
---

Uygulamanın tanıtımı ve uzun açıklaması.
InterPacs.CaptureDevice uygulaması Gastroenteroloji bölümündeki işlemlerde görüntü ve video alınmasını sağlayıp bunların PACS'a gönderilmesini ve bu işleme ait raporların yazılmasını sağlayan uygulamadır.
# Tabs {.tabset}
## Sürüm Notları
### v3.0.0
- Raporun HBYS'ye gönderilmesi için HL7 entegrasyonu eklendi
- Doktor tanımlama ekranı eklendi
- Cihaz tanımlama ekranı eklendi
- Rapora cihaz parametresi eklendi
- Worklist'ten hasta güncellenmesi eklendi
- Yeni hasta kayıt ekranına doktor ve cihaz eklendi
- Hasta değişikliklerinin takibi için hasta geçmiş takibi eklendi



## Kurulum

## Güncelleme

### Gereksinimler
Windows 10 ve üstü olmalıdır
SQL Server 2016 ve üstü kurulmalıdır

### Kurulum Adımları
1. Setup kurulumu yapılır
2. Editor klasörü kurulum yapılan path'e kopyalanır
3. phantom.js klasörü yoksa kurulum yapılan path'e kopyalanır.
4. x64 klasörünün içeriği kurulum yapılan path'e kopyalanır.
5. ffmpeg.exe dosyası kurulum yapılan path'e kopyalanır.
6. HID exe çalıştırılır ve oluşan id ile lisans verilir
7. Oluşturulan lisans kurulum yapılan path'e kopyalanır.
8. ReportHeader klasörün de bulunan header dosyasından kurum bilgileri düzenlenir. Header dosyası şablona 8 tane fotoğraf gelecek şekilde ayarlanmıştır. Eğer 6 tane fotoğrafın şablonda olması talep edilirse header-6.html dosyasının içeriği header.html dosyasının içeriğine kopyalanır.
9. ReportHeader klasöründe bulunan footer dosyasından kurum adres bilgisi düzenlenir.


## Kullanım

[endo.pdf](/endo.pdf)

## Bakım

## Hata Çözümleri

### Uygulama Hataları


### Uygulama Dışı Hatalar

#

[Geliştirme Notları](/Gelistirme/Uygulama-Adi)