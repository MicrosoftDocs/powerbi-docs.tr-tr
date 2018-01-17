---
title: "Şirket içi veri ağ geçidi"
description: "Bu, Power BI için şirket içi veri ağ geçidine bir genel bakıştır. DirectQuery veri kaynaklarıyla çalışmak için bu ağ geçidini kullanabilirsiniz. Bulut veri kümelerini şirket içi verilerle yenilemek için de bu ağ geçidini kullanabilirsiniz."
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
ms.date: 01/10/2018
ms.author: davidi
ms.openlocfilehash: 0e0ad501ed809fc1f7cd8cc66d7f5d13badf7d15
ms.sourcegitcommit: afd6e9e6f8b192b26486cd04d2cbc9de046911b3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2018
---
# <a name="on-premises-data-gateway"></a>Şirket içi veri ağ geçidi
Şirket içi veri ağ geçidi bir köprü işlevi görerek şirket içi veriler (bulutta olmayan veriler) ile Power BI, Microsoft Flow, Logic Apps ve PowerApps hizmetleri arasında hızlı ve güvenli veri aktarımı sağlar.

Tek bir ağ geçidini aynı anda farklı hizmetlerle kullanabilirsiniz. Power BI'ın yanı sıra PowerApps hizmetini kullanıyorsanız her iki hizmet için tek bir ağ geçidi kullanılabilir. Bu, oturum açmak için kullandığınız hesaba bağlıdır.

> [!NOTE]
> Şirket içi veri ağ geçidi, tüm modlarda veri sıkıştırma ve aktarım şifreleme uygular.
> 
> 

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-requirements-include.md)]

### <a name="limitations-of-analysis-services-live-connections"></a>Analysis Services canlı bağlantılarına ilişkin sınırlamalar
Tablolu veya çok boyutlu örnekler için canlı bağlantı kullanabilirsiniz.

| **Sunucu sürümü** | **Gerekli SKU** |
| --- | --- |
| 2012 SP1 CU4 veya sonraki sürümler |İş Zekası ve Enterprise SKU'su |
| 2014 |İş Zekası ve Enterprise SKU'su |
| 2016 |Standart SKU veya sonraki sürümler |

* Hücre düzeyinde Biçimlendirme ve çeviri özellikleri desteklenmez.
* Eylemler ve Adlandırılmış Kümeler Power BI için açık değildir ancak Eylemleri ve Adlandırılmış kümeleri de içeren çok boyutlu küplere yine de bağlanabilir, görseller ve raporlar oluşturabilirsiniz.

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="download-and-install-the-on-premises-data-gateway"></a>Şirket içi veri ağ geçidi indirme ve yükleme
Ağ geçidini indirmek için İndir menüsü altında **Data Gateway**'i seçin. [Şirket içi veri ağ geçidini](http://go.microsoft.com/fwlink/?LinkID=820925) indirin.

![](media/service-gateway-onprem/powerbi-download-data-gateway.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-install-include](./includes/gateway-onprem-install-include.md)]

## <a name="install-the-gateway-in-personal-mode"></a>Ağ geçidini kişisel modda yükleme
> [!NOTE]
> Kişisel ağ geçidi yalnızca Power BI ile çalışır.
> 
> 

Kişisel ağ geçidi yüklendikten sonra **Power BI Gateway - Personal Yapılandırma Sihirbazı**'nı başlatmalısınız.

![](media/service-gateway-onprem/personal-gateway-launch-configuration.png)

Ardından, ağ geçidini bulut hizmetinde kaydetmek için Power BI'da oturum açmanız gerekir.

![](media/service-gateway-onprem/personal-gateway-signin.png)

Ayrıca, Windows hizmetinin çalışacağı Windows kullanıcı adını ve parolayı sağlamanız gerekir. Size ait farklı bir Windows hesabı belirtebilirsiniz. Ağ geçidi hizmeti bu hesabı kullanarak çalışacaktır.

![](media/service-gateway-onprem/personal-gateway-windows-service.png)

Yükleme tamamlandıktan sonra, Power BI içindeki veri kümelerinize gitmeniz ve şirket içi veri kaynaklarınıza yönelik kimlik bilgilerinin girildiğinden emin olmanız gerekir.

<a name="credentials"></a>

## <a name="storing-encrypted-credentials-in-the-cloud"></a>Şifrelenmiş kimlik bilgilerini bulutta depolama
Ağ geçidine bir veri kaynağı eklediğinizde bu veri kaynağına yönelik kimlik bilgilerini sağlamanız gerekir. Veri kaynağına yönelik tüm sorgular bu kimlik bilgileri kullanılarak çalıştırılır. Kimlik bilgileri bulutta depolanmadan önce, bulutta şifrelerinin çözülmesini önlemek için asimetrik şifreleme kullanılarak güvenli bir şekilde şifrelenir. Kimlik bilgileri, şirket içinde ağ geçidini çalıştıran, veri kaynaklarına erişildiği zaman şifrelerinin çözüldüğü makineye gönderilir.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

<!-- How the gateway works -->
[!INCLUDE [gateway-onprem-how-it-works-include](./includes/gateway-onprem-how-it-works-include.md)]

## <a name="troubleshooting"></a>Sorun giderme
Bir ağ geçidini yüklerken ve yapılandırırken sorun yaşıyorsanız [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md) makalesini mutlaka inceleyin. Güvenlik duvarınızla ilgili bir sorun yaşadığınızı düşünüyorsanız sorun giderme makalesindeki [güvenlik duvarı veya ara sunucu](service-gateway-onprem-tshoot.md#firewall-or-proxy) bölümüne bakın.

Ara sunucu sorunlarıyla karşılaştığınızı düşünüyorsanız bkz. [Power BI ağ geçitleri için ara sunucu ayarlarını yapılandırma](service-gateway-proxy.md).

## <a name="next-steps"></a>Sonraki adımlar
[Veri kaynağınızı yönetme - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Veri kaynağınızı yönetme - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Veri kaynağınızı yönetme - SQL Server](service-gateway-enterprise-manage-sql.md)  
[Veri kaynağınızı yönetme - Oracle](service-gateway-onprem-manage-oracle.md)  
[Veri kaynağınızı yönetme - İçeri aktarma/Zamanlanmış yenileme](service-gateway-enterprise-manage-scheduled-refresh.md)  
[Şirket içi veri ağ geçidi (ayrıntılı)](service-gateway-onprem-indepth.md)  
[Şirket içi veri ağ geçidi (kişisel mod) - kişisel ağ geçidinin yeni sürümü](service-gateway-personal-mode.md)
[Şirket içi veri ağ geçidi için ara sunucu ayarlarını yapılandırma](service-gateway-proxy.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

