---
title: Şirket içi veri ağ geçidi için ara sunucu ayarlarını yapılandırma
description: Şirket içi veri ağ geçidinin ara sunucu ayarlarını yapılandırmaya ilişkin bilgiler.
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 11/21/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: f6bfc47e7b74d9b17479a2ac7fc3dbc3f3e76816
ms.sourcegitcommit: 65426de556cd7207cbc4f478198664e25c33a769
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/30/2018
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

Varsayılan yapılandırma Windows kimlik doğrulamasını kullanır. Ara sunucunuz başka bir kimlik doğrulaması türü kullanıyorsa ayarları değiştirmeniz gerekir. Emin değilseniz ağ yöneticinize başvurabilirsiniz.

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

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidi (kişisel mod)](service-gateway-personal-mode.md)
[Güvenlik duvarı bilgileri](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

