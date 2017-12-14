---
title: "Şirket içi veri ağ geçidi (ayrıntılı)"
description: "Bu makalede, şirket içi veri ağ geçidi ayrıntılı olarak ele alınmaktadır. Analysis Services kullanılırken hizmetin Azure Active Directory ve yerel Active Directory hesabınız ile nasıl çalıştığı incelenmektedir"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: ca1761c0708681e6b413ba679980bacb3931e01d
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2017
---
# <a name="on-premises-data-gateway-in-depth"></a>Şirket içi veri ağ geçidi (ayrıntılı)
Kuruluşunuzdaki kullanıcılar şirket içi verilere (erişim yetkisine sahip oldukları) erişebilir ancak şirket içi veri kaynağınıza bağlanabilmeleri için bir şirket içi veri ağ geçidinin yüklenmiş ve yapılandırılmış olması gerekir. Ağ geçidi, buluttaki bir kullanıcıdan şirket içi veri kaynağınıza gelen ve daha sonra buluta geri giden hızlı ve güvenli arka plan iletişimini kolaylaştırır.

Ağ geçidi, genellikle bir yönetici tarafından yüklenir ve yapılandırılır. Bu işlem için şirket içi sunucularınız ile ilgili özel bilgiler gerekebileceği gibi bazı durumlarda Sunucu Yöneticisi izinleri de gerekli olabilir.

Bu makale, ağ geçidini yüklemeye ve yapılandırmaya ilişkin bir adım adım kılavuz içermez. Bunun için [Şirket içi veri ağ geçidi](service-gateway-onprem.md) makalesine göz atın. Bu makalenin amacı, ağ geçidinin çalışma şekline ilişkin ayrıntılı bir açıklama sunmaktır. Ayrıca, hem Azure Active Directory hem de Analysis Services'deki güvenlik ve kullanıcı adlarının yanı sıra bulut hizmetinin, şirket içi verilerinize güvenle bağlanmak ve bu verileri sorgulamak için bir kullanıcının oturum açtığı e-posta adresini, ağ geçidini ve Active Directory'yi nasıl kullandığı ile ilgili ayrıntılara da yer verilecektir.

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-how-it-works-include.md)]

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="sign-in-account"></a>Oturum açma hesabı
Kullanıcılar, iş veya okul hesabıyla oturum açar. Bu, kuruluş hesabınızdır. Bir Office 365 teklifine kaydolduysanız ve gerçek iş e-postanızı sağlamadıysanız e-postanız şöyle görünebilir: nancy@contoso.onmicrosoft.com. Bir bulut hizmetindeki hesabınız, Azure Active Directory'deki (AAD) bir kiracıda depolanır. Çoğu durumda AAD hesabınızın UPN'si e-posta adresiyle eşleşir.

## <a name="authentication-to-on-premises-data-sources"></a>Şirket içi veri kaynaklarına yönelik kimlik doğrulaması
Analysis Services hariç olmak üzere ağ geçidinden şirket içi veri kaynaklarına bağlanmak için, depolanan bir kimlik bilgisi kullanılır. Ağ geçidi, bireysel kullanıcılardan bağımsız olarak, depolanan kimlik bilgisini kullanarak bağlanır.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Canlı bir Analysis Services veri kaynağına yönelik kimlik doğrulaması
Bir kullanıcı Analysis Services ile her etkileşim kurduğunda, etkin kullanıcı adı ağ geçidi üzerinden şirket içi Analysis Services sunucunuza iletilir. Kullanıcı asıl adı (UPN) (genel olarak, bulutta oturum açmak için kullandığınız e-posta adresi) etkin kullanıcı olarak Analysis Services'e geçireceğimiz addır. UPN, EffectiveUserName bağlantı özelliği ile geçirilir. Bu e-posta adresinin, yerel Active Directory etki alanında tanımlı bir UPN ile eşleşmesi gerekir. UPN, bir Active Directory hesabı özelliğidir. Daha sonra ilgili Windows hesabının, sunucu erişimi kazanmak için bir Analysis Services rolünde olması gerekir. Active Directory'de eşleşme bulunmazsa oturum açma işlemi başarısız olur.

