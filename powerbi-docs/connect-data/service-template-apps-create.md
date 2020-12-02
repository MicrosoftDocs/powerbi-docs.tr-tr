---
title: Power BI’da şablon uygulamaları oluşturma
description: Power BI’da tüm Power BI müşterilerine dağıtabileceğiniz şablon uygulamaları oluşturma.
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 09/15/2020
ms.openlocfilehash: fc62d291b890d840b89997cd5d5253572f91bf3e
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96410241"
---
# <a name="create-a-template-app-in-power-bi"></a>Power BI’da şablon uygulaması oluşturma

Power BI *şablon uygulamaları*, Power BI iş ortaklarının çok az kodlamayla veya hiç kodlama kullanmadan Power BI uygulamaları oluşturmasını ve bunları Power BI müşterilerine dağıtmasını sağlar.  Bu makalede, Power BI şablon uygulaması oluşturmaya yönelik adım adım yönergeler yer almaktadır.

Power BI raporları ve panoları oluşturabiliyorsanız, *şablon uygulaması oluşturucusu* olabilir ve analitik içeriklerini derleyip *uygulama* içinde paketleyebilirsiniz. Uygulamanızı, AppSource gibi herhangi bir kullanılabilir platform aracılığıyla veya kendi web hizmetinizde kullanarak diğer Power BI kiracılarına dağıtabilirsiniz. Bir oluşturucu olarak dağıtım için korumalı bir analiz paketi oluşturabilirsiniz.

Kuruluşlarında kimlerin şablon uygulamaları oluşturabileceğini ve kimlerin bu uygulamaları yükleyebileceğini Power BI yöneticileri yönetir ve denetler. Yetkili kullanıcılar şablon uygulamanızı yükleyebilir, sonra uygulamada değişiklik yapabilir ve bunu kendi kuruluşlarındaki Power BI müşterilerine dağıtabilir.

## <a name="prerequisites"></a>Önkoşullar

Şablon uygulaması oluşturmak için şunları gerekir:  

