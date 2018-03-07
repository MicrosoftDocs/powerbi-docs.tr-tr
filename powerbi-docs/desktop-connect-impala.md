---
title: "Power BI Desktop'ta bir Impala veritabanına bağlanma"
description: "Power BI Desktop'ta bir Impala veritabanına kolayca bağlanma ve bu veritabanını kullanma"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 196974bedcace4fbe51b7e7ac551bd0923f7a891
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Power BI Desktop'ta bir Impala veritabanına bağlanma
Tıpkı Power BI Desktop'taki diğer veri kaynaklarında olduğu gibi Power BI Desktop'ta bir **Impala** veritabanına bağlanabilir ve temel alınan verileri kullanabilirsiniz.

## <a name="connect-to-an-impala-database"></a>Impala veritabanlarına bağlanma
Bir **Impala** veritabanına bağlanmak için Power BI Desktop'ın **Giriş** şeridindeki **Veri Al**'ı seçin. Soldaki kategorilerden **Veritabanı**'nı seçtiğinizde **Impala**'yı görebilirsiniz.

![](media/desktop-connect-impala/connect_impala_2.png)

Açılan **Impala** penceresindeki kutuya Impala sunucunuzun adını yazın veya yapıştırın ve **Tamam**'ı seçin. Ayrıca, **İçeri aktar** seçeneğini belirleyerek verileri doğrudan Power BI'a aktarmayı tercih edebilir veya **DirectQuery**'yi kullanabilirsiniz. [DirectQuery'yi kullanma](desktop-use-directquery.md) hakkında daha fazla bilgi edinebilirsiniz.

![](media/desktop-connect-impala/connect_impala_3a.png)

İstendiğinde kullanıcı adı ve parolanızı girin veya anonim olarak bağlanın (hangisi destekleniyorsa).

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> Belirli bir **Impala** sunucusu için kullanıcı adı ve parolanızı girdiğinizde Power BI Desktop, sonraki bağlantı denemelerinde de aynı kimlik bilgilerini kullanır. **Dosya > Seçenekler ve ayarlar > Veri kaynağı ayarları**'na giderek bu kimlik bilgilerini değiştirebilirsiniz.
> 
> 

Bağlantı başarıyla kurulduktan sonra bir **Gezgin** penceresi açılır ve sunucudaki kullanılabilir verileri görüntüler. Bu veriler arasından **Power BI Desktop**'a aktarılıp kullanılacak bir veya daha fazla öğe seçebilirsiniz.

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Önemli Noktalar ve Sınırlamalar
**Impala** bağlayıcısı ile ilgili olarak göz önünde bulundurmanız gereken bazı sınırlar ve önemli noktalar vardır:

* Gelecekte **Power BI Gateway** ile yenileme desteği sunulması planlanmaktadır.

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md)
* [Power BI Desktop'taki veri kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   

