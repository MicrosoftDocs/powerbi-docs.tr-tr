## <a name="sign-in-account"></a>Oturum açma hesabı
Kullanıcılar, iş veya okul hesabıyla oturum açar. Bu, kuruluş hesabınızdır. Bir Office 365 teklifine kaydolduysanız ve gerçek iş e-postanızı sağlamadıysanız e-postanız şu şekilde görünebilir: nancy@contoso.onmicrosoft.com. Bir bulut hizmetindeki hesabınız, Azure Active Directory'deki (AAD) bir kiracıda depolanır. Çoğu durumda AAD hesabınızın UPN'si e-posta adresiyle eşleşir.

## <a name="windows-service-account"></a>Windows Hizmet hesabı
Şirket içi veri ağ geçidi, Windows hizmeti oturum açma kimlik bilgileri için *NT SERVICE\PBIEgwService* kullanılacak şekilde yapılandırılır. Varsayılan ayara göre, Hizmet olarak oturum açma hakkına sahiptir. Bu durum, ağ geçidini yüklemekte olduğunuz makinenin bağlamında geçerlidir.

> [!NOTE]
> Kişisel modu seçtiyseniz Windows hizmet hesabını ayrı olarak yapılandırırsınız.
> 
> 

Bu, şirket içi veri kaynaklarına bağlanmak için kullandığınız hesap değildir.  Ayrıca bu hesap, bulut hizmetlerinde oturum açmak için kullandığınız iş veya okul hesabınız da değildir.

Ara sunucunuzda kimlik doğrulaması ile ilgili sorunlarla karşılaşırsanız Windows hizmet hesabını bir etki alanı kullanıcısı veya yönetilen hizmet hesabı olarak değiştirebilirsiniz. [Ara sunucu yapılandırmasındaki](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user) hesabı nasıl değiştireceğiniz hakkında bilgi edinebilirsiniz.

## <a name="ports"></a>Bağlantı noktaları
Ağ geçidi, Azure Service Bus'a yönelik bir giden bağlantı oluşturur. Şu giden bağlantı noktaları üzerinden iletişim kurar: TCP 443 (varsayılan), 5671, 5672, 9350 ila 9354.  Ağ geçidi için gelen bağlantı noktaları gerekli değildir. [Daha fazla bilgi](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/)

