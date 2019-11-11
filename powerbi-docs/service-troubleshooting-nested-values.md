---
title: Power BI Hizmetinde Metin Olarak Döndürülen İç İçe Değerlerle İlgili Sorunları Giderme
description: Hatalı veri kaynağı gizlilik ayarları kullanıldığında iç içe değerlerin dizeye dönüştürülmesini nasıl düzelteceğinizi öğrenin
author: cpopell
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 6/4/2019
ms.author: gepopell
LocalizationGroup: Reports
ms.openlocfilehash: ab40ca9c415dacf52f4d82eb2c157d57aef92f93
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73871278"
---
# <a name="troubleshooting-nested-values-returned-as-text-in-power-bi-service"></a>Power BI Hizmetinde Metin Olarak Döndürülen İç İçe Değerlerle İlgili Sorunları Giderme

## <a name="cause"></a>Neden

Geçmişte, bazı durumlarda Desktop'da düzgün yenilenen bir Power BI raporu Power BI hizmetinde “"[Tablo]" değerini Tablo türüne dönüştüremiyoruz” gibi bir hatayla başarısız oluyordu. Bu hatanın nedenlerinden biri Veri Gizliliği Ağ Geçidi veri kaynağını arabelleğe aldığında iç içe skaler olmayan değerlerin (tablolar, kayıtlar, listeler ve işlevler gibi) otomatik olarak metin değerlerine (“[Tablo]” veya “[Kayıt]” gibi) dönüştürülmesidir.

Artık Power BI hizmeti gizlilik düzeylerinin ayarlanmasını (veya Güvenlik Duvarının tamamen kapatılmasını) desteklediğinden, Power BI hizmetinde [veri kaynağı gizlilik ayarları Gizli dışında bir değere yapılandırılarak](https://powerbi.microsoft.com/blog/privacy-levels-for-cloud-data-sources/) bu tür hatalar önlenebilir.

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
Öyleyse, Power BI hizmetinde [veri kaynağı gizlilik ayarlarını Gizli dışında bir değere yapılandırarak](https://powerbi.microsoft.com/blog/privacy-levels-for-cloud-data-sources/) hatayı düzeltebilmelisiniz.
