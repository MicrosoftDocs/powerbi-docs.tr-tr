---
title: Uygulamayı Power BI'da yayımlama
description: Yerleşik gezintiyle pano ve rapor koleksiyonları olan yeni uygulamaları yayımlamayı öğrenin.
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/23/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c2e68b894c7f3e259fd2236d655d562257383433
ms.sourcegitcommit: a199dda2ab50184ce25f7c9a01e7ada382a88d2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82866576"
---
# <a name="publish-an-app-in-power-bi"></a>Uygulamayı Power BI'da yayımlama

Power BI'da resmi olarak paketlenmiş içerik oluşturabilir ve bunu geniş bir hedef kitleye *uygulama* olarak dağıtabilirsiniz. İş arkadaşlarınızla Power BI içeriği üzerinde işbirliği yapabildiğiniz bir yer olan *çalışma alanlarında* uygulama oluşturabilirsiniz. Ardından tamamlanmış uygulamaları kuruluşunuzdaki büyük kullanıcı gruplarına yayımlayabilirsiniz. 

![Power BI uygulamaları](media/service-create-distribute-apps/power-bi-new-apps.png)

İş kullanıcılarınız işlerini yürütmek için sıklıkla birden fazla Power BI panosu ve raporuna ihtiyaç duyar. Power BI uygulamalarıyla, pano ve rapor koleksiyonları oluşturabilir, bu koleksiyonları ister bütün kuruluşunuza, ister belirli kişi ve gruplara uygulama olarak yayımlayabilirsiniz. Bir rapor oluşturucusu veya yönetici olarak sizin için uygulamalar, bu koleksiyonlarda izin yönetimini kolaylaştırır.

İş kullanıcıları, uygulamalarınızı birkaç farklı yöntemle alabilir:

- Bu kişiler uygulamanızı Microsoft AppSource’tan bulup yükleyebilir.
- Onlara bir doğrudan bağlantı gönderebilirsiniz.
- Power BI yöneticiniz izin verirse, uygulamayı otomatik olarak iş arkadaşlarınızın Power BI hesaplarına yükleyebilirsiniz.
- Power BI, bir uygulamayı dağıttığınızda veya güncelleştirdiğinizde iç kullanıcılara e-posta göndermez. Bunu dış kullanıcılara dağıtırsanız bu kullanıcılar doğrudan bağlantı içeren bir e-posta iletisi alır. 

Uygulamayı kendi yerleşik gezintisiyle oluşturabilirsiniz, bu sayede kullanıcılarınız içeriğinizde yollarını kolayca bulabilirler. Uygulamanın içeriğini değiştiremezler. İster Power BI hizmetinde ister mobil uygulamalardan birinde içerikle etkileşim kurarak verileri filtreleyebilir, vurgulayabilir ve sıralayabilirler. Güncelleştirmeleri otomatik olarak alırlar ve verinin ne sıklıkla yenileneceğini denetleyebilirsiniz. Ayrıca, temel alınan veri kümelerine bağlanmak ve uygulamada raporların kopyalarını oluşturmak için onlara Oluşturma izni verebilirsiniz. [Oluşturma izni](service-datasets-build-permissions.md) hakkında daha fazla bilgi edinin.

## <a name="licenses-for-apps"></a>Uygulamalar için lisanslar
Uygulamayı oluşturmak veya güncelleştirmek için Power BI Pro lisansınız olmalıdır. Uygulama *tüketicileri* için iki seçenek sağlanır.

* **Seçenek 1** Bu uygulamanın çalışma alanı bir Power BI Premium kapasitesi içinde *değildir*: Tüm iş kullanıcılarının uygulamanızı görüntülemek için Power BI Pro lisansına ihtiyacı vardır. 
* **Seçenek 2** Bu uygulamanın çalışma alanı bir Power BI Premium kapasitesi *içindedir*: Kuruluşunuzda Power BI Pro lisansı olmayan iş kullanıcıları, uygulama içeriğini görüntüleyebilir. Ancak, raporları kopyalayamaz veya temel alınan veri kümelerine dayalı raporlar oluşturamazlar. Ayrıntılar için [Power BI Premium nedir?](service-premium.md) makalesini okuyun.

## <a name="publish-your-app"></a>Uygulamanızı yayımlama
Çalışma alanınızdaki panolar ve raporlar hazır olduğunda, hangi panoları ve raporları yayımlamak istediğinizi seçer ve ardından bunları bir uygulama olarak yayımlarsınız. 

