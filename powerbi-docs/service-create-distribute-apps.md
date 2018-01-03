---
title: "Power BI'da panolar ve raporlar içeren uygulamalar oluşturma ve yayımlama"
description: "Kuruluşunuza ana ölçümler sunmayı amaçlayan pano ve rapor koleksiyonlarına sahip uygulamalar oluşturmayı ve yayımlamayı öğrenin."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/11/2017
ms.author: maggies
ms.openlocfilehash: 27ead0a3104693aff4a6fc3c2641c207ad44dc09
ms.sourcegitcommit: bb577045145b2e6e5807622a53cefa2d46574618
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="create-and-publish-apps-with-dashboards-and-reports-in-power-bi"></a>Power BI'da panolar ve raporlar içeren uygulamalar oluşturma ve yayımlama

Power BI'da, ilişkili pano ve raporları bir araya getirip kuruluşunuzda kalabalık gruplara yayımlamak için *uygulamalar* oluşturabilirsiniz. Ayrıca, Google Analytics ve Microsoft Dynamics CRM gibi [dış hizmetler için Power BI uygulamalarına](service-connect-to-services.md) da bağlanabilirsiniz.

![Power BI uygulamaları](media/service-create-distribute-apps/power-bi-apps-left-nav.png)

İş kullanıcılarınız işlerini yürütmek için sıklıkla birden fazla Power BI panosu ve raporuna ihtiyaç duyar. Uygulamalar bu parçaları bir araya getirir. Böylece tüm bu panoların adını ve konumunu hatırlamalarına gerek kalmaz.  

Şimdi önizlemede olan Power BI uygulamalarıyla, pano ve rapor koleksiyonları oluşturabilir, bu uygulamaları ister bütün kuruluşunuza, ister belirli kişi ve gruplara yayımlayabilirsiniz. Bir rapor oluşturucusu veya yönetici olarak sizin için uygulamalar, pano koleksiyonlarında izin yönetimini kolaylaştırır.

İşletme kullanıcıları bu uygulamaları Microsoft AppSource'tan yükleyebilir veya onlara doğrudan bağlantı gönderebilirsiniz. Hepsi tek bir yerde olduğu için içeriğinizi kolayca bulabilir ve içeriğinize geri dönebilirler. Güncelleştirmeleri otomatik olarak alırlar ve verinin ne sıklıkla yenileneceğini denetleyebilirsiniz. [İş kullanıcıları için uygulama deneyimiyle](service-install-use-apps.md) ilgili daha fazla bilgi edinin.

### <a name="apps-and-organizational-content-packs"></a>Uygulamalar ve kurumsal içerik paketleri
Uygulamalar, kurumsal içerik paketlerinin gelişmiş halidir. Zaten kurumsal içerik paketleriniz varsa bu paketler, uygulamalarla yan yana çalışmaya devam ederler.

Uygulamalara genel bakış yaptığımıza göre, uygulamaları oluşturduğumuz yer olan *uygulama çalışma alanlarından* bahsedelim. 

## <a name="video-apps-and-app-workspaces"></a>Video: Uygulamalar ve uygulama çalışma alanları
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="licenses-for-apps"></a>Uygulamalar için lisanslar
Bir uygulama oluşturucusu olarak Power BI Pro lisansına ihtiyacınız vardır. Uygulama kullanıcılarınız için iki seçenek vardır.

* 1. Seçenek: Tüm iş kullanıcılarının uygulamanızı görüntülemek için **Power BI Pro** lisansına ihtiyacı vardır. 
* 2. Seçenek: Kuruluşunuzdaki ücretsiz sürüm kullanıcıları, uygulamanız Power BI Premium kapasitesinde yer alıyorsa uygulama içeriğini görüntüleyebilir. Ayrıntılar için [Power BI Premium nedir?](service-premium.md) makalesini okuyun.

