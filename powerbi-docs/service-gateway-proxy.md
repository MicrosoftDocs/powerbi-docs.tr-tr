---
title: Şirket içi veri ağ geçidi için ara sunucu ayarlarını yapılandırma
description: Şirket içi veri ağ geçidinin ara sunucu ayarlarını yapılandırmaya ilişkin bilgiler.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 11/21/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 621a5f92ebd9c7314b719b6643f5bfef958916c3
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37599347"
---
# <a name="configuring-proxy-settings-for-the-on-premises-data-gateway"></a>Şirket içi veri ağ geçidi için ara sunucu ayarlarını yapılandırma
Çalışma ortamınızda İnternet'e erişmek için ara sunucu kullanmanız gerekebilir. Bu da Şirket içi veri ağ geçidinin hizmete bağlanmasını engelleyebilir.

## <a name="does-your-network-use-a-proxy"></a>Ağınızda ara sunucu kullanılıyor mu?
superuser.com adresinde bulunan bu gönderi, ağınızda ara sunucu olup olmadığını belirlemenize yardımcı olabilir.

[How do I know what proxy server I'm using? (Hangi ara sunucuyu kullandığımı nasıl anlayabilirim?) (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## <a name="configuration-file-location-and-default-configuration"></a>Yapılandırma dosyası konumu ve varsayılan yapılandırma
Ara sunucu bilgileri bir .NET yapılandırma dosyasından ayarlanır. Konum ve dosya adları, kullandığınız ağ geçidine göre farklılık gösterebilir.

### <a name="on-premises-data-gateway"></a>Şirket içi veri ağ geçidi
Şirket içi veri ağ geçidinde kullanılan iki ana yapılandırma dosyası vardır.

**Yapılandırma**

Birincisi, ağ geçidini yapılandıran yapılandırma ekranlarına ilişkindir. Ağ geçidini yapılandırma konusunda sorun yaşıyorsanız bu dosyaya bakmanzı gerekir.

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Windows Hizmeti**

İkincisi, Power BI hizmetiyle etkileşim kuran ve istekleri işleyen gerçek Windows hizmetiyle ilgilidir.

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

## <a name="configuring-proxy-settings"></a>Ara sunucu ayarlarını yapılandırma
Varsayılan ara sunucu yapılandırması aşağıda verilmiştir.

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

Varsayılan yapılandırma Windows kimlik doğrulamasını kullanır. Ara sunucunuz başka bir kimlik doğrulaması türü kullanıyorsa ayarları değiştirmeniz gerekir. Emin değilseniz ağ yöneticinize başvurabilirsiniz. Temel ara sunucu kimlik doğrulaması önerilmez ve temel ara sunucu kimlik doğrulamasını kullanma girişimi, ağ geçidinin düzgün şekilde yapılandırılmamasıyla sonuçlanan ara sunucu kimlik doğrulaması hatalarına neden olabilir. Çözümlemek için daha güçlü bir kimlik doğrulaması mekanizması kullanın.

Varsayılan kimlik bilgilerini kullanmaya ek olarak, ara sunucu ayarlarını daha ayrıntılı bir şekilde tanımlamak için bir <proxy> öğesi ekleyebilirsiniz. Örneğin, bypassonlocal değerini false olarak ayarlayarak şirket içi veri ağ geçidinizin yerel kaynaklar için bile her zaman ara sunucu kullanması gerektiğini belirtebilirsiniz. Bunun yapılması, ara sunucu günlük dosyalarındaki bir Şirket içi veri ağ geçidinden kaynaklanan tüm https isteklerini takip etmek istemeni durumunda yararlı olabilir. Aşağıdaki örnek yapılandırma, tüm isteklerin 192.168.1.10 IP adresi ile belirli bir ara sunucudan geçmesi gerektiğini belirtir.

    <system.net>
        <defaultProxy useDefaultCredentials="true">
            <proxy  
                autoDetect="false"  
                proxyaddress="http://192.168.1.10:3128"  
                bypassonlocal="false"  
                usesystemdefault="true"
            />  
        </defaultProxy>
    </system.net>

.NET yapılandırma dosyalarının ara sunucu öğelerinin yapılandırılması hakkında daha fazla bilgi için bkz. [defaultProxy Öğesi (Ağ Ayarları)](https://msdn.microsoft.com/library/kd3cf2ex.aspx).

## <a name="changing-the-gateway-service-account-to-a-domain-user"></a>Ağ geçidi hizmet hesabını etki alanı kullanıcısı olarak değiştirme
Ara sunucu ayarlarını yukarıda belirtildiği gibi varsayılan kimlik bilgilerini kullanacak şekilde yapılandırdığınızda ara sunucunuzda kimlik doğrulaması sorunlarıyla karşılaşabilirsiniz. Bunun nedeni, varsayılan hizmet hesabının kimliği doğrulanmış etki alanı kullanıcısı değil, Hizmet SID'si olmasıdır. Ağ geçidinin hizmet hesabını değiştirerek ara sunucunuzda kimlik doğrulaması gerçekleştirilmesini sağlayabilirsiniz.

> [!NOTE]
> Parola sıfırlama gereksinimiyle karşılaşmamak için yönetilen hizmet hesabı kullanmanız önerilir. Active Directory'de [yönetilen hizmet hesabı](https://technet.microsoft.com/library/dd548356.aspx) oluşturmayı öğrenin.
> 
> 

### <a name="change-the-on-premises-data-gateway-service-account"></a>Şirket içi veri ağ geçidi hizmet hesabını değiştirme
1. **Şirket içi veri ağ geçidi hizmetinin** Windows hizmet hesabını değiştirin.

    Bu hizmet için varsayılan hesap *NT SERVICE\PBIEgwService* olarak yapılandırılmıştır. Bu hesabı Active Directory etki alanınızdaki bir etki alanı kullanıcı hesabıyla değiştirmek isteyebilirsiniz. Alternatif olarak parola sıfırlama gereksinimiyle karşılaşmamak için yönetilen hizmet hesabı da kullanabilirsiniz.

    Hesabı Windows hesabının özellikler sayfasının **Oturum Açma** sekmesinden değiştirebilirsiniz.
2. **Şirket içi veri ağ geçidi hizmetini** yeniden başlatın.

    Yönetici komut isteminden aşağıdaki komutları çalıştırın.

        net stop PBIEgwService

        net start PBIEgwService
3. **Şirket içi veri ağ geçidi yapılandırıcısını** başlatın. Windows başlat düğmesini seçip *Şirket içi veri ağ geçidi* için arama yapabilirsiniz.
4. Power BI'da oturum açın.
5. Kurtarma anahtarınızı kullanarak ağ geçidini geri yükleyin.

    Bu şekilde yeni hizmet hesabı, depolanan veri kaynağı kimlik bilgilerinin şifresini çözebilir.

> [!NOTE]
> Hizmetler Denetim masasını kullanarak hizmet hesabını doğrudan değiştirdiğinizde, ACL’ler otomatik olarak güncelleştirilmez. Yeni hizmet hesabının yükleme dosyalarına ve klasöre erişimi olduğundan emin olmanız gerekir. Ağ Geçidi Yükleme klasörünü C:\Program Files\Şirket içi veri ağ geçidi dizininde bulabilirsiniz. 
> 

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidi (kişisel mod)](service-gateway-personal-mode.md)
[Güvenlik duvarı bilgileri](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

