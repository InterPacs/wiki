---
title: Mobile Viewer
description: Dicom görüntülerinin mobil ortamlardan görüntülenebilmesini sağlar.
published: true
date: 2024-06-26T11:21:57.702Z
tags: 
editor: markdown
dateCreated: 2024-06-26T08:49:04.687Z
---

Uygulamanın tanıtımı ve uzun açıklaması.

# Tabs {.tabset}
## Sürüm Notları
### v1.1.0
- Framework kütüphaneleri 1.1.0 versiyonuna yükseltildi




## Kurulum

### Gereksinimler
> [App Server](/Uygulamalar/AppServer) kurulu ve erişilebilir olmak zorundadır.
{.is-warning}

### Kurulum Adımları
1. zip dosyası C:\ITP klasörü içine açılır.
2. IIS üzerinde yeni bir uygulama oluşturularak bu klasöre bağlanır.
3. [Teletıp WADO](/Uygulamalar/TeletipWado) uygulaması kurulu ve çalışır durumda olmalıdır. WADO uygulamasının Mobile Viewer'ın yayınlandığı kök dizinin altında /wado olarak çalıştırılması önerilir.

## Kullanım

### Ayarlar
**PACS Port:** Pacs sunucusunun portu

**PACS AE Title:** Pacs sunucusunun AE Title bilgisi

**WADO URL:** [Teletıp WADO](/Uygulamalar/TeletipWado) uygulamasının kurulduğu URL. Genellikle /wado klasörüne kurulur. Örneğin: https://mobile.test.com/wado

**Series Create Delay:** Uygulamada serilerin oluşturulma gecikmesi. Örneğin 1000 yazıldığında uygulama her bir seriyi oluşturduktan sonra bir sonraki seriyi oluşturmadan önce bir saniye bekler.

**Instance Create Delay:** Uygulamada her bir resmin oluşturulma gecikmesi. Örneğin 1000 yazıldığında uygulama her bir resmi oluşturduktan sonra bir sonraki resmi oluşturmadan önce bir saniye bekler.



## Bakım

## Hata Çözümleri

### Uygulama Hataları

### Uygulama Dışı Hatalar

#

[Geliştirme Notları](/Gelistirme/Uygulama-Adi)