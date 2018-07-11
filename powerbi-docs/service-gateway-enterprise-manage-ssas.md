---
title: Veri kaynağınızı yönetme - Analysis Services
description: Şirket içi veri ağ geçidini ve bu ağ geçidine ait veri kaynaklarını yönetme. Bu hem Çok Boyutlu hem de Tablolu moddaki Analysis Services'e yöneliktir.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: a4c931b671840ca78f340005c30aeb92454ca2a6
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37599193"
---
# <a name="manage-your-data-source---analysis-services"></a>Veri kaynağınızı yönetme - Analysis Services
Şirket içi veri ağ geçidini yükledikten sonra, ilgili ağ geçidi ile kullanılabilecek veri kaynaklarını eklemeniz gerekir. Bu makalede, ağ geçitleriyle ve veri kaynaklarıyla nasıl çalışıldığı anlatılmaktadır. Analysis Services veri kaynağını zamanlanmış yenileme veya canlı bağlantılar için kullanabilirsiniz.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ownIGbcRAAU" frameborder="0" allowfullscreen></iframe>

## <a name="download-and-install-the-gateway"></a>Ağ geçidini indirme ve yükleme
Ağ geçidini Power BI hizmetinden indirebilirsiniz. **İndir** > **Data Gateway** seçeneğini belirleyin veya [ağ geçidi indirme sayfasına](https://go.microsoft.com/fwlink/?LinkId=698861) gidin.

![](media/service-gateway-enterprise-manage-ssas/powerbi-download-data-gateway.png)

## <a name="limitations-of-analysis-services-live-connections"></a>Analysis Services canlı bağlantılarına ilişkin sınırlamalar
Tablolu veya çok boyutlu örnekler için canlı bağlantı kullanabilirsiniz.

| **Sunucu sürümü** | **Gerekli SKU** |
| --- | --- |
| 2012 SP1 CU4 veya sonraki sürümler |İş Zekası ve Enterprise SKU'su |
| 2014 |İş Zekası ve Enterprise SKU'su |
| 2016 |Standart SKU veya sonraki sürümler |

* Hücre düzeyinde Biçimlendirme ve çeviri özellikleri desteklenmez.
* Eylemler ve Adlandırılmış Kümeler Power BI için açık değildir ancak Eylemleri veya Adlandırılmış kümeleri de içeren çok boyutlu küplere yine de bağlanabilir, görseller ve raporlar oluşturabilirsiniz.

## <a name="add-a-gateway"></a>Ağ geçidi ekleme
Bir ağ geçidi eklemek için ortamınızdaki bir sunucudan ağ geçidini [indirip](https://go.microsoft.com/fwlink/?LinkId=698861) yüklemeniz yeterlidir. Ağ geçidi, yüklendikten sonra **Ağ geçitlerini yönet** seçeneği altındaki ağ geçidi listelerinde görünür.

> [!NOTE]
> **Ağ geçitlerini yönet** seçeneği en az bir ağ geçidinin yöneticisi olduğunuzda görüntülenir. Bunun için bir yönetici olarak eklenmeniz veya bir ağ geçidi yükleyip yapılandırmanız gerekir.
> 
> 

## <a name="remove-a-gateway"></a>Ağ geçitlerini kaldırma
Bir ağ geçidini kaldırmak, söz konusu ağ geçidi altındaki tüm veri kaynaklarının da silinmesine neden olur.  Ayrıca bu işlem, ilgili veri kaynaklarını kullanan panoların ve raporların da çalışmamasına yol açar.

1. Sağ üst köşedeki dişli simgesi ![](media/service-gateway-enterprise-manage-ssas/pbi_gearicon.png) > **Ağ geçitlerini yönet**'i seçin.
2. Ağ geçidi > **Kaldır**'ı seçin

   ![](media/service-gateway-enterprise-manage-ssas/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Veri kaynağı ekleme
Bir ağ geçidi seçip **Veri kaynağı ekle**'ye tıklayarak veya Ağ geçidi > **Veri kaynağı ekle** bölümüne giderek veri kaynağı ekleyebilirsiniz.

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings1.png)

Böylece **Veri Kaynağı Türü**'nü listeden seçebilirsiniz. Çok Boyutlu veya Tablolu bir sunucuya bağlanıyorsanız Analysis Services'i seçin.

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings2-ssas.png)

Ardından **Sunucu**'yu ve **Veritabanı**'nı içeren veri kaynağına ilişkin bilgileri doldurmanız gerekir.  

Girdiğiniz **Kullanıcı Adı** ve **Parola** Analysis Services örneğine bağlanmak için ağ geçidi tarafından kullanılır.

> [!NOTE]
> Girdiğiniz Windows hesabının bağlantı kurduğunuz örneğe ilişkin Sunucu Yöneticisi izinlerine sahip olması gerekir. Bu hesabın parolası, süresi dolacak şekilde ayarlanmışsa kullanıcılar, parolanın veri kaynağı için güncelleştirilmemesi durumunda bağlantı hatası alabilir. [Kimlik bilgilerinin](service-gateway-onprem.md#credentials) nasıl depolandığı ile ilgili daha fazla bilgi için, şirket içi veri ağ geçidi konusunun ele alındığı ana makaleye başvurun.
> 
> 

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings3-ssas.png)

Tüm bilgileri doldurduktan sonra **Ekle**'ye tıklayabilirsiniz.  Şirket içi bir Analysis Services örneğine yönelik olarak, zamanlanmış yenileme veya canlı bağlantılar için bu veri kaynağını kullanabilirsiniz.  İşlem başarılı olursa *Bağlantı Başarılı* iletisi görürsünüz.

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings4.png)