Ayrıca, Analysis Services bu hesaba dayalı filtreleme olanağı sağlayabilir. Fitreleme, rol tabanlı güvenlik veya satır düzeyi güvenlik ile gerçekleşebilir.

## <a name="role-based-security"></a>Rol tabanlı güvenlik
Modeller, kullanıcı rollerine göre güvenlik sağlar. Roller, belirli bir model projesi için SQL Server Veri Araçları - Business Intelligence'ta (SSDT-BI) yazma sırasında veya model dağıtıldıktan sonra SQL Server Management Studio (SSMS) kullanılarak tanımlanır. Roller, Windows kullanıcı adı veya Windows grubuna göre üyeler içerir. Roller, bir kullanıcının modelde sorgulama yapma veya eylem gerçekleştirme izinlerini tanımlar. Çoğu kullanıcı, Okuma izinlerine sahip bir role aittir. Diğer roller; öğeleri işleme, veritabanı işlevlerini yönetme ve diğer rolleri yönetme izinlerine sahip yöneticilere yöneliktir.

## <a name="row-level-security"></a>Satır düzeyi güvenlik
Satır düzeyi güvenlik, Analysis Services satır düzeyi güvenliğine özgüdür. Modeller dinamik, satır düzeyi güvenlik sağlayabilir. Kullanıcıların ait olduğu en az bir rol bulunan durumların aksine dinamik güvenlik, herhangi bir tablolu model için gerekli değildir. Üst düzeyde ele alındığında dinamik güvenlik, kullanıcıların bir tablodaki belirli bir satıra ilişkin verilere yönelik okuma erişimini tanımlar. Rollere benzer şekilde dinamik satır düzeyi güvenlik, kullanıcıların Windows kullanıcı adlarını kullanır.

Kullanıcının model verileri için sorgulama ve görüntüleme gerçekleştirip gerçekleştiremeyeceği, ilk olarak Windows kullanıcı hesabının üyesi olduğu rollere; ikinci olarak ise dinamik satır düzeyi güvenliğe (yapılandırılmışsa) bağlıdır.

Modellerde rol ve dinamik satır düzeyi güvenlik uygulaması, bu makalede ele alınmamıştır.  MSDN'deki [Roles (SSAS Tabular) (Roller (SSAS Tablosu))](https://msdn.microsoft.com/library/hh213165.aspx) ve [Security Roles (Analysis Services - Multidimensional Data) (Güvenlik Rolleri (Analysis Services - Çok Boyutlu Veriler))](https://msdn.microsoft.com/library/ms174840.aspx) sayfalarını inceleyerek daha fazla bilgi edinebilirsiniz. Tablolu model güvenliğini en ayrıntılı şekilde kavramak için [Securing the Tabular BI Semantic Model (Tablolu BI Anlam Modelinin güvenliğini sağlama) teknik incelemesini](https://msdn.microsoft.com/library/jj127437.aspx) indirin ve okuyun.

## <a name="what-about-azure-active-directory"></a>Azure Active Directory hakkında
Microsoft bulut hizmetleri, kullanıcıların kimliklerini doğrulamak için [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/)'yi kullanır. Azure Active Directory, kullanıcı adlarının ve güvenlik gruplarının bulunduğu kiracıdır. Genellikle, kullanıcının oturum açmak için kullandığı e-posta adresi hesabın UPN'si ile aynıdır.

Yerel Active Directory etki alanımın rolü nedir?

Analysis Services'in, buraya bağlanan bir kullanıcının veri okuma izinlerine sahip bir role ait olup olmadığını belirlemesi için sunucunun, AAD'den ağ geçidine ve daha sonra Analysis Services sunucusuna geçirilen etkin kullanıcı adını dönüştürmesi gerekir. Analysis Services sunucusu, etkin kullanıcı adını bir Windows Active Directory etki alanı denetleyicisine (DC) geçirir. Ardından Active Directory etki alanı denetleyicisi, yerel bir hesapta etkin kullanıcı adının geçerli bir UPN olduğunu doğrular ve ilgili kullanıcının Windows kullanıcı adını Analysis Services sunucusuna döndürür.

