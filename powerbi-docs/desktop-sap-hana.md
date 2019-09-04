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
ms.date: 08/21/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1932848cb2f8ad7d75e841870265cc22308467c2
ms.sourcegitcommit: a00fe5fb545c3df13b7cd13a701fd6a2b2521a17
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70200891"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Power BI Desktop'ta SAP HANA'yı kullanma
Power BI Desktop'ta artık **SAP HANA** veritabanlarına erişebilirsiniz. **SAP HANA**'yı kullanabilmek için Power BI Desktop **SAP HANA** veri bağlantısının düzgün çalışabilmesi amacıyla yerel istemci bilgisayara SAP HANA ODBC sürücüsünün yüklenmesi gerekir. SAP HANA ODBC sürücüsünü [SAP Software Download Center](https://support.sap.com/swdc) sayfasından indirebilirsiniz. Bu sayfada Windows bilgisayarlar için SAP HANA CLIENT uygulamasını arayın. **SAP Software Download Center** sayfasının yapısı sıklıkla değiştiğinden sitede gezinmeyle ilgili ayrıntılı bilgi veremiyoruz.

Bir **SAP HANA** veritabanına bağlanmak için aşağıdaki görüntüde gösterildiği gibi **Veri Al > Veritabanı > SAP HANA Veritabanı** yolunu izleyin:

![](media/desktop-sap-hana/sap-hana-1.png)

Bir SAP HANA veritabanına bağlanırken sunucu adını belirtin. Ardından, açılan menüden ve giriş kutusundan bağlantı noktasını belirtin.

Bu sürümde Power BI Desktop ve Power BI hizmetinde **SAP HANA**, [DirectQuery](desktop-directquery-sap-hana.md) modunda desteklenmektedir ve **SAP HANA** kullanan raporları DirectQuery modunda Power BI hizmetine yükleyip orada yayımlayabilirsiniz. Ayrıca, **SAP HANA**'yı DirectQuery modunda kullanmadığınızda da raporları Power BI hizmetine yükleyip orada yayımlayabilirsiniz.

## <a name="supported-features-for-sap-hana"></a>SAP HANA için desteklenen özellikler
Bu sürümde aşağıdaki listede görebileceğiniz gibi birçok **SAP HANA** özelliği desteklenmektedir:

* **SAP HANA** için Power BI bağlayıcısı, en iyi kullanıcı deneyimini sunmak için SAP ODBC sürücüsünü kullanır
* **SAP HANA**, hem DirectQuery hem de İçeri Aktarma seçeneklerini destekler
* Power BI, HANA bilgi modellerini (Analiz ve Hesaplama Görünümleri gibi) destekler ve en iyi duruma getirilmiş gezinti özelliklerine sahiptir
* **SAP HANA** ile doğrudan SQL özelliğini kullanarak Satır ve Sütun Tablolarına bağlanabilirsiniz
* HANA Modelleri için En İyi Duruma Getirilmiş Gezinti özelliklerine sahiptir
* Power BI, **SAP HANA** Değişkenlerini ve giriş parametrelerini destekler
* HDI kapsayıcı tabanlı Hesaplama Görünümleri
  * HDI kapsayıcı tabanlı Hesaplama Görünümleri, Power BI Desktop'ın Ağustos 2019 sürümünde genel önizleme aşamasındadır. Power BI'da HDI kapsayıcı tabanlı Hesaplama Görünümlerinize erişmek için, Power BI ile kullandığınız HANA veritabanı kullanıcısının veya kullanıcılarının erişmek istediğiniz görünümlerin depolandığı HDI çalışma zamanı kapsayıcısına erişim izni olduğundan emin olun. Bu erişimi vermek için HDI kapsayıcınıza erişim izni veren bir Rol oluşturmalı ve bu rolü Power BI ile kullanacağınız HANA veritabanı kullanıcısına atamalısınız (bu kullanıcının her zamanki gibi \_SYS\_BI şemasındaki sistem tablolarından okuma izni de olmalıdır). Veritabanı rollerini oluşturma ve atama konusunda ayrıntılı yönergeler için resmi SAP belgelerine bakın. [Bu SAP blog gönderisi](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fblogs.sap.com%2F2018%2F01%2F24%2Fthe-easy-way-to-make-your-hdi-container-accessible-to-a-classic-database-user%2F&data=02%7C01%7Cv-adbold%40microsoft.com%7Cf7e0a405fe334598ba0608d7096ef5b4%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636988244476739316&sdata=PuRu61GPRYp34mLuGbQk6gdbRikdgbxfqo8q1RBQtm0%3D&reserved=0) iyi bir başlangıç noktası olabilir.
  * Şu anda HDI tabanlı Hesaplama Görünümlerine eklenen HANA değişkenleriyle ilgili bazı sınırlamalar olduğuna dikkat edin. Bu sınırlamalar HANA tarafındaki hatalardan kaynaklanır ve SAP HANA'nın gelecek sürümlerinde bu durum düzeltilecektir. İlk olarak HDI kapsayıcı tabanlı Hesaplama Görünümünün paylaşılan bir sütununa HANA değişkeni uygulamak mümkün değildir. Bu sınırlama HANA 2 sürüm 37.02 veya sonraki sürümlere ya da HANA 2 sürüm 42 ve sonraki sürümlere yükseltilerek giderilebilir. İkincisi, değişkenler ve parametreler için çok girdili varsayılan değerler Power BI kullanıcı arabiriminde gösterilmez. Bu durum SAP HANA'daki bir hatadan kaynaklanır, ancak SAP henüz bir düzeltme duyurmamıştır.

## <a name="limitations-of-sap-hana"></a>SAP HANA ile ilgili sınırlamalar
**SAP HANA** ile ilgili sınırlamalar aşağıda gösterilmiştir:

* NVARCHAR dizeleri 4000 Unicode karakter olan maksimum uzunluğa göre kısaltılır
* SMALLDECIMAL desteklenmez
* VARBINARY desteklenmez
* Geçerli Tarihler 1899/12/30 ile 9999/12/31 arasıdır


## <a name="next-steps"></a>Sonraki adımlar
DirectQuery ve SAP HANA hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen Veri Kaynakları](desktop-directquery-data-sources.md)
* [SAP HANA için şifrelemeyi etkinleştirme](desktop-sap-hana-encryption.md)


