---
title: Power BI ile QuickBooks Online'a bağlanma
description: Power BI için QuickBooks Online
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/04/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 4c21c36694f36e4d6f95b8edc920648313dc8a7a
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348517"
---
# <a name="connect-to-quickbooks-online-with-power-bi"></a>Power BI ile QuickBooks Online'a bağlanma
Power BI'dan QuickBooks Online verilerine bağlandığınızda işletmenizin nakit akışına, kârlılığına, müşterilerine ve daha fazlasına yönelik öngörüler içeren bir Power BI panosu ve Power BI raporları alırsınız. Panoyu ve raporları olduğu gibi kullanabilir ya da en çok değer verdiğiniz bilgiler vurgulanacak şekilde özelleştirebilirsiniz. Veriler günde bir kez otomatik olarak yenilenir.

Power BI için [QuickBooks Online şablon uygulamasına](https://dxt.powerbi.com/getdata/services/quickbooks-online) bağlanın.

>[!NOTE]
>QuickBooks Online verilerinizi Power BI'a aktarmak için QuickBooks Online hesabınızda bir yönetici olmanız ve yönetici hesabı kimlik bilgilerinizle oturum açmanız gerekir. Bu bağlayıcıyı QuickBooks Desktop yazılımı ile birlikte kullanamazsınız. 

## <a name="how-to-connect"></a>Bağlanma

[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

3. **QuickBooks Online**'ı ve ardından **Al**'ı seçin.
   
   ![QuickBooks'u alın](media/service-connect-to-quickbooks-online/qbo.png)

4. **Bu Power BI uygulaması yüklensin mi?** iletişim kutusunda **Yükle**’yi seçin.

    ![QuickBooks'u yükleyin](media/service-connect-to-quickbooks-online/power-bi-install-quickbooks.png)

4. **Uygulamalar** bölmesinde **QuickBooks** kutucuğunu seçin.

   ![QuickBooks kutucuğunu seçin](media/service-connect-to-quickbooks-online/power-bi-quickbooks-tile.png)

6. **Yeni uygulamanızı kullanmaya başlayın** alanında **Bağlan** seçeneğini belirleyin.

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

4. Kimlik doğrulama yöntemi için **OAuth2** seçeneğini belirleyin ve **Oturum aç**'ı seçin. 
5. İstendiğinde QuickBooks Online kimlik bilgilerinizi girin ve QuickBooks Online kimlik doğrulaması işlemindeki diğer adımları uygulayın. Tarayıcınızda önceden QuickBooks Online oturumu açtıysanız kimlik bilgileriniz istenmeyebilir.
   >[!NOTE]
   >QuickBooks Online hesabınızın yönetici kimlik bilgileri gereklidir.
6. Sonraki ekranda, Power BI'a bağlamak istediğiniz şirketi seçin.
   
   ![QuickBooks neredeyse hazır](media/service-connect-to-quickbooks-online/pbi_qbo_almost.png)

7. İçeri aktarma işlemini başlatmak için sonraki ekranda bulunan **Authorize** (Yetkilendir) seçeneğini belirleyin. Bu işlem, şirket verilerinizin boyutuna bağlı olarak birkaç dakika sürebilir. 
   
   ![QuickBooks'u yetkilendirme](media/service-connect-to-quickbooks-online/pbi_qbo_authorizesm.png)
   
8. Veriler Power BI tarafından içeri aktarıldıktan sonra QuickBooks uygulamanızın içerik listesini görürsünüz: yeni bir pano, rapor ve veri kümesi.
9. Araştırma sürecini başlatmak için QuickBooks panosunu seçin. Bu, içeri aktarılan verilerinizi görüntülemek için Power BI tarafından otomatik olarak oluşturulan panodur.

    ![QuickBooks panosu](media/service-connect-to-quickbooks-online/power-bi-connect-quickbooks-sample.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](../consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](../create-reports/service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](../consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="troubleshooting"></a>Sorun giderme
**"Oops! An error has occurred"** ("Hata! Bir hata oluştu")

**Authorize** (Yetkilendir) seçeneğini belirledikten sonra bu iletiyi alırsanız:

"Oops! An error has occurred." Close this window and try again.

The application has already been subscribed to by another user for this company. Contact [admin email] to make changes to this subscription." (Hata! Bir sorun oluştu. Bu kapatın ve tekrar deneyin. Bu şirket için başka bir kullanıcı uygulamaya zaten abone oldu. Bu abonelik ile ilgili değişiklik yapmak için [yönetici e-postası] ile irtibat kurun.)

![Eyvah! Bir hata oluştu](media/service-connect-to-quickbooks-online/pbi_qbo_oopssm.png)

... bu hata, şirketinizdeki başka bir yöneticinin Power BI ile şirket verilerinize zaten bağlandığı anlamına gelir. İlgili yöneticiden panoyu sizinle paylaşmasını isteyin. Şu anda yalnızca bir yönetici kullanıcı, belirli bir QuickBooks Online şirket veri kümesini Power BI'a bağlayabilir. Power BI panoyu oluşturduktan sonra yönetici, bu panoyu aynı Power BI kiracılarındaki birden çok iş arkadaşıyla paylaşabilir.

**"This app is not set up to allow connections from your country"** ("Bu uygulama, ülkenizden yapılan bağlantılara izin verecek şekilde ayarlanmadı")

Power BI şu anda yalnızca QuickBooks Online'ın ABD sürümlerini desteklemektedir. 

![Bu uygulama, ülkenizden yapılan bağlantılara izin verecek şekilde ayarlanmadı](media/service-connect-to-quickbooks-online/pbi_qbo_countrynotsupported.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI nedir?](../fundamentals/power-bi-overview.md)

[Power BI hizmetinde tasarımcılara yönelik temel kavramlar](../fundamentals/service-basic-concepts.md)
