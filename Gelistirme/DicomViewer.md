---
title: Dicom Viewer
description: Geliştirme Notları
published: true
date: 2023-11-23T12:34:14.861Z
tags: dev
editor: markdown
dateCreated: 2023-11-23T09:07:21.808Z
---

Uygulamanın tanıtımı ve uzun açıklaması.

# Tabs {.tabset}
## Sürüm Notları
### v1.0.0
- Değişiklik 1
- Değişiklik 2



## Kurulum

### Gereksinimler
> [App Server](/Uygulamalar/AppServer) kurulu ve erişilebilir olmak zorundadır.
{.is-warning}

> InterPacs.Logs veritabanı kurulu ve erişilebilir olmak zorundadır.
{.is-warning}

### Kurulum Adımları
1. zip dosyası ... klasörü içine açılır.
2. IIS üzerinde yeni bir uygulama oluşturularak bu klasöre bağlanır.

## Kullanım

### Retrieve

- Servis oluşturulur.
>sc create InterPacs.DicomViewer binpath= "C:\ITP\VIEWER\ClearCanvas.Server.ShredHostService.exe -service"
- Retrieve için dicom viewer tarafından kullanılan port [firewalla]() eklenir.




## Bakım

## Hata Çözümleri

### Uygulama Hataları

### Uygulama Dışı Hatalar

#

[Geliştirme Notları](/Gelistirme/Uygulama-Adi)