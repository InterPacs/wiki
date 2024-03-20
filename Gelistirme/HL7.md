---
title: HL7 Works
description: HL7 Receive ve Send işlemlerinden sorumlu uygulama
published: true
date: 2024-03-20T07:53:26.200Z
tags: dev
editor: markdown
dateCreated: 2024-03-19T11:43:04.517Z
---

Uygulamanın tanıtımı ve uzun açıklaması.

# Tabs {.tabset}
## Sürüm Notları
### v1.0.0




## Kurulum

### Gereksinimler
> InterPacs.RMS veritabanı kurulu ve erişilebilir olmak zorundadır {.is-warning}


### Kurulum Adımları
1. **InterPacs.HL7.MLLP.exe** setup uygulaması çalıştırılır. Kurulum tamamlanır.
2. Servis konfigürasyonu yapıldıktan sonra **InterPacs HL7 MLLP Service** başlatılır


## Kullanım
> HL7 mesaj yapısı standartlarla belirlenmiş olmasına karşın, farklı hbys'lerde farklı mesaj yapıları ile karşılaşmak mümkün olabiliyor. Bu sebeple HL7 message layout uygulama ayarları içerisinde parametrik olarak saklanmaktadır. {.is-info}

Uygulama konfigürasyon parametreleri;
```toml
[db_settings]
  host = "localhost:1433"
  pass = "sapacs"
  user = "sa"
```
**host**: SQL database host adresi
**pass**: SQL database password
**user**: SQL database username

```toml
forward_addrs = ["127.0.0.1:2101", "10.0.10.1:2102"]
```
Eğer gelen HL7 mesajı başka bir adrese de yönlendirilmek isteniyorsa kullanılır. 
Mesaj aynen iletilir.


```toml
sending_app = "INTERPACS"
sending_facility = "INTERPACS_RIS"
receiving_app = "MONAD"
receiving_facility = "MEDICANA"
hl7_report_addrs = ["localhost:2200"]
hl7_trigger_addr = ":2205"

[doctor_codes]
  "1"= "hbysdoc1"  
  "2"= "hbysdoc2"  
  "3"= "hbysdoc3"  
```

HL7 rapor gönderimi ile ilgili parametreler.
**hl7_trigger_addr**: RMS tarafından rapor onaylandığında, RMS bu port üzerinden worknum iletmektedir. Benzer parametre RMS içerisinde de bulunmaktadır.
**hl7_report_addrs**: Birden fazla uç noktaya rapor gönderilmek isteniyorsa buraya birden fazla adres eklenebilir.
**sending_app, sending_facility, receiving_app, receiving_facility**: HL7 mesaj yapısı ile ilgili. Çalışılan HBYS'ye göre doldurulmalıdır.
**[doctor_codes]**: Rapor gönderiminde HBYS tarafında rapor doktor eşleşmesi yapılabilmesi için her bir doktorun HBYS üzerinde tanımlı bir kodu vardır. Bu parametre girilirken HBYS tarafından iletilen kodun doktorun RMS üzerindeki user'ının id'si ile eşleşmesi gerektiği unutulmamalıdır.

```toml
info_service_enable = false
[scu_setting]
  "host" = "localhost"
  "port" = "104"
  "calling_aet" = "ITP"
  "called_aet" = "SERVERAE"
```

**info_service_enable**: Her gelen HL7 mesajında hasta bilgisi ile bir görüntü oluşturularak hastanın kendi görüntüsüne kaydedilir.
**[scu_setting]**: HL7 uygulamasının PACS'a görüntü gönderebilmesi için gerekli SCU tanımlamaları.

Örnek uygulama konfigürasyon dosyası;

``` toml
forward_addrs = []
listen_addr = ":2100"
rest_addrs = []
log_level = 0
sending_app = "INTERPACS"
sending_facility = "INTERPACS_RIS"
receiving_app = "MONAD"
receiving_facility = "MEDICANA"
hl7_report_addrs = ["localhost:2200"]
hl7_trigger_addr = ":2205"
info_service_enable = false

[db_settings]
  host = "localhost:1433"
  pass = "sapacs"
  user = "sa"

[layout]
  "PID.2" = "PatientID"
  "PID.4.0" = "PatientOtherID" # T.C. Kimlik
  "OBR.2" = "AccessionNumber"
  "PID.5.1" = "PatientFirstName"
  "PID.5.0" = "PatientLastName"
  "PID.5.2" = "PatientMiddleName"
  "PID.7" = "PatientBirthDate"
  "PID.8" = "PatientSex"
  "PID.11" = "PatientAddress"
  "PID.22" = "PatientEthnicGroup"
  "NTE(2).3" = "PatientHistory"
  "OBR.13" = "PatientComments"
  "PV1.8.5" = "ReqPhysicianID"
  "PV1.8.1" = "ReqPhysicianFamilyName"
  "PV1.8.2" = "ReqPhysicianGivenName"
  "PV1.3.1" = "RequestingService"
  "ORC.9" = "SPStartDateTime"
  "OBR.24" = "Modality"
  #"ORC.12" = "RequestingPhysician"
  "ORC.12" = "ReferringPhysician"
  #"ORC.12.5" = "ReqPhysicianID"
  #"ORC.12.1" = "ReqPhysicianFamilyName"
  #"ORC.12.2" = "ReqPhysicianGivenName"
  "OBR.4.0" = "SPStepID"
  "OBR.4.1" = "SPStepDescription"
  "PV1.19" = "AdmissionID"
  "DG1(*).3.1" = "AdmittingDiagnosisDesc"
  "OBR.17" = "PatientPhone"
  #"OBR.21" = "SStationAETitle"
  "PV1.2" = "PatientClass"
  "OBR.21" = "ModalityId"

[doctor_codes]
  "1"= "fdasd564654654"  

[scu_setting]
  "host" = "localhost"
  "port" = "104"
  "calling_aet" = "ITP"
  "called_aet" = "SERVERAE"
```

## Bakım

## Hata Çözümleri

### Uygulama Hataları

### Uygulama Dışı Hatalar

#

[Geliştirme Notları](/Gelistirme/Uygulama-Adi)