1. Çalışma alanı liste görünümünde, hangi panoların ve raporların **uygulamaya eklenmesini** istediğinize karar verin.

    ![Yayımlamak için pano seçme](media/service-create-distribute-apps/power-bi-apps-incude-dashboard.png)

    İlgili panosu olan bir raporu eklememeyi seçerseniz raporun yanında bir uyarı görürsünüz. Yine de uygulamayı yayımlayabilirsiniz ama ilişkili panoda söz konusu raporun kutucukları bulunmayacaktır.

    ![İlişkili pano uyarısı](media/service-create-distribute-apps/power-bi-apps-report-warning.png)

2. Çalışma alanından uygulama oluşturma ve yayımlama sürecini başlatmak için sağ üstteki **Uygulamayı yayımla** düğmesini seçin.
   
    ![Uygulamayı yayımla](media/service-create-distribute-apps/power-bi-apps-publish-button.png)

3. **Kurulum** alanında kullanıcıların uygulamayı bulmasını kolaylaştıracak adı ve açıklamayı girin. Bunu özelleştirmek için bir tema rengi ayarlayabilirsiniz. Destek sitesinin bağlantısını da ekleyebilirsiniz.
   
    ![Uygulamanızı derleme](media/service-create-distribute-apps/power-bi-apps-build-your-apps.png)

