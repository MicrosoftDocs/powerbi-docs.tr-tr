---
title: Power BI Desktop'ta Snowflake bilgi işlem ambarına bağlanma
description: Power BI Desktop'ta Snowflake bilgi işlem ambarına kolayca bağlanma ve bu ambarı kullanma
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 01/04/2021
LocalizationGroup: Connect to data
ms.openlocfilehash: 377ede2171a721a33aa0b70819ef511d721f2590
ms.sourcegitcommit: f7330dabb9cd8bce90bb2efec3e3273a11578f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99494461"
---
# <a name="connect-to-snowflake-in-power-bi-desktop"></a>Power BI Desktop'ta Snowflake'e bağlanma
Tıpkı Power BI Desktop'taki diğer veri kaynaklarında olduğu gibi Power BI Desktop'ta bir **Snowflake** bilgi işlem ambarına bağlanabilir ve temel alınan verileri kullanabilirsiniz. 

## <a name="connect-to-a-snowflake-computing-warehouse"></a>Bir Snowflake bilgi işlem ambarına bağlanma
Bir **Snowflake** bilgi işlem ambarına bağlanmak için Power BI Desktop'ın **Giriş** şeridindeki **Veri Al**'ı seçin. Soldaki kategorilerden **Veritabanı**'nı seçtiğinizde **Snowflake**'i görebilirsiniz.

![Snowflake veritabanı seçimini gösteren Veri Al iletişim kutusunun ekran görüntüsü.](media/desktop-connect-snowflake/connect-snowflake-2b.png)

Açılan **Snowflake** penceresindeki kutuya Snowflake bilgi işlem ambarınızın adını girin veya yapıştırın ve **Tamam**'ı seçin. Ayrıca, **İçeri aktar** seçeneğini belirleyerek verileri doğrudan Power BI'a aktarmayı tercih edebilir veya **DirectQuery**'yi kullanabilirsiniz. [DirectQuery'yi kullanma](desktop-use-directquery.md) hakkında daha fazla bilgi edinebilirsiniz. AAD SSO'nun yalnızca DirectQuery desteğine sahip olduğunu lütfen unutmayın.

![Radyoyu içeri aktar düğmesinin seçili olduğunu gösteren Snowflake iletişim kutusunun ekran görüntüsü.](media/desktop-connect-snowflake/connect-snowflake-3.png)

İstendiğinde kullanıcı adınızı ve parolanızı girin.

![Kullanıcı Adı ve Parola alanlarını gösteren Snowflake kimlik bilgileri isteminin ekran görüntüsü.](media/desktop-connect-snowflake/connect-snowflake-4.png)

> [!NOTE]
> Belirli bir **Snowflake** sunucusu için kullanıcı adı ve parola girildikten sonra, Power BI Desktop bu kimlik bilgilerini sonraki bağlanma denemelerinde de kullanır. **Dosya > Seçenekler ve ayarlar > Veri kaynağı ayarları**'na giderek bu kimlik bilgilerini değiştirebilirsiniz.
> 
> 

Microsoft hesabı seçeneğini kullanmak istiyorsanız, Snowflake ve AAD tümleştirmesinin Snowflake tarafında yapılandırılması gerekir. Bunu yapmak için [konuyla ilgili Snowflake belgelerinin](https://docs.snowflake.net/manuals/user-guide/oauth-powerbi.html#power-bi-sso-to-snowflake) Kullanmaya Başlama bölümünü okuyun.

![Snowflake bağlayıcısında Microsoft hesabı kimlik doğrulaması türü.](media/desktop-connect-snowflake/connect-snowflake-6.png)


Bağlantı başarıyla kurulduktan sonra bir **Gezgin** penceresi açılır ve sunucudaki kullanılabilir verileri görüntüler. Bu veriler arasından **Power BI Desktop**'a aktarılıp kullanılacak bir veya daha fazla öğe seçebilirsiniz.

![ODBC Bağlantı kurulamamasına neden olan 28000 Hatası.](media/desktop-connect-snowflake/connect-snowflake-5.png)

Seçili tabloyu **Yüklemeyi** seçtiğinizde tablonun tamamı **Power BI Desktop**'a getirilir. Sorguyu **Düzenlemeyi** seçtiğinizde ise kullanmak istediğiniz veri kümesini filtreleyebileceğiniz ve iyileştirebileceğiniz, ardından, iyileştirilen bu veri kümesini **Power BI Desktop**'a yükleyebileceğiniz **Sorgu Düzenleyicisi** açılır.

## <a name="custom-roles"></a>Özel Roller

Şu anda, kar tanesi bağlayıcısında ' özel rol ' desteği yalnızca temel kimlik doğrulamasıyla çalışır. Bu, yakın gelecekte çözülecektir.

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   