Güvenlik duvarınızda veri bölgenize ilişkin IP adreslerini beyaz listeye eklemeniz önerilir. [Microsoft Azure Veri Merkezi IP listesini](https://www.microsoft.com/download/details.aspx?id=41653) indirebilirsiniz. Bu liste haftalık olarak güncelleştirilir. Ağ geçidi, tam etki alanı adı (FQDN) ile IP adresini kullanarak Azure Service Bus ile iletişim kurar. Ağ geçidini HTTPS kullanarak iletişim kurmaya zorluyorsanız yalnızca FQDN kullanılır ve IP adresleri kullanılarak herhangi bir iletişim kurulmaz.

> [!NOTE]
> Azure Veri Merkezi IP listesindeki adresler, CIDR gösteriminde listelenir. Örneğin, 10.0.0.0/24 değeri, 10.0.0.0 ila 10.0.0.24 anlamına gelmez. [CIDR gösterimi](http://whatismyipaddress.com/cidr) hakkında daha fazla bilgi edinin.
> 
> 

Aşağıda, ağ geçidi tarafından kullanılan tam etki alanı adlarının bir listesi verilmiştir.

| Etki alanı adları | Giden bağlantı noktaları | Açıklama |
| --- | --- | --- |
| *.download.microsoft.com |80 |Yükleyiciyi indirmek için kullanılan HTTP. |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Gelişmiş İleti Sıraya Alma Protokolü (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |TCP üzerinden Service Bus Geçişi'ndeki dinleyiciler (Erişim Denetimi belirtecinin alınması için 443 gerekir) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| *.msftncsi.com |443 |Power BI hizmeti tarafından ağ geçidine ulaşılamaması halinde İnternet bağlantısını test etmek için kullanılır. |
| *.microsoftonline-p.com |443 |Yapılandırmaya bağlı olarak kimlik doğrulaması için kullanılır. |

> [!NOTE]
> visualstudio.com veya visualstudioonline.com'a giden trafik uygulama öngörüleri için kullanılır ve ağ geçidinin çalışması için gerekli değildir.
> 
> 

## <a name="forcing-https-communication-with-azure-service-bus"></a>Azure Service Bus ile HTTPS iletişimini zorlama
Ağ geçidinin Azure Service Bus ile doğrudan TCP yerine HTTPS kullanarak iletişim kurmasını zorunlu kılabilirsiniz. Bu, performansı etkileyebilir. Bu işlemi gerçekleştirmek için, bu paragrafın hemen altındaki kod parçacığında gösterilen şekilde, *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* dosyasını düzenleyerek `AutoDetect` değerini `Https` olarak değiştirin. Bu dosya varsayılan olarak *C:\Program Files\On-premises data gateway* konumunda bulunur.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

*ServiceBusSystemConnectivityModeString* parametresinin değeri büyük/küçük harfe duyarlıdır. Geçerli değerler şunlardır: *AutoDetect* ve *Https*.

Alternatif olarak, [Mart 2017](https://powerbi.microsoft.com/blog/power-bi-gateways-march-update/) ve sonrasında kullanıma sunulan sürümlerde ağ geçidi kullanıcı arabirimini kullanarak, ağ geçidini bu davranışı benimsemeye zorlayabilirsiniz. Ağ geçidi kullanıcı arabiriminde **Ağ** seçeneğini belirleyin ve ardından **Azure Service Bus bağlantı modu** değerini **Açık** olarak değiştirin.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_01.png)

Değişikliğin ardından **Uygula**'yı seçtiğinizde (yalnızca değişiklik yaptığınızda görünen bir düğme) *ağ geçidi Windows hizmeti* otomatik olarak yeniden başlatılır ve söz konusu değişiklik geçerli olur.

Daha sonra gerçekleştireceğiniz işlemler için, *ağ geçidi Windows hizmetini*, kullanıcı arabiriminde **Hizmet Ayarları**'nı ve ardından *Şimdi Yeniden Başlat*'ı seçerek ilgili iletişim kutusundan yeniden başlatabilirsiniz.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_02.png)

## <a name="support-for-tls-1112"></a>TLS 1.1/1.2 desteği
Ağustos 2017 güncelleştirmesinden bu yana şirket içi veri ağ geçidinde, **Power BI hizmeti** ile iletişim kurmak için varsayılan olarak Aktarım Katmanı Güvenliği (TLS) 1.1 veya 1.2 sürümü kullanılmaktadır. Şirket içi veri ağ geçidinin önceki sürümlerinde varsayılan olarak TLS 1.0 sürümü kullanılır. 15 Mart 2018’de TLS 1.0 desteği (ağ geçidinin, **Power BI hizmeti** ile etkileşim kurmak için TLS 1.0 sürümünü kullanabilmesi de dahil) sona ereceğinden, ağ geçitlerinizin çalışmaya devam etmesini sağlamak üzere bu tarihe kadar şirket içi veri ağ geçidi yüklemelerinizi Ağustos 2017 veya sonraki bir sürümüne yükseltmeniz gerekmektedir.

TLS 1.0 sürümünün, şirket içi veri ağ geçidi tarafından 1 Kasım’a kadar desteklendiği ve ağ geçidi tarafından bir geri dönme mekanizması olarak kullanıldığı göz önünde bulundurulmalıdır. Tüm ağ geçidi trafiği için TLS 1.1 veya 1.2 sürümünün kullanılmasını (ve ağ geçidinizde TLS 1.0 sürümünün kullanılmasını önlemeyi) sağlamak üzere, ağ geçidi hizmetinin çalıştırıldığı makinede şu kayıt defteri anahtarlarını eklemeniz veya değiştirmeniz gerekmektedir:

        [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
        [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001

> [!NOTE]
> Bu kayıt defteri anahtarları eklendiğinde veya değiştirildiğinde değişiklikler tüm .NET uygulamalarında geçerli olur. Diğer uygulamalar için TLS'yi etkileyen kayıt defteri değişiklikleri hakkında bilgi edinmek için bkz. [Transport Layer Security (TLS) registry settings (Aktarım Güvenliği Katmanı (TLS) kayıt defteri ayarları)](https://docs.microsoft.com/windows-server/security/tls/tls-registry-settings).
> 
> 

## <a name="how-to-restart-the-gateway"></a>Ağ geçidini yeniden başlatma
Ağ geçidi, bir Windows hizmeti olarak çalışır. Ağ geçidini de diğer Windows hizmetleri gibi başlatıp durdurabilirsiniz. Bunu yapmanın birden çok yolu vardır. Aşağıda, bu işlemleri komut isteminden nasıl gerçekleştireceğiniz açıklanmıştır.

1. Ağ geçidinin çalıştırıldığı makinede bir yönetici komut istemi başlatın.
2. Hizmeti durdurmak için aşağıdaki komutu kullanın.
   
   net stop PBIEgwService
3. Hizmeti başlatmak için aşağıdaki komutu kullanın.
   
   net start PBIEgwService

