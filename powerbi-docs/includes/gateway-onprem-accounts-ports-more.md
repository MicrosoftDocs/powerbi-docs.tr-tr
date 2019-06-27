---
ms.openlocfilehash: e24218e2a465619fdfbfc279d3cc45370202dd6e
ms.sourcegitcommit: aef57ff94a5d452d6b54a90598bd6a0dd1299a46
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66814898"
---
## <a name="sign-in-account"></a>Oturum açma hesabı

Kullanıcılar, iş veya okul hesabıyla oturum açar. Bu hesap, **kuruluş hesabınızdır**. Bir Office 365 teklifine kaydolduysanız ve gerçek iş e-postanızı sağlamadıysanız e-postanız şu şekilde görünebilir: nancy@contoso.onmicrosoft.com. Hesabınız, Azure Active Directory’deki (AAD) bir kiracıda depolanır. Çoğu durumda AAD hesabınızın UPN'si e-posta adresiyle eşleşir.

## <a name="windows-service-account"></a>Windows Hizmet hesabı

Şirket içi veri ağ geçidi, Windows hizmeti oturum açma kimlik bilgileri için *NT SERVICE\PBIEgwService* kullanılacak şekilde yapılandırılır. Varsayılan olarak, ağ geçidini yüklediğiniz makine bağlamında Hizmet olarak oturum açma hakkına sahiptir. Bu hesap, şirket içi veri kaynaklarına bağlanmak için kullandığınız hesap değildir. Ayrıca bu hesap, bulut hizmetlerinde oturum açmak için kullandığınız iş veya okul hesabı da değildir.

> [!NOTE]
> Kişisel modu seçtiyseniz Windows hizmet hesabını ayrı olarak yapılandırırsınız.

