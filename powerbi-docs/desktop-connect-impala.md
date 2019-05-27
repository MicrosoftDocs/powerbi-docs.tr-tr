---
title: Power BI Desktop'ta bir Impala veritabanına bağlanma
description: Power BI Desktop'ta bir Impala veritabanına kolayca bağlanma ve bu veritabanını kullanma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 0befceba2651ad4f8f414d3669c5830c07ece06d
ms.sourcegitcommit: 10a87c016f497dbeba32f94ed1f3688a70816fea
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65514200"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Power BI Desktop'ta bir Impala veritabanına bağlanma
Tıpkı Power BI Desktop'taki diğer veri kaynaklarında olduğu gibi Power BI Desktop'ta bir **Impala** veritabanına bağlanabilir ve temel alınan verileri kullanabilirsiniz.

## <a name="connect-to-an-impala-database"></a>Impala veritabanlarına bağlanma
Bir **Impala** veritabanına bağlanmak için aşağıdaki adımları izleyin: 

1. Power BI Desktop'taki **Giriş** şeridinde bulunan **Veri Al** seçeneğini belirleyin. 

2. Soldaki kategorilerden **Veritabanı**'nı seçin. Açılan sayfada **Impala**'yı göreceksiniz.

    ![Veri Al](media/desktop-connect-impala/connect_impala_2.png)

3. Açılan **Impala** penceresindeki kutuya Impala sunucunuzun adını yazın veya yapıştırın. Ardından **Tamam**'ı seçin. **İçeri aktar** seçeneğini belirleyerek verileri doğrudan Power BI'a aktarabilir veya **DirectQuery**'yi kullanabilirsiniz. [DirectQuery'yi kullanma](desktop-use-directquery.md) hakkında daha fazla bilgi edinin.

    ![Impala penceresi](media/desktop-connect-impala/connect_impala_3a.png)

4. İstendiğinde, kimlik bilgilerinizi girin veya anonim olarak bağlanın. Impala bağlayıcısı Anonim, Temel (kullanıcı adı + parola) ve Windows kimlik doğrulamasını destekler.

    ![Impala bağlayıcısı](media/desktop-connect-impala/connect_impala_4.png)

    > [!NOTE]
    > Belirli bir **Impala** sunucusu için kullanıcı adı ve parolanızı girdiğinizde Power BI Desktop, sonraki bağlantı denemelerinde de aynı kimlik bilgilerini kullanır. **Dosya > Seçenekler ve ayarlar > Veri kaynağı ayarları**'na giderek bu kimlik bilgilerini değiştirebilirsiniz.


5. Bağlantı kurulduktan sonra sunucudaki verileri gösteren bir **Gezgin** penceresi açılır. Bu verilerden içeri aktarmak ve **Power BI Desktop**'ta kullanmak istediklerinizi seçin.

    ![Gezgin penceresi](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar
**Impala** bağlayıcısı ile ilgili olarak göz önünde bulundurmanız gereken bazı sınırlamalar ve önemli noktalar vardır:

* Impala bağlayıcısı, desteklenen üç kimlik doğrulama mekanizmasından biri kullanılarak şirket içi veri ağ geçidi üzerinde desteklenir.

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak bağlanabileceğiniz çok çeşitli türlerde veri kaynağı mevcuttur. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop'ta veri kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta verileri şekillendirme ve birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   

