---
title: Power BI ile SQL Sentry'ye bağlanma
description: Power BI için SQL Sentry
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 8ad41917c887cff7db991051aa35d5dad6b6a8fa
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242435"
---
# <a name="connect-to-sql-sentry-with-power-bi"></a>Power BI ile SQL Sentry'ye bağlanma
SQL Sentry tarafından toplanan performans verilerinizi Power BI ile çözümlemek kolaydır. Power BI, verilerinizi alır ve ardından bu verilere dayalı varsayılan bir pano ve raporlar oluşturur.

Power BI için [SQL Sentry içerik paketine](https://app.powerbi.com/groups/me/getdata/services/sql-sentry) bağlanın.

>[!NOTE]
>Bağlanmak için, http://cloud.sqlsentry.com adresine bağlanırken kullandığınız SQL Sentry hesabına erişim ve izleyeceğiniz Veritabanı Kimliği gereklidir.  Veritabanı Kimliğini nerede bulacağınıza yönelik bilgiler aşağıda verilmiştir.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-sql-sentry/pbi_getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-sql-sentry/pbi_getservices.png) 
3. **SQL Sentry  \> Al**'ı seçin.
   
   ![](media/service-connect-to-sql-sentry/sqlsentry.png)
4. Power BI'da izlemek istediğiniz veritabanının **Veritabanı Kimliği**'ni girin. Aşağıda [bu parametreyi bulmaya](#FindingParams) yönelik daha fazla ayrıntıya ulaşabilirsiniz.
   
   ![](media/service-connect-to-sql-sentry/img2400.png)
5. Kimlik Doğrulama Yöntemi için **OAuth2\> Oturum aç** seçeneğini belirleyin.
   
   İstendiğinde, cloud.sqlsentry.com kimlik bilgilerinizi girin ve SQL Sentry kimlik doğrulaması adımlarını uygulayın.
   
   ![](media/service-connect-to-sql-sentry/img6400.png)
   
   İlk kez bağlandığınızda Power BI, hesabınıza salt okunur erişime izin vermenizi ister. İçeri aktarma işlemini başlatmak için Allow (İzin ver) seçeneğini belirleyin.  Hesabınızdaki veri hacmine bağlı olarak, içeri aktarma işlemi birkaç dakika sürebilir.
   
   ![](media/service-connect-to-sql-sentry/img7400.png)
6. Veriler Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Yeni öğeler sarı yıldız işareti \* ile gösterilir:
   
   ![](media/service-connect-to-sql-sentry/img8200.png)
7. SQL Sentry panosunu seçin.
   
   Bu, Power BI'ın verilerinizi görüntülemek için oluşturduğu varsayılan panodur. Bu panoyu, verilerinizi istediğiniz herhangi bir biçimde görüntüleyecek şekilde değiştirebilirsiniz.
   
   ![](media/service-connect-to-sql-sentry/img9dashboard800.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
Aşağıdaki verilere Power BI'da SQL Sentry'den ulaşılabilir:

| Tablo adı | Açıklama |
| --- | --- |
| Connection |Bu tablo, SQL Sentry ile tanımlanan bağlantılarınız hakkındaki bilgileri içerir. |
| Date<br /> |Bu tablo, içinde bulunulan gün ile performans verilerinin toplanmaya ve saklanmaya başlandığı tarih arasındaki tarihleri içerir. |
| Downtime<br /> |Bu tablo, ortamınızda izlenen her bir sunucu için çalışma ve çalışmama süresi ile ilgili bilgileri içerir. |
| Memory Usage<br /> |Bu tablo, sunucularınızdan her birindeki kullanılabilir bellek miktarı hakkında veriler içerir.<br /> |
| Server<br /> |Bu tablo, ortamınızdaki her bir sunucuya ilişkin kayıtlar içerir. |
| Server Health<br /> |Bu tablo, önem derecesi ve sayı da dahil olmak üzere, ortamınızdaki özel durumlar sonucunda meydana gelen tüm olaylara ilişkin veriler içerir. |

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri Bulma
**Veritabanı Kimliği**, yeni bir tarayıcı penceresinden <https://cloud.sqlsentry.com> sayfasında oturum açılarak bulunabilir.  **Veritabanı Kimliği**, ana genel bakış sayfasında yer alır:

    ![](media/service-connect-to-sql-sentry/database2.png)

**Veritabanı Kimliği** Database Details (Veritabanı Ayrıntıları) ekranında da gösterilir:

    ![](media/service-connect-to-sql-sentry/database.png)


## <a name="troubleshooting"></a>Sorun giderme
Uygulamalarınızın bazılarındaki veriler Power BI'da görünmüyorsa doğru Veritabanı Kimliğini kullandığınızdan ve verileri görüntüleme yetkinizin bulunduğundan emin olun. 

<https://cloud.sqlsentry.com> ile eşitlenmekte olan SQL Sentry veritabanının sahibi değilseniz toplanan verileri görüntüleme haklarına sahip olduğunuzdan emin olmak için yöneticinizle iletişime geçin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI için Veri Alma](service-get-data.md)