## <a name="app-workspaces"></a>Uygulama çalışma alanları
*Uygulama çalışma alanları*, uygulamaları oluşturduğunuz yerdir, diğer bir deyişle, bir uygulama oluşturmadan önce uygulama çalışma alanı oluşturmanız gerekir. Daha önce Power BI'da bir grup çalışma alanında çalıştıysanız uygulama çalışma alanları size tanıdık gelecektir. Bunlar grup çalışma alanlarının gelişmiş halidir. Uygulama içeriği için hazırlama alanları ve kapsayıcılardır. 

Bu çalışma alanlarına iş arkadaşlarınızı üye veya yönetici olarak ekleyebilirsiniz. Uygulama çalışma alanlarının tüm üyelerine ve yöneticilerine Power BI Pro lisansları gerekir. Çalışma alanında hep birlikte panolar, raporlar ve daha geniş bir kitleye, hatta tüm kuruluşunuza dağıtmayı planladığınız diğer makaleler üzerinde işbirliği yapabilirsiniz. 

İçerik hazır olduğunda, uygulamayı yayımlarsınız. İstediğiniz geniş kitleye doğrudan bağlantı gönderebilirsiniz veya uygulamanızı, **daha fazla uygulama indirmek ve keşfetmek üzere AppSource'taki Uygulamalar** sekmesine giderek kendileri indirebilir. Diğer kişiler uygulamanın içeriğini değiştiremez ancak ister Power BI hizmetinde ister mobil uygulamalardan birinde içerikle etkileşim kurarak verileri filtreleyebilir, vurgulayabilir ve sıralayabilir. 

### <a name="how-are-app-workspaces-different-from-group-workspaces"></a>Uygulama çalışma alanlarının grup çalışma alanlarından farkı nedir?
Var olan tüm grup çalışma alanları uygulama çalışma alanı işlevi görebilir ve bu çalışma alanlarının herhangi birinden uygulama yayımlayabilirsiniz. Uygulama çalışma alanları ve grup çalışma alanlarının bir farkı şudur: Uygulama çalışma alanları, belirli bir uygulamayı oluşturmak ve barındırmak için oluşturulur. Uygulama çalışma alanı içeriği ve uygulama arasında bire bir ilişki vardır. Uygulama çalışma alanındaki her şey, uygulamayı yayımladığınızda uygulamada olacaktır. 

Artık uygulamaları ve uygulama çalışma alanlarını anladığınıza göre, bir uygulama oluşturmaya ve yayımlamaya başlayalım. 

## <a name="create-an-app-workspace"></a>Bir uygulama çalışma alanı oluşturma
[!INCLUDE [powerbi-service-create-app-workspace](./includes/powerbi-service-create-app-workspace.md)]

Şu anda boş. Bu nedenle şimdi içerik ekleyeceğiz. Çalışma alanını ilk oluşturduğunuzda, Office 365'e yayılması için yaklaşık bir saat beklemeniz gerekebileceğini unutmayın. 

İçerik eklemek tıpkı Çalışma Alanım bölümünüze içerik eklemeye benzer ancak çalışma alanındaki diğer kişiler de bu içeriği görüp onunla çalışabilir. İçeriği tamamladığınızda bir uygulama olarak yayımlayabilecek olmanız büyük bir farktır. Uygulama çalışma alanındayken, tıpkı Çalışma Alanım bölümünüzde olduğu gibi dosyaları karşıya yükleyebilir veya dosyalara ya da aynı şekilde üçüncü taraf hizmetlere de bağlanabilirsiniz. Örneğin:

* Microsoft Dynamics CRM, Salesforce veya Google Analytics gibi [hizmetlere bağlanın](service-connect-to-services.md).
* Excel, CSV veya Power BI Desktop (PBIX) gibi [dosyalardan veri alın](service-get-data-from-files.md).

