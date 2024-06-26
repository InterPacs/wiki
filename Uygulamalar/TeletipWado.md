---
title: Teletıp Wado
description: Teletıp için özelleştirilmiş bir wado sunucusudur.
published: true
date: 2024-06-26T10:59:43.616Z
tags: 
editor: markdown
dateCreated: 2024-06-26T10:59:43.616Z
---

Teletıp için özelleştirilmiş bir wado sunucusudur.

Hastanenin sağladığı bir domainin 35005 numaralı portundan public olarak yayınlanır. Sağlık bakanlığı bu porta bağlanarak gerekli olduğunda pacs görüntülerine erişir.

Yayınlandığı yerden index.html dosyasına eriştiğinizde izin verilmiş olan kişilere o anki işlemlerle ilgili logları gösterir

# Tabs {.tabset}
## Sürüm Notları
### v1.0.0
- Değişiklik 1



## Kurulum

### Gereksinimler
> [App Server](/Uygulamalar/AppServer) kurulu ve erişilebilir olmak zorundadır.
{.is-warning}

### Kurulum Adımları
1. zip dosyası C:\ITP klasörü içine açılır.
2. IIS üzerinde yeni bir uygulama oluşturularak bu klasöre bağlanır.
3. Genellikle [Mobile Viewer](/Uygulamalar/MobileViewer) uygulaması ile beraber kullanılır. Örneğin mobile viewer mobil.test.com üzerinden yayınlanıyorsa wado da mobil.test.com/wado yolundan yayınlanır. Sağlık bakanlığı için 35005 nolu port ayrıca yayınlanır.

## Kullanım
### Ayarlar
**Cookie Base URL:** Genellikle yayınlandığı domainin kök adresidir. Örneğin https://mobil.test.com şeklindedir.

**Mobile Viewer URL:** Genellikle yayınlandığı domainin kök adresidir. Örneğin https://mobil.test.com şeklindedir.

**Unrestricted Socket IP Address:** /index.html adresinden loglara erişebilecek IP adreslerinin listesi.

**Unrestricted WADO IP Address:** Kimlik doğrulama olmadan direk görüntü gönderilecek IP adreslerinin listesi.

**Unrestricted Domains:** Hangi diğer domainlerin bu hizmete erişebileceğinin listesi.

**Second WADO:** Bulunamayan görüntülerin başka bir WADO sunucusundan sorgulanmasını sağlar.

## Bakım

## Hata Çözümleri

### Uygulama Hataları

### Uygulama Dışı Hatalar

#

[Geliştirme Notları](/Gelistirme/Uygulama-Adi)