### <a name="advanced-settings"></a>Gelişmiş ayarlar
Veri kaynağınızın gizlilik düzeyini yapılandırabilirsiniz. Bu işlem, verilerin nasıl bir araya getirilebileceğini denetler. Bu işlem yalnızca zamanlanmış yenileme için kullanılır. Canlı bağlantılar için geçerli değildir. [Daha fazla bilgi](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings9.png)

## <a name="usernames-with-analysis-services"></a>Analysis Services'de kullanıcı adları
Bir kullanıcının Analysis Services'e bağlı bir raporla kurduğu her etkileşimde etkin kullanıcı adı, ağ geçidine ve ardından şirket içi Analysis Services sunucunuza geçirilir. Etkin kullanıcı olarak Analysis Services'e, Power BI'da oturum açmak için kullandığınız e-posta adresini geçiririz. Bu, [EffectiveUserName](https://msdn.microsoft.com/library/dn140245.aspx#bkmk_auth) bağlantı özelliğine geçirilir. Bu e-posta adresi, yerel Active Directory Etki Alanı'nda tanımlı bir UPN ile eşleşmelidir. UPN, Active Directory hesabının bir özelliğidir. Daha sonra bu Windows hesabının, bir Analysis Services rolünde mevcut olması gerekir. Active Directory'de eşleşme bulunamazsa oturum açma işlemi başarılı olmaz. [Daha fazla bilgi](https://msdn.microsoft.com/library/ms677605.aspx)

Ayrıca, Power BI oturum açma adınızı yerel dizin UPN'si ile eşleyebilirsiniz. [Daha fazla bilgi](service-gateway-enterprise-manage-ssas.md#map-user-names)

<iframe width="560" height="315" src="https://www.youtube.com/embed/Qb5EEjkHoLg" frameborder="0" allowfullscreen></iframe>

### <a name="how-do-i-tell-what-my-upn-is"></a>UPN'min ne olduğunu nasıl anlarım?
UPN'nizin ne olduğunu bilmeyebilir ve bir etki alanı yöneticisi olmayabilirsiniz. Hesabınızın UPN'sini bulmak için iş istasyonunuzdan aşağıdaki komutu çalıştırabilirsiniz.

    whoami /upn

