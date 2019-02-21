---
title: Power BI şablon uygulamaları nedir? (önizleme)
description: Bu makale Power BI şablon uygulaması programına genel bir bakış sağlar. Çok az kodlamayla veya hiç kodlama kullanmadan Power BI uygulamaları oluşturmayı ve bunları Power BI müşterilerine dağıtmayı öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: maggies
ms.openlocfilehash: 445f5f087bd9589b18f798e8db40a63b0ddceafe
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56250107"
---
# <a name="what-are-power-bi-template-apps-preview"></a>Power BI şablon uygulamaları nedir? (önizleme)

Yeni Power BI *şablon uygulamaları* Power BI iş ortaklarının çok az kodlamayla veya hiç kodlama kullanmadan Power BI uygulamaları oluşturmasını ve bunları Power BI müşterilerine dağıtmasını sağlar.  Bu makale Power BI şablon uygulaması programına genel bir bakış sağlar.

Şablon uygulamaları geçerli hizmet içerik paketlerinin yerini almıştır. Bir Power BI iş ortağı olarak, müşterileriniz için kullanıma hazır bir içerik kümesi oluşturur ve bunu kendiniz yayımlarsınız.  

Müşterilerinizin kendi hesaplarıyla bağlanmasına ve örnek oluşturmasına olanak sağlayan şablon uygulamaları oluşturursunuz. Etki alanı uzmanları olarak, işletme kullanıcıları tarafından kolayca kullanılabilecek şekilde verilerin kilidini açabilirler.  

İş ortağınızın derlediği şablon uygulamalarını Bulut İş Ortağı Portalı’na gönderirsiniz. Ardından uygulamalar Power BI Uygulama galerisinde (app.powerbi.com/getdata/services) ve Microsoft AppSource’ta (appsource.microsoft.com) genel kullanıma sunulur. Aşağıda genel şablon uygulaması deneyimine bir örnek verilmiştir.  

## <a name="overview"></a>Genel Bakış
Genel şablon uygulaması geliştirme ve gönderme süreci çeşitli aşamalardan oluşur ve bunlardan bazıları aynı anda birden çok etkinlik içerir.


| Aşama | Power BI Desktop |  |Power BI hizmeti  |  |Bulut İş Ortağı Portalı  |
|---|--------|--|---------|---------|---------|
| **Bir** | Bir .pbix dosyasında veri modeli ve rapor oluşturma |  | Çalışma alanı oluşturma. .pbix dosyasını içeri aktarma. Tamamlayıcı bir pano oluşturma  |  | İş ortağı olarak kaydetme |
| **İki** |  |  | Test paketi oluşturma ve kuruluş içinde doğrulamayı çalıştırma        |  | |
| **Üç** | |  | Power BI kiracınızın dışında doğrulama için test paketini üretim öncesi aşamaya yükseltme ve AppSource’a gönderme  |  | Üretim öncesi paketinizle bir Power BI şablon uygulaması teklifi oluşturma ve doğrulama sürecini başlatma |
| **Dört** | |  | Üretim öncesi paketi üretime yükseltme |  | Canlı yayına geçme |

## <a name="requirements"></a>Gereksinimler

Şablon uygulaması oluşturmak için, bu uygulamayı oluşturma izinleriniz olmalıdır. Ayrıntılar için bkz. Power BI yönetim portalı, Şablon uygulaması ayarları. 

Şablon uygulamasını Power BI hizmetine ve AppSource’a yayımlamak için, [Bulut Marketi Yayımcısı olma](https://docs.microsoft.com/azure/marketplace/become-publisher) gereksinimlerini karşılamanız gerekir.
 
## <a name="high-level-steps"></a>Üst düzey adımlar

Üst düzey adımlar aşağıda verilmiştir. 

1. [Gereksinimleri gözden geçirip](#requirements) bunları karşıladığınızdan emin olun. 

1. Power BI Desktop'ta rapor oluşturun. Raporu diğer kişilerin kullanabileceği bir dosya olarak kaydedebilmek için parametreleri kullanın. 

1. Power BI hizmetinde (app.powerbi.com) şablon uygulamanız için kiracınızda bir çalışma alanı oluşturun. 

1. .pbix dosyanızı içeri aktarın ve uygulamanıza içerik, örneğin bir pano ekleyin. 

1. Şablon uygulamasını kuruluşunuzun içinde kendiniz test etmek için bir test paketi oluşturun. 

1. Test uygulamasını üretim öncesi aşamaya yükselterek uygulamayı AppSource’ta doğrulamaya gönderin ve kendi kiracınızın dışında test edin. 

1. İçeriği yayımlanmak üzere Bulut İş Ortağı Platformu’na gönderin. 

1. Teklifinizi AppSource’ta 'Canlı Yayına' geçirin ve Power BI’da üretime taşıyın.
2. Artık aynı çalışma alanında, üretim öncesi aşamada bir sonraki sürümü geliştirmeye başlayabilirsiniz. 

## <a name="requirements"></a>Gereksinimler

Şablon uygulaması oluşturmak için, bu uygulamayı oluşturma izinleriniz olmalıdır. Ayrıntılar için bkz. Power BI [yönetim portalı, Şablon uygulaması ayarları](service-admin-portal.md#template-apps-settings-preview). 

Şablon uygulamasını Power BI hizmetine ve AppSource’a yayımlamak için, [Bulut Marketi Yayımcısı olma](https://docs.microsoft.com/azure/marketplace/become-publisher) gereksinimlerini karşılamanız gerekir.

## <a name="tips"></a>İpuçları 

- Herkesin tek tıklamayla başlayabilmesi için uygulamanıza örnek verilerin eklendiğinden emin olun. 
- Uygulamanızı kiracınıza ve ikinci bir kiracıya yükleyerek dikkatle inceleyin. Müşterilerin yalnızca onlara göstermek istediklerinizi gördüğünden emin olun. 
- Uygulamanızı barındırmak için çevrimiçi deponuz olarak AppSource’u kullanın. Bu şekilde Power BI kullanan herkesi uygulamanızı bulabilir. 
- Ayrı benzersiz senaryolar için birden fazla şablon uygulaması sunmayı göz önüne alın. 
- Veri özelleştirmesini etkinleştirin, örneğin yükleyicinin özel bağlantısını ve parametre yapılandırmasını destekleyin.

Diğer öneriler için bkz. [Power BI’da şablon uygulaması yazma ipuçları (önizleme)](service-template-apps-tips.md).

## <a name="support"></a>Destek
Geliştirme sırasında destek almak için [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support) adresine gidin. Bu siteyi etkin bir şekilde izliyor ve yönetiyoruz. Müşteri olayları hızla ilgili ekibe aktarılmaktadır.

## <a name="next-steps"></a>Sonraki adımlar

[Şablon uygulaması oluşturma](service-template-apps-create.md)