## <a name="add-an-image-to-your-app-optional"></a>Uygulamanıza bir görüntü ekleme (isteğe bağlı)
Varsayılan olarak Power BI, uygulamanız için uygulamanın baş harflerini içeren küçük ve renkli bir daire oluşturur. Ancak, bunu bir görüntüyle özelleştirmek isteyebilirsiniz. Bir görüntü eklemek için Exchange Online lisansı gerekir.

1. **Çalışma Alanı**'nı ve ardından çalışma alanı adının yanındaki üç nokta (...) simgesiyle **Üyeler**'i seçin. 
   
     ![Çalışma Alanı Üyelerini seçme](media/service-create-distribute-apps/power-bi-apps-workspace-members.png)
   
    Çalışma alanı için Office 365 Outlook hesabı yeni bir tarayıcı penceresinde açılır.
2. Sol üstteki renkli dairenin üzerine gelirseniz daire bir kalem simgesine dönüşür. Kalem simgesini seçin.
   
     ![Office 365 kalem simgesi](media/service-create-distribute-apps/power-bi-apps-workspace-edit-image.png)
3. Kalem simgesini yeniden seçin ve kullanmak istediğiniz görüntüyü bulun.
   
     ![Kalemi yeniden seçin](media/service-create-distribute-apps/power-bi-apps-workspace-edit-group.png)