Sonuç, e-posta adresi gibi görünür ancak bu, etki alanı hesabınızdaki UPN'dir. Canlı bağlantılar için Analysis Services veri kaynağı kullanıyorsanız ve bu, Power BI'da oturum açmak için kullandığınız e-posta adresiyle eşleşmiyorsa [Kullanıcı adlarını eşlemeyi](#map-user-names) öğrenmek isteyebilirsiniz.

## <a name="map-user-names"></a>Kullanıcı adlarını eşleme
<iframe width="560" height="315" src="https://www.youtube.com/embed/eATPS-c7YRU" frameborder="0" allowfullscreen></iframe>

Analysis Services için kullanıcı adlarını iki farklı şekilde eşleyebilirsiniz:

1. El ile kullanıcı yeniden eşleme 
2. AAD UPN'lerini Active Directory kullanıcıları ile yeniden eşlemeye (AD Arama eşlemesi) yönelik şirket içi Active Directory Özellik Arama

İkinci yaklaşım kullanılarak el ile eşleme gerçekleştirilebiliyor olsa da bunu yapmak zaman alıcı ve sürdürülmesi zor olabilir; desen eşleşmesi yeterli olmadığında (örneğin, etki alanı adları AAD ile şirket içi AD arasında farklı olduğunda veya kullanıcı hesabı adları AAD ve AD arasında farklı olduğunda) bu, özellikle zor bir işlemdir. Bu nedenle, ikinci yaklaşım kullanılarak el ile eşleme önerilmez.

Bu iki yaklaşımı sırasıyla aşağıdaki iki bölümde açıklayacağız

### <a name="manual-user-name-re-mapping"></a>El ile kullanıcı adı yeniden eşlemesi
Analysis Services veri kaynakları için özel Kullanıcı Asıl Adı (UPN) kuralları yapılandırabilirsiniz. Power BI hizmeti oturum açma adlarınızın yerel dizin UPN'nizle eşleşmemesi durumunda bu işlem yardımcı olur. Örneğin, Power BI'da john@contoso.com ile oturum açtığınızda ancak yerel dizin UPN'niz john@contoso.local olduğunda john@contoso.local adresinin Analysis Services'e geçirilmesini sağlayacak bir eşleme kuralı yapılandırabilirsiniz.

UPN Eşleme ekranına gitmek için aşağıdakileri yapın.

1. **Dişli simgesine** gidip **Ağ Geçitlerini Yönet** seçeneğini belirleyin.
2. Analysis Services veri kaynağını içeren ağ geçidini genişletin. Alternatif olarak, Analysis Services veri kaynağını oluşturmadıysanız bu işlemi bu noktada gerçekleştirebilirsiniz.
3. Veri kaynağını seçin ve ardından **Kullanıcılar** sekmesini seçin.
4. **Kullanıcı adlarını eşle** seçeneğini belirleyin.

    ![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_02.png)

Ardından, kural eklemenin yanı sıra belirli bir kullanıcı için test gerçekleştirmeye yönelik seçenekler görürsünüz.

> [!NOTE]
> Bir kullanıcıyı yanlışlıkla değiştirebilirsiniz. Örneğin, **Değiştir (Özgün ad)** değeriniz <em>@contoso.com</em>, **Şununla (Yeni ad)** değeriniz de <em>@contoso.local</em> ise <em>@contoso.com</em> içeren oturum açma bilgilerine sahip tüm kullanıcılar <em>@contoso.local</em> ile değiştirilir. Ayrıca **Değiştir (Özgün ad)** değeriniz <em>dave@contoso.com</em>, **Şununla (Yeni ad)** değeriniz de <em>dave@contoso.local</em> ise v-dave@contoso.com oturum açma bilgisine sahip bir kullanıcı v-dave<em>@contoso.local</em> olarak gönderilir.

### <a name="ad-lookup-mapping"></a>AD arama eşlemesi
AAD UPN'lerini Active Directory kullanıcılarıyla yeniden eşlemek için şirket içi AD özellik arama işlemi gerçekleştirmek üzere bu bölümdeki adımları uygulayın. Başlangıç olarak bunun nasıl çalıştığını gözden geçirelim.

**Power BI hizmetinde** aşağıdakiler gerçekleşir:

- Bir Power BI AAD kullanıcısı tarafından şirket içi SSAS sunucusuna yapılan her sorgu için şunun gibi bir UPN dizesi geçirilir:      firstName.lastName@contoso.com

> [!NOTE]
> Power BI veri kaynağı yapılandırmasında tanımlanmış tüm el ile UPN kullanıcı eşlemeleri yine de kullanıcı adı dizesi Şirket içi veri ağ geçidine gönderilmeden *önce* uygulanır.
> 
> 

Yapılandırılabilir Özel Kullanıcı Eşlemesi’ne sahip Şirket içi veri ağ geçidinde aşağıdaki işlemleri gerçekleştirin:

1. Aramak için Active Directory'yi bulun (otomatik veya yapılandırılabilir)
2. **Power BI hizmetinden** gelen UPN dizesine ("firstName.lastName@contoso.com") bağlı olarak AD Kullanıcısının özniteliğini (*E-posta* gibi) arayın.
3. AD Arama başarısız olursa SSAS'ye EffectiveUser olarak geçirilen UPN'yi kullanmayı dener.
4. AD Arama başarılı olursa söz konusu AD Kullanıcısı'na ilişkin *UserPrincipalName* e-postasını alır. 
5. *UserPrincipalName* e-postasını SSAS'ye <em>Alias@corp.on-prem.contoso</em> gibi *EffectiveUser* olarak geçirir

AD Arama gerçekleştirmek için ağ geçidinizi yapılandırma:

1. En yeni ağ geçidini indirme ve yükleme
2. Ağ geçidinde **Şirket içi veri ağ geçidi hizmetini** yerel hizmet hesabı yerine bir etki alanı hesabıyla çalışacak şekilde değiştirmeniz gerekir (Aksi halde AD arama, çalışma zamanında düzgün şekilde çalışmaz). Değişikliğin geçerli olması için ağ geçidi hizmetini yeniden başlatmanız gerekir.  Makinenizde ağ geçidi uygulamasına gidin. ("On-premises data gateway" (Şirket içi veri ağ geçidi) araması yapın). Bunu yapmak için **Service settings > Change service account** (Hizmet ayarları > Hizmet hesabını değiştir) seçeneğine gidin. Yeni bir ağ geçidi oluşturmak istemiyorsanız bu ağ geçidini aynı makinede geri yüklemeniz gerekeceğinden ağ geçidine ilişkin kurtarma anahtarını bildiğinizden emin olun. 
3. Yazma izinlerine sahip olduğunuzdan emin olmak ve şu dosyayı düzenlemek için ağ geçidinin yüklendiği klasöre (*C:\Program Files\On-premises data gateway*) yönetici olarak gidin:

       Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config 
4. AD kullanıcılarınıza ilişkin Active Directory özniteliği *yapılandırmalarınıza* göre aşağıdaki iki yapılandırma değerini düzenleyin. Aşağıda gösterilen yapılandırma değerleri yalnızca örnek amaçlıdır, Active Directory yapılandırmanıza göre değer belirtmeniz gerekir. 

   ![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_03.png)
5. Yapılandırma değişikliğinin geçerli olması için **Şirket içi veri ağ geçidi** hizmetini yeniden başlatın.

### <a name="working-with-mapping-rules"></a>Eşleme kuralları ile çalışma
Eşleme kuralı oluşturmak için **Özgün ad** ve **Yeni Ad** değerlerini belirtmeniz ve ardından **Ekle** seçeneğini belirlemeniz gerekir.

| Alan | Açıklama |
| --- | --- |
| Değiştir (Özgün ad) |Power BI'da oturum açmak için kullandığınız e-posta adresi. |
| Şununla (Yeni Ad) |Özgün adın yerini almasını istediğiniz değer. Değiştirme işleminin sonucu Analysis Services bağlantısı için *EffectiveUserName* özelliğine geçirilecek değerdir. |

![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-effective-user-names.png)

Listede bir öğe seçtiğinizde **köşeli çift ayraç simgelerini** veya giriş için **Sil** seçeneğini kullanarak öğeyi yeniden sıralamayı tercih edebilirsiniz.

![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-entry-selected.png)

### <a name="using-wildcard-"></a>Joker karakter (\*) kullanma
**Değiştir (Özgün ad)** dizeniz için joker karakter kullanabilirsiniz. Joker karakter yalnızca tek başına kullanılabilir, diğer herhangi bir dize bölümüyle kullanılamaz. Bu, tüm kullanıcılarınızı alıp veri kaynağına tek bir değer geçirmenize olanak tanır. Bu, kuruluşunuzdaki tüm kullanıcıların yerel ortamınızda aynı kullanıcı adını kullanmasını istediğinizde fayda sağlar.

### <a name="test-a-mapping-rule"></a>Bir eşleme kuralını test etme
**Özgün ad** için değer girip **Kuralı test et** seçeneğini belirleyerek özgün adın ne ile değiştirileceğini doğrulayabilirsiniz.

![](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-test-mapping-rule.png)

> [!NOTE]
> Hizmetin, kaydedilen kuralları kullanmaya başlaması birkaç dakika sürer. Kural, tarayıcının içinden hemen çalışır.
> 
> 

### <a name="limitations-for-mapping-rules"></a>Eşleme kurallarına ilişkin sınırlamalar
* Eşleme, yapılandırılmakta olan belirli bir veri kaynağına yönelik olarak gerçekleştirilir. Genel bir ayar değildir. Birden çok Analysis Services veri kaynağınız varsa kullanıcıları her veri kaynağına yönelik olarak eşlemeniz gerekir.

## <a name="remove-a-data-source"></a>Veri kaynaklarını kaldırma
Bir veri kaynağını kaldırmak, ilgili veri kaynağını kullanan panoların ve raporların tümünü bozar.  

Bir veri kaynağını kaldırmak için, Veri Kaynağı > **Kaldır** seçeneğine gidin.

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings6.png)

