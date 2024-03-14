---
title: CaptureDevice
description: Uygulama kısa açıklama
published: true
date: 2024-03-14T13:48:40.086Z
tags: 
editor: markdown
dateCreated: 2024-01-29T08:13:49.234Z
---

Uygulamanın tanıtımı ve uzun açıklaması.
InterPacs.CaptureDevice uygulaması Gastroenteroloji bölümündeki işlemlerde görüntü ve video alınmasını sağlayıp bunların PACS'a gönderilmesini ve bu işleme ait raporların yazılmasını sağlayan uygulamadır.
# Tabs {.tabset}
## Sürüm Notları
### v1.0.0
- Değişiklik 1
- Değişiklik 2



## Kurulum



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