4. **Kaydet**'i seçin.
   
     ![Kaydet'i seçme](media/service-create-distribute-apps/power-bi-apps-workspace-save-image.png)
   
    Görüntü, Office 365 Outlook penceresindeki renkli dairenin yerine geçer. 
   
     ![Özelleştirilmiş görüntü](media/service-create-distribute-apps/power-bi-apps-workspace-image-in-office-365.png)
   
    Birkaç dakika sonra Power BI'daki uygulamada da görünecektir.
   
     ![Özelleştirilmiş görüntü](media/service-create-distribute-apps/power-bi-apps-image.png)

## <a name="publish-your-app"></a>Uygulamanızı yayımlama
Uygulama çalışma alanınızdaki panolar ve raporlar hazır olduğunda, bunları bir uygulama olarak yayımlayabilirsiniz. Unutmayın, çalışma alanındaki tüm raporları ve panoları yayımlamanıza gerek yoktur. Yalnızca hazır olanları yayımlamanız yeterlidir. 

1. Çalışma alanı liste görünümünde, hangi panoları ve raporları uygulamaya eklemek istediğinize karar verin.

     ![Yayımlamak için pano seçme](media/service-create-distribute-apps/power-bi-apps-incude-dashboard.png)

     Bir raporu yayımlamamaya karar verirseniz raporun ve ilişkili panonun yanında bir uyarı görürsünüz. Yine de uygulamayı yayımlayabilirsiniz ancak ilişkili panoda söz konusu raporun kutucukları eksik olacaktır.

     ![İlişkili pano uyarısı](media/service-create-distribute-apps/power-bi-apps-report-warning.png)

1. Sağ üstteki **Uygulamayı yayımla** düğmesini seçtiğinizde tüm içeriğin söz konusu çalışma alanında paylaşılma süreci başlar.
   
     ![Uygulama yayımlama](media/service-create-distribute-apps/power-bi-apps-publish-button.png)

2. İlk olarak, **Ayrıntılar**'da kullanıcıların uygulamayı bulmasını kolaylaştıracak bir açıklama girin. Bunu özelleştirmek için bir arka plan rengi ayarlayabilirsiniz.
   
     ![Uygulama ayrıntıları](media/service-create-distribute-apps/power-bi-apps-details.png)

3. Sonra, **İçerik**'te uygulamanın parçası olarak yayımlanacak içeriği, diğer bir deyişle söz konusu çalışma alanında seçtiğiniz her şeyi görebilirsiniz. Ayrıca, uygulama giriş sayfasını, başka bir deyişle kullanıcıların uygulamanıza girdiğinde göreceği ilk pano veya raporu da ayarlayabilirsiniz. **Hiçbiri**'ni seçebilirsiniz. Bu durumda giriş sayfası uygulamadaki bütün içeriklerin bir listesi olacaktır. 
   
     ![Uygulama içeriği](media/service-create-distribute-apps/power-bi-apps-content.png)

4. Son olarak, **Erişim** bölümünde uygulamaya kimin erişebileceğine (kuruluşunuzdaki herkes, belirli kişiler veya Active Directory güvenlik grupları) karar verin. 

5. **Son**'u seçtiğinizde, uygulamanın yayımlamaya hazır olduğunu doğrulayan bir ileti göreceksiniz. Başarılı iletişim kutusundaki URL'yi kopyalayabilirsiniz. Bu, uygulamaya doğrudan bir bağlantıdır ve bunu uygulamayı paylaştığınız kişilere gönderebilirsiniz.
   
     ![Uygulama sonu](media/service-create-distribute-apps/power-bi-apps-success.png)

Uygulamayı yayımladığınız işletme kullanıcıları, söz konusu uygulamayı iki farklı yolla bulabilir. Uygulamanın doğrudan bağlantısını gönderebilirsiniz veya kullanıcılar, erişimleri olan her uygulamayı görebildiği Microsoft AppSource'ta uygulamayı arayabilir. Daha sonra Uygulamalar'a her gittiklerinde, bu uygulamayı listelerinde görürler.

[İş kullanıcıları için uygulama deneyimiyle](service-install-use-apps.md) ilgili daha fazla bilgi edinin.

## <a name="change-your-published-app"></a>Yayımlanmış uygulamanızı değiştirme
Uygulamanızı yayımladıktan sonra değiştirmek veya güncelleştirmek isteyebilirsiniz. Uygulama çalışma alanının yöneticisi veya üyesiyseniz uygulamayı güncelleştirmek kolaydır. 

1. Uygulamaya karşılık gelen uygulama çalışma alanını açın. 
   
     ![Çalışma alanını açma](media/service-create-distribute-apps/power-bi-apps-open-workspace.png)
2. Raporu veya panoyu açın. İstediğiniz değişikliği yapabileceğinizi göreceksiniz.
   
     Uygulama çalışma alanı sizin hazırlama alanınızdır. Değişiklikleriniz, uygulamayı tekrar yayımlamadığınız sürece uygulamada kullanıma alınmaz. Böylece yayımlanmış uygulamaları etkilemeden değişiklik yapabilirsiniz.  
 
1. Uygulama çalışma alanı içerik listesine geri dönün ve **Uygulamayı güncelleştir**'i seçin.
   
     ![Uygulamayı güncelleştir düğmesi](media/service-create-distribute-apps/power-bi-app-update-button.png)
4. Gerektiği durumda **Ayrıntılar**, **İçerik** ve **Erişim**'i güncelleştirin, daha sonra **Uygulamayı güncelleştir**'i seçin.
   
     ![Uygulamayı güncelleştir düğmesi](media/service-create-distribute-apps/power-bi-app-update-complete.png)

Uygulamayı yayımladığınız kişiler, otomatik olarak uygulamanın güncelleştirilmiş sürümünü görür. 

## <a name="unpublish-an-app"></a>Bir uygulamayı yayımdan kaldırma
Uygulama çalışma alanının herhangi bir üyesi uygulamayı yayımdan kaldırabilir.

* Bir uygulama çalışma alanında sağ üst köşedeki üç nokta (**...**) simgesini ve **Uygulamayı yayımdan kaldır**ı seçin.
  
     ![Uygulamayı yayımdan kaldırma](media/service-create-distribute-apps/power-bi-app-unpublish.png)

Bu eylem uygulamayı yayımladığınız herkesten uygulamayı kaldırır ve bu kullanıcılar artık uygulamaya erişemez. Uygulama çalışma alanı veya içerikleri silinmez.

## <a name="power-bi-apps-faq"></a>Power BI uygulamaları hakkında SSS
### <a name="how-are-app-workspaces-different-from-group-workspaces"></a>Uygulama çalışma alanlarının grup çalışma alanlarından farkı nedir?
Bu sürümde, tüm grup çalışma alanlarını uygulama çalışma alanları olarak yeniden adlandırdık. Bu çalışma alanlarının herhangi birinden uygulama yayımlayabilirsiniz. İşlevsellik, çoğunlukla grup çalışma alanlarıyla aynı düzeyde sabit kalmıştır. Önümüzdeki birkaç ay içinde uygulama çalışma alanlarını aşağıdaki gibi iyileştirmeyi planlıyoruz: 

* Uygulama çalışma alanları oluşturmak, grup çalışma alanlarının yaptığı gibi Office 365'te kendilerine karşılık gelen varlıklar oluşturmaz. Bu nedenle, arka planda farklı Office 365 gruplarının oluşturulmasından endişe duymaksızın istediğiniz sayıda uygulama çalışma alanı oluşturabilirsiniz (dosyalarınızı depolamak için hâlâ bir Office 365 grubunun OneDrive İş'ini kullanabilirsiniz). 
* Şu anda üyeler ve yöneticiler listesine sadece bireyleri ekleyebilirsiniz. Yakın zamanda yönetimin kolaylaşması için bu listelere birden çok AD güvenlik grubu ya da modern grup ekleyebileceksiniz.  

