---
title: Power BI’da şablon uygulamaları oluşturma (önizleme)
description: Power BI’da tüm Power BI müşterilerine dağıtabileceğiniz şablon uygulamaları oluşturma.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: maggies
ms.openlocfilehash: c08b7e60777b720aa4fc2489b02c212bdd3e7169
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56250033"
---
# <a name="create-a-template-app-in-power-bi-preview"></a>Power BI’da şablon uygulaması oluşturma (önizleme)

Yeni Power BI *şablon uygulamaları* Power BI iş ortaklarının çok az kodlamayla veya hiç kodlama kullanmadan Power BI uygulamaları oluşturmasını ve bunları Power BI müşterilerine dağıtmasını sağlar.  Bu makale, Power BI şablon uygulaması oluşturmak için adım adım yönergeler içerir. 

Power BI raporları ve panoları oluşturabiliyorsanız, analitik içerik oluşturan ve bu içeriği *uygulama* içinde paketleyen bir *şablon uygulaması oluşturucusu* olabilirsiniz. Ardından uygulamanızı, AppSource gibi herhangi bir kullanılabilir platform aracılığıyla veya kendi web hizmetinizde kullanarak diğer Power BI kiracılarına dağıtabilirsiniz. Bir oluşturucu olarak dağıtım için korumalı bir analiz paketi oluşturabilirsiniz. 

Kuruluşlarında kimlerin şablon uygulamaları oluşturabileceğini ve kimlerin bu uygulamaları yükleyebileceğini Power BI kiracı yöneticileri yönetir ve denetler. Yetkili kullanıcılar şablon uygulamanızı yükleyebilir, sonra uygulamada değişiklik yapabilir ve bunu kendi kuruluşlarındaki Power BI müşterilerine dağıtabilir.

## <a name="prerequisites"></a>Önkoşullar 

Şablon uygulaması oluşturmak için şunları gerekir:  

