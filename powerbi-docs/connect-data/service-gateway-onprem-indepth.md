---
title: Şirket içi veri ağ geçidi (ayrıntılı)
description: Bu makalede, şirket içi veri ağ geçidi ayrıntılı olarak ele alınmaktadır. Analysis Services kullanılırken hizmetin Azure Active Directory ve yerel Active Directory hesabınız ile nasıl çalıştığı incelenmektedir
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: how-to
ms.date: 07/15/2019
ms.author: arthii
LocalizationGroup: Gateways
ms.openlocfilehash: 34cf796db212112baa8083f5b4cbf1796b465cba
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85237560"
---
# <a name="on-premises-data-gateway-in-depth"></a>Şirket içi veri ağ geçidi (ayrıntılı)

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

Bilgileri, bu makaleden Power BI ve genel belgelerde yer alan çeşitli makalelere taşıdık. İlgili içerikleri bulmak için her başlığın altındaki bağlantıları izleyin.

## <a name="how-the-gateway-works"></a>Ağ geçidi nasıl çalışır?

Bkz. [Şirket içi veri ağ geçidi mimarisi](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="list-of-available-data-source-types"></a>Kullanılabilir veri kaynağı türlerinin listesi

Bkz. [Veri kaynaklarını yönetme](service-gateway-data-sources.md).

## <a name="authentication-to-on-premises-data-sources"></a>Şirket içi veri kaynaklarına yönelik kimlik doğrulaması

Bkz. [Şirket içi veri kaynaklarına yönelik kimlik doğrulaması](/data-integration/gateway/service-gateway-onprem-indepth#authentication-to-on-premises-data-sources).

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Canlı bir Analysis Services veri kaynağına yönelik kimlik doğrulaması

Bkz. [Canlı bir Analysis Services veri kaynağına yönelik kimlik doğrulaması](service-gateway-enterprise-manage-ssas.md#authentication-to-a-live-analysis-services-data-source).

## <a name="role-based-security"></a>Rol tabanlı güvenlik

Bkz. [Rol tabanlı güvenlik](service-gateway-enterprise-manage-ssas.md#role-based-security).

## <a name="row-level-security"></a>Satır düzeyi güvenlik

Bkz. [Satır Düzeyi Güvenlik](service-gateway-enterprise-manage-ssas.md#row-level-security).

## <a name="what-about-azure-active-directory"></a>Azure Active Directory hakkında

Bkz. [Azure Active Directory](/data-integration/gateway/service-gateway-onprem-indepth#azure-active-directory).

## <a name="how-do-i-tell-what-my-upn-is"></a>UPN'mi nasıl bulabilirim?

Bkz. [UPN'mi nasıl bulabilirim?](/data-integration/gateway/service-gateway-onprem-indepth#how-do-i-tell-what-my-upn-is).

## <a name="map-user-names-for-analysis-services-data-sources"></a>Analysis Services veri kaynakları için kullanıcı adlarını eşleme

Bkz. [Analysis Services veri kaynakları için kullanıcı adlarını eşleme](service-gateway-enterprise-manage-ssas.md#map-user-names-for-analysis-services-data-sources).

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Bir şirket içi Active Directory hesabını Azure Active Directory ile eşitleme

Bkz. [Bir şirket içi Active Directory hesabını Azure Active Directory ile eşitleme](/data-integration/gateway/service-gateway-onprem-indepth#synchronize-an-on-premises-active-directory-with-azure-active-directory).

## <a name="what-to-do-next"></a>Sırada ne var?

Veri kaynaklarıyla ilgili makalelere bakın:

[Veri kaynaklarını yönetme](service-gateway-data-sources.md)
[Veri kaynaklarını yönetme - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Veri kaynağınızı yönetme - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Veri kaynağınızı yönetme - SQL Server](service-gateway-enterprise-manage-sql.md)  
[Veri kaynağınızı yönetme - Oracle](service-gateway-onprem-manage-oracle.md)  
[Manage your data source - Import/Scheduled refresh (Veri kaynağınızı yönetme - İçeri aktarma/Zamanlanmış yenileme)](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>Olası sorunlar

Bkz. [Şirket içi veri ağ geçidinde sorun giderme](/data-integration/gateway/service-gateway-tshoot) ve [Ağ geçitlerinde sorun giderme - Power BI](service-gateway-onprem-tshoot.md).

## <a name="sign-in-account"></a>Oturum açma hesabı

Bkz. [Oturum açma hesabı](/data-integration/gateway/service-gateway-onprem-indepth#sign-in-account).

## <a name="windows-service-account"></a>Windows Hizmet hesabı

Bkz. [Şirket içi veri ağ geçidi hizmet hesabını değiştirme](/data-integration/gateway/service-gateway-service-account).

## <a name="ports"></a>Bağlantı noktaları

Bkz [Bağlantı noktaları](/data-integration/gateway/service-gateway-communication#ports).

## <a name="forcing-https-communication-with-azure-service-bus"></a>Azure Service Bus ile HTTPS iletişimini zorlama

Bkz. [Azure Service Bus ile HTTPS iletişimini zorlama](/data-integration/gateway/service-gateway-communication#force-https-communication-with-azure-service-bus).

## <a name="support-for-tls-12"></a>TLS 1.2 Desteği

Bkz. [Ağ geçidi trafiği için TLS 1.2](/data-integration/gateway/service-gateway-communication#tls-12-for-gateway-traffic).

## <a name="how-to-restart-the-gateway"></a>Ağ geçidini yeniden başlatma

Bkz. [Ağ geçidini yeniden başlatma](/data-integration/gateway/service-gateway-restart).

## <a name="next-steps"></a>Sonraki adımlar

[Şirket içi veri ağ geçidi nedir?](service-gateway-onprem.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)