### <a name="how-are-apps-different-from-organizational-content-packs"></a>Uygulamalarla kurumsal içerik paketlerinin farkı nedir?
Uygulamalar, içerik paketlerinin evrim geçirmiş, basitleşmiş ve birkaç önemli farklılığı olan halleridir. 

* İş kullanıcıları bir içerik paketi yükledikten sonra paket, gruplandırılmış kimliğini kaybeder: Başka panolar ve raporlara karışmış bir pano ve rapor listesinden ibaret olur. Buna karşın uygulamalar, gruplandırılmış halleri ve kimliklerini yüklemeden sonra bile korur. Böylece iş kullanıcıları zaman geçtikten sonra bile uygulamalara kolayca gidebilir.  
* Herhangi bir çalışma alanında birden çok içerik paketi oluşturabilirsiniz ancak bir uygulamanın çalışma alanıyla bire bir ilişkisi vardır. Böylece uygulamaların anlaşılmasının ve korunmasının uzun vadede kolaylaştığına inanıyoruz. Bu alanı nasıl iyileştirmeyi planladığımızla ilgili daha çok bilgi için Power BI blogunun "roadmap" (yol haritası) bölümüne başvurun. 
* Zaman içinde kurumsal içerik paketlerini kullanımdan kaldırmayı planlıyoruz. Bu nedenle bundan sonra uygulama oluşturmanızı öneririz.  

### <a name="what-about-read-only-members-in-groups"></a>Gruplardaki salt okunur kullanıcılara ne olacak?
Gruplara, içeriği yalnızca görüntüleyebilen salt okunur kullanıcılar ekleyebilirsiniz. Bu yaklaşımdaki ana problem, güvenlik gruplarının üye olarak eklenememesiydi. Uygulamalarda ise, uygulama çalışma alanınızın salt okunur bir sürümünü güvenlik grupları dahil olmak üzere geniş kitlelere yayımlayabilirsiniz. Uygulamanın içindeki panolarda ve raporlarda yapacağınız değişiklikleri, son kullanıcıyı etkilemeden hazırlayabilirsiniz. Gelecekte uygulamaları bu şekilde kullanmanızı öneriyoruz. Uzun vadede, çalışma alanlarının salt okunur kullanıcılarını da kullanımdan kaldırmayı planlıyoruz.  

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da uygulamaları yükleme ve kullanma](service-install-use-apps.md)
* [Dış hizmetler için Power BI uygulamaları](service-connect-to-services.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

