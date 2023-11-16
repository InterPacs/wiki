---
title: Application Server
description: InterPacs uygulamalarının kimlik doğrulama, yetkilendirme gibi ihtiyaçlarını karşılayan servis.
published: true
date: 2023-11-13T11:17:35.275Z
tags: 
editor: markdown
dateCreated: 2023-11-13T10:45:16.073Z
---

# Gereksinimler
> [Lisans](/Yardımcı-Uygulamalar/Lisans) verilmesi zorunludur.
{.is-warning}

> InterPacs.Logs veritabanı kurulu ve erişilebilir olmak zorundadır.
{.is-warning}


# Kurulum
- Setup dosyasından kurulup yapılır.
- [Lisans verilir](/Yardımcı-Uygulamalar/Lisans).
- C:\Program Files (x86)\InterPacs Health Solutions\InterPacs Application Server klasöründeki config dosyalarına sql bağlantı bilgileri yazılır.
- Kurulum klasöründeki InterPacs.AppServer.DebugForm uygulaması çalıştırılır.
- Certificates sekmesinden uygun bir SSL sertifikası seçilerek **Bind port to certificate** düğmesine basılır.
- Bilgisayarda kullanılabilir durumda bir SSL sertifikası yoksa [SSL sertifikası oluşturulur](/Windows/IIS-Sertifika-Olusturma).
- Main sekmesinden **Start App Server** düğmesine basılarak servis ilk defa çalıştırılır ve veritabanı otomatik olarak oluşur.
- Uygulama kapatılır ve windows servislerinden InterPacs App Server hizmeti başlatılır.

# Kullanım

# Bakım

# Hata Çözümleri
- [APPSRV001 Session timeout.]() Uygulamanızdan başarılı bir şekilde oturum açıldıktan sonra session timeout hatası ile karşılaşılır. Uygulamayı HTTPS üzerinden çalıştırdığınıza emin olun.
{.links-list}