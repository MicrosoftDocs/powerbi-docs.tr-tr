---
title: "Power BI Desktop'ta Snowflake bilgi işlem ambarına bağlanma"
description: "Power BI Desktop'ta Snowflake bilgi işlem ambarına kolayca bağlanma ve bu ambarı kullanma"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: bb1c649d62ad9c8a3c4fb854db2478feecc82e70
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-snowflake-in-power-bi-desktop"></a>Power BI Desktop'ta Snowflake'e bağlanma
Tıpkı Power BI Desktop'taki diğer veri kaynaklarında olduğu gibi Power BI Desktop'ta bir **Snowflake** bilgi işlem ambarına bağlanabilir ve temel alınan verileri kullanabilirsiniz. 

> [!NOTE]
> 32 bit veya 64 bit olan **Power BI Desktop** yüklemesiyle eşleşen mimariyi kullanarak, **Snowflake** bağlayıcısını kullanan bilgisayarlara **Snowflake ODBC sürücüsünü** de yüklemeniz *gerekir*. Aşağıdaki bağlantıyı kullanmanız ve [uygun Snowflake ODBC sürücüsünü indirmeniz](http://go.microsoft.com/fwlink/?LinkID=823762) yeterlidir.
> 
> 

## <a name="connect-to-a-snowflake-computing-warehouse"></a>Bir Snowflake bilgi işlem ambarına bağlanma
Bir **Snowflake** bilgi işlem ambarına bağlanmak için Power BI Desktop'ın **Giriş** şeridindeki **Veri Al**'ı seçin. Soldaki kategorilerden **Veritabanı**'nı seçtiğinizde **Snowflake**'i görebilirsiniz.

![](media/desktop-connect-snowflake/connect_snowflake_2b.png)

Açılan **Snowflake** penceresindeki kutuya Snowflake bilgi işlem ambarınızın adını girin veya yapıştırın ve **Tamam**'ı seçin. Ayrıca, **İçeri aktar** seçeneğini belirleyerek verileri doğrudan Power BI'a aktarmayı tercih edebilir veya **DirectQuery**'yi kullanabilirsiniz. [DirectQuery'yi kullanma](desktop-use-directquery.md) hakkında daha fazla bilgi edinebilirsiniz.

![](media/desktop-connect-snowflake/connect_snowflake_3.png)

İstendiğinde kullanıcı adınızı ve parolanızı girin.

![](media/desktop-connect-snowflake/connect_snowflake_4.png)

> [!NOTE]
> Belirli bir **Snowflake** sunucusu için kullanıcı adı ve parolanızı girdiğinizde Power BI Desktop, sonraki bağlantı denemelerinde de aynı kimlik bilgilerini kullanır. **Dosya > Seçenekler ve ayarlar > Veri kaynağı ayarları**'na giderek bu kimlik bilgilerini değiştirebilirsiniz.
> 
> 

Bağlantı başarıyla kurulduktan sonra bir **Gezgin** penceresi açılır ve sunucudaki kullanılabilir verileri görüntüler. Bu veriler arasından **Power BI Desktop**'a aktarılıp kullanılacak bir veya daha fazla öğe seçebilirsiniz.

![](media/desktop-connect-snowflake/connect_snowflake_5.png)

Seçili tabloyu **Yüklemeyi** seçtiğinizde tablonun tamamı **Power BI Desktop**'a getirilir. Sorguyu **Düzenlemeyi** seçtiğinizde ise kullanmak istediğiniz veri kümesini filtreleyebileceğiniz ve iyileştirebileceğiniz, ardından, iyileştirilen bu veri kümesini **Power BI Desktop**'a yükleyebileceğiniz **Sorgu Düzenleyicisi** açılır.

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md)
* [Power BI Desktop'taki Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   
