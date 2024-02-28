---
title: Dicom Viewer
description: Geliştirme Notları
published: true
date: 2024-02-28T12:29:17.711Z
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

`msbuild.exe ImageViewer.proj /p:DistributionBuild=true,param2=value`

## ImageViewer_dist.proj
- `DesktopBuild` true, false
- `ShredHostBuild` true, false
- `ConsoleBuild` true, false


## ImageViewer.proj

- `Configuration` Debug, Release
- `DistributionBuild` true, false
- `PROCESSOR_ARCHITECTURE` IA64, AMD64, x86
- `PackageOption` ThinEnterprise, NormalEnterprise, Thin, Normal
- `KeyFile` Key dosyası verildiğinde exe'yi imzalıyormuş

## ImageViewerManifest.proj

- `DistributionDirectory`
- `Certificate`
- `Password`
- `ManifestFiles`
- `OptionsFlags`
	- `ExcludeExplorer`
  - `ExcludeDesktopServices`
  - `ExcludeStudyComposer`
  - `ExcludeDicomEditor`
  - `ExcludeStudyFilters`
  - `ExcludeReporting`
  - `ExcludeHelpUpdate`
  - `ExcludeDatabase`
  - `ExcludeDicomRemote`
  - `ExcludeStreaming`
  - `ExcludeMpr`
  - `ExcludeFusion`
  - `ExcludeExternals`
  - `ExcludeSynchronizationTools`
  - `ExcludeEnterprise`
  - `ExcludeHelpFiles`

### Bazı proj dosyalarının ilişkileri
* `PostBuild_dist.proj` Bazı projelerde build öncesi devreye giriyor

* `ImageViewerSamples_dist.proj`
	* `ImageViewer_dist.proj`
  
* `Calendar_dist.proj`
	* `ImageViewer_dist.proj`
  
* `Ris.proj`
	* `RisClient.proj`
  * `RisServer.proj`
  
* `RisServer_dist.proj`
* `RisServerManifest.proj`
  
* `RisClient_NativeViewer_dist.proj`
	* `RisClient_dist.proj`
	* `ImageViewer_dist.proj`
  