---
title: "İş arkadaşlarınızla ve diğer kullanıcılarla pano paylaşma - Power BI"
description: "Power BI panolarını kuruluşunuzdaki iş arkadaşlarınızla ve kuruluş dışındaki diğer kullanıcılarla paylaşma ve bu paylaşım konusunda bilinmesi gerekenler."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: monitoring
qualitydate: 08/14/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/08/2018
ms.author: maggies
ms.openlocfilehash: d0fbe2ca891096cf8b1ae2145260c3341c451658
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="share-your-power-bi-dashboards-with-coworkers-and-others"></a>Power BI panolarınızı iş arkadaşlarınızla ve diğer kullanıcılarla paylaşma
*Paylaşım*, kullanıcıların, panolarınıza ve raporlarınıza erişmesini sağlamanın iyi bir yoludur. Power BI, [işbirliği yapmak ve panolarınızı dağıtmak](service-how-to-collaborate-distribute-dashboards-reports.md) için çeşitli yöntemler sunar ve paylaşım, bu yöntemlerden yalnızca biridir.

![Bir pano listesindeki Paylaş simgesi](media/service-share-dashboards/power-bi-share-dash.png)

Paylaşım ile içeriği ister kuruluş içindeki ister kuruluş dışındaki kişilerle paylaşıyor olun sizin ve alıcılarınızın bir [Power BI Pro lisansına](service-free-vs-pro.md) sahip olması veya içeriğin [Premium kapasitede](service-premium.md) olması gerekir. Önerileriniz mi var? Power BI ekibi geri bildirimlerinize her zaman önem verir. [Power BI Topluluğu sitesine](https://community.powerbi.com/) gitmeye ne dersiniz?

Çalışma Alanım bölümünüzden veya bir uygulama çalışma alanından pano paylaşabilirsiniz. Bir panoyu paylaştığınızda, paylaştığınız kişiler panoyu görüntüleyebilir ve panoyla etkileşim kurabilir ancak panoyu düzenleyemez. [Satır düzeyi güvenlik (RLS)](service-admin-rls.md) uygulanmadığı sürece bu kişiler, panoda ve raporlarda sizinle aynı verileri görür. Paylaşımda bulunduğunuz iş arkadaşlarınız, izin vermeniz durumunda panoyu kendi iş arkadaşlarıyla paylaşabilir. Kuruluşunuz dışındaki kişiler de panoyu görüntüleyebilir ve panoyla etkileşim kurabilir ancak panoyu paylaşamaz. 

Ayrıca, [Power BI mobil uygulamalarından da pano paylaşabilirsiniz](mobile-share-dashboard-from-the-mobile-apps.md). Panoları Power BI hizmetinden ve Power BI mobil uygulamalarından paylaşabilir ancak Power BI Desktop'tan paylaşamazsınız.

## <a name="video-share-a-dashboard"></a>Video: Bir panoyu paylaşma
Amanda'nın, panosunu şirket içindeki ve dışındaki kişilerle paylaşma videosunu izleyin. Ardından kendiniz denemek için videonun altındaki adım adım yönergeleri uygulayın.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard"></a>Bir panoyu paylaşma
1. Çalışma Alanım bölümünüzde veya bir uygulama çalışma alanınızda bir pano açıp **Paylaş**'ı ![Paylaş simgesi](media/service-share-dashboards/power-bi-share-icon.png) seçin.
2. Üstteki kutuya kişilerin, dağıtım gruplarının veya güvenlik gruplarının tam e-posta adreslerini girin. Dinamik dağıtım listeleri ile paylaşım yapamazsınız. 
   
   Adresleri kuruluşunuz dışında olan kişilerle paylaşım yapabilirsiniz ancak bu durumda bir uyarıyla karşılaşırsınız.
   
   ![Harici paylaşım uyarısı](media/service-share-dashboards/power-bi-share-dialog-warning.png)  
3. İsterseniz ileti ekleyebilirsiniz. İsteğe bağlıdır.
4. İş arkadaşlarınızın panonuzu diğer kullanıcılarla paylaşmasına izin vermek için **Alıcıların panonuzu paylaşmasına izin verin** onay kutusunu işaretleyin.
   
   Başkalarının da paylaşmasına izin verme, *yeniden paylaşım* olarak adlandırılır. İzin vermeniz halinde alıcılar, Power BI hizmetinden ve mobil uygulamalardan yeniden paylaşım yapabilir veya e-posta davetini kuruluşunuzdaki diğer çalışanlara iletebilir. Davetin süresi bir ay sonra dolar. Kuruluşunuz dışındaki kişiler yeniden paylaşım yapamaz. Panonun sahibi olarak yeniden paylaşımı devre dışı bırakabilir veya kişi temelinde iptal edebilirsiniz. Aşağıdaki, [Pano paylaşımını veya yeniden paylaşımı durdurma](service-share-dashboards.md#stop-sharing-a-dashboard-or-stop-others-from-sharing) başlıklı bölüme bakın.
5. **Paylaş**'ı seçin.
   
   ![Paylaş düğmesini seçme](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI, kişilere (gruplara değil) paylaşılan panonun bağlantısını içeren bir e-posta daveti gönderir. Ekranda **Başarılı** bildirimi görüntülenir. 
   
   Kuruluşunuzdaki alıcılar bu bağlantıya tıkladığında Power BI, ilgili panoyu bu kişilerin **Benimle paylaşılan** listesi sayfasına ekler. Söz konusu kişiler, adınızı seçerek paylaştığınız tüm panoları görebilir. 
   
   ![Benimle paylaşılan listesi sayfası](media/service-share-dashboards/power-bi-shared-with-me-list-page.png)
   
   Kuruluşunuz dışındaki alıcılar bağlantıya tıkladığında panoyu görür ancak pano, normal Power BI portalında görüntülenmez. Ayrıntılar için aşağıdaki [Bir panoyu kuruluşunuz dışındaki kişilerle paylaşma](service-share-dashboards.md#share-a-dashboard-with-people-outside-your-organization) başlığına bakın.

## <a name="who-has-access-to-a-dashboard-you-shared"></a>Paylaştığınız bir panoya kimler erişebilir?
Bazen bir panoyu kimlerle paylaştığınızı ve bu panonun kimler tarafından yeniden paylaşıldığını görmeniz gerekir.

1. Pano listesinde veya panoda bulunan **Paylaş** ![Paylaş simgesi](media/service-share-dashboards/power-bi-share-icon.png) seçeneğini belirleyin. 
2. **Panoyu paylaş** iletişim kutusunda **Erişim**'i seçin.
   
    ![Panoyu paylaş iletişim kutusu, Erişim sekmesi](media/service-share-dashboards/power-bi-share-dialog-access.png)
   
    Kuruluşunuz dışındaki kişiler **Konuk** olarak listelenir.

## <a name="stop-sharing-a-dashboard-or-stop-others-from-sharing"></a>Pano paylaşımını veya yeniden paylaşımı durdurma
Yalnızca pano sahibi, yeniden paylaşımı etkinleştirebilir veya devre dışı bırakabilir.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>Henüz paylaşım daveti göndermediyseniz
* Göndermeden önce davetin alt bölümünde bulunan **Alıcıların panonuzu paylaşmasına izin verin** onay kutusunun işaretini kaldırın.

### <a name="if-youve-already-shared-the-dashboard"></a>Panoyu zaten paylaştıysanız
1. Pano listesinde veya panoda bulunan **Paylaş** ![Paylaş simgesi](media/service-share-dashboards/power-bi-share-icon.png) seçeneğini belirleyin. 
2. **Panoyu paylaş** iletişim kutusunda **Erişim**'i seçin.
   
    ![Panoyu paylaş iletişim kutusu, Erişim sekmesi](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. **Oku ve yeniden paylaş**'ın yanındaki üç nokta simgesini (**...**) seçin ve şu seçeneği belirleyin:
   
   ![Oku ve yeniden paylaş üç nokta simgesi](media/service-share-dashboards/power-bi-change-access.png)
   
   * **Oku**, söz konusu kişinin yeniden paylaşım yapmasını engeller.
   * **Erişimi kaldır**, söz konusu kişinin panoyu hiç görmemesini sağlar.

4. **Erişimi kaldır** iletişim kutusunda, ilgili içeriğe (raporlar ve veri kümeleri gibi) erişimi kaldırmak isteyip istemediğinize karar verin. Uyarı simgesine ![Power BI uyarı simgesi](media/service-share-dashboards/power-bi-warning-icon.png) sahip bir öğeyi kaldırmanız durumunda ilgili içerik düzgün bir şekilde görüntülenmeyeceğinden bu içeriği silmenizde yarar vardır.

## <a name="share-a-dashboard-with-people-outside-your-organization"></a>Bir panoyu kuruluşunuz dışındaki kişilerle paylaşma
Kuruluşunuz dışındaki kişilerle bir paylaşımda bulunduğunuzda bu kişiler, paylaşılan panonun bağlantısını içeren bir e-posta alır ve bu kişilerden panoyu görmek için Power BI'da oturum açmaları istenir. Power BI Pro lisansları yoksa bağlantıya tıkladıktan sonra lisans almak için kaydolabilirler.

Oturum açtıktan sonra, paylaşılan panoyu normal Power BI portallarında değil, kendi tarayıcı pencerelerinde sol gezinti bölmesi olmadan görürler. Bu panoya gelecekte de erişmek için bağlantıya yer işareti eklemeleri gerekir.

Bu panoda veya raporda herhangi bir içerik düzenlemesi yapamazlar. Rapordaki grafiklerle etkileşimde bulunabilir (çapraz vurgulama) ve panoya bağlı raporlarda bulunan filtreleri/dilimleyicileri değiştirebilirler ancak bu değişiklikleri kaydedemezler.

Paylaşılan panoyu yalnızca doğrudan alıcılarınız görebilir. Örneğin, e-postayı Vicki@contoso.com adresine gönderdiyseniz panoyu yalnızca Vicki görebilir. Bağlantıya sahip olsa bile ilgili panoyu başka hiç kimse göremez ve Vicki'nin panoya erişmek için aynı e-posta adresini kullanması gerekir. Başka bir e-posta adresiyle kaydolursa Vicki de panoya erişemez.

Şirket içi Analysis Services tablolu modellerde rol veya satır düzeyi güvenlik uygulanması durumunda kuruluşunuz dışındaki kişiler hiçbir veri göremez.

Kuruluşunuz dışındaki kişilere bir Power BI mobil uygulamasından bağlantı gönderirseniz ilgili kişiler bu bağlantıya tıkladığında pano, Power BI mobil uygulaması yerine bir tarayıcıda açılır.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
Pano paylaşma ile ilgili olarak dikkat edilmesi gerekenler:

* Genel olarak iş arkadaşlarınızla panoda aynı verileri görürsünüz. Bu nedenle, iş arkadaşlarınıza kıyasla daha fazla veri görme iznine sahipseniz iş arkadaşlarınız, panonuzda sizin gördüğünüz tüm verileri görebilir. Ancak, bir panonun bağlantılı veri kümesinde [satır düzeyi güvenlik (RLS)](service-admin-rls.md) uygulanırsa kullanıcıların hangi verilere erişebileceği kimlik bilgilerine göre belirlenir.
* Paylaştığınız herkes panonuzu görebilir ve [Okuma Görünümü](service-reading-view-and-editing-view.md)'nde raporlarınızla etkileşim kurabilir. Bu kişiler rapor oluşturamaz veya mevcut raporlarda yapılan değişiklikleri kaydedemez.
* Hiç kimse veri kümesini göremez veya indiremez.
* Herkes el ile [pano verilerini yenileyebilir](refresh-data.md).
* E-posta için Office 365 hizmetini kullanıyorsanız bir dağıtım grubu ile ilişkili e-posta adresini girerek dağıtım grubu üyeleri ile paylaşımda bulunabilirsiniz.
* Sizinle aynı e-posta etki alanını kullanan iş arkadaşlarınız ve e-posta etki alanı sizinkinden farklı olan ancak aynı kiracıda kayıtlı kişiler, panoyu başka kullanıcılarla paylaşabilir. Örneğin, contoso.com ve contoso2.com etki alanlarının aynı kiracıda kayıtlı olduğunu varsayalım. E-posta adresiniz konrads@contoso.com ise paylaşım izni verdiğiniz sürece hem ravali@contoso.com hem de gustav@contoso2.com paylaşımda bulunabilir.
* İş arkadaşlarınızın belirli bir panoya zaten erişimi varsa panodayken URL'yi kopyalayarak söz konusu panoya ait doğrudan bir bağlantı gönderebilirsiniz. Örnek: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`
* Aynı şekilde, iş arkadaşlarınızın belirli bir panoya zaten erişimi varsa [bağlantılı rapora yönelik doğrudan bir bağlantı gönderebilirsiniz](service-share-reports.md). 

## <a name="troubleshoot-sharing"></a>Paylaşım sorunlarını giderme

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>Panomun alıcıları bir kutucukta kilit simgesiyle veya "İzin gerekiyor" iletisiyle karşılaşıyor

Pano paylaşımında bulunduğunuz kişiler burada kilitli bir kutucuk veya bir raporu görüntülemeye çalıştıklarında "İzin gerekiyor" iletisi görebilir.

![Power BI kilitli kutucuğu](media/service-share-dashboards/power-bi-locked_tile_small.png)

Bu durumda bu kişilere, temel alınan veri kümesine yönelik erişim izni vermeniz gerekir. Aşağıdaki adımları uygulayın:

1. İçerik listenizdeki **Veri kümeleri** sekmesine gidin.

1. Veri kümesinin yanındaki üç nokta (**...**) simgesini seçin ve ardından **İzinleri yönet** seçeneğini belirleyin.

    ![İzinleri yönet](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

3. **Kullanıcı ekle**'yi seçin.

    ![Kullanıcı ekle seçeneğini belirleme](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. Kişilerin, dağıtım gruplarının veya güvenlik gruplarının tam e-posta adreslerini girin. Dinamik dağıtım listeleri ile paylaşım yapamazsınız.

    ![E-posta adresi ekleme](media/service-share-dashboards/power-bi-add-user-dataset.png)

5. **Ekle**'yi seçin.

### <a name="i-cant-share-a-dashboard"></a>Pano paylaşamıyorum

Bir panoyu paylaşmak için, temel alınan içeriği (ilgili tüm raporlar ve veri kümeleri) yeniden paylaşma iznine sahip olmanız gerekir. Paylaşım yapamayacağınızı belirten bir iletiyle karşılaşırsanız raporun yazarından size söz konusu raporlar ve veri kümeleri için yeniden paylaşma izni vermesini isteyin.


## <a name="next-steps"></a>Sonraki adımlar
* Geri bildirimde bulunmak ister misiniz? [Power BI Topluluğu sitesine](https://community.powerbi.com/) giderek önerilerinizi belirtin.
* [Panolar ve raporlar üzerinde nasıl işbirliği yapabilir ve bunları nasıl paylaşabilirim?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Power BI raporu paylaşma](service-share-reports.md)
* Sorularınız mı var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/).