- [Power BI Pro lisansı](../fundamentals/service-self-service-signup-for-power-bi.md)
- [Power BI Desktop yüklemesi](../fundamentals/desktop-get-the-desktop.md) (isteğe bağlı)
- [Temel Power BI kavramlarını](../fundamentals/service-basic-concepts.md) tanıma
- Bir şablon uygulamasını herkese açık şekilde paylaşma izni (daha fazla bilgi için bkz. Power BI [yönetici portalı, Şablon uygulaması ayarları](../admin/service-admin-portal.md#template-apps-settings)

## <a name="create-the-template-workspace"></a>Şablon çalışma alanını oluşturma

Diğer Power BI kiracılarına dağıtabileceğiniz bir şablon uygulaması oluşturmak için, bu uygulamayı yeni çalışma alanlarından birinde oluşturmalısınız.

1. Power BI hizmetinde **Çalışma alanları** > **Çalışma alanı oluştur**’u seçin.

    ![Çalışma alanı oluşturma](media/service-template-apps-create/power-bi-new-workspace.png)

2. **Çalışma alanı oluştur** bölümünde, çalışma alanınız için ad, açıklama (isteğe bağlı) ve logo resmi (isteğe bağlı) girin.

    ![Yeni çalışma alanlarını deneme](media/service-template-apps-create/power-bi-upgrade-new.png)

4. **Gelişmiş** bölümünü genişletin ve **Şablon uygulaması geliştirin**’i seçin.

    ![Şablon uygulaması geliştirin](media/service-template-apps-create/power-bi-template-app-develop.png)

5. **Kaydet**’i seçin.
>[!NOTE]
>Şablon uygulamalarını tanıtmak için Power BI yöneticinizin izinleri gerekir.

## <a name="add-content-to-the-template-app-workspace"></a>Şablon uygulaması çalışma alanına içerik ekleme

Normal Power BI çalışma alanlarında olduğu gibi, sonraki adımınız çalışma alanına içerik eklemektir.  

- Çalışma alanınızda [Power BI içeriğinizi oluşturun](index.yml).

Power Query’de parametreleri kullanıyorsanız, bunların iyi tanımlanmış türlerde (örneğin, Metin) olmasına dikkat edin. Any ve Binary türleri desteklenmez.

[Power BI’da şablon uygulaması yazmaya yönelik ipuçları](service-template-apps-tips.md) makalesinde şablon uygulamanız için rapor ve pano oluştururken göz önüne alınacak öneriler bulunur.

## <a name="define-the-properties-of-the-template-app"></a>Şablon uygulamasının özelliklerini tanımlama

Artık çalışma alanınızda içeriğiniz olduğuna göre, bu içeriği bir şablon uygulamasında paketlemeye hazırsınız. İlk adım yalnızca kiracınızda kuruluşunuzun içinden erişilebilen bir test şablon uygulaması oluşturmaktır.

1. Şablon uygulaması çalışma alanında **Uygulama oluştur**’u seçin.

    ![Uygulama oluşturma](media/service-template-apps-create/power-bi-create-app.png)

    Burada, şablon uygulamanız için altı sekmede ek derleme seçeneklerini doldurursunuz:

    **Marka**

    ![Marka](media/service-template-apps-create/power-bi-create-branding.png)
    - Uygulama adı
    - Description
    - Destek sitesi (şablon uygulaması kuruluş uygulaması olarak yeniden dağıtıldıktan sonra bu bağlantı uygulama bilgilerinin altında gösterilir)
    - Uygulama logosu (45K dosya boyutu sınırı, 1:1 en boy oranı, .png .jpg .jpeg biçimleri)
    - Uygulama tema rengi

    **Gezinti**

    Uygulamanın gezinti bölmesini tanımlayabileceğiniz **Yeni gezinti derleyicisi**’ni etkinleştirin (Ayrıntılar için bu makaledeki [Gezinti deneyimini tasarlama](../collaborate-share/service-create-distribute-apps.md#design-the-navigation-experience) bölümüne bakın).

   ![Uygulama giriş sayfasını ayarlama](media/service-template-apps-create/power-bi-install-app-content.png)
    
    **Uygulama giriş sayfası:** Gezinti oluşturucuyu kullanmamaya karar verirseniz uygulama giriş sayfasını seçebilirsiniz. Uygulamanızın giriş sayfası olarak bir rapor veya pano tanımlayın. Doğru etkiyi bırakan bir giriş sayfası kullanın.

    **Denetim**

    Uygulamanızın içeriğiyle ilgili olarak, uygulama kullanıcılarınız için geçerli olacak sınırları ve kısıtlamaları ayarlayın. Bu denetimi kullanarak uygulamanızda fikri mülkiyeti koruyabilirsiniz.

    ![Denetim](media/service-template-apps-create/power-bi-create-control.png)

    >[!NOTE]
    >Uygulamayı yükleyen kullanıcılar için .pbix biçimine dışarı aktarmak her zaman engellenir.

    **Parametreler**

    Parametreler özgün pbix dosyasında oluşturulur ([sorgu parametreleri oluşturma](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) hakkında daha fazla bilgi edinin). Uygulama yükleyicisinin, verilerine bağlandığında yüklemeden sonra uygulamayı yapılandırmasına yardımcı olmak için bu sekmedeki özellikleri kullanırsınız.

    Bu sekmede, uygulama belgelerinin bağlantısını da sağlarsınız.

    ![Parametreler](media/service-template-apps-create/power-bi-create-parameters.png)

    Her parametrenin, sorgudan gelen bir adı ve açıklaması ile bir değer alanı vardır. Yükleme sırasında parametreye yönelik bir değer almak için üç seçeneğiniz vardır.

    * Yükleyicinin bir değer girmesini zorunlu tutabilirsiniz. Bu durumda, yerlerini alacak bir örnek sağlarsınız. Bir parametreyi bu şekilde yapılandırmak için, **Zorunlu** onay kutusunu işaretleyin ve metin kutusunda, kullanıcıya ne tür değer beklendiğini gösteren bir örnek verin. Örnek:

       ![Kullanıcının girmek zorunda olduğu parametre değerinin ekran görüntüsü.](media/service-template-apps-create/power-bi-create-parameters-require-user.png)

    * Uygulamayı yükleyen kullanıcının değiştiremeyeceği, önceden doldurulmuş bir değer sağlayabilirsiniz. Bu şekilde yapılandırılan bir parametre, uygulamayı yükleyen kişiden gizlenir. Yalnızca önceden doldurulmuş değerin, tüm kullanıcılar için geçerli olduğundan eminseniz bu yöntemi kullanmanız gerekir. Aksi takdirde, kullanıcı girişini gerektiren, yukarıda belirtilen birinci yöntemi kullanın.

       Bir parametreyi bu şekilde yapılandırmak için, **Değer** metin kutusuna değeri girin ve kilit simgesine tıklayın. Böylece değer değiştirilemez hale getirilir. Örnek:

       ![Mutlak parametre değerinin ekran görüntüsü.](media/service-template-apps-create/power-bi-create-parameters-absolute.png)

    * Kullanıcının yükleme sırasında değiştirebileceği varsayılan bir değer sağlayabilirsiniz. Bir parametreyi bu şekilde yapılandırmak için, **Değer** metin kutusuna istediğiniz varsayılan değeri girin ve kilit simgesini kilidi açık şekilde bırakın. Örnek:

      ![Değiştirilebilir varsayılan parametre değerinin ekran görüntüsü.](media/service-template-apps-create/power-bi-create-parameters-default.png)

    **Kimlik Doğrulaması**
    
    Bu sekmede, kullanılacak kimlik doğrulama yöntemini seçersiniz. Kullanılabilen seçenekler, kullanılmakta olan veri kaynağı türlerine bağlıdır.

    ![Kimlik doğrulama yöntemi seçeneğinin ekran görüntüsü.](media/service-template-apps-create/power-bi-create-authentication.png)

    Gizlilik düzeyi otomatik olarak yapılandırılır:
   * Tek bir veri kaynağı: Otomatik şekilde özel olarak yapılandırılır.
   * Çoklu anonim veri kaynağı: Otomatik şekilde genel olarak yapılandırılır.

    **Erişim**
    
    Test aşamasında, kuruluşunuzda başka kimlerin uygulamanızı yükleyebileceğine ve test edebileceğine karar verin. Endişelenmeyin; istediğiniz zaman geri dönebilir ve bu ayarları değiştirebilirsiniz. Bu ayar, dağıtılmış şablon uygulamasının erişimini etkilemez.

    ![Erişim sekmesinin ekran görüntüsü.](media/service-template-apps-create/power-bi-create-access.png)

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

Sürüm aşamaları arasında hareket ettiğinizde URL değişmez. Yükseltme URL'nin kendisini etkilemez.

Şimdi aşamaları gözden geçirelim:

1. Şablon çalışma alanında **Release Management**’ı seçin.

    ![Sürüm Yönetimi simgesi](media/service-template-apps-create/power-bi-release-management-icon.png)

2. Yukarıdaki **Şablon uygulamasının özelliklerini tanımlama** bölümünde test uygulamasını oluşturduysanız (sonuç olarak, **Test**’in yanındaki sarı nokta önceden doldurulmuş olur) **Bağlantı al** seçeneğini belirleyin.

    Henüz uygulamayı oluşturmadıysanız **Uygulama oluştur**’u seçin. Böylece şablon uygulaması oluşturma işlemine geri dönersiniz.

    ![Uygulama oluşturma, bağlantı alma](media/service-template-apps-create/power-bi-dev-template-create-app-get-link.png)

4. Uygulama yükleme deneyimini test etmek için, bildirim penceresindeki bağlantıyı kopyalayın ve yeni bir tarayıcı penceresine yapıştırın.

    Burada, müşterilerinizin izleyeceği yordamın aynısını izlersiniz. Bkz. [Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma](service-template-apps-install-distribute.md).

5. İletişim kutusunda **Yükle**'yi seçin.

    Yükleme başarılı olduğunda yeni uygulamanın hazır olduğuna ilişkin bir bildirim görürsünüz.

6. **Uygulamaya gidin**'i seçin.
7. **Yeni uygulamanızı kullanmaya başlayın** penceresinde uygulamanızı aynı müşterilerinizin göreceği gibi görürsünüz.

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-template-apps-create/power-bi-template-app-get-started.png)
8. Test uygulamasını örnek verilerle doğrulamak için **Uygulamayı Keşfet**’i seçin.
9. Değişiklik yapmak için özgün çalışma alanındaki uygulamaya geri dönün. Sonuçtan memnun kalana kadar test uygulamasını güncelleştirin.
10. Uygulamanızı kiracınızın dışında test edilmek üzere üretim öncesi aşamaya yükseltmek için, **Sürüm Yönetimi** bölmesine dönün ve **Uygulamayı yükselt**’i seçin.

    ![Uygulamayı üretim öncesi aşamaya yükseltme](media/service-template-apps-create/power-bi-template-app-promote.png)
    >[!NOTE]
    > Uygulama yükseltildiğinde kuruluşunuzun dışında herkese açık duruma gelir.

    Bu seçeneği görmüyorsanız, Power BI yöneticinize başvurun ve size yönetim portalında [şablon uygulaması geliştirme izinleri](../admin/service-admin-portal.md#template-apps-settings) vermesini isteyin.
11. Seçiminizi onaylamak için **Yükselt**’i seçin.
12. Bu yeni URL’yi kopyalayın ve kiracınızın dışında test edilmesi için paylaşın. Bu aynı zamanda, [yeni İş ortağı merkezi teklifi](/azure/marketplace/partner-center-portal/create-power-bi-app-offer) oluşturarak uygulamanızı AppSource’ta dağıtma sürecini başlatmak için göndereceğiniz bağlantıdır. İş ortağı merkezine yalnızca üretim öncesi bağlantılarını gönderin. Ancak uygulama onaylandıktan ve AppSource’ta yayımlandığına ilişkin bildirim aldıktan sonra bu paketi Power BI’da üretime yükseltebilirsiniz.
13. Uygulamanız üretime veya AppSource yoluyla paylaşıma hazır olduğunda, **Sürüm Yönetimi** bölmesine dönün ve **Ön üretim**’in yanındaki **Uygulamayı yükselt**’i seçin.
14. Seçiminizi onaylamak için **Yükselt**’i seçin.

    Artık uygulamanız üretim aşamasındadır ve dağıtıma hazırdır.

    ![Üretim ortamında uygulama](media/service-template-apps-create/power-bi-template-app-production.png)

Uygulamanızın dünya genelinde binlerce Power BI kullanıcısına sunulabilmesi için, uygulamayı AppSource’a göndermenizi öneririz. Ayrıntılar için bkz. [Power BI Uygulama teklifi](/azure/marketplace/partner-center-portal/create-power-bi-app-offer).

## <a name="next-steps"></a>Sonraki adımlar

Müşterilerinizin şablon uygulamanızla nasıl etkileşim kurduğunu görmek için bkz. [Kuruluşunuzda şablon uygulamalarını yükleme, özelleştirme ve dağıtma](service-template-apps-install-distribute.md).

Uygulamanızı dağıtma işleminin ayrıntıları için bkz. [Power BI Uygulama teklifi](/azure/marketplace/partner-center-portal/create-power-bi-app-offer).