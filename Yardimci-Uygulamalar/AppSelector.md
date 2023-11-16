---
title: Application Selector
description: Web uygulamaları tarafından gelen istekleri InterPacs uygulamalarına gönderir
published: true
date: 2023-11-16T11:04:21.518Z
tags: 
editor: markdown
dateCreated: 2023-11-16T10:53:30.317Z
---

Web uygulamalarının InterPacs uygulamalarına entegre olarak istek ve veri gönderebilmesini sağlar. Kurulum sonraı windows üzerinde itp:// protokolü aktif hale gelir.


# Sürüm Notları
### v1.2.2.0
- "Yönetici olarak çalıştır" seçeneği eklendi.
### v1.2.1.1
- Yeni ClearCanvas Viewer versiyonu için değişiklik yapıldı. Bu versiyondan sonra eski viewer açılmayacak sadece yeni viewer açılacak.
- Viewer açık olduğu halde yeni bir viewer açılması sorunu düzeltildi.
### v1.2.0.0
- URL ile verilen MP3 dosyasını C:\ITP\ITPPlayer\ITPPlayer.exe ile açma özelliği eklendi.
Örnek: `itp:Type=MP3&URL=http://www.interpacs.com.tr:1983/video/000_3/Rihana.mp3`



# Kurulum
1. Setup dosyasından kurulum başlatılır.
2. Eğer bilgisayar bir Active Directory Domainine bağlı ise kurulum esnasında sorulan URL yetkisi alanına yetki verilecek domain kullanıcı adı veya grubu yazılır.
3. Kurulum tamamlanır.

Not: Eğer URL yetkisi verme işlemi bir şekilde başarısız oluyorsa [Uygulamanın açılması çok uzun sürdü](/Hatalar/AppSel001) hatasına bakınız.

## Gereksinimler


### v1.0.0 - Kurulum notları
- Talimat 1
- Talimat 2

# Kullanım

# Bakım

# Hata Çözümleri

### Uygulama Hataları
- [AppSel001 *Uygulamanın açılması çok uzun sürdü.*](/Hatalar/AppSel001)
{.links-list}

### Uygulama Dışı Hatalar

[Geliştirme Notları](/Gelistirme/Uygulama-Adi)