- [Power BI Pro lisansı](service-self-service-signup-for-power-bi.md)
- [Power BI Desktop yüklemesi](desktop-get-the-desktop.md) (isteğe bağlı)
- [Temel Power BI kavramlarını](service-basic-concepts.md) tanıma
- Şablon uygulaması oluşturma izinleri. Ayrıntılar için bkz. Power BI [yönetim portalı, Şablon uygulaması ayarları](service-admin-portal.md#template-apps-settings-preview).

## <a name="enable-app-developer-mode"></a>Uygulama geliştirici modunu etkinleştirme

Diğer Power BI kiracılarına dağıtabileceğiniz bir şablon uygulaması oluşturmak için Uygulama Geliştirici modunda olmalısınız. Aksi takdirde, yalnızca kendi kuruluşunuzdaki Power BI kullanıcıları için uygulama oluşturursunuz.
 
1. Tarayıcıda Power BI hizmetini açın.
2. **Ayarlar** > **Genel** > **Geliştirici** > **Şablon uygulaması geliştirme modunu etkinleştir**’e gidin.

    ![Şablon uygulamalarını etkinleştirme](media/service-template-apps-create/power-bi-dev-template-app.png)

    Bu seçeneği görmüyorsanız, Power BI yöneticinize başvurun ve size yönetim portalında [şablon uygulaması geliştirme izinleri](service-admin-portal.md#template-apps-settings-preview) vermesini isteyin.

3. **Apply** (Uygula) seçeneğini belirleyin.

## <a name="create-the-template-app-workspace"></a>Şablon uygulaması çalışma alanını oluşturma

Diğer Power BI kiracılarına dağıtabileceğiniz bir şablon uygulaması oluşturmak için, bu uygulamayı yeni uygulama çalışma alanlarından birinde oluşturmalısınız. 
 
1. Power BI hizmetinde **Çalışma alanları** > **Uygulama çalışma alanı oluştur**’u seçin. 
 
    ![Uygulama çalışma alanı oluştur](media/service-template-apps-create/power-bi-new-workspace.png)

3. **Uygulama çalışma alanı oluştur** penceresinin **Geliştirilmiş çalışma alanlarını önizle** alanında **Şimdi dene**'yi seçin.

    ![Yeni çalışma alanlarını deneme](media/service-template-apps-create/power-bi-try-now-new-workspace.png)

5. Uygulama çalışma alanınız için ad, açıklama (isteğe bağlı) ve logo resmi (isteğe bağlı) girin.

4. Select **Bir şablon uygulaması geliştirin** öğesini seçin.

    ![Şablon uygulaması geliştirin](media/service-template-apps-create/power-bi-template-app-develop.png)

5. **Kaydet**'i seçin.

## <a name="create-the-content-in-your-template-app"></a>Şablon uygulamanızdaki içeriği oluşturma

Normal Power BI uygulama çalışma alanlarında olduğu gibi, sonraki adımınız çalışma alanında içeriği oluşturmaktır.  Şablon uygulamalarının bu önizleme sürümünde, her türden birer tane oluşturmayı destekliyoruz: bir veri kümesi, bir rapor ve bir pano.

- Uygulama çalışma alanınızda [Power BI içeriğinizi oluşturun](power-bi-creator-landing.md).

Power Query’de parametreleri kullanıyorsanız, bunların iyi tanımlanmış türde (örneğin, Text) olmasına dikkat edin. Any ve Binary türleri desteklenmez. 

[Power BI’da şablon uygulaması yazmaya yönelik ipuçları (önizleme)](service-template-apps-tips.md) makalesinde şablon uygulamanız için rapor ve pano oluştururken göz önüne alınacak öneriler bulunur.

## <a name="create-the-test-template-app"></a>Test şablon uygulaması oluşturma

Artık çalışma alanınızda içeriğiniz olduğuna göre, bu içeriği bir şablon uygulamasında paketlemeye hazırsınız. İlk adım yalnızca kiracınızda kuruluşunuzun içinden erişilebilen bir test şablon uygulaması oluşturmaktır.

1. Şablon uygulaması çalışma alanında **Uygulama oluştur**’u seçin. 

    ![Uygulama oluşturma](media/service-template-apps-create/power-bi-create-app.png)
 
    Burada, şablon uygulamanız için dört kategoride ek parametreleri doldurursunuz. 

    **Markalama**

    - Uygulama adı 
    - Açıklama
    - Uygulama logosu (isteğe bağlı)
    - Uygulama rengi 

    **İçerik** 

    - Uygulama giriş sayfası (isteğe bağlı): Uygulamanızın giriş sayfası olarak bir rapor veya pano tanımlayın.  
    
    **Denetim** 

    Uygulamanızdaki içerikle ilgili olarak, uygulama kullanıcıları için geçerli olacak çeşitli sınırlamaları ve kısıtlamaları denetleyin. Bu denetimi kullanarak uygulamanızda bulunabilecek fikri mülkiyeti koruyabilirsiniz.

    **Erişim**

    - Test aşamasında, kuruluşunuzda başka kimlerin uygulamanızı yükleyebileceğine ve test edebileceğine karar verin.

    Endişelenmeyin; istediğiniz zaman geri dönebilir ve bu ayarları değiştirebilirsiniz.  

2. **Uygulama oluştur**'u seçin. 

    Test uygulamasının hazır olduğunu belirten ve kopyalayıp uygulamanızı test edenlerle paylaşabileceğiniz bir bağlantı içeren bir ileti görürsünüz.

    ![Test uygulaması hazır](media/service-template-apps-create/power-bi-template-app-test-ready.png)

    Aşağıdaki sürüm yönetim işleminin de ilk adımını tamamlamış oldunuz.

    

## <a name="manage-the-template-app-release"></a>Şablon uygulaması sürümünü yönetme

Bu şablon uygulamasını genel kullanıma sunmadan önce, kullanıma hazır olduğundan emin olmak istersiniz. Power BI, tüm uygulama sürüm yolunu izleyip inceleyebileceğiniz sürüm yönetim bölmesini oluşturmuştur. Bir aşamadan diğerine geçişi de tetikleyebilirsiniz. Yaygın aşamalar şunlardır: 

- Test uygulaması oluşturma: yalnızca kuruluşunuzda test etmek için. 
- Test paketini üretim öncesi aşamaya yükseltme: kuruluşunuzun dışında test etme.
- Üretim öncesi paketini Üretime yükseltme: üretim sürümü. 
- Tüm paketleri silme veya önceki aşamadan yeniden başlama. 

Şimdi aşamaları gözden geçirelim.

1. Şablon uygulaması çalışma alanında **Sürüm Yönetimi**’ni seçin.

    ![Sürüm Yönetimi simgesi](media/service-template-apps-create/power-bi-release-management-icon.png)

2. **Uygulama oluştur**'u seçin. 

    Yukarıdaki **Test şablon uygulaması oluştur** seçeneğiyle test uygulaması oluşturduysanız, **Test**’in yanındaki sarı nokta zaten doldurulmuş görünür ve burada **Uygulama oluştur**’u seçmeniz gerekmez. Seçerseniz, şablon uygulaması oluşturma işlemine geri dönersiniz.
 
3. **Bağlantı al**’ı seçin.

    ![Uygulama oluşturma, bağlantı alma](media/service-template-apps-create/power-bi-dev-template-create-app-get-link.png)
 
9. Uygulama yükleme deneyimini test etmek için, bildirim penceresindeki bağlantıyı kopyalayın ve yeni bir tarayıcı penceresine yapıştırın. 

    Burada, müşterilerinizin izleyeceği yordamın aynısını izlersiniz. Sürümleri için bkz. [Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma](service-template-apps-install-distribute.md).
 
10. İletişim kutusunda **Yükle**'yi seçin.

    Yükleme başarılı olduğunda yeni uygulamanın hazır olduğuna ilişkin bir bildirim görürsünüz. 
 
11. **Uygulamaya git**’i seçin.
 
12. **Yeni uygulamanızı kullanmaya başlayın** penceresinde uygulamanızı aynı müşterilerinizin göreceği gibi görürsünüz. 

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-template-apps-create/power-bi-template-app-get-started.png)

13. Test uygulamasını örnek verilerle doğrulamak için **Uygulamayı Keşfet**’i seçin.

1. Değişiklik yapmak için özgün çalışma alanındaki uygulamaya geri dönün. Sonuçtan memnun kalana kadar test uygulamasını güncelleştirin.

9. Uygulamanızı kiracınızın dışında test edilmek üzere üretim öncesi aşamaya yükseltmek için, **Sürüm Yönetimi** bölmesine dönün ve **Test**’in yanındaki **Uygulamayı yükselt**’i seçin.
 
    ![Uygulamayı üretim öncesi aşamaya yükseltme](media/service-template-apps-create/power-bi-template-app-promote.png)

11. Seçiminizi onaylamak için **Yükselt**’i seçin. 

12. Bu yeni URL’yi kopyalayın ve kiracınızın dışında test edilmesi için paylaşın. Bu aynı zamanda, uygulamanızı AppSource’ta dağıtma sürecini başlatmak için göndereceğiniz bağlantıdır.

12. Uygulamanız üretime veya AppSource yoluyla paylaşıma hazır olduğunda, **Sürüm Yönetimi** bölmesine dönün ve **Ön üretim**’in yanındaki **Uygulamayı yükselt**’i seçin.
 
11. Seçiminizi onaylamak için **Yükselt**’i seçin. 

    Artık uygulamanız üretim aşamasındadır ve dağıtıma hazırdır.

    ![Üretim ortamında uygulama](media/service-template-apps-create/power-bi-template-app-production.png)

Uygulamanızın dünya genelinde binlerce Power BI kullanıcısına sunulabilmesi için, uygulamayı AppSource’a göndermenizi öneririz. Ayrıntılar için bkz. [Power BI Uygulama teklifi](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer). 

## <a name="update-your-app"></a>Uygulamanızı güncelleştirme

Uygulamanız artık üretim ortamında olduğundan, üretimdeki uygulamaya müdahale etmeden test aşamasının üzerinden geçebilirsiniz. 

1. **Sürüm yönetimi** bölmesinde **Uygulama oluştur**’u seçin.

1. Uygulama oluşturma sürecine en baştan yeniden başlayın. 
2. **Markalama**, **İçerik**, **Denetim** ve **Erişim**’i ayarladıktan sonra yeniden **Uygulama oluştur**’u seçin.
3. **Kapat**’ı seçin ve **Sürüm yönetimi**’ne dönün. 

    Şimdi iki sürümünüz olduğunu görürsünüz: üretimdeki sürüm ve test aşamasındaki yeni sürüm. 

    ![Şablon uygulamasının iki sürümü](media/service-template-apps-create/power-bi-template-app-2-versions.png)

## <a name="next-steps"></a>Sonraki adımlar

Müşterilerinizin şablon uygulamanızla nasıl etkileşim kurduğunu görmek için bkz. [Kuruluşunuzda şablon uygulamalarını yükleme, özelleştirme ve dağıtma](service-template-apps-install-distribute.md).

Uygulamanızı dağıtma işleminin ayrıntıları için bkz. [Power BI Uygulama teklifi](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).