Ara sunucunuzda kimlik doğrulaması ile ilgili sorunlarla karşılaşırsanız Windows hizmet hesabını bir etki alanı kullanıcısı veya yönetilen hizmet hesabı olarak değiştirmeyi deneyin. Daha fazla bilgi için bkz. [ara sunucu yapılandırması](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

## <a name="ports"></a>Bağlantı noktaları

Ağ geçidi, Azure Service Bus'a yönelik bir giden bağlantı oluşturur. Şu giden bağlantı noktaları üzerinden iletişim kurar: TCP 443 (varsayılan), 5671, 5672, 9350 - 9354.  Ağ geçidi için gelen bağlantı noktaları gerekli değildir.

Güvenlik duvarınızda veri bölgenize ilişkin IP adreslerini izin verilenler listesine eklemeniz önerilir. Haftalık olarak güncelleştirilen [Microsoft Azure Veri Merkezi IP listesini](https://www.microsoft.com/download/details.aspx?id=41653) indirebilirsiniz. Alternatif olarak şirket içi veri ağ geçidi uygulamasında [Ağ bağlantı noktası testi](../service-gateway-onprem-tshoot.md#network-ports-test) yaparak gerekli bağlantı noktalarının listesini alabilirsiniz. Ağ geçidi, tam etki alanı adı (FQDN) ile IP adresini kullanarak Azure Service Bus ile iletişim kurar. Ağ geçidini HTTPS kullanarak iletişim kurmaya zorluyorsanız yalnızca FQDN kullanılır ve IP adresleri kullanılarak herhangi bir iletişim kurulmaz.


> [!NOTE]
> Azure Veri Merkezi IP listesindeki adresler, CIDR gösteriminde listelenir. Örneğin, 10.0.0.0/24 değeri, 10.0.0.0’dan 10.0.0.24’e kadar anlamına gelmez. [CIDR gösterimi](http://whatismyipaddress.com/cidr) hakkında daha fazla bilgi edinin.

Aşağıda, ağ geçidi tarafından kullanılan tam etki alanı adlarının bir listesi verilmiştir.

| Etki alanı adları | Giden bağlantı noktaları | Açıklama |  |
|-----------------------------|----------------|--------------------------------------------------------------------------------------------------------------------|---|
| *.download.microsoft.com | 80 | Yükleyiciyi indirmek için kullanılır. Ayrıca veri ağ geçidi uygulaması tarafından sürüm ve ağ geçidi bölgesini denetlemek için de kullanılır. |  |
| *.powerbi.com | 443 | İlgili Power BI kümesini belirlemek için kullanılır. |  |
| *.analysis.windows.net | 443 | İlgili Power BI kümesini belirlemek için kullanılır. |  |
| *.login.windows.net | 443 | Azure Active Directory / OAuth2 ile veri ağ geçidi uygulamasının kimliğini doğrulamak için kullanılır. |  |
| *.servicebus.windows.net | 5671-5672 | Gelişmiş İleti Sıraya Alma Protokolü (AMQP) için kullanılır. |  |
| *.servicebus.windows.net | 443, 9350-9354 | TCP üzerinden Service Bus Geçişi'ndeki dinleyiciler tarafından kullanılır (erişim denetimi belirtecinin alınması için 443 gerekir). |  |
| *.frontend.clouddatahub.net | 443 | Kullanım dışı bırakıldı - artık gerekli değildir. Daha sonra belgelerden kaldırılacaktır. |  |
| *.core.windows.net | 443 | Power BI'daki veri akışları tarafından Azure Data Lake'e veri yazmak için kullanılır. |  |
| login.microsoftonline.com | 443 | Azure Active Directory / OAuth2 ile veri ağ geçidi uygulamasının kimliğini doğrulamak için kullanılır. |  |
| *.msftncsi.com | 443 | Power BI hizmeti tarafından İnternet bağlantısını ve ağ geçidinin ulaşılabilir olup olmadığını test etmek için kullanılır. |  |
| *.microsoftonline-p.com | 443 | Azure Active Directory / OAuth2 ile veri ağ geçidi uygulamasının kimliğini doğrulamak için kullanılır. |  |
| | |

> [!NOTE]
> Ağ geçidi yüklendikten ve kaydedildikten sonra, gereken tek bağlantı noktaları/IP'ler Azure Service Bus (yukarıdaki servicebus.windows.net) için gerekenlerdir. Şirket içi veri ağ geçidi uygulamasında [Ağ bağlantı noktası testi](../service-gateway-onprem-tshoot.md#network-ports-test) yaparak gerekli bağlantı noktalarının listesini alabilirsiniz.

## <a name="forcing-https-communication-with-azure-service-bus"></a>Azure Service Bus ile HTTPS iletişimini zorlama

Ağ geçidinin Azure Service Bus ile doğrudan TCP yerine HTTPS kullanarak iletişim kurmasını zorunlu kılabilirsiniz.

> [!NOTE]
> Azure Service Bus'tan gelen öneriler doğrultusunda Haziran 2019 sürümünden başlayarak yeni yüklemelerde (güncelleştirmelerde değil) varsayılan olarak TCP yerine HTTPS kullanılacaktır.

HTTP üzerinden iletişimi zorlamak için, bu paragrafın hemen altındaki kod parçacığında gösterildiği gibi *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* dosyasını düzenleyerek `AutoDetect` değerini `Https` olarak değiştirin. Bu dosya varsayılan olarak *C:\Program Files\On-premises data gateway* konumunda bulunur.

```xml
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

*ServiceBusSystemConnectivityModeString* parametresinin değeri büyük/küçük harfe duyarlıdır. Geçerli değerler şunlardır: *AutoDetect* ve *Https*.

Alternatif olarak ağ geçidi kullanıcı arabirimini kullanarak, ağ geçidini bu davranışı benimsemeye zorlayabilirsiniz. Ağ geçidi kullanıcı arabiriminde **Ağ** seçeneğini belirleyin ve ardından **Azure Service Bus bağlantı modu** değerini **Açık** olarak değiştirin.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_01.png)

Değişikliğin ardından **Uygula**'yı seçtiğinizde (yalnızca değişiklik yaptığınızda görünen bir düğme) *ağ geçidi Windows hizmeti* otomatik olarak yeniden başlatılır ve söz konusu değişiklik geçerli olur.

Daha sonra gerçekleştireceğiniz işlemler için, *ağ geçidi Windows hizmetini*, kullanıcı arabiriminde **Hizmet Ayarları**'nı ve ardından *Şimdi Yeniden Başlat*'ı seçerek ilgili iletişim kutusundan yeniden başlatabilirsiniz.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_02.png)

## <a name="support-for-tls-12"></a>TLS 1.2 Desteği

Varsayılan olarak Şirket içi veri ağ geçidinde, Power BI hizmeti ile iletişim kurmak için Aktarım Katmanı Güvenliği (TLS) 1.2 sürümü kullanılmaktadır. Tüm ağ geçidi trafiğinin TLS 1.2 kullanmasını sağlamak için, ağ geçidi hizmetinin çalıştırıldığı makinede şu kayıt defteri anahtarlarını eklemeniz veya değiştirmeniz gerekebilir:

```
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
```

> [!NOTE]
> Bu kayıt defteri anahtarları eklendiğinde veya değiştirildiğinde değişiklikler tüm .NET uygulamalarında geçerli olur. Diğer uygulamalar için TLS'yi etkileyen kayıt defteri değişiklikleri hakkında bilgi edinmek için bkz. [Transport Layer Security (TLS) registry settings (Aktarım Güvenliği Katmanı (TLS) kayıt defteri ayarları)](https://docs.microsoft.com/windows-server/security/tls/tls-registry-settings).

## <a name="how-to-restart-the-gateway"></a>Ağ geçidini yeniden başlatma

Ağ geçidi, bir Windows hizmeti olarak çalışır. Ağ geçidini de diğer Windows hizmetleri gibi başlatıp durdurabilirsiniz. Aşağıda, bu işlemleri komut isteminden nasıl gerçekleştireceğiniz açıklanmıştır.

1. Ağ geçidinin çalıştırıldığı makinede bir yönetici komut istemi başlatın.
2. Hizmeti durdurmak için aşağıdaki komutu kullanın.
   
   net stop PBIEgwService
3. Hizmeti başlatmak için aşağıdaki komutu kullanın.
   
   net start PBIEgwService