4. **Gezinti** bölümünde, uygulamanın bir parçası olarak yayımlanacak içeriği seçersiniz. Ardından içeriği bölümler halinde düzenlemek için uygulama gezintisini eklersiniz. Ayrıntılar için bu makalenin [Uygulamanız için gezinti deneyimini tasarlama](#design-the-navigation-experience) bölümüne bakın.
   
    ![Uygulama gezintisi](media/service-create-distribute-apps/power-bi-apps-navigation.png)

5. **İzinler** bölümünde uygulamaya kimlerin erişebileceğine ve uygulamada neler yapabileceklerine karar verin. 

    - [Klasik çalışma alanlarında](service-create-workspaces.md): kuruluşunuzdaki herkes, belirli kişiler veya Azure Active Directory (Azure AD) güvenlik grupları.
    - [Yeni deneyimin çalışma alanlarında](service-create-the-new-workspaces.md): belirli kişiler, Azure AD güvenlik grupları ile dağıtım listeleri ve Office 365 Grupları. Tüm çalışma alanı kullanıcılarına çalışma alanı için otomatik olarak uygulamaya erişim verilir.
    - Derleme iznini vererek, uygulama kullanıcılarının uygulamanın temel veri kümelerine bağlanmasına izin verebilirsiniz. Kullanıcılar paylaşılan veri kümelerini ararken bu veri kümelerini görürler. Bu makaledeki [kullanıcıların uygulama veri kümelerine bağlanmasına izin verme](#allow-users-to-connect-to-datasets) bölümünü okuyun.
    - Derleme izni olan kullanıcılar aynı zamanda bu uygulamadan başka bir çalışma alanına rapor kopyalama iznine de sahip olabilir. Bu makaledeki [kullanıcıların uygulamadaki raporları kopyalamasına izin verme](#allow-users-to-copy-reports) bölümünü okuyun.
    
    >[!IMPORTANT]
    >Uygulamanız başka çalışma alanlarındaki veri kümelerini kullanıyorsa, tüm uygulama kullanıcılarının temel veri kümelerine erişebildiğinden emin olmak sizin sorumluluğunuzdadır.
    >

6. Power BI yöneticiniz Power BI Yönetim Portalında sizi için bu ayarı etkinleştirdiyse uygulamayı alıcılar için otomatik olarak yükleyebilirsiniz. Bu makalede [uygulamayı otomatik olarak yükleme](#automatically-install-apps-for-end-users) konusundaki diğer bilgileri okuyun.

    ![Uygulama izinleri](media/service-create-distribute-apps/power-bi-apps-permissions.png)

7. **Uygulamayı yayımlayın**'ı seçtiğinizde, uygulamanın yayımlamaya hazır olduğunu doğrulayan bir ileti göreceksiniz. **Bu uygulamayı paylaşın** iletişim kutusunda, bu uygulamanın doğrudan bağlantısı olan URL'yi kopyalayabilirsiniz.
   
    ![Uygulama sonu](media/service-create-distribute-apps/power-bi-apps-success.png)

Uygulamayı paylaştığınız kişilere bu doğrudan bağlantıyı gönderebilirsiniz veya **daha fazla uygulama indirmek ve keşfetmek üzere AppSource'taki Uygulamalar** sekmesine giderek uygulamanızı kendileri indirebilir. [İş kullanıcıları için uygulama deneyimiyle](consumer/end-user-apps.md) ilgili daha fazla bilgi edinin.

## <a name="change-your-published-app"></a>Yayımlanmış uygulamanızı değiştirme
Uygulamanızı yayımladıktan sonra değiştirmek veya güncelleştirmek isteyebilirsiniz. Yeni çalışma alanının yöneticisi veya üyesiyseniz uygulamayı güncelleştirmek kolaydır. 

1. Uygulamaya karşılık gelen çalışma alanını açın. 
   
    ![Çalışma alanını açma](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)

2. Panolarda veya raporlarda istediğiniz değişiklikleri yapın.
 
    Çalışma alanı sizin hazırlama alanınızdır. Dolayısıyla değişiklikleriniz, uygulamayı tekrar yayımlamadığınız sürece geçerlilik kazanmaz. Böylece yayımlanmış uygulamaları etkilemeden değişiklik yapabilirsiniz.  
 
    > [!IMPORTANT]
    > Bir raporu kaldırır ve uygulamayı güncelleştirirseniz, raporu uygulamaya yeniden ekleseniz bile uygulama tüketicileriniz yer işaretleri ve açıklamalar gibi tüm özelleştirmeleri kaybeder.  
 
3. Çalışma alanı içerik listesine dönün ve sağ üst köşedeki **Uygulamayı güncelleştir**'i seçin.
   
1. Gerekiyorsa **Kurulum**, **Gezinti** ve **İzinler**'i güncelleştirin, sonra da **Uygulamayı güncelleştir**'i seçin.
   
Uygulamayı yayımladığınız kişiler, otomatik olarak uygulamanın güncelleştirilmiş sürümünü görür. 

## <a name="design-the-navigation-experience"></a>Gezinti deneyimini tasarlama
**Yeni gezinti oluşturucu** seçeneği uygulamanız için özel gezinti oluşturmanıza olanak tanır. Özel gezinti kullanıcılarınızın uygulamanızdaki içeriği bulmasını ve kullanmasını kolaylaştırır. Bu seçenek mevcut uygulamalarda kapalıdır ve yeni uygulamalarda varsayılan olarak açık olur.

Seçenek kapalıyken, **Uygulama açılış sayfası** için pano veya rapor gibi **Belirli bir içerik** seçebilir veya **Yok**'u seçerek kullanıcıya içeriğin temel listesini gösterebilirsiniz.

**Yeni gezinti oluşturucu**'yu açtığınızda özel bir gezinti tasarlayabilirsiniz. Varsayılan olarak, uygulamanıza eklediğiniz tüm raporlar, panolar ve Excel çalışma kitapları düz bir listede gösterilir. 

![Uygulama gezintisi](media/service-create-distribute-apps/power-bi-apps-navigation.png)

Aşağıdakileri yaparak uygulama gezintisini daha da özelleştirebilirsiniz:

* Yukarı / Aşağı okları kullanarak öğeleri yeniden sıralama. 
* **Rapor ayrıntıları**, **Pano ayrıntıları** ve **Çalışma kitabı ayrıntıları**'ndaki öğeleri yeniden adlandırma.
* Bazı öğeleri gezintiden gizleme.
* **Yeni** seçeneğini kullanıp **bölümler** ekleyerek birbiriyle ilgili içeriği gruplandırma.
* **Yeni** seçeneğini kullanarak gezinti bölmesine bir dış kaynağın **bağlantısını** ekleme. 

**Bağlantı** eklerken **Bağlantı ayrıntıları** altında bağlantının nerede açılacağını seçebilirsiniz. Varsayılan olarak bağlantılar **Geçerli sekme**'de açılır ama **Yeni sekme**'yi veya **İçerik alanı**'nı da seçebilirsiniz. 

### <a name="considerations-for-using-the-new-navigation-builder-option"></a>Yeni gezinti oluşturucu seçeneğini kullanırken dikkat edilecek noktalar
Yeni gezinti oluşturucuyu kullanırken genel olarak aklınızda tutmanız gerekenler şunlardır:

* Rapor sayfaları uygulama gezinti alanında genişletilebilir bir bölüm olarak gösterilir. Raporun tek görünür sayfası olduğunda, yalnızca rapor adı gösterilir. Gezintide rapor adına tıklandığında raporun ilk sayfası açılır. 

    > [!NOTE]
    > Raporunuzun tek görünür sayfası olabilir çünkü kalan sayfalara düğmeler veya detaylandırma eylemleriyle gezinti ayarlamış olabilirsiniz.

* Yeni gezinti oluşturucuyu kapatır ve sonra uygulamanızı yayımlar veya güncelleştirirseniz, yaptığınız özelleştirmeleri kaybedersiniz. Örneğin bölümler, sıralama, bağlantılar ve gezinti öğeleri için özel adların tümü kaybedilir.
* Uygulama oluşturucuyu kullanmama seçeneği sağlanır.

Uygulamanızın gezintisine bağlantı eklediğinizde ve İçerik alanı seçeneğini kullandığınızda:
* Bağlantının eklenebildiğinden emin olun. Bazı hizmetler Power BI gibi üçüncü taraf sitelerine içeriğinin eklenmesini engeller.
* Raporlar ve panolar gibi Power BI hizmeti içeriğinin başka çalışma alanlarına eklenmesi desteklenmez. 
* Power BI Rapor Sunucusu içeriğini bir şirket içi dağıtımdan yerel ekleme URL'si içeriği aracılığıyla ekleyin. URL'yi almak için [Power BI Rapor Sunucusu URL'sini oluşturma](https://docs.microsoft.com/power-bi/report-server/quickstart-embed#create-the-power-bi-report-url) altında verilen adımları kullanın. Normal kimlik doğrulama kurallarının geçerli olduğunu, dolayısıyla içeriği görüntülemek için şirket içi sunucuya VPN bağlantısı gerektiğini aklınızda bulundurun. 
* Eklenen içeriğin Power BI'da olmadığını belirtmek için bu içeriğin en üstünde bir güvenlik uyarısı gösterilir.

## <a name="automatically-install-apps-for-end-users"></a>Son kullanıcılar için uygulamaları otomatik olarak yükleme
Bir yönetici size gereken izinleri verirse uygulamaları otomatik olarak yükleyebilir ve son kullanıcılara *gönderebilirsiniz*. Bu gönderme işlevselliği doğru kişilere veya gruplara doğru uygulamaları dağıtmayı kolaylaştırır. Uygulamanız son kullanıcılarınızın Uygulamalar içerik listesinde otomatik olarak görüntülenir. Uygulamayı Microsoft AppSource'tan bulmaları veya yükleme bağlantısını izlemeleri gerekmez. Power BI yönetim portalı makalesinde yöneticilerin [uygulamaları son kullanıcılara göndermeyi](service-admin-portal.md#push-apps-to-end-users) nasıl etkinleştirdiğini bulabilirsiniz.

### <a name="how-to-push-an-app-automatically-to-end-users"></a>Uygulamayı son kullanıcılara otomatik olarak gönderme
Yöneticiniz size izinleri verdikten sonra, **uygulamayı otomatik olarak yüklemek** için yeni bir seçeneğiniz olur. Kutuyu işaretlediğinizde ve **Uygulamayı yayımlayın**'ı (veya **Uygulamayı güncelleştir**'i) seçtikten sonra, uygulama **Erişim** sekmesinin **İzinler** bölümünde tanımlanan tüm kullanıcılara veya gruplara gönderilir.

![Uygulama göndermeyi etkinleştirme](media/service-create-distribute-apps//power-bi-apps-access.png)

### <a name="how-users-get-the-apps-that-you-push-to-them"></a>Kullanıcılar onlara gönderdiğiniz uygulamaları nasıl alır?
Uygulamayı göndermenizin ardından uygulama otomatik olarak onların Uygulamalar listesinde görünür. Bu şekilde kuruluşunuzdaki belirli bir kullanıcının veya iş rolünün el altında bulundurması gereken uygulamaları seçki olarak sunabilirsiniz.

![Uygulama göndermeyi etkinleştirme](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

### <a name="considerations-for-automatically-installing-apps"></a>Uygulamaları otomatik olarak yüklemeye ilişkin dikkat edilmesi gereken noktalar
Aşağıda, son kullanıcılara uygulama gönderirken göz önünde bulundurmanız gereken noktalar verilmiştir:

* Kullanıcılar için bir uygulamayı otomatik olarak yüklemek zaman alabilir. Uygulamaların çoğu kullanıcılar için hemen yüklenir ancak uygulamaları göndermek zaman alabilir.  Bu, uygulamadaki öğelerin ve erişim verilen kişilerin sayısını bağlıdır. Uygulamaları, çalışma saatleri dışında ve kullanıcılar bunlara ihtiyaç duymadan önce yeterince zaman varken göndermenizi öneririz. Uygulamaların kullanılabilirliği hakkında genel bilgilendirme göndermeden önce birkaç kullanıcı ile bunu doğrulayın.

* Tarayıcıyı yenileyin. Kullanıcının, gönderilen uygulamayı Uygulamalar listesinde görebilmek için önce tarayıcısını yenilemesi veya kapatıp yeniden açması gerekebilir.

* Kullanıcılar, uygulamayı Uygulamalar listesinde hemen görmüyorsa tarayıcılarını yenilemeli veya kapatıp yeniden açmalıdır.

* Kullanıcılara zahmet vermemeye çalışın. Kullanıcılarınızın önceden yüklenen uygulamaların onlar için kullanışlı olduğu algısına kapılmaması için çok fazla sayıda uygulama göndermemeye dikkat edin. İdeal yaklaşım, zamanlamayı koordine edebilmek açısından son kullanıcılara kimlerin uygulama gönderebileceğini denetlemektir. Kuruluşunuzda, son kullanıcılara gönderilen uygulamaları alacak bir ilgili kişi belirleyin.

* Bir daveti kabul etmeyen konuk kullanıcılar için uygulamalar otomatik olarak yüklü gelmez.  

## <a name="allow-users-to-connect-to-datasets"></a>Kullanıcıların veri kümelerine bağlanmasına izin verme

**Kullanıcıların uygulamanın temel veri kümelerine bağlanmasına izin ver** seçeneğini işaretlediğinizde, uygulama kullanıcılarına bu veri kümeleri üzerinde *Derleme izinleri* vermiş olursunuz. Bu izinle birkaç temel eylem gerçekleştirebilirler:

- Raporlarının temeli olarak [uygulama veri kümelerini kullanma](service-datasets-across-workspaces.md).
- Power BI Desktop’ta ve Power BI hizmeti içindeki veri alma deneyiminde bu veri kümelerini arayın.
- Bu veri kümelerini temel alan raporlar ve panolar oluşturun.

Bu seçeneğin işaretini kaldırdığınızda, uygulamaya eklediğiniz yeni kullanıcılar Oluşturma iznine sahip olmaz. Öte yandan, mevcut uygulama kullanıcıları için temel veri kümeleri üzerindeki izinler değişmez. Artık Oluşturma iznine sahip olmaması gereken uygulama kullanıcılarından bu izni kaldırabilirsiniz. [Oluşturma izni](service-datasets-build-permissions.md) hakkında daha fazla bilgi edinin.

## <a name="allow-users-to-copy-reports"></a>Kullanıcıların raporları kopyalamasına izin ver

**Kullanıcıların bu uygulamadaki raporların bir kopyasını oluşturmalarına izin ver** seçeneğini işaretlediğinizde, kullanıcılarınız uygulamadaki raporların herhangi birini Çalışma Alanım’a veya başka bir çalışma alanına kaydedebilir. Bir kopya oluşturmak için, özgün rapor Premium kapasitesi içindeki bir çalışma alanında olsa bile kullanıcıların bir Pro lisansına ihtiyacı vardır. Ardından raporları kendi benzersiz gereksinimlerine uygun olarak özelleştirebilirler. İlk olarak **Kullanıcıların Oluşturma iznini kullanarak uygulamanın temel veri kümelerine bağlanmasına izin ver** seçeneğini belirlemeniz gerekir. Bu seçenekleri belirleyerek, [diğer çalışma alanlarından rapor kopyalama](service-datasets-copy-reports.md) özelliğini etkinleştirmiş olursunuz.

## <a name="unpublish-an-app"></a>Bir uygulamayı yayımdan kaldırma
Bir çalışma alanının herhangi bir üyesi uygulamayı yayımdan kaldırabilir.

>[!IMPORTANT]
>Uygulamayı yayımdan kaldırdığınızda uygulama kullanıcıları özelleştirmelerini kaybederler. Uygulamadaki içerikle ilişkilendirilmiş tüm kişisel yer işaretlerini, yorumları veya abonelikleri kaybederler. Yalnızca kaldırmanız gereken uygulamaları yayımdan kaldırın.
> 

* Bir çalışma alanında sağ üst köşedeki üç nokta ( **...** ) simgesini ve **Uygulamayı yayımdan kaldır**’ı seçin.
  
    ![Uygulamayı yayımdan kaldırma](media/service-create-distribute-apps/power-bi-app-unpublish.png)

Bu eylem uygulamayı yayımladığınız herkesten uygulamayı kaldırır ve bu kullanıcılar artık uygulamaya erişemez. Bu işlem çalışma alanını veya içeriklerini silmez.

## <a name="view-your-published-app"></a>Yayımlanmış uygulamanızı görüntüleme

Uygulamanızın tüketicileri uygulamayı açtığında standart Power BI gezinti bölmesi yerine sizin oluşturduğunuz gezintiyi görür. Uygulama gezintisi sizin tanımladığınız bölümlerde raporları ve panoları listeler. Ayrıca, yalnızca rapor adını değil her rapordaki tek tek sayfaları da listeler. Menü çubuğundaki okları kullanarak sol gezintiyi genişletebilir ve daraltabilirsiniz.

![Gezintisi gösterilen uygulama](media/service-create-distribute-apps/power-bi-new-apps-navigation.png)

Tam ekran modunda köşedeki seçeneği belirterek gezintiyi gösterebilir veya gizleyebilirsiniz.

![Tam ekran gezinti](media/service-create-distribute-apps/full-screen-app-show-navigation.png)

## <a name="considerations-and-limitations"></a>Önemli Noktalar ve Sınırlamalar
Uygulama yayımlama ile ilgili olarak dikkat edilmesi gerekenler:

* İzinler sayfası, diğer çalışma alanlarındaki veri kümelerinin iznini değiştirmez. Söz konusu veri kümelerine bağımsız olarak erişim vermeniz gerektiğini anımsatan bir uyarı görürsünüz. Tüm uygulama kullanıcılarınıza veri kümelerine erişim vermenin sorun yaratmayacağından emin olmak için, uygulamanızı derlemeye başlamadan önce söz konusu veri kümelerinin sahipleriyle iletişim kurmak iyi bir yöntemdir. 
* Uygulama erişim listesinde en fazla 100 kullanıcı veya grup olabilir. Öte yandan, 100’den fazla kullanıcıya uygulama için erişim izni verebilirsiniz. Bunu yapmak için, istenen tüm kullanıcıları içeren bir veya daha fazla kullanıcı grubu kullanın.
* Yeni çalışma alanı deneyimi için, uygulama erişim listesine eklenen kullanıcının uygulamaya çalışma alanı üzerinden erişimi zaten varsa, bu kullanıcı uygulama erişim listesinde gösterilmez.  
* Power BI hizmetinde yeni görünümü kullanmak için, öğe bilgi kartında destek sitesi URL’si gösterilir. [Power BI’da 'yeni görünüm'](service-new-look.md) hakkında daha fazla bilgi edinin.
* Uygulamaların, kullanıcılara paylaşım iznini kullanarak uygulamayı ve uygulamanın temel veri kümelerini paylaşma olanağı tanıyan bir seçeneği vardır. Yeni uygulamalarda bu seçenek varsayılan olarak kapalıdır. Mevcut uygulamalarınızda bu seçeneği kapatmanızı ve temel veri kümeleri üzerindeki izni güncelleştirmenizi öneririz. Mevcut veri kümelerinde seçeneğin etkinleştirilmiş olmasının nedeni uygulamaların başlangıçta bu davranışa sahip olan içerik paketlerinin yerini alacak şekilde tasarlanmış olmasıdır.

## <a name="next-steps"></a>Sonraki adımlar
* [Çalışma alanı oluşturma](service-create-workspaces.md)
* [Power BI'da uygulamaları yükleme ve kullanma](consumer/end-user-apps.md)
* [Dış hizmetler için Power BI uygulamaları](service-connect-to-services.md)
* [Power BI Yönetici Portalı](https://docs.microsoft.com/power-bi/service-admin-portal)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)