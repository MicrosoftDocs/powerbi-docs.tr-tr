---
title: Power BI mobil uygulamalarında belirli bir konumun bağlantısını oluşturma
description: Tekdüzen kaynak tanımlayıcısı (URI) kullanarak Power BI mobil uygulamasındaki belirli bir panonun, kutucuğun veya raporun ayrıntılı bağlantısını oluşturmayı öğrenin.
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 11/16/2020
ms.openlocfilehash: 8c5b3c394d54df390d690d58b56e9084f9829733
ms.sourcegitcommit: 1cad78595cca1175b82c04458803764ac36e5e37
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2021
ms.locfileid: "98565648"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında belirli bir konumun bağlantısını oluşturma
Rapor, rapor sayfası, pano, kutucuk gibi belirli bir Power BI içeriğine doğrudan erişmek için bağlantıları kullanabilirsiniz.

Power BI mobil uygulamalarındaki içeriğe erişmek amacıyla bağlantıların kullanılacağı iki temel senaryo vardır: 

* Power BI’ı **mobil uygulamanın dışından** açmak ve belirli içeriklere erişmek. Bu, genellikle Power BI mobil uygulamasını başka uygulamadan açtığınız bir tümleştirme senaryosudur. 
* Power BI’da **gezinmek** için. Bu, genellikle Power BI’da özel bir gezinti oluşturmayı hedeflediğiniz durumları ifade eder.

Bu makalede aşağıdaki durumlar ele alınmaktadır:
* Mobil uygulamanın dışındaki belirli Power BI içeriklerini açmak için bağlantıları kullanma. Bu amaçla kullanılabilen iki bağlantı biçimi vardır. Bunlardan birinde, bir yeniden yönlendirme yöntemi kullanılır ve Power BI’ın nerede açılacağından bağımsız olarak kullanılabilir. Diğeri ise doğrudan Power BI mobil uygulamasında açılır ve yalnızca mobil uygulamanın yüklü olduğu mobil cihazlarda çalışır.
* Belirli Power BI içeriklerine gitmek için Power BI’daki bağlantıları kullanma.

## <a name="use-links-from-outside-the-mobile-app"></a>Mobil uygulamanın dışındaki bağlantıları kullanma
Mobil uygulamanın dışından, Power BI’daki belirli bir öğeye yönlendiren bağlantı vermek istediğinizde, bağlantının açılacağı yere bağlı olarak iki seçeneğiniz vardır:

* Bağlantının bir bilgisayar tarayıcısında veya mobil cihazda tıklanması fark etmeksizin doğru bir şekilde açılmasını istiyorsanız, tıklandığı her yerden doğru bir şekilde açılmasını sağlayan bir bağlantı oluşturabilirsiniz. Bu bağlantı, bu akıllı davranışa olanak veren özel bir yeniden yönlendirme söz dizimine sahiptir.

* Yukarıdaki yöntem, yeniden yönlendirme işlemi için ek yük getirir. Bağlantının yalnızca Power BI mobil uygulamasının yüklü olduğu bir mobil cihazda açılacağını biliyorsanız bundan kaçınabilir ve bağlantıyı doğrudan mobil cihazdaki Power BI mobil uygulamasında açan başka bir bağlantı söz dizimi kullanabilirsiniz. Ancak, ilk yöntemdeki yeniden yönlendirme yükünden kaçınsa da bu bağlantının yalnızca Power BI mobil uygulamasının yüklü olduğu mobil cihazlarda çalışacağını unutmayın.

### <a name="create-a-link-that-works-anywhere"></a>Her yerde çalışacak bir bağlantı oluşturma
Bu bölümde bahsedilen bağlantı biçiminde, bağlantının nereden tıklandığı fark etmeksizin çalıştığından emin olmak için yeniden yönlendirme kullanılır.
* Bağlantıya bir mobil cihazda tıklandıysa cihazın bağlantıyı açmak için Power BI mobil uygulamasını kullandığından emin olur. Mobil uygulama cihazda yüklü değilse kullanıcının mağazaya gidip almasını önerir.
* Bağlantıya bir bilgisayarda tıklandıysa ilgili öğeyi Power BI web portalında açar.

Bağlantı özel ön ek ile başlamalı ve sorgu parametreleriyle devam etmelidir:

https<nolink>://app.powerbi.com/Redirect? **[QUERYPARAMETERS]** </code>

> [!IMPORTANT]
> İçeriğiniz Kamu, Çin vb. özel bir veri merkezinde barındırılıyorsa bağlantının **app.powerbigov.us** veya **app.powerbi.cn** gibi uygun Power BI adresiyle başlaması gerekir.

Sorgu parametreleri şunlardır:

