---
title: Power BI Hizmetinde Metin Olarak Döndürülen İç İçe Değerlerle İlgili Sorunları Giderme
description: Hatalı veri kaynağı gizlilik ayarları kullanıldığında iç içe değerlerin dizeye dönüştürülmesini nasıl düzelteceğinizi öğrenin
author: cpopell
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 6/4/2019
ms.author: gepopell
LocalizationGroup: Reports
ms.openlocfilehash: 61181f9317718b6a4fb1cd73a767e4002b5b27f5
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72544247"
---
# <a name="troubleshooting-nested-values-returned-as-text-in-power-bi-service"></a>Power BI Hizmetinde Metin Olarak Döndürülen İç İçe Değerlerle İlgili Sorunları Giderme

## <a name="cause"></a>Neden

Geçmişte, bazı durumlarda Desktop'da düzgün yenilenen bir Power BI raporu Power BI hizmetinde “"[Tablo]" değerini Tablo türüne dönüştüremiyoruz” gibi bir hatayla başarısız oluyordu. Bu hatanın nedenlerinden biri Veri Gizliliği Ağ Geçidi veri kaynağını arabelleğe aldığında iç içe skaler olmayan değerlerin (tablolar, kayıtlar, listeler ve işlevler gibi) otomatik olarak metin değerlerine (“[Tablo]” veya “[Kayıt]” gibi) dönüştürülmesidir.

Artık Power BI hizmeti gizlilik düzeylerinin ayarlanmasını (veya Güvenlik Duvarının tamamen kapatılmasını) desteklediğinden, Power BI hizmetinde [veri kaynağı gizlilik ayarları Gizli dışında bir değere yapılandırılarak](https://powerbi.microsoft.com/en-us/blog/privacy-levels-for-cloud-data-sources/) bu tür hatalar önlenebilir.

Haziran ayından başlayarak, Güvenlik Duvarı iç içe bir tabloyu/kaydı/listeyi/vb. arabelleğe aldığında Power BI sessizce bu değerleri metne dönüştürmek yerine şu hatayı oluşturacak: 

`We cannot return a value of type Table in this context`

## <a name="effect-on-loadrefresh"></a>Yükleme/Yenileme Etkileniyor

Bu değişikliği Güvenlik Duvarı arabelleği harekete geçirmiş olsa da, değişiklik Yükleme/Yenileme üzerinde de etkili olacak. Güvenlik Duvarı arabellek davranışını çözmek için, iç içe tabloların/kayıtların/vb. Power BI Modeline ve Excel için PQ'da Excel Veri Modeline yüklenme davranışını da değiştirmek zorunda kaldık. Daha önce iç içe tablolar/kayıtlar/vb. metin değerleri (“[Tablo]” veya “[Kayıt]” gibi) olarak yüklenebiliyordu. Artık bunlar hata olarak kabul edilecek, sonuçta yüklenen tabloda null değer yer alacak ve yükleme sonuçlarında hata sayısı bir artırılacak.

Bu hatalar yalnızca Yükleme/Yenileme sırasında oluştuğundan Power Query Editor'da gösterilmeyecekler.

### <a name="before"></a>Önce

- Hatasız Yükleme/Yenileme
- Yüklenen tablo “[Tablo]”, “[Kayıt]” vb. içeriyor
 

### <a name="after"></a>Sonra

- Hatalı Yükleme/Yenileme
- Yüklenen tablo “[Tablo]”, “[Kayıt]” vb. yerine NULL değerler içeriyor
 

## <a name="resolution"></a>Çözüm

Skaler olmayan değerlerin bulunduğu bir sütun mu yüklüyorsunuz (örneğin tablolar, listeler, kayıtlar vb.)?
Öyleyse, sütunu kaldırarak hataları ortadan kaldırabilmelisiniz.
Sütunu kaldıramıyorsanız, özel bir sütun ekleyip aşağıdaki örnekte gösterilene benzer bir mantık kullanarak eski davranışı yineleyebilmelisiniz:

`if [MyColumn] is table then "[Table]" else if [MyColumn] is record then "[Record]" else if [MyColumn] is list then "[List]" else if [MyColumn] is function then "[Function]" else [MyColumn]`

Power BI Desktop'ta tüm veri kaynağı gizlilik ayarlarınızı Gizli olarak belirlediğinizde sorun yeniden üretilebiliyor mu?
Öyleyse, Power BI hizmetinde [veri kaynağı gizlilik ayarlarını Gizli dışında bir değere yapılandırarak](https://powerbi.microsoft.com/en-us/blog/privacy-levels-for-cloud-data-sources/) hatayı düzeltebilmelisiniz.