## <a name="manage-administrators"></a>Yöneticileri yönetme
Ağ geçidine ilişkin Yöneticiler sekmesinde, ağ geçidini yönetebilen kullanıcılar (veya güvenlik grupları) ekleyebilir ve kaldırabilirsiniz.

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings8.png)

## <a name="manage-users"></a>Kullanıcıları yönetme
Veri kaynakları için, Kullanıcılar sekmesinde ilgili veri kaynağını kullanabilen kullanıcılar veya güvenlik grupları ekleyebilir ve kaldırabilirsiniz.

> [!NOTE]
> Kullanıcılar listesi yalnızca kimlerin rapor yayımlayabildiğini denetler. Rapor sahipleri panolar veya içerik paketleri oluşturabilir ve bunları diğer kullanıcılarla paylaşabilir.
> 
> 

![](media/service-gateway-enterprise-manage-ssas/datasourcesettings5.png)

## <a name="using-the-data-source"></a>Veri kaynağını kullanma
Veri kaynağı, oluşturulduktan sonra canlı bağlantılarla veya zamanlanmış yenileme yoluyla kullanılabilir.

> [!NOTE]
> Şirket içi veri ağ geçidinde bulunan veri kaynağındaki ve Power BI Desktop’taki sunucu ve veritabanı adı eşleşmelidir!
> 
> 

