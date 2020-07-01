---
title: Power BI Desktop'ta SAP HANA'yı kullanma
description: Power BI Desktop'ta SAP HANA'yı kullanma
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 3d78ded05d199676708c0000cab043226a47b166
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85222788"
---
# <a name="connect-to-sap-hana-databases-in-power-bi-desktop"></a>Power BI Desktop'ta SAP HANA veritabanlarına bağlanma

Power BI Desktop'ta artık *SAP HANA* veritabanlarına erişebilirsiniz. SAP HANA'yı kullanmak için, yerel istemci bilgisayara SAP HANA ODBC sürücüsünün yükleyerek Power BI Desktop SAP HANA veri bağlantısının düzgün çalışmasını sağlamanız gerekir. Gerekli ODBC sürücüsünü içeren SAP HANA İstemci araçlarını [SAP Development Tools](https://tools.hana.ondemand.com/#hanatools) sayfasından indirebilirsiniz. Bunu [SAP Software Download Center](https://support.sap.com/en/my-support/software-downloads.html) sayfasından da alabilirsiniz. Software portalında Windows bilgisayarlar için *SAP HANA CLIENT* uygulamasını arayın. SAP Software Download Center sayfasının yapısı sıklıkla değiştiğinden sitede gezinmeyle ilgili ayrıntılı bilgi veremiyoruz.

SAP HANA veritabanına bağlanmak için **Veri Al**'ı, **Veritabanı** > **SAP HANA Veritabanı**'nı ve sonra da **Bağlan**'ı seçin:

![SAP HANA Veritabanı, Veri Al iletişim kutusu, Power BI Desktop](media/desktop-sap-hana/sap-hana-1.png)

SAP HANA veritabanına bağlanırken sunucu adını belirtin. Ardından, açılan listeden ve giriş kutusundan bağlantı noktasını belirtin.

Bu sürümde, Power BI Desktop'ta ve Power BI hizmetinde [DirectQuery](desktop-directquery-sap-hana.md) modunda SAP HANA desteklenir. DirectQuery modunda SAP HANA kullanan raporları Power BI hizmetine yayımlayabilir ve yükleyebilirsiniz. Ayrıca, SAP HANA'yı DirectQuery modunda kullanmadığınızda da raporları Power BI hizmetine yükleyip orada yayımlayabilirsiniz.

## <a name="supported-features-for-sap-hana"></a>SAP HANA için desteklenen özellikler

Bu sürümde aşağıdaki listede görebileceğiniz gibi birçok SAP HANA özelliği desteklenmektedir:

* SAP HANA için Power BI bağlayıcısı, en iyi kullanıcı deneyimini sunmak için SAP ODBC sürücüsünü kullanır.

* SAP HANA, hem DirectQuery hem de İçeri Aktarma seçeneklerini destekler.

* Power BI, Analiz ve Hesaplama Görünümleri gibi HANA bilgi modellerini destekler ve iyileştirilmiş gezinti özelliklerine sahiptir.

* SAP HANA ile doğrudan SQL özelliğini kullanarak Satır ve Sütun Tablolarına bağlanabilirsiniz.

* Power BI, HANA Modelleri için İyileştirilmiş Gezinti özelliklerine sahiptir.

* Power BI, SAP HANA Değişkenlerini ve Giriş parametrelerini destekler.

* Power BI, HDI kapsayıcı tabanlı Hesaplama Görünümlerini destekler.

  * HDI kapsayıcı tabanlı Hesaplama Görünümleri, Power BI Desktop'ın Ağustos 2019 sürümünde genel önizleme aşamasındadır. Power BI'da HDI kapsayıcı tabanlı Hesaplama Görünümlerinize erişmek için, Power BI ile kullandığınız HANA veritabanı kullanıcılarının erişmek istediğiniz görünümlerin depolandığı HDI çalışma zamanı kapsayıcısına erişim izni olduğundan emin olun. Bu erişimi vermek için HDI kapsayıcınıza erişim izni veren bir Rol oluşturun. Sonra bu rolü Power BI ile kullanacağınız HANA veritabanı kullanıcına atayın. (Bu kullanıcının her zamanki gibi \_SYS\_BI şemasındaki sistem tablolarından okuma izni de olması gerekir.) Veritabanı rollerini oluşturma ve atama konusunda ayrıntılı yönergeler için resmi SAP belgelerine bakın. [Bu SAP blog gönderisi](https://blogs.sap.com/2018/01/24/the-easy-way-to-make-your-hdi-container-accessible-to-a-classic-database-user/) iyi bir başlangıç noktası olabilir.

  * Şu anda HDI tabanlı Hesaplama Görünümlerine eklenen HANA değişkenleriyle ilgili bazı sınırlamalar vardır. Bu sınırlamaların nedeni HANA tarafındaki hatalardır.
  
    İlk olarak HDI kapsayıcı tabanlı Hesaplama Görünümünün paylaşılan bir sütununa HANA değişkeni uygulamak mümkün değildir. Bu sınırlamayı gidermek için HANA 2 sürüm 37.02 veya sonraki sürümlere ya da HANA 2 sürüm 42 ve sonraki sürümlere yükseltin. İkincisi, değişkenler ve parametreler için çok girdili varsayılan değerler Power BI kullanıcı arabiriminde gösterilmez. Bu sınırlamaya SAP HANA tarafındaki bir hata neden olur ama SAP henüz bir düzeltme duyurusu yapmamıştır.

## <a name="limitations-of-sap-hana"></a>SAP HANA ile ilgili sınırlamalar

SAP HANA kullanımıyla ilgili de birkaç sınırlama vardır ve bunlar aşağıda gösterilmiştir:

* NVARCHAR dizeleri 4000 Unicode karakter olan maksimum uzunluğa göre kesilir.
* SMALLDECIMAL desteklenmez.
* VARBINARY desteklenmez.
* Geçerli Tarihler 1899/12/30 ile 9999/12/31 arasıdır.

## <a name="next-steps"></a>Sonraki adımlar

DirectQuery ve SAP HANA hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
* [Power BI'da DirectQuery'yi kullanma](desktop-directquery-about.md)
* [Power BI veri kaynakları](power-bi-data-sources.md)
* [SAP HANA için şifrelemeyi etkinleştirme](desktop-sap-hana-encryption.md)