EffectiveUserName, etki alanına katılmamış bir Analysis Services sunucusunda kullanılamaz. Herhangi bir oturum açma hatası ile karşılaşılmaması için Analysis Services sunucusunun, bir etki alanına katılmış olması gerekir.

## <a name="how-do-i-tell-what-my-upn-is"></a>UPN'mi nasıl bulabilirim?
UPN'nizin ne olduğunu bilmeyebilir ve bir etki alanı yöneticisi olmayabilirsiniz. Hesabınızın UPN'sini bulmak için iş istasyonunuzda aşağıdaki komutu çalıştırabilirsiniz.

    whoami /upn

Sonuç bir e-posta adresi gibi görünür ancak bu, yerel etki alanı hesabınızdaki UPN'dir. Canlı bağlantılar için bir Analysis Services veri kaynağı kullanıyorsanız bu veri kaynağı, ağ geçidinden EffectiveUserName'e geçirilen değer ile eşleşmelidir.

## <a name="mapping-usernames-for-analysis-services-data-sources"></a>Analysis Services veri kaynakları için kullanıcı adlarını eşleme
Power BI, Analytics Services veri kaynakları için kullanıcı adı eşlemesine olanak sağlar. Power BI'da oturum açmak için kullanılan bir kullanıcı adını, Analysis Services bağlantısında EffectiveUserName için geçirilen adla eşlemeye yönelik kurallar yapılandırabilirsiniz. Kullanıcı adlarını eşleme özelliği, AAD'deki kullanıcı adınız yerel Active Directory etki alanınızdaki bir UPN ile eşleşmediğinde bu sorunu çözmenin etkili bir yoludur. Örneğin, e-posta adresiniz nancy@contoso.onmicrsoft.com ise bunu nancy@contoso.com ile eşleyebilirsiniz ve elde edilen değer, ağ geçidine geçirilir. [Kullanıcı adlarını eşleme](service-gateway-enterprise-manage-ssas.md#map-user-names) makalesini okuyarak konu ile ilgili daha fazla bilgi edinebilirsiniz.

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Bir şirket içi Active Directory hesabını Azure Active Directory ile eşitleme
Analysis Services canlı bağlantıları kullanacaksanız yerel Active Directory hesaplarınızın Azure Active Directory ile eşleşmesi gerekir. Bunun nedeni, UPN'nin hesaplar arasında eşleşmek zorunda olmasıdır.

Bulut hizmetleri yalnızca Azure Active Directory'deki hesapları tanır. Yerel Active Directory etki alanınıza bir hesap ekleseniz de bu hesap AAD'de mevcut değilse kullanılamaz. Yerel Active Directory hesaplarınızı Azure Active Directory ile eşlemeye yönelik farklı yöntemler bulunmaktadır.

1. Hesapları Azure Active Directory'ye el ile ekleyebilirsiniz.
   
   Azure portalı veya Office 365 Yönetim Portalı'nda bir hesap oluşturabilirsiniz. Böylece hesap adı, yerel Active Directory hesabının UPN'si ile eşleşir.
2. Yerel hesapları Azure Active Directory kiracınız ile eşitlemek için [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) aracını kullanabilirsiniz.
   
   Azure AD Connect aracı, dizin ve parola eşitlemesine yönelik seçenekler sunar. Bir kiracı yöneticisi veya yerel etki alanı yöneticisi değilseniz bu yapılandırmayı gerçekleştirmesi için BT yöneticinizle iletişime geçmeniz gerekir.
3. Active Directory Federasyon Hizmetleri'ni (ADFS) yapılandırabilirsiniz.
   
   [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) aracını kullanarak ADFS sunucunuzu AAD kiracınız ile ilişkilendirebilirsiniz. ADFS, yukarıda bahsedilen dizin eşitlemesini kullanır ancak çoklu oturum açma (SSO) deneyimine olanak sağlar. Örneğin, iş ağınızdaysanız bir bulut hizmetine bağlanmak ve oturum açmak istediğinizde kullanıcı adı veya parola girmeniz istenmeyebilir. Bu özelliğin kuruluşunuzda mevcut olup olmadığını öğrenmek için BT Yöneticiniz ile iletişime geçmeniz gerekir.

Azure AD Connect, UPN'nin AAD ile yerel Active Directory etki alanınız arasında eşleşmesini sağlar.

> [!NOTE]
> Hesapların Azure AD Connect aracı ile eşitlenmesi, AAD kiracınızda yeni hesaplar oluşturur.
> 
> 

## <a name="now-this-is-where-the-gateway-comes-in"></a>Bu noktada ağ geçidi devreye girer
Ağ geçidi, bulut ile şirket içi sunucunuz arasında bir köprü işlevi görür. Bulut ile ağ geçidi arasındaki veri aktarımının güvenliği [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/) tarafından sağlanır. Service Bus, ağ geçidinde bir giden bağlantı yoluyla bulut ile şirket içi sunucunuz arasında güvenli bir kanal oluşturur.  Şirket içi güvenlik duvarınızda açmanız gereken herhangi bir gelen bağlantı yoktur.

Bir Analysis Services veri kaynağınız varsa ağ geçidini, Analysis Services sunucunuz ile aynı ormana/etki alanına katılmış bir bilgisayara yüklemeniz gerekir.

Ağ geçidi sunucuya ne kadar yakın olursa bağlantı da o kadar hızlı olacaktır. Ağ geçidi ile sunucu arasındaki ağ gecikmesini önlemenin en iyi yolu, ağ geçidini veri kaynağı ile aynı sunucuya almaktır.

## <a name="what-to-do-next"></a>Sırada ne var?
Ağ geçidini yükledikten sonra bu ağ geçidi için veri kaynakları oluşturmanız gerekir. Veri kaynaklarını **Ağ geçitlerini yönet** ekranından ekleyebilirsiniz. Daha fazla bilgi için veri kaynaklarını yönetme konulu makalelere başvurun.

[Veri kaynağınızı yönetme - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Veri kaynağınızı yönetme - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Veri kaynağınızı yönetme - SQL Server](service-gateway-enterprise-manage-sql.md)  
[Veri kaynağınızı yönetme - Oracle](service-gateway-onprem-manage-oracle.md)  
[Manage your data source - Import/Scheduled refresh (Veri kaynağınızı yönetme - İçeri aktarma/Zamanlanmış yenileme)](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>Olası sorunlar
Bazen ağ geçidini yükleme işlemi başarısız olur. Ağ geçidi sorunsuz yüklenmiş gibi görünse de hizmet, ağ geçidiyle çalışamıyor olabilir. Çoğu durumda bu, ağ geçidinin, veri kaynağında oturum açmak için kimlik bilgisi olarak sağladığı parola gibi basit bir şeyden kaynaklanır.

Diğer bir neden de kullanıcıların oturum açarken kullandığı e-posta adresi türü ile ilgili sorunlar veya Analysis Services'in bir etkin kullanıcı adını çözümleyememesi olabilir. Birbirine güvenen birden çok etki alanınız varsa ve ağ geçidiniz ile Analysis Services farklı etki alanlarında yer alıyorsa bu durum da bazı sorunlara neden olabilir.

Ağ geçidiyle ilgili sorunları gidermeye yönelik adımlar bu makalede değil, başka bir makalede ele alınmıştır: [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md). Herhangi bir sorunla karşılaşmayacağınızı umuyoruz. Ancak, karşılaşmanız halinde tüm bu işlemlerin nasıl gerçekleştiğini anlamanız ve sorun giderme makalesi size yardımcı olacaktır.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
[Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/)  
[Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

