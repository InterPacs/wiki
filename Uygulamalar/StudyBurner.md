---
title: Study Burner
description: Hastanın PACS verilerini medya ortamına aktararak üzerine baskı yapılmasını sağlar
published: true
date: 2023-11-16T13:31:22.507Z
tags: 
editor: markdown
dateCreated: 2023-11-16T13:31:22.507Z
---

Rimage ve Epson marka CD Robot cihazları ile entegre olarak PACS sunucusundaki hasta verilerini medya ortamına aktarır ve üzerine hastane, hasta, çekim bilgilerini yazar.


# Sürüm Notları
### v1.3.1
- Medya uyuşmazlığı gibi görünüp işlerin iş sırasında kalması ile ilgili bir sorun giderildi.
- Birden fazla medya türü konulabilen cihazlarda tek medya kullanabilme özelliği eklendi.

### v1.3.0
- Birden fazla Rimage cihazının tek bilgisayarda kullanılabilmesi sağlandı. (lisans alınırken cihaz sayısının belirtilmesi gerekiyor aksi taktirde ilk cihaz hariç diğer cihazlar çalışmayacaktır)
- Rimage SDK 9.2 versiyonuna geçildi.
- Sipariş düğmesi kaldırıldı.
- Yükleme ve kaldırma sorunları giderildi.
- Depolama alanı ayarlara eklendi.
- CD yerine DVD basma sorunu giderildi.
- Eski PET cihazları için "Positron Emission Tomography Curve Storage" görüntülerinin kabul edilmesi sağlandı.
- Medya üzerine basılan hasta bilgilerinin içerisinde virgül karakterinin bulunduğu durumlarda çıkan sorun giderildi.
- Medya giriş çıkışlarının isimlerinin düzgün gözükmesi sağlandı.
- Referring Physician ve Requesting Physician alanlarının etiketlerde kullanılması sağlandı.

### v1.2.2
- Rimage Allegro 100 desteği eklendi.
- Eski görüntülerin otomatik silinmesi ile ilgili bir sorun giderildi.
- Birden fazla medya türü konulabilen modellerde iki tarafa birden DVD konulduğunda çıkabilecek bir sorun giderildi.
- Epson desteği stabil hale getirildi.
- Epson için bazı hata mesajları türkçeleştirildi.
- Masaüstüne StudyBurner kısayolu oluşturulması sağlandı.
- Setup ile firewall üzerinden 104 ve 1010 numaralı portların açılması sağlandı.
- Windows 10 desteği eklendi.
- IIS Application Pool ayarlarının otomatik yapılması sağlandı.
- Bazı durumlarda işlerin sol taraftaki listede kalması ve baskı yapmaması sorunu için geliştirme yapıldı.

### v1.1.1
- Donanım bağımlı lisans modeline geçildi
- EPSON PP100 cihaz desteği eklendi
- AETitle ve Port bilgileri ayarlara konuldu
- EPSON veya Rimage ile çalışabilmek için ayarlara çalışma modu eklendi
- Lisans bilgileri ana ekranda görülecek şekilde ayarlandı



# Kurulum
## Gereksinimler
> IIS kurulu olmak zorundadır.
{.is-warning}
### Rimage
> Rimage yazılımları kurulu olmalıdır.
{.is-warning}

### Epson
> Epson yazılımları kurulu olmalıdır.
{.is-warning}

> TDBridge yazılımı kurulu olmak zorundadır.
{.is-warning}

> Epson Total Disc Manager ile TDBridge aynı versiyon olmalıdır.
{.is-warning}

## Kurulum Adımları
1. Web setup ve servis setup kurulumları yapılır.
1. [Lisans]() verilir.
1. Study Burner servisi çalıştırılır.
1. [https://localhost/StudyBurner](https://localhost/StudyBurner) adresinden uygulamaya erişilir.
1. Varsayılan yönetici hesabı: admin, şifresi: 1
1. Ayarlardan kullanılan cihaza göre Rimage yada Epson seçeneği seçilir.
1. Servis yeniden başlatılır.


# Kullanım

# Bakım

# Hata Çözümleri

### Uygulama Hataları

### Uygulama Dışı Hatalar

[Geliştirme Notları](/Gelistirme/StudyBurner)