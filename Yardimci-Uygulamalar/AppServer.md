---
title: Application Server
description: InterPacs uygulamalarının kimlik doğrulama, yetkilendirme gibi ihtiyaçlarını karşılayan servis.
published: true
date: 2024-01-10T11:10:27.777Z
tags: 
editor: markdown
dateCreated: 2023-11-13T10:45:16.073Z
---

# Tabs {.tabset}
## Sürüm Notları
## Kurulum
### Gereksinimler
> [Lisans](/Yardımcı-Uygulamalar/Lisans) verilmesi zorunludur.
{.is-warning}

> InterPacs.Logs veritabanı kurulu ve erişilebilir olmak zorundadır.
{.is-warning}

### Kurulum Adımları
- Setup dosyasından kurulum yapılır.
- [Lisans verilir](/Yardımcı-Uygulamalar/Lisans).
- C:\Program Files (x86)\InterPacs Health Solutions\InterPacs Application Server klasöründeki config dosyalarına sql bağlantı bilgileri yazılır.
- Kurulum klasöründeki InterPacs.AppServer.DebugForm uygulaması çalıştırılır.
- Certificates sekmesinden uygun bir SSL sertifikası seçilerek **Bind port to certificate** düğmesine basılır.
- Bilgisayarda kullanılabilir durumda bir SSL sertifikası yoksa [SSL sertifikası oluşturulur](/Windows/IIS-Sertifika-Olusturma).
- Main sekmesinden **Start App Server** düğmesine basılarak servis ilk defa çalıştırılır ve veritabanı otomatik olarak oluşur.
- Uygulama kapatılır ve windows servislerinden InterPacs App Server hizmeti başlatılır.

## Kullanım
- AppServer InterPacs'ın geliştirdiği diğer programlar için bir altyapı oluşturmaktadır. Kimlik doğrulama, yetkilendirme gibi hazır hizmetleri diğer programların kullanımına sunmaktadır.
- Diğer programlar ilk açılışlarında AppServer kurulumlarını tamamlamak için ilk oturumlarını AppServer yönetici hesabı ile açmalılar. AppServer yönetici hesabı ile oturum açıldığında diğer program AppServer sistemine kurulmuş olur. Bu sayede diğer programın default hesap grupları, hesapları, yetkileri otomatik olarak oluşturulur.
- Diğer programın ilk kurulumundan sonra güncelleme ile yetkilerinin değiştirilmesi durumunda, yetkilerin AppServer tarafında güncellenmesi için bir kere AppServer yönetici hesabı ile oturum açılması gerekir.
## Bakım

## Hata Çözümleri
- [APPSRV001 Session timeout.]() Uygulamanızdan başarılı bir şekilde oturum açıldıktan sonra session timeout hatası ile karşılaşılır. Uygulamayı HTTPS üzerinden çalıştırdığınıza emin olun.
{.links-list}