|Parametre  | Değer  | Açıklama |
|---------|---------|---------|
|**action** (zorunlu)    | OpenApp<br>OpenReport<br>OpenDashboard<br>OpenTile | |
|**appId**| 36 karakterden oluşan GUID | Bir uygulamanın parçası olan raporu veya panoyu açmak istiyorsanız belirtilmelidir.<br>Örnek: **appId=baf4b16d-b5bd-4360-8a3a-51d11242c09b** |
|**groupObjectId**| 36 karakterden oluşan GUID | Çalışma Alanımın parçası olan bir raporu veya panoyu açmak istediğinizde çalışma alanını belirtir.<br>Örnek: **groupObjectId=9a3841c6-74b3-46f1-85fd-bdd78f27b30e** |
| **dashboardObjectId** | 36 karakterden oluşan GUID | Pano nesnesi kimliği (eylem OpenDashboard veya OpenTile olduğunda)<br>Örnek: **dashboardObjectId=033bb049-5b68-4392-b3ef-ae9a43738a4a** |
| **reportObjectId** | 36 karakterden oluşan GUID | Rapor nesnesi kimliği (eylem OpenReport olduğunda)<br>Örnek: **reportObjectId=6114cec7-78e1-4926-88ff-0bc5338452cf** |
| **tileObjectId** | 36 karakterden oluşan GUID | Kutucuk nesnesi kimliği (eylem OpenTile olduğunda)<br>Örnek: **tileObjectId=a845dcb8-a289-43a8-94ea-67a8c0a068f9** |
| **reportPage** | ReportSection&lt;num&gt; | Belirli bir rapor sayfasını açmak istediğinizde sayfa adı. (eylem OpenReport ise)<br>Örnek: **reportPage=ReportSection6**  |
| **bookmarkGuid** | 36 karakterden oluşan GUID | Yer işareti eklenmiş belirli bir görünümü açmak istediğinizde yer işareti kimliği. (eylem OpenReport ise)<br>Örnek: **bookmarkGuid=18e8872f-6db8-4cf8-8298-3b2ab254cc7f** |
| **ctid** | 36 karakterden oluşan GUID | Öğenin kuruluş kimliği (B2B senaryolarına yöneliktir. Öğe, kullanıcının kuruluşuna aitse bu atlanabilir)<br>Örnek: **ctid=5367c770-09d0-4110-bf6a-d760cb5ef681** . |
||||

**Örnekler:**

Aşağıdaki örneklerde, parametre değerlerinin yere tutucuları kalın biçimle vurgulanmıştır. Gerçek değerleri almak için Power BI hizmetine gidin, bağlantı oluşturmak istediğiniz öğeyi açın ve öğenin URL’sinden ihtiyaç duyduğunuz değerleri ayıklayın.

* **Uygulamayı açma**

    https<nolink>://app.powerbi.com/Redirect?action=OpenApp&appId= **&lt;appid-guid&gt;** &ctid= **&lt;ctid-guid&gt;**
   
* **Bir uygulamanın parçası olan panoyu açma**

    https<nolink>://app.powerbi.com/Redirect?action=OpenDashboard&appId= **&lt;appid-guid&gt;** &dashboardObjectId= **&lt;dashboardid-guid&gt;** &ctid= **&lt;ctid-guid&gt;**

* **Çalışma Alanım dışındaki bir çalışma alanının parçası olan raporu açma**

    https<nolink>://app.powerbi.com/Redirect?Action=OpenReport&reportObjectId= **&lt;reportid-guid&gt;** &groupObjectId= **&lt;groupobjectid-guid&gt;** &reportPage=**ReportSection&lt;num&gt;**

### <a name="how-to-get-the-correct-link-format"></a>Doğru bağlantı biçimini alma

#### <a name="links-to-apps-and-items-in-apps"></a>Uygulamaların ve uygulamalardaki öğelerin bağlantıları

**Uygulamanın kendisine ve uygulamanın parçası olan rapor ve panolara** yönlendiren bağlantıyı almanın en kolay yolu, uygulama çalışma alanına gidip **Uygulamayı güncelleştir** seçeneğini belirlemektir. Bu, “uygulamayı yayımlama” deneyimini açar. Uygulamaya ve tüm içeriğine yönlendiren bağlantıları görmek için İzinler sekmesini açıp Bağlantılar bölümünü genişletin. Uygulamaya ve içeriklerine doğrudan erişmek için bu bağlantıları Power BI’ın dışından kullanabilirsiniz.

![Power BI uygulama yayımlama bağlantıları ](./media/mobile-apps-links/mobile-link-copy-app-links.png)

#### <a name="links-to-items-that-are-not-in-an-app"></a>Uygulamada olmayan öğelerin bağlantıları 

Bir uygulamanın parçası olmayan rapor ve panolar için, öğenin URL’sinden ihtiyacınız olan nesne kimliklerini ayıklamanız gerekir. Bunu yapmak için Power BI hizmeti gidin, bağlantı oluşturmak istediğiniz öğeye gidin ve ihtiyacınız olan değerleri tarayıcının adres çubuğunda gördüğünüz URL’de arayın.

