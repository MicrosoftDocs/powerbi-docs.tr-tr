---
title: Power BI Desktop'ta Snowflake bilgi işlem ambarına bağlanma
description: Power BI Desktop'ta Snowflake bilgi işlem ambarına kolayca bağlanma ve bu ambarı kullanma
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: d6de937f4be3c503c146c31a32c56b67ee97a8c4
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86214805"
---
# <a name="connect-to-a-snowflake-computing-warehouse-in-power-bi-desktop"></a>Power BI Desktop'ta bir Snowflake bilgi işlem ambarına bağlanma
Tıpkı Power BI Desktop'taki diğer veri kaynaklarında olduğu gibi Power BI Desktop'ta bir **Snowflake** bilgi işlem ambarına bağlanabilir ve temel alınan verileri kullanabilirsiniz. 

## <a name="connect-to-a-snowflake-computing-warehouse"></a>Bir Snowflake bilgi işlem ambarına bağlanma
Bir **Snowflake** bilgi işlem ambarına bağlanmak için Power BI Desktop'ın **Giriş** şeridindeki **Veri Al**'ı seçin. Soldaki kategorilerden **Veritabanı**'nı seçtiğinizde **Snowflake**'i görebilirsiniz.

![Snowflake veritabanı seçimini gösteren Veri Al iletişim kutusunun ekran görüntüsü.](media/desktop-connect-snowflake/connect-snowflake-2b.png)

Açılan **Snowflake** penceresindeki kutuya Snowflake bilgi işlem ambarınızın adını girin veya yapıştırın ve **Tamam**'ı seçin. Ayrıca, **İçeri aktar** seçeneğini belirleyerek verileri doğrudan Power BI'a aktarmayı tercih edebilir veya **DirectQuery**'yi kullanabilirsiniz. [DirectQuery'yi kullanma](desktop-use-directquery.md) hakkında daha fazla bilgi edinebilirsiniz. AAD SSO'nun yalnızca DirectQuery desteğine sahip olduğunu lütfen unutmayın.

![Radyoyu içeri aktar düğmesinin seçili olduğunu gösteren Snowflake iletişim kutusunun ekran görüntüsü.](media/desktop-connect-snowflake/connect-snowflake-3.png)

İstendiğinde kullanıcı adınızı ve parolanızı girin.

![Kullanıcı Adı ve Parola alanlarını gösteren Snowflake kimlik bilgileri isteminin ekran görüntüsü.](media/desktop-connect-snowflake/connect-snowflake-4.png)

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

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   
