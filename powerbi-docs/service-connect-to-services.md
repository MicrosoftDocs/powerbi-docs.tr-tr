---
title: Power BI ile kullandığınız hizmetlere bağlanma
description: Salesforce, Microsoft Dynamics CRM ve Google Analytics gibi, işletmenizde kullandığınız birçok hizmetle bağlantı kurabilirsiniz.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 91740d16a91aa8dc1936e8ae1a2812653c45e6a1
ms.sourcegitcommit: 50c4bebd3432ef9c09eacb1ac30f028ee4e66d61
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73925824"
---
# <a name="connect-to-the-services-you-use-with-power-bi"></a>Power BI ile kullandığınız hizmetlere bağlanma
Power BI ile, Salesforce, Microsoft Dynamics ve Google Analytics gibi, işletmenizde kullandığınız birçok hizmetle bağlantı kurabilirsiniz. Power BI, hizmete bağlanmak için sizin kimlik bilgilerinizi kullanarak başlar. Verilerinizi otomatik olarak gösteren ve işletmenizle ilgili görsel öngörüler sunan bir panoyu ve çeşitli Power BI raporlarını içeren bir Power BI *çalışma alanı* oluşturur.

>[!IMPORTANT]
>Hizmet içerik paketleri [Şablon uygulamaları](https://docs.microsoft.com/power-bi/service-template-apps-overview) ile değiştiriliyor. 25 Eylül 2019’dan itibaren bir dizi içerik paketi zaten kullanım dışı bırakılmıştır. Yüklediğiniz tüm kullanım dışı içerik paketleri hesabınızda kalır, ancak bunlar için bir belge veya destek sağlanmaz ya da bunları yeniden yüklemek mümkün olmaz.

[Bağlantı kurabileceğiniz tüm hizmetleri](https://app.powerbi.com/getdata/services) görüntülemek için Power BI’da oturum açın. 

![AppSource uygulamaları](media/service-connect-to-services/overview.png)

Uygulamayı yükledikten sonra, panoyu ve raporları uygulamada ve Power BI hizmetindeki çalışma alanında ([https://app.powerbi.com](https://app.powerbi.com)) görüntüleyebilirsiniz. Bunları Power BI mobil uygulamalarında da görüntüleyebilirsiniz. Çalışma alanında, panoyu ve raporları kuruluşunuzun gereksinimlerine uygun olarak değiştirebilir ve bunları *uygulama* olarak iş arkadaşlarınıza dağıtabilirsiniz. 

![Power BI mobil uygulamasında Google Analytics uygulaması](media/service-connect-to-services/power-bi-service-mobile-app-240.png)

## <a name="get-started"></a>Başlangıç
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

## <a name="edit-the-dashboard-and-reports"></a>Panoyu ve raporları düzenleme
İçeri aktarma tamamlandığında, yeni uygulama Uygulamalar sayfasında görünür.

1. Gezinti bölmesinde **Uygulamalar** seçeneğini belirleyin ve ardından uygulamayı seçin.
   
     ![Uygulamalar sayfası](media/service-connect-to-services/power-bi-service-apps-open-app.png)
2. Soru-Cevap kutusuna yazarak soru sorabilir veya bağlantılı raporu açmak için bir kutucuğa tıklayabilirsiniz. 
   
    ![Google Analytics panosu](media/service-connect-to-services/googleanalytics2.png)
   
    Panoyu ve raporu kuruluşunuzun ihtiyaçlarına uyacak şekilde değiştirin. Ardından, [uygulamanızı iş arkadaşlarınıza dağıtın](service-create-distribute-apps.md)

## <a name="whats-included"></a>Neleri kapsar?
Bir hizmete bağlandıktan sonra pano, raporlar ve veri kümesi içeren yeni oluşturulmuş uygulamayı ve çalışma alanını görürsünüz. Hizmetten alınan veriler belirli bir senaryoya bağlıdır ve hizmetteki tüm bilgileri içermeyebilir. Veriler günde bir kez otomatik olarak yenilenecek şekilde ayarlanır. Veri kümesini seçerek, zamanlamayı denetleyebilirsiniz.

Ayrıca, Google Analytics gibi [Power BI Desktop’taki birçok hizmete bağlanabilir](desktop-data-sources.md) ve kendi özelleştirilmiş pano ve raporlarınızı oluşturabilirsiniz.  

Belirli hizmetlere bağlanma hakkında ayrıntılı bilgi için hizmetlerle ilgili yardım sayfalarına bakın.

## <a name="troubleshooting"></a>Sorun giderme
**Boş kutucuklar**  
Power BI hizmete ilk kez bağlandığında panonuzda boş kutucuklar görebilirsiniz. 2 saat sonra da panonuz boşsa bağlantı başarısız olmuş olabilir. Sorunu düzeltme önerileri içeren bir hata iletisiyle karşılaşmadıysanız destek bileti oluşturun.

* Sağ üst köşedeki soru işareti simgesini ( **?** ) seçin ve ardından **Yardım al** seçeneğini belirleyin.
  
    ![Yardım al simgesi](media/service-connect-to-services/power-bi-service-get-help.png)

**Eksik bilgiler**  
Panolar ve raporlar, hizmetten alınan ve belirli bir senaryoya odaklanmış içerikleri içerir. Uygulamada belirli bir ölçümü ararsanız ve bunu bulamazsanız [Power BI Desteği](https://support.powerbi.com/forums/265200-power-bi) sayfasına bir fikir ekleyin.

## <a name="suggesting-services"></a>Hizmet önerme
Power BI uygulaması için önermek istediğiniz bir hizmet mi kullanıyorsunuz? [Power BI Destek](https://support.powerbi.com/forums/265200-power-bi) sayfasına giderek bizimle paylaşın.

Kendiniz dağıtmak üzere şablon uygulamaları oluşturmak ilginizi çekiyorsa, bkz. [Power BI’da şablon uygulaması oluşturma](service-template-apps-create.md). Power BI iş ortakları çok az kodlamayla veya hiç kodlama kullanmadan Power BI uygulamaları oluşturabilir ve bunları Power BI müşterilerine dağıtabilir. 

## <a name="next-steps"></a>Sonraki adımlar
* [Uygulamaları iş arkadaşlarınıza dağıtma](service-create-distribute-apps.md)
* [Power BI'da yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