Aşağıdaki örneklerde, ihtiyaç duyduğunuz kimlikleri bağlantı oluşturmak istediğiniz öğelerin URL’lerinde nasıl bulabileceğiniz gösterilmektedir.

* 36 karakterlik bir pano nesnesi kimliği bulmak için Power BI hizmetindeki bağlantı oluşturmak istediğiniz panoya gidip aşağıda belirtilen yerlerde pano nesnesi kimliğini ve diğer gerekli kimlikleri bulun:

    https<nolink>://app.powerbi.com/groups/me/dashboards/ **&lt;dashboard-object-id&gt;** ?ctid= **&lt;org-object-id&gt;**

* 36 karakterlik rapor nesne kimliği bulmak için Power BI hizmetindeki bağlantı oluşturmak istediğiniz rapora gidin ve aşağıda gösterildiği şekilde gerekli kimlikleri bulun. Bu örneğin belirli bir rapor sayfasına ve yer işaretine başvuru içerdiğini unutmayın.

    https<nolink>://app.powerbi.com/groups/me/reports/ **&lt;report-object-id&gt;** /**ReportSection&lt;num&gt;** ?bookmarkGuid= **&lt;bookmark-id&gt;**

* Çalışma Alanım dışındaki bir çalışma alanındaki öğeye bağlantı oluşturmak için grup nesnesi kimliğini ayıklamanız gerekir. Bu örnekte, Çalışma Alanım dışındaki bir çalışma alanında yer alan rapor gösterilmektedir.

    https<nolink>://app.powerbi.com/groups/ **&lt;group-object-id&gt;** /reports/ **&lt;report-object-id&gt;** /**ReportSection&lt;report-section-num&gt;** ?ctid= **&lt;org-object-id&gt;**

### <a name="create-a-link-that-opens-only-on-a-device-that-has-the-power-bi-mobile-app-installed"></a>Yalnızca Power BI mobil uygulamasının yüklü olduğu bir cihazda açılan bağlantı oluşturma

Bu bölümde bahsedilen bağlantı biçimi, tüm mobil platformlardaki (iOS, Android cihazları ve Windows 10) Power BI mobil uygulamalarında yer alan belirli bir konuma bağlantı oluşturur. Bu bağlantı biçimi, önceki bölümde bahsedilen yöntemdeki yeniden yönlendirme işlemi olmadan doğrudan konumu açar. **Bu biçim, yalnızca Power BI mobil uygulamasının yüklü olduğu mobil cihazlarda açılabilir**.

Bu biçimdeki bağlantılar doğrudan panolara, kutucuklara ve raporlara işaret edebilir. Ayrıntılı bağlantının hedefi, biçimini belirler. Farklı konumların ayrıntılı bağlantılarını oluşturmak için aşağıdaki adımları uygulayın. 

* **Power BI mobil uygulamasını açma**

    Herhangi bir cihazda Power BI mobil uygulamasını açmak için bu bağlantıyı kullanın:

    mspbi://app/

* **Belirli bir pano ile açma**

    Bu bağlantı, Power BI mobil uygulamasını belirli bir pano ile açar:

    mspbi://app/OpenDashboard?DashboardObjectId= **<36-character-dashboard-id>**

    36 karakterden oluşan pano nesnesi kimliğini almak için Power BI hizmetinde söz konusu panoya gidin ve kimliği URL’den ayıklayın. Örneğin, pano nesnesi kimliği Power BI hizmetindeki şu URL’de vurgulanmıştır:

    https<nolink>://app.powerbi.com/groups/me/dashboards/ **&lt;61b7e871-cb98-48ed-bddc-6572c921e270&gt;**

    Pano Çalışma Alanım’da değilse pano kimliğinden önce veya sonra grup nesnesi kimliğini de eklemeniz gerekir. Aşağıda gösterilen ayrıntılı bağlantıda, pano nesnesi kimliğinden sonra eklenen grup nesnesi kimliği parametresi yer almaktadır:

    mspbi://app/OpenDashboard?DashboardObjectId=**e684af3a-9e7f-44ee-b679-b9a1c59b5d60**&GroupObjectId=**8cc900cc-7339-467f-8900-fec82d748248**</code>

    İki parametre arasındaki ve işaretine (&) dikkat edin.