Ağ geçidindeki veri kaynağı ve veri kümeniz arasındaki bağlantı, sunucu ve veritabanı adınızı temel alır. Bunlar eşleşmelidir. Örneğin, Power BI Desktop'ta sunucu adı için bir IP Adresi sağlarsanız bu IP Adresini ağ geçidi yapılandırmasındaki veri kaynağında da kullanmanız gerekir. Power BI Desktop'ta *SUNUCU\ÖRNEK* yapılandırmasını kullanırsanız ağ geçidi için yapılandırılan veri kaynağında da aynısını kullanmanız gerekir.

Bu durum hem canlı bağlantılar hem de zamanlanmış yenileme için geçerlidir.

### <a name="using-the-data-source-with-live-connections"></a>Veri kaynağını canlı bağlantılarla kullanma
Sunucu ve veritabanı adının Power BI Desktop'ta ve ağ geçidinin yapılandırılmış veri kaynağında eşleştiğinden emin olmanız gerekir. Ayrıca, canlı bağlantı veri kümeleri yayımlamak için veri kaynağının **Kullanıcılar** sekmesinde kullanıcınızın listelendiğinden emin olmanız gerekir. Canlı bağlantılara yönelik seçim, verileri ilk kez içeri aktardığınızda Power BI Desktop içinde gerçekleşir.

Power BI Desktop'tan veya **Veri Al** seçeneğini kullanarak yayımladığınız raporlarınızla hemen çalışmaya başlayabilirsiniz. Ağ geçidinde veri kaynağı oluşturulduktan sonra bağlantının kullanılabilir hale gelmesi için birkaç dakika beklemeniz gerekebilir.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Zamanlanmış yenileme ile veri kaynağını kullanma
Ağ geçidinde yapılandırılan veri kaynağının **Kullanıcılar** sekmesinde listeleniyorsanız ve sunucu ile veritabanı adı eşleşiyorsa ağ geçidini zamanlanmış yenileme ile kullanılabilen bir seçenek olarak görürsünüz.

![](media/service-gateway-enterprise-manage-ssas/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidi](service-gateway-onprem.md)  
[Şirket içi veri ağ geçidi (ayrıntılı)](service-gateway-onprem-indepth.md)  
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

