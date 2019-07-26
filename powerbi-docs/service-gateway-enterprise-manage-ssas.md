---
title: Veri kaynağınızı yönetme - Analysis Services
description: Şirket içi veri ağ geçidini ve bu ağ geçidine ait veri kaynaklarını yönetme. Bu hem Çok Boyutlu hem de Tablolu moddaki Analysis Services'e yöneliktir.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 93475f6476f8baad73229473bd3ce60db68a320b
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271628"
---
# <a name="manage-your-data-source---analysis-services"></a>Veri kaynağınızı yönetme - Analysis Services

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

[Şirket içi veri ağ geçidini yükledikten](/data-integration/gateway/service-gateway-install) sonra, ilgili ağ geçidi ile kullanılabilecek [veri kaynaklarını](service-gateway-data-sources.md#add-a-data-source) eklemeniz gerekir. Bu makalede, zamanlanmış yenileme veya canlı bağlantılar için kullanılan ağ geçitleri ve Analysis Services veri kaynaklarıyla nasıl çalışılacağı açıklanır.

Analysis Services'e canlı bağlantı ayarlama hakkında daha fazla bilgi edinmek için [bu videoyu izleyin](https://www.youtube.com/watch?v=GPf0YS-Xbyo&feature=youtu.be).

> [!NOTE]
> Bir Analysis Services veri kaynağınız varsa ağ geçidini, Analysis Services sunucunuz ile aynı ormana/etki alanına katılmış bir bilgisayara yüklemeniz gerekir.

## <a name="add-a-data-source"></a>Veri kaynağı ekleme

Veri kaynağı ekleme hakkında bilgi edinmek için bkz. [Veri kaynağı ekleme](service-gateway-data-sources.md#add-a-data-source). Çok Boyutlu veya Tablolu bir sunucuya bağlanıyorsanız **Veri Kaynağı Türü** olarak Analysis Services'i seçin.

![Analysis Services veri kaynağını ekleme](media/service-gateway-enterprise-manage-ssas/datasourcesettings2-ssas.png)

Ardından **Sunucu**'yu ve **Veritabanı**'nı içeren veri kaynağına ilişkin bilgileri doldurmanız gerekir. Girdiğiniz **Kullanıcı Adı** ve **Parola** Analysis Services örneğine bağlanmak için ağ geçidi tarafından kullanılır.

> [!NOTE]
> Girdiğiniz Windows hesabının bağlantı kurduğunuz örneğe ilişkin Sunucu Yöneticisi izinlerine sahip olması gerekir. Bu hesabın parolası, süresi dolacak şekilde ayarlanmışsa kullanıcılar, parolanın veri kaynağı için güncelleştirilmemesi durumunda bağlantı hatası alabilir. Kimlik bilgilerinin nasıl depolandığı hakkında daha fazla bilgi almak için bkz. [Şifrelenmiş kimlik bilgilerini bulutta depolama](service-gateway-data-sources.md#storing-encrypted-credentials-in-the-cloud).

![Veri kaynağı ayarlarını doldurma](media/service-gateway-enterprise-manage-ssas/datasourcesettings3-ssas.png)

Tüm bilgileri doldurduktan sonra **Ekle**'yi seçin. Şirket içi bir Analysis Services örneğine yönelik olarak, zamanlanmış yenileme veya canlı bağlantılar için bu veri kaynağını kullanabilirsiniz. İşlem başarılı olduğunda *Bağlantı Başarılı* iletisini göreceksiniz.

![Bağlantı durumunu görüntüleme](media/service-gateway-enterprise-manage-ssas/datasourcesettings4.png)

### <a name="advanced-settings"></a>Gelişmiş ayarlar

İsteğe bağlı olarak, veri kaynağınızın gizlilik düzeyini yapılandırabilirsiniz. Bu işlem verilerin nasıl birleştirilebileceğini denetler. Bu işlem yalnızca zamanlanmış yenileme için kullanılır. Canlı bağlantılar için geçerli değildir. Veri kaynağınıza ilişkin gizlilik düzeyleri hakkında daha fazla bilgi edinmek için bkz. [Gizlilik düzeyleri (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Gizlilik düzeyini ayarlama](media/service-gateway-enterprise-manage-ssas/datasourcesettings9.png)

## <a name="usernames-with-analysis-services"></a>Analysis Services'de kullanıcı adları

<iframe width="560" height="315" src="https://www.youtube.com/embed/Qb5EEjkHoLg" frameborder="0" allowfullscreen></iframe>

Bir kullanıcının Analysis Services'e bağlı bir raporla kurduğu her etkileşimde etkin kullanıcı adı, ağ geçidine ve ardından şirket içi Analysis Services sunucunuza geçirilir. Etkin kullanıcı olarak Analysis Services'e, Power BI'da oturum açmak için kullandığınız e-posta adresini geçiririz. Bu, [EffectiveUserName](https://msdn.microsoft.com/library/dn140245.aspx#bkmk_auth) bağlantı özelliğine geçirilir. Bu e-posta adresinin, yerel Active Directory etki alanında tanımlı bir kullanıcı asıl adı (UPN) ile eşleşmesi gerekir. UPN, Active Directory hesabının bir özelliğidir. Daha sonra bu Windows hesabının, bir Analysis Services rolünde mevcut olması gerekir. Active Directory'de eşleşme bulunamazsa oturum açma işlemi başarılı olmaz. Active Directory ve kullanıcı adlandırması hakkında daha fazla bilgi edinmek için bkz. [Kullanıcı Adlandırma Öznitelikleri](https://msdn.microsoft.com/library/ms677605.aspx).

Ayrıca [Power BI oturum açma adınızı yerel dizin UPN'si ile eşleyebilirsiniz](service-gateway-enterprise-manage-ssas.md#mapping-usernames-for-analysis-services-data-sources).

## <a name="mapping-usernames-for-analysis-services-data-sources"></a>Analysis Services veri kaynakları için kullanıcı adlarını eşleme

<iframe width="560" height="315" src="https://www.youtube.com/embed/eATPS-c7YRU" frameborder="0" allowfullscreen></iframe>

Power BI, Analytics Services veri kaynakları için kullanıcı adı eşlemesine olanak sağlar. Power BI'da oturum açmak için kullanılan bir kullanıcı adını, Analysis Services bağlantısında EffectiveUserName için geçirilen adla eşlemeye yönelik kurallar yapılandırabilirsiniz. Kullanıcı adlarını eşleme özelliği, AAD'deki kullanıcı adınız yerel Active Directory etki alanınızdaki bir UPN ile eşleşmediğinde bu sorunu çözmenin etkili bir yoludur. Örneğin, e-posta adresiniz nancy@contoso.onmicrsoft.com ise bunu nancy@contoso.com ile eşleyebilirsiniz ve elde edilen değer, ağ geçidine geçirilir.

Analysis Services için kullanıcı adlarını iki farklı şekilde eşleyebilirsiniz:

* El ile kullanıcı yeniden eşleme
* AAD UPN'lerini Active Directory kullanıcıları ile yeniden eşlemeye (AD Arama eşlemesi) yönelik şirket içi Active Directory Özellik Arama

İkinci yaklaşımı kullanarak el ile eşleme yapmak mümkün olsa da, bunu yapmak zaman alıcı olabilir ve bakımını yapmak zordur. Özellikle desen eşlemesi yetersiz kaldığında, örneğin etki alanı adları AAD ile şirket içi AD arasında farklı olduğunda veya kullanıcı hesabı adları AAD ile AD arasında farklı olduğunda zor olabilir. Bu nedenle, ikinci yaklaşım kullanılarak el ile eşleme önerilmez.

Bu iki yaklaşımı sırasıyla aşağıdaki iki bölümde açıklayacağız.

### <a name="manual-user-name-re-mapping"></a>El ile kullanıcı adı yeniden eşlemesi

Analysis Services veri kaynakları için özel Kullanıcı Asıl Adı (UPN) kuralları yapılandırabilirsiniz. Power BI hizmeti oturum açma adlarınızın yerel dizin UPN'nizle eşleşmemesi durumunda bu işlem yardımcı olur. Örneğin, Power BI'da john@contoso.com ile oturum açtığınızda ancak yerel dizin UPN'niz john@contoso.local olduğunda john@contoso.local adresinin Analysis Services'e geçirilmesini sağlayacak bir eşleme kuralı yapılandırabilirsiniz.

UPN Eşleme ekranına gitmek için aşağıdakileri yapın.

1. **Dişli simgesine** gidip **Ağ Geçitlerini Yönet** seçeneğini belirleyin.
2. Analysis Services veri kaynağını içeren ağ geçidini genişletin. Alternatif olarak, Analysis Services veri kaynağını oluşturmadıysanız bu işlemi bu noktada gerçekleştirebilirsiniz.
3. Veri kaynağını seçin ve ardından **Kullanıcılar** sekmesini seçin.
4. **Kullanıcı adlarını eşle** seçeneğini belirleyin.

    ![UPN eşleme ekranı](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_02.png)

Ardından, kural eklemenin yanı sıra belirli bir kullanıcı için test gerçekleştirmeye yönelik seçenekler görürsünüz.

> [!NOTE]
> Bir kullanıcıyı yanlışlıkla değiştirebilirsiniz. Örneğin, **Değiştir (Özgün ad)** değeriniz <em>@contoso.com</em>, **Şununla (Yeni ad)** değeriniz de <em>@contoso.local</em> ise <em>@contoso.com</em> içeren oturum açma bilgilerine sahip tüm kullanıcılar <em>@contoso.local</em> ile değiştirilir. Ayrıca **Değiştir (Özgün ad)** değeriniz <em>dave@contoso.com</em>, **Şununla (Yeni ad)** değeriniz de <em>dave@contoso.local</em> ise v-dave@contoso.com oturum açma bilgisine sahip bir kullanıcı v-dave<em>@contoso.local</em> olarak gönderilir.

### <a name="ad-lookup-mapping"></a>AD arama eşlemesi

AAD UPN'lerini Active Directory kullanıcılarıyla yeniden eşlemek için şirket içi AD özellik arama işlemi gerçekleştirmek üzere bu bölümdeki adımları uygulayın. Başlangıç olarak bunun nasıl çalıştığını gözden geçirelim.

**Power BI hizmetinde** aşağıdakiler gerçekleşir:

* Bir Power BI AAD kullanıcısı tarafından şirket içi SSAS sunucusuna yapılan her sorgu için şunun gibi bir UPN dizesi geçirilir:      firstName.lastName@contoso.com

> [!NOTE]
> Power BI veri kaynağı yapılandırmasında tanımlanmış tüm el ile UPN kullanıcı eşlemeleri yine de kullanıcı adı dizesi şirket içi veri ağ geçidine gönderilmeden *önce* uygulanır.

Yapılandırılabilir Özel Kullanıcı Eşlemesi'ne sahip şirket içi veri ağ geçidinde aşağıdaki işlemleri gerçekleştirin:

1. Aranacak Active Directory'yi bulun (otomatik veya yapılandırılabilir).
2. **Power BI hizmetinden** gelen UPN dizesine ("firstName.lastName@contoso.com") bağlı olarak AD Kullanıcısının özniteliğini (*E-posta* gibi) arayın.
3. AD Arama başarısız olursa SSAS'ye EffectiveUser olarak geçirilen UPN'yi kullanmayı dener.
4. AD Arama başarılı olursa söz konusu AD Kullanıcısı'na ilişkin *UserPrincipalName* e-postasını alır.
5. *UserPrincipalName* e-postasını SSAS'ye <em>Alias@corp.on-prem.contoso</em> gibi *EffectiveUser* olarak geçirir.

AD Araması yapmak üzere ağ geçidinizi yapılandırmak için:

1. [En yeni ağ geçidini indirin ve yükleyin](/data-integration/gateway/service-gateway-install).

2. Ağ geçidinde **şirket içi veri ağ geçidi hizmetini** yerel hizmet hesabı yerine bir etki alanı hesabıyla çalışacak şekilde değiştirmeniz gerekir. (Aksi halde AD arama, çalışma zamanında düzgün şekilde çalışmaz.) Makinenizde [şirket içi veri ağ geçidi uygulamasına](/data-integration/gateway/service-gateway-app) ve sonra da **Hizmet ayarları > Hizmet hesabını değiştir**'e gidin. Yeni bir ağ geçidi oluşturmak istemiyorsanız bu ağ geçidini aynı makinede geri yüklemeniz gerekeceğinden ağ geçidine ilişkin kurtarma anahtarını bildiğinizden emin olun. Değişikliğin geçerli olması için ağ geçidi hizmetini yeniden başlatmanız gerekir.

3. Yazma izinlerine sahip olduğunuzdan emin olmak ve şu dosyayı düzenlemek için ağ geçidinin yüklendiği klasöre (*C:\Program Files\On-premises data gateway*) yönetici olarak gidin ve *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* dosyasını açın.

4. AD kullanıcılarınıza ilişkin Active Directory özniteliği *yapılandırmalarınıza* göre aşağıdaki iki yapılandırma değerini düzenleyin. Aşağıda gösterilen yapılandırma değerleri yalnızca örnek amaçlıdır, Active Directory yapılandırmanıza göre değer belirtmeniz gerekir. Bu yapılandırmalar büyük/küçük harfe duyarlıdır, bu nedenle Active Directory'deki değerlerle eşleştiğinden emin olun.

    ![Azure Active Directory ayarları](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names_03.png)

    ADServerPath yapılandırması için değer verilmemişse, ağ geçidi varsayılan Genel Kataloğu kullanır. Ayrıca, ADServerPath için birden çok değer belirtebilirsiniz. Her değer, aşağıdaki örnekte gösterildiği gibi noktalı virgülle ayrılmalıdır.

    ```xml
    <setting name="ADServerPath" serializeAs="String">
        <value> >GC://serverpath1; GC://serverpath2;GC://serverpath3</value>
    </setting>
    ```

    Ağ geçidi, ADServerPath değerlerini bir eşleşme bulana kadar soldan sağa ayrıştırır. Eşleşme bulunmazsa özgün UPN kullanılır. Ağ geçidi hizmetini (PBIEgwService) çalıştıran hesabın, ADServerPath’te belirttiğiniz tüm AD sunucularına yönelik sorgu izinlerine sahip olduğundan emin olun.

    Ağ geçidi, aşağıdaki örneklerde gösterildiği üzere, iki tür ADServerPath'ı destekler.

    **WinNT**

    ```xml
    <value="WinNT://usa.domain.corp.contoso.com,computer"/>
    ```

    **GC**

    ```xml
    <value> GC://USA.domain.com </value>
    ```

5. Yapılandırma değişikliğinin geçerli olması için **şirket içi veri ağ geçidini** yeniden başlatın.

### <a name="working-with-mapping-rules"></a>Eşleme kuralları ile çalışma

Eşleme kuralı oluşturmak için **Özgün ad** ve **Yeni Ad** değerlerini belirtmeniz ve ardından **Ekle** seçeneğini belirlemeniz gerekir.

| Alan | Açıklama |
| --- | --- |
| Değiştir (Özgün ad) |Power BI'da oturum açmak için kullandığınız e-posta adresi. |
| Şununla (Yeni Ad) |Özgün adın yerini almasını istediğiniz değer. Değiştirme işleminin sonucu Analysis Services bağlantısı için *EffectiveUserName* özelliğine geçirilecek değerdir. |

![Eşleme kuralı oluşturma](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-effective-user-names.png)

Listede bir öğe seçtiğinizde **köşeli çift ayraç simgelerini** veya giriş için **Sil** seçeneğini kullanarak öğeyi yeniden sıralamayı tercih edebilirsiniz.

![Listede bir öğenin sırasını değiştirme](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-map-user-names-entry-selected.png)

### <a name="using-wildcard-"></a>Joker karakter (\*) kullanma

**Değiştir (Özgün ad)** dizeniz için joker karakter kullanabilirsiniz. Joker karakter yalnızca tek başına kullanılabilir, diğer herhangi bir dize bölümüyle kullanılamaz. Bu, tüm kullanıcılarınızı alıp veri kaynağına tek bir değer geçirmenize olanak tanır. Bu, kuruluşunuzdaki tüm kullanıcıların yerel ortamınızda aynı kullanıcı adını kullanmasını istediğinizde fayda sağlar.

### <a name="test-a-mapping-rule"></a>Bir eşleme kuralını test etme

**Özgün ad** için değer girip **Kuralı test et** seçeneğini belirleyerek özgün adın ne ile değiştirileceğini doğrulayabilirsiniz.

![Eşleme kuralını test etme](media/service-gateway-enterprise-manage-ssas/gateway-enterprise-test-mapping-rule.png)

> [!NOTE]
> Kurallar kaydedildikten sonra hizmetin bunları kullanmaya başlaması birkaç dakika sürer. Kural, tarayıcının içinden hemen çalışır.

### <a name="limitations-for-mapping-rules"></a>Eşleme kurallarına ilişkin sınırlamalar

Eşleme, yapılandırılmakta olan belirli bir veri kaynağına yönelik olarak gerçekleştirilir. Bu genel bir ayar değildir. Birden çok Analysis Services veri kaynağınız varsa kullanıcıları her veri kaynağına yönelik olarak eşlemeniz gerekir.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Canlı bir Analysis Services veri kaynağına yönelik kimlik doğrulaması

Bir kullanıcı Analysis Services ile her etkileşim kurduğunda, etkin kullanıcı adı ağ geçidi üzerinden şirket içi Analysis Services sunucunuza iletilir. Kullanıcı asıl adı (UPN; genel olarak, bulutta oturum açmak için kullandığınız e-posta adresi) etkin kullanıcı olarak Analysis Services'e geçireceğimiz addır. UPN, EffectiveUserName bağlantı özelliği ile geçirilir. Bu e-posta adresinin, yerel Active Directory etki alanında tanımlı bir UPN ile eşleşmesi gerekir. UPN, bir Active Directory hesabı özelliğidir. Daha sonra ilgili Windows hesabının, sunucu erişimi kazanmak için bir Analysis Services rolünde olması gerekir. Active Directory'de eşleşme bulunmazsa oturum açma işlemi başarısız olur.

Ayrıca, Analysis Services bu hesaba dayalı filtreleme olanağı sağlayabilir. Fitreleme, rol tabanlı güvenlik veya satır düzeyi güvenlik ile gerçekleşebilir.

## <a name="role-based-security"></a>Rol tabanlı güvenlik

Modeller, kullanıcı rollerine göre güvenlik sağlar. Roller, belirli bir model projesi için SQL Server Veri Araçları - Business Intelligence'ta (SSDT-BI) yazma sırasında veya model dağıtıldıktan sonra SQL Server Management Studio (SSMS) kullanılarak tanımlanır. Roller, Windows kullanıcı adı veya Windows grubuna göre üyeler içerir. Roller, bir kullanıcının modelde sorgulama yapma veya eylem gerçekleştirme izinlerini tanımlar. Çoğu kullanıcı, Okuma izinlerine sahip bir role aittir. Diğer roller; öğeleri işleme, veritabanı işlevlerini yönetme ve diğer rolleri yönetme izinlerine sahip yöneticilere yöneliktir.

## <a name="row-level-security"></a>Satır düzeyi güvenlik

Satır düzeyi güvenlik, Analysis Services satır düzeyi güvenliğine özgüdür. Modeller dinamik, satır düzeyi güvenlik sağlayabilir. Kullanıcıların ait olduğu en az bir rol bulunan durumların aksine dinamik güvenlik, herhangi bir tablolu model için gerekli değildir. Üst düzeyde ele alındığında dinamik güvenlik, kullanıcıların bir tablodaki belirli bir satıra ilişkin verilere yönelik okuma erişimini tanımlar. Rollere benzer şekilde dinamik satır düzeyi güvenlik, kullanıcıların Windows kullanıcı adlarını kullanır.

Kullanıcının model verileri için sorgulama ve görüntüleme gerçekleştirip gerçekleştiremeyeceği, ilk olarak Windows kullanıcı hesabının üyesi olduğu rollere; ikinci olarak ise dinamik satır düzeyi güvenliğe (yapılandırılmışsa) bağlıdır.

Modellerde rol ve dinamik satır düzeyi güvenlik uygulaması, bu makalede ele alınmamıştır. MSDN'deki [Roles (SSAS Tabular) (Roller (SSAS Tablosu))](https://msdn.microsoft.com/library/hh213165.aspx) ve [Security Roles (Analysis Services - Multidimensional Data) (Güvenlik Rolleri (Analysis Services - Çok Boyutlu Veriler))](https://msdn.microsoft.com/library/ms174840.aspx) sayfalarını inceleyerek daha fazla bilgi edinebilirsiniz. Tablolu model güvenliğini en ayrıntılı şekilde kavramak için [Securing the Tabular BI Semantic Model (Tablolu BI Anlam Modelinin Güvenliğini Sağlama) teknik incelemesini](https://msdn.microsoft.com/library/jj127437.aspx) indirin ve okuyun.

## <a name="what-about-azure-active-directory"></a>Azure Active Directory hakkında

Microsoft bulut hizmetleri, kullanıcıların kimliklerini doğrulamak için [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)'yi kullanır. Azure Active Directory, kullanıcı adlarının ve güvenlik gruplarının bulunduğu kiracıdır. Genellikle, kullanıcının oturum açmak için kullandığı e-posta adresi hesabın UPN'si ile aynıdır.

Yerel Active Directory etki alanımın rolü nedir?

Analysis Services'in, buraya bağlanan bir kullanıcının veri okuma izinlerine sahip bir role ait olup olmadığını belirlemesi için sunucunun, AAD'den ağ geçidine ve daha sonra Analysis Services sunucusuna geçirilen etkin kullanıcı adını dönüştürmesi gerekir. Analysis Services sunucusu, etkin kullanıcı adını bir Windows Active Directory etki alanı denetleyicisine (DC) geçirir. Ardından Active Directory etki alanı denetleyicisi, yerel bir hesapta etkin kullanıcı adının geçerli bir UPN olduğunu doğrular ve ilgili kullanıcının Windows kullanıcı adını Analysis Services sunucusuna döndürür.

EffectiveUserName, etki alanına katılmamış bir Analysis Services sunucusunda kullanılamaz. Herhangi bir oturum açma hatası ile karşılaşılmaması için Analysis Services sunucusunun, bir etki alanına katılmış olması gerekir.

### <a name="how-do-i-tell-what-my-upn-is"></a>UPN'mi nasıl bulabilirim?

UPN'nizin ne olduğunu bilmeyebilir ve bir etki alanı yöneticisi olmayabilirsiniz. Hesabınızın UPN'sini bulmak için iş istasyonunuzda aşağıdaki komutu çalıştırabilirsiniz.

    whoami /upn

Sonuç e-posta adresi gibi görünür ancak bu, etki alanı hesabınızdaki UPN'dir. Canlı bağlantılar için Analysis Services veri kaynağı kullanıyorsanız ve bu Power BI'da oturum açmak için kullandığınız e-posta adresiyle eşleşmiyorsa [kullanıcı adlarını eşlemeyi](#mapping-usernames-for-analysis-services-data-sources) öğrenmek isteyebilirsiniz.

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Bir şirket içi Active Directory hesabını Azure Active Directory ile eşitleme

Analysis Services canlı bağlantılarını kullanacaksanız yerel Active Directory hesaplarınızın Azure Active Directory ile eşleşmesi gerekir. Bunun nedeni, UPN'nin hesaplar arasında eşleşmek zorunda olmasıdır.

Bulut hizmetleri yalnızca Azure Active Directory'deki hesapları tanır. Yerel Active Directory etki alanınıza bir hesap ekleseniz de bu hesap AAD'de mevcut değilse kullanılamaz. Yerel Active Directory hesaplarınızı Azure Active Directory ile eşlemeye yönelik farklı yöntemler bulunmaktadır.

1. Hesapları Azure Active Directory'ye el ile ekleyebilirsiniz.

   Azure portalı veya Microsoft 365 yönetim merkezinde bir hesap oluşturabilirsiniz. Böylece hesap adı, yerel Active Directory hesabının UPN’si ile eşleşir.

2. Yerel hesapları Azure Active Directory kiracınız ile eşitlemek için [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-sync-whatis) aracını kullanabilirsiniz.

   Azure AD Connect aracı, parola karma eşitlemesi, geçişli kimlik doğrulama ve federasyon gibi dizin eşitleme ve kimlik doğrulaması ayarlamaya yönelik seçenekler sağlar. Bir kiracı yöneticisi veya yerel etki alanı yöneticisi değilseniz bu yapılandırmayı gerçekleştirmesi için BT yöneticinizle iletişime geçmeniz gerekir.

Azure AD Connect, UPN'nin AAD ile yerel Active Directory etki alanınız arasında eşleşmesini sağlar.

> [!NOTE]
> Hesapların Azure AD Connect aracı ile eşitlenmesi, AAD kiracınızda yeni hesaplar oluşturur.

## <a name="using-the-data-source"></a>Veri kaynağını kullanma

Veri kaynağı, oluşturulduktan sonra canlı bağlantılarla veya zamanlanmış yenileme yoluyla kullanılabilir.

> [!NOTE]
> Şirket içi veri ağ geçidinde bulunan veri kaynağındaki ve Power BI Desktop’taki sunucu ve veritabanı adı eşleşmelidir.

Ağ geçidindeki veri kaynağı ve veri kümeniz arasındaki bağlantı, sunucu ve veritabanı adınızı temel alır. Bunlar eşleşmelidir. Örneğin, Power BI Desktop'ta sunucu adı için bir IP Adresi sağlarsanız ağ geçidi yapılandırmasındaki veri kaynağında da bu IP Adresini kullanmanız gerekir. Power BI Desktop'ta *SUNUCU\ÖRNEK* yapılandırmasını kullanırsanız ağ geçidi için yapılandırılan veri kaynağında da aynısını kullanmanız gerekir.

Bu durum hem canlı bağlantılar hem de zamanlanmış yenileme için geçerlidir.

### <a name="using-the-data-source-with-live-connections"></a>Veri kaynağını canlı bağlantılarla kullanma

Sunucu ve veritabanı adının, Power BI Desktop'ta ve ağ geçidinin yapılandırılmış veri kaynağında eşleştiğinden emin olmanız gerekir. Ayrıca, canlı bağlantı veri kümelerini yayımlamak için veri kaynağının **Kullanıcılar** sekmesinde kullanıcınızın listelendiğinden emin olmanız gerekir. Canlı bağlantılara yönelik seçim, verileri ilk kez içeri aktardığınızda Power BI Desktop içinde gerçekleşir.

Power BI Desktop'tan veya **Veri Al** seçeneğini kullanarak yayımladığınız raporlarınızla hemen çalışmaya başlayabilirsiniz. Ağ geçidinde veri kaynağı oluşturulduktan sonra bağlantının kullanılabilir hale gelmesi için birkaç dakika beklemeniz gerekebilir.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Zamanlanmış yenileme ile veri kaynağını kullanma

Ağ geçidinde yapılandırılan veri kaynağının **Kullanıcılar** sekmesinde yer alıyorsanız ve sunucu ile veritabanı adı eşleşiyorsa ağ geçidini zamanlanmış yenileme ile kullanılabilen bir seçenek olarak görürsünüz.

![Kullanıcıları görüntüleme](media/service-gateway-enterprise-manage-ssas/powerbi-gateway-enterprise-schedule-refresh.png)

### <a name="limitations-of-analysis-services-live-connections"></a>Analysis Services canlı bağlantılarına ilişkin sınırlamalar

Tablolu veya çok boyutlu örnekler için canlı bağlantı kullanabilirsiniz.

| **Sunucu sürümü** | **Gerekli SKU** |
| --- | --- |
| 2012 SP1 CU4 veya sonraki sürümler |İş Zekası ve Enterprise SKU'su |
| 2014 |İş Zekası ve Enterprise SKU'su |
| 2016 |Standart SKU veya sonraki sürümler |

* Hücre düzeyinde Biçimlendirme ve çeviri özellikleri desteklenmez.
* Eylemler ve Adlandırılmış Kümeler Power BI için açık değildir ancak Eylemleri veya Adlandırılmış kümeleri de içeren çok boyutlu küplere yine de bağlanabilir, görseller ve raporlar oluşturabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

* [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](/data-integration/gateway/service-gateway-tshoot)
* [Ağ geçidiyle ilgili sorunları giderme - Power BI](service-gateway-onprem-tshoot.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

