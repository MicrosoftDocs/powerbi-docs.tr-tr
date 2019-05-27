---
title: Power BI Desktop'ta bir Amazon Redshift veritabanına bağlanma
description: Power BI Desktop'ta bir Amazon Redshift veritabanına kolayca bağlanma ve veritabanını kullanma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b92935bb9f4b9ad3738151cb2f671af96283f625
ms.sourcegitcommit: 10a87c016f497dbeba32f94ed1f3688a70816fea
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65513613"
---
# <a name="connect-to-amazon-redshift-in-power-bi-desktop"></a>Power BI Desktop'ta Amazon Redshift'e bağlanma
Tıpkı Power BI Desktop'taki diğer veri kaynaklarında olduğu gibi **Power BI Desktop'ta** **Amazon Redshift** veritabanına bağlanabilir ve temel alınan verileri kullanabilirsiniz.

## <a name="connect-to-an-amazon-redshift-database"></a>Bir Amazon Redshift veritabanına bağlanma
Bir **Amazon Redshift** veritabanına bağlanmak için Power BI Desktop'taki **Giriş** şeridinden **Veri Al** seçeneğini belirleyin. Soldaki kategorilerden **Veritabanı**'nı seçtiğinizde **Amazon Redshift**'i görebilirsiniz.

![](media/desktop-connect-redshift/connect_redshift_3.png)

Görüntülenen **Amazon Redshift** penceresindeki kutuya, **Amazon Redshift** sunucunuzun ve veritabanınızın adını yazın veya yapıştırın. Kullanıcılar, *Sunucu* alanına şu biçimde bir bağlantı noktası girebilir: *SunucuURL:BağlantıNoktası*

![](media/desktop-connect-redshift/connect_redshift_4.png)

İstendiğinde kullanıcı adınızı ve parolanızı girin. Hataları önlemek için SSL sertifikası ile tam olarak eşleşen sunucu adını kullanmanız gerekir. 

![](media/desktop-connect-redshift/connect_redshift_5.png)

Bağlantı başarıyla kurulduktan sonra bir **Gezgin** penceresi açılır ve sunucudaki kullanılabilir verileri görüntüler. Bu veriler arasından **Power BI Desktop**'a aktarılıp kullanılacak bir veya daha fazla öğe seçebilirsiniz.

![](media/desktop-connect-redshift/connect_redshift_6.png)

**Gezgin** penceresinden seçiminizi yaptıktan sonra veriler için **Yükle** veya **Düzenle** seçeneğini belirleyebilirsiniz.

* Veriler için **Yükle** seçeneğini belirlerseniz verileri yüklemek için *İçeri Aktar* veya *DirectQuery* modlarından birini kullanmanız istenir. Daha fazla bilgi için [DirectQuery'nin açıklandığı makaleye](desktop-use-directquery.md) göz atın.
* Veriler için **Düzenle** seçeneğini belirlerseniz verilere her türden dönüştürme ve filtre uygulayabileceğiniz **Sorgu Düzenleyicisi** açılır. Söz konusu dönüştürmelerin ve filtrelerin çoğu, temel alınan **Amazon Redshift** veritabanına da uygulanmıştır (destekleniyorsa).

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   

