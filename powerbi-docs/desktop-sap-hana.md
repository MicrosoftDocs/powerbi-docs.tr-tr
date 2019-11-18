---
title: Power BI Desktop'ta SAP HANA'yı kullanma
description: Power BI Desktop'ta SAP HANA'yı kullanma
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/21/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: bf258597f6369541fb9a221c8d423e8a9078a3a4
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879760"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Power BI Desktop'ta SAP HANA'yı kullanma
Power BI Desktop'ta artık **SAP HANA** veritabanlarına erişebilirsiniz. **SAP HANA**'yı kullanabilmek için Power BI Desktop **SAP HANA** veri bağlantısının düzgün çalışabilmesi amacıyla yerel istemci bilgisayara SAP HANA ODBC sürücüsünün yüklenmesi gerekir. Gerekli ODBC sürücüsünü içeren SAP HANA İstemci araçlarını [SAP Development Tools](https://tools.hana.ondemand.com/#hanatools) sayfasından indirebilirsiniz. Alternatif olarak [SAP Software Download Center](https://support.sap.com/swdc) sayfasından da edinebilirsiniz. Yazılım portalında Windows bilgisayarlar için SAP HANA CLIENT uygulamasını arayın. **SAP Software Download Center** sayfasının yapısı sıklıkla değiştiğinden sitede gezinmeyle ilgili ayrıntılı bilgi veremiyoruz.

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
  * HDI kapsayıcı tabanlı Hesaplama Görünümleri, Power BI Desktop'ın Ağustos 2019 sürümünde genel önizleme aşamasındadır. Power BI'da HDI kapsayıcı tabanlı Hesaplama Görünümlerinize erişmek için, Power BI ile kullandığınız HANA veritabanı kullanıcısının veya kullanıcılarının erişmek istediğiniz görünümlerin depolandığı HDI çalışma zamanı kapsayıcısına erişim izni olduğundan emin olun. Bu erişimi vermek için HDI kapsayıcınıza erişim izni veren bir Rol oluşturmalı ve bu rolü Power BI ile kullanacağınız HANA veritabanı kullanıcısına atamalısınız (bu kullanıcının her zamanki gibi \_SYS\_BI şemasındaki sistem tablolarından okuma izni de olmalıdır). Veritabanı rollerini oluşturma ve atama konusunda ayrıntılı yönergeler için resmi SAP belgelerine bakın. [Bu SAP blog gönderisi](https://blogs.sap.com/2018/01/24/the-easy-way-to-make-your-hdi-container-accessible-to-a-classic-database-user/) iyi bir başlangıç noktası olabilir.
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