* **Odak modunda belirli bir kutucukla açma**

    Bu bağlantı, Power BI mobil uygulamasını odak modunda belirli bir pano ile açar:

    mspbi://app/OpenTile?DashboardObjectId= **<36-character-dashboard-id>** &TileObjectId= **<36-character-tile-id>**

    36 karakterden oluşan pano ve kutucuk nesnesi kimliklerini bulmak için Power BI hizmetinde söz konusu panoya gidin ve kutucuğu odak modunda açın. Aşağıdaki örnekte pano ve kutucuk kimlikleri vurgulanmıştır.

    https<nolink>://app.powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus

    O halde, bu kutucuğu doğrudan açacak olan bağlantı şöyle olacaktır:

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

    İki parametre arasındaki ve işaretine (&) dikkat edin.

    Pano Çalışma Alanımda değilse GroupObjectId parametresini (ör. &GroupObjectId=<36-character-group-id>) ekleyin

* **Belirli bir rapor ile açma**

    Bu bağlantı, Power BI mobil uygulamasında belirli bir raporu açar:

    mspbi://app/OpenReport?ReportObjectId= **<36-character-report-id>**

    36 karakterden oluşan rapor nesnesi kimliğini bulmak için Power BI hizmetindeki söz konusu rapora gidin. Power BI hizmetindeki şu URL’de, ayıklamanız gereken rapor kimliği gösterilmektedir.

    https<nolink>://app.powerbi.com/groups/me/reports/**df9f0e94-31df-450b-b97f-4461a7e4d300**

    Rapor Çalışma Alanımda değilse rapor kimliğinden önce veya sonra **&GroupObjectId=<36-character-group-id>** parametresini eklemeniz gerekir. Örneğin, bu durumda ayrıntılı bağlantı şöyle olacaktır:

    mspbi://app/OpenReport?ReportObjectId=**e684af3a-9e7f-44ee-b679-b9a1c59b5d60**&GroupObjectId=**8cc900cc-7339-467f-8900-fec82d748248**

    İki parametre arasındaki ve işaretine (&) dikkat edin.

* **Belirli bir rapor sayfasını açma**

    Bu bağlantı, Power BI mobil uygulamasında belirli bir rapor sayfasını açar:

    mspbi://app/OpenReport?ReportObjectId= **<36-character-report-id>** &reportPage=**ReportSection&lt;number&gt;**

    Rapor sayfası, ardından gelecek bir sayıyla birlikte **ReportSection** olarak adlandırılır. Yine, ihtiyacınız olan değerleri bulmak için raporu Power BI hizmetinde açın, söz konusu rapor sayfasına gidin ve ihtiyaç duyduğunuz değerleri URL’den ayıklayın. Örneğin, bu URL’deki vurgulanan kısımlar, belirli bir rapor sayfasını açmak için ihtiyaç duyacağınız değerleri göstermektedir:

    https<nolink>://app.powerbi.com/groups/me/reports/**df9f0e94-31df-450b-b97f-4461a7e4d300**/**ReportSection11**</code>

* **Tam ekran modunda açma (yalnızca Windows cihazları için)**

    Windows cihazlarında, belirli bir raporu tam ekran modunda açmak için **openFullScreen** parametresini de ekleyebilirsiniz. Aşağıdaki örnek, bir rapor sayfasını tam ekran modunda açar:

    mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&**openFullScreen=true**

* **Bağlam ekleme** (isteğe bağlı)

    Ayrıca dizeye bağlam da ekleyebilirsiniz. Ardından bize ulaşmanız gerekirse uygulamanızla ilgili verilerimizi filtrelemek için bu bağlamı kullanabiliriz. Bağlam eklemek için bağlantıya **context=&lt;app-name&gt;** parametresini ekleyin:

    Örneğin, aşağıdaki örnekte bağlam parametresi içeren bir bağlantı gösterilmektedir: 

    mspbi://app/OpenReport?ReportObjectId=**e684af3a-9e7f-44ee-b679-b9a1c59b5d60**&GroupObjectId=**8cc900cc-7339-467f-8900-fec82d748248**&**context=SlackDeepLink**

## <a name="use-links-inside-power-bi"></a>Bağlantıları Power BI’ın içinden kullanma

Power BI mobil uygulamalarında, Power BI’daki bağlantılar Power BI hizmetinde çalıştıkları gibi çalışır.

Raporunuza, farklı bir Power BI öğesine işaret eden bağlantı eklemek istiyorsanız, tarayıcı adres çubuğundan bu öğenin URL’sini kopyalayabilirsiniz. [Bir rapordaki metin kutusuna köprü ekleme](../../create-reports/service-add-hyperlink-to-text-box.md) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
Geri bildiriminiz gelecekte neler yapacağımıza karar verme konusunda bize yardımcı olur, bu nedenle Power BI mobil uygulamalarında görmek istediğiniz diğer özellikleri oylamayı unutmayın. 

* [Mobil cihazlar için Power BI uygulamaları](mobile-apps-for-mobile-devices.md)
* Bizi Twitter'da takip edin: @MSPowerBI
* [Power BI Topluluğu](http://community.powerbi.com/)'nda sohbete katılın
* [Power BI nedir?](../../fundamentals/power-bi-overview.md)