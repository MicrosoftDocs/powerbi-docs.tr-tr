---
title: Power BI Desktop'ta SAP HANA'yı kullanma
description: Power BI Desktop'ta SAP HANA'yı kullanma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7b3a59ae8926ce5e302cfcdecec617d1f3fd107b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513854"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Power BI Desktop'ta SAP HANA'yı kullanma
Power BI Desktop'ta artık **SAP HANA** veritabanlarına erişebilirsiniz. **SAP HANA**'yı kullanabilmek için Power BI Desktop **SAP HANA** veri bağlantısının düzgün çalışabilmesi amacıyla yerel istemci bilgisayara SAP HANA ODBC sürücüsünün yüklenmesi gerekir. SAP HANA ODBC sürücüsünü [SAP Software Download Center](https://support.sap.com/swdc) sayfasından indirebilirsiniz. Bu sayfada Windows bilgisayarlar için SAP HANA CLIENT uygulamasını arayın. **SAP Software Download Center** sayfasının yapısı sıklıkla değiştiğinden sitede gezinmeyle ilgili ayrıntılı bilgi veremiyoruz.

Bir **SAP HANA** veritabanına bağlanmak için aşağıdaki görüntüde gösterildiği gibi **Veri Al > Veritabanı > SAP HANA Veritabanı** yolunu izleyin:

![](media/desktop-sap-hana/sap-hana-1.png)

SAP HANA veritabanına bağlanırken sunucu adını ve bağlantı noktasını *sunucu adı:bağlantı noktası* biçiminde belirtin. Aşağıdaki resimde *ServerXYZ* adlı ve *30015* numaralı bağlantı noktasını kullanan bir örnek gösterilmiştir.

![](media/desktop-sap-hana/sap-hana-2.png)

Bu sürümde Power BI Desktop ve Power BI hizmetinde **SAP HANA**, [DirectQuery](desktop-directquery-sap-hana.md) modunda desteklenmektedir ve **SAP HANA** kullanan raporları DirectQuery modunda Power BI hizmetine yükleyip orada yayımlayabilirsiniz. Ayrıca, **SAP HANA**'yı DirectQuery modunda kullanmadığınızda da raporları Power BI hizmetine yükleyip orada yayımlayabilirsiniz.

## <a name="supported-features-for-sap-hana"></a>SAP HANA için desteklenen özellikler
Bu sürümde aşağıdaki listede görebileceğiniz gibi birçok **SAP HANA** özelliği desteklenmektedir:

* **SAP HANA** için Power BI bağlayıcısı, en iyi kullanıcı deneyimini sunmak için SAP ODBC sürücüsünü kullanır
* **SAP HANA**, hem DirectQuery hem de İçeri Aktarma seçeneklerini destekler
* Power BI, HANA bilgi modellerini (Analiz ve Hesaplama görünümleri gibi) destekler ve en iyi duruma getirilmiş gezinti özelliklerine sahiptir
* **SAP HANA** ile doğrudan SQL özelliğini kullanarak Satır ve Sütun Tablolarına bağlanabilirsiniz
* HANA Modelleri için En İyi Duruma Getirilmiş Gezinti özelliklerine sahiptir
* Power BI, **SAP HANA** Değişkenlerini ve giriş parametrelerini destekler

## <a name="limitations-of-sap-hana"></a>SAP HANA ile ilgili sınırlamalar
**SAP HANA** ile ilgili sınırlamalar aşağıda gösterilmiştir:

* NVARCHAR dizeleri 4000 Unicode karakter olan maksimum uzunluğa göre kısaltılır
* SMALLDECIMAL desteklenmez
* VARBINARY desteklenmez
* Geçerli Tarihler 1899/12/30 ile 9999/12/31 arasıdır


## <a name="next-steps"></a>Sonraki adımlar
DirectQuery hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen Veri Kaynakları](desktop-directquery-data-sources.md)

