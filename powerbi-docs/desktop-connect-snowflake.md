---
title: Power BI Desktop'ta Snowflake bilgi işlem ambarına bağlanma
description: Power BI Desktop'ta Snowflake bilgi işlem ambarına kolayca bağlanma ve bu ambarı kullanma
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e7534fd0da2039a2dafaf3ca80ee6957fa8d8754
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464313"
---
# <a name="connect-to-a-snowflake-computing-warehouse-in-power-bi-desktop"></a>Power BI Desktop'ta bir Snowflake bilgi işlem ambarına bağlanma
Tıpkı Power BI Desktop'taki diğer veri kaynaklarında olduğu gibi Power BI Desktop'ta bir **Snowflake** bilgi işlem ambarına bağlanabilir ve temel alınan verileri kullanabilirsiniz. 

> [!NOTE]
> 32 bit veya 64 bit olan **Power BI Desktop** yüklemesiyle eşleşen mimariyi kullanarak, **Snowflake** bağlayıcısını kullanan bilgisayarlara **Snowflake ODBC sürücüsünü** de yüklemeniz *gerekir*. Aşağıdaki bağlantıyı kullanmanız ve [uygun Snowflake ODBC sürücüsünü indirmeniz](https://go.microsoft.com/fwlink/?LinkID=823762) yeterlidir.
> 
> 

## <a name="connect-to-a-snowflake-computing-warehouse"></a>Bir Snowflake bilgi işlem ambarına bağlanma
Bir **Snowflake** bilgi işlem ambarına bağlanmak için Power BI Desktop'ın **Giriş** şeridindeki **Veri Al**'ı seçin. Soldaki kategorilerden **Veritabanı**'nı seçtiğinizde **Snowflake**'i görebilirsiniz.

![](media/desktop-connect-snowflake/connect-snowflake-2b.png)

Açılan **Snowflake** penceresindeki kutuya Snowflake bilgi işlem ambarınızın adını girin veya yapıştırın ve **Tamam**'ı seçin. Ayrıca, **İçeri aktar** seçeneğini belirleyerek verileri doğrudan Power BI'a aktarmayı tercih edebilir veya **DirectQuery**'yi kullanabilirsiniz. [DirectQuery'yi kullanma](desktop-use-directquery.md) hakkında daha fazla bilgi edinebilirsiniz. AAD SSO'nun yalnızca DirectQuery desteğine sahip olduğunu lütfen unutmayın.

![](media/desktop-connect-snowflake/connect-snowflake-3.png)

İstendiğinde kullanıcı adınızı ve parolanızı girin.

![](media/desktop-connect-snowflake/connect-snowflake-4.png)

> [!NOTE]
> Belirli bir **Snowflake** sunucusu için kullanıcı adı ve parolanızı girdiğinizde Power BI Desktop, sonraki bağlantı denemelerinde de aynı kimlik bilgilerini kullanır. **Dosya > Seçenekler ve ayarlar > Veri kaynağı ayarları**'na giderek bu kimlik bilgilerini değiştirebilirsiniz.
> 
> 

Microsoft hesabı seçeneğini kullanmak istiyorsanız, Snowflake ve AAD tümleştirmesinin Snowflake tarafında yapılandırılması gerekir. Bunu yapmak için [konuyla ilgili Snowflake belgelerinin](https://docs.snowflake.net/manuals/user-guide/oauth-powerbi.html#power-bi-sso-to-snowflake) Kullanmaya Başlama bölümünü okuyun.

![Snowflake bağlayıcısında Microsoft hesabı kimlik doğrulaması türü.](media/desktop-connect-snowflake/connect-snowflake-6.png)


Bağlantı başarıyla kurulduktan sonra bir **Gezgin** penceresi açılır ve sunucudaki kullanılabilir verileri görüntüler. Bu veriler arasından **Power BI Desktop**'a aktarılıp kullanılacak bir veya daha fazla öğe seçebilirsiniz.

![ODBC Bağlantı kurulamamasına neden olan 28000 Hatası.](media/desktop-connect-snowflake/connect-snowflake-5.png)

Seçili tabloyu **Yüklemeyi** seçtiğinizde tablonun tamamı **Power BI Desktop**'a getirilir. Sorguyu **Düzenlemeyi** seçtiğinizde ise kullanmak istediğiniz veri kümesini filtreleyebileceğiniz ve iyileştirebileceğiniz, ardından, iyileştirilen bu veri kümesini **Power BI Desktop**'a yükleyebileceğiniz **Sorgu Düzenleyicisi** açılır.

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   

