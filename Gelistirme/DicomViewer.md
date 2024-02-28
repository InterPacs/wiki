---
title: Dicom Viewer
description: Geliştirme Notları
published: true
date: 2024-02-28T08:35:04.354Z
tags: dev
editor: markdown
dateCreated: 2023-11-23T09:07:21.808Z
---

>Tüm kod geliştirmeleri `/trunk` üzerinde yapılır.

>Viewer'ın siyah temalı versiyonu için `/trunk`'dan `/theme` branchine merge işlemi yapılır. Conflictler giderilir.

# Build
>İlk defa checkout yapıldığında ilk build her zaman fail olur. Devamındaki buildlerde hata alınmıyor olmalı.

>Startup projesi ClearCanvas.Desktop.Executable olmalı.

>Release olarak Build edildiğinde düzenlenmiş hali `/bin/Publish` klasöründen alınabilir.

## Proj Otomasyon Dosyaları
ClearCanvas tarafından oluşturulmuş `.proj` uzantılı otomasyon dosyalarını çalıştırmak için örnek komut satırı aşağıdadır. Parametreler ve ne işe yaradıkları keşfedildikçe dokümana eklenecektir.

`msbuild.exe ImageViewer.proj /p:DistributionBuild=true`

## ImageViewer.proj

- `DistributionBuild` true, false
- `PROCESSOR_ARCHITECTURE` AMD64, x86