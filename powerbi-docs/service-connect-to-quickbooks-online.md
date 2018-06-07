---
title: Power BI ile QuickBooks Online'a bağlanma
description: Power BI için QuickBooks Online
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 7caf471674c20607826550fc14f8ebc8e772b61a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34584266"
---
# <a name="connect-to-quickbooks-online-with-power-bi"></a>Power BI ile QuickBooks Online'a bağlanma
Power BI'dan QuickBooks Online verilerine bağlandığınızda işletmenizin nakit akışına, kârlılığına, müşterilerine ve daha fazlasına yönelik öngörüler içeren bir Power BI panosu ve Power BI raporları alırsınız. Panoyu ve raporları olduğu gibi kullanabilir ya da en çok değer verdiğiniz bilgiler vurgulanacak şekilde özelleştirebilirsiniz. Veriler günde bir kez otomatik olarak yenilenir.

Power BI için [QuickBooks Online içerik paketine](https://dxt.powerbi.com/getdata/services/quickbooks-online) bağlanın.

>[!NOTE]
>QuickBooks Online verilerinizi Power BI'a aktarmak için QuickBooks Online hesabınızda bir yönetici olmanız ve yönetici hesabı kimlik bilgilerinizle oturum açmanız gerekir. Bu bağlayıcıyı QuickBooks Desktop yazılımı ile birlikte kullanamazsınız. 

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getservices.png) 
3. **QuickBooks Online**'ı ve ardından **Al**'ı seçin.
   
   ![](media/service-connect-to-quickbooks-online/qbo.png)
4. Kimlik doğrulama yöntemi için **OAuth2** seçeneğini belirleyin ve **Oturum aç**'ı seçin. 
5. İstendiğinde QuickBooks Online kimlik bilgilerinizi girin ve QuickBooks Online kimlik doğrulaması işlemindeki diğer adımları uygulayın. Tarayıcınızda önceden QuickBooks Online oturumu açtıysanız kimlik bilgileriniz istenmeyebilir.
   >[!NOTE]
   >QuickBooks Online hesabınızın yönetici kimlik bilgileri gereklidir.
6. Sonraki ekranda, Power BI'a bağlamak istediğiniz şirketi seçin.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_almost.png)
7. İçeri aktarma işlemini başlatmak için sonraki ekranda bulunan **Authorize** (Yetkilendir) seçeneğini belirleyin. Bu işlem, şirket verilerinizin boyutuna bağlı olarak birkaç dakika sürebilir. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_authorizesm.png)
   
   Veriler Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Yeni öğeler sarı yıldız işareti \* ile gösterilir.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_leftnavnew.png)
8. QuickBooks Online panosunu seçin. Bu, içeri aktarılan verilerinizi görüntülemek için Power BI tarafından otomatik olarak oluşturulan panodur. Bu panoyu, verilerinizi istediğiniz herhangi bir biçimde görüntüleyecek şekilde değiştirebilirsiniz. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_dash.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="troubleshooting"></a>Sorun giderme
**"Oops! An error has occurred"** ("Hata! Bir hata oluştu")

**Authorize** (Yetkilendir) seçeneğini belirledikten sonra bu iletiyi alırsanız:

"Oops! An error has occurred." Please close this window and try again.

The application has already been subscribed to by another user for this company. Please contact [admin email] to make changes to this subscription." (Hata! Bir sorun oluştu. Lütfen pencereyi kapatın ve tekrar deneyin. Bu şirket için başka bir kullanıcı uygulamaya zaten abone oldu. Bu abonelik ile ilgili değişiklik yapmak için lütfen [yönetici e-postası] ile irtibat kurun.)

![](media/service-connect-to-quickbooks-online/pbi_qbo_oopssm.png)

... bu durum, şirketinizdeki başka bir yöneticinin Power BI ile şirket verilerinize zaten bağlandığı anlamına gelir. İlgili yöneticiden panoyu sizinle paylaşmasını isteyin. Şu anda yalnızca bir yönetici kullanıcı, belirli bir QuickBooks Online şirket veri kümesini Power BI'a bağlayabilir. Power BI panoyu oluşturduktan sonra yönetici, bu panoyu aynı Power BI kiracılarındaki birden çok iş arkadaşıyla paylaşabilir.

**"This app is not set up to allow connections from your country"** ("Bu uygulama, ülkenizden yapılan bağlantılara izin verecek şekilde ayarlanmadı")

Power BI şu anda yalnızca QuickBooks Online'ın ABD sürümlerini desteklemektedir. 

![](media/service-connect-to-quickbooks-online/pbi_qbo_countrynotsupported.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

