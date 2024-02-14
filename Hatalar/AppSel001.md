---
title: AppSel001
description: Uygulamanın açılması çok uzun sürdü
published: true
date: 2023-11-16T11:00:06.863Z
tags: 
editor: markdown
dateCreated: 2023-11-16T11:00:04.221Z
---

# Hata Mesajı
Uygulamanın açılması çok uzun sürdü.

# Ekran Görüntüsü

# Çözüm
Setup paketi ile kurulum yapılırken URL yetkisinin kime verileceği sorulmaktadır. Eğer bilgisayar Active Directory Domainine bağlı ise URL yetkisi verilmesi gerekebilir. Bilgisayarı kullanan domain kullanıcısına yada bir domain gurubuna yetki verilebilir. Setup paketi tamamlandığında URL yetkisini uygulamayı kullanan kişiye vermeyi başardı ise sorun çözülecektir. Eğer URL yetkisi verme işlemi bir şekilde başarısız oluyorsa yönetici olarak açılmış komut satırından aşağıdaki kod çalıştırılarak yetki verilebilir. Aşağıdaki komutta örnek kullanıcı adı ahmet olarak verilmiştir. Bu kısıma domainadı\kullanıcıadı şeklinde uygun bilgiyi yazmalısınız.

`netsh http add urlacl url=http://+:51124/ClearCanvas/ImageViewer/Automation user=ahmet`