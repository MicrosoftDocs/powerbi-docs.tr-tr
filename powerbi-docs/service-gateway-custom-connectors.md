---
title: Şirket içi veri ağ geçidinde özel veri bağlayıcılarını kullanma
description: Şirket içi veri ağ geçidinde özel veri bağlayıcılarını kullanabilirsiniz.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 074a8dd876e0612f87c220f9fb077b60b2b85c88
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271792"
---
# <a name="use-custom-data-connectors-with-the-on-premises-data-gateway"></a>Şirket içi veri ağ geçidinde özel veri bağlayıcılarını kullanma

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Power BI veri bağlayıcıları bir uygulamadan, hizmetten veya veri kaynağından verilere bağlanmanızı ve erişmenizi sağlar. Özel veri bağlayıcıları geliştirebilir ve bunları Power BI Desktop'ta kullanabilirsiniz.

Power BI için özel veri bağlayıcıları geliştirme hakkında daha fazla bilgi edinmek için [Veri Bağlayıcı SDK’sı GitHub sayfasını](http://aka.ms/dataconnectors) inceleyin. Bu site, Power BI ve Power Query için kullanmaya başlama bilgilerini ve örneklerini içerir.

Power BI Desktop'ta özel veri bağlayıcıları kullanan raporlar oluşturduğunuzda, şirket içi veri ağ geçidini kullanarak bu raporları Power BI hizmetinden yenileyebilirsiniz.

## <a name="how-to-enable-and-use-this-capability"></a>Bu özelliği etkinleştirme ve kullanma

Şirket içi veri ağ geçidinin Temmuz 2018 veya üzeri bir sürümünü yüklediğinizde, özel bağlayıcıların yükleneceği klasörü belirleme seçeneğinin bulunduğu **Bağlayıcılar** sekmesini şirket içi veri ağ geçidinde görebilirsiniz. Ağ geçidi hizmetini çalıştıran kullanıcının (varsayılan olarak *“NT SERVICE\PBIEgwService*”) erişebileceği bir klasör seçtiğinizden emin olun. Ağ geçidi bu klasörde bulunan özel bağlayıcı dosyalarını otomatik olarak yükler ve bunları veri bağlayıcıları listesinde görürsünüz.

![Özel bağlayıcı 1](media/service-gateway-custom-connectors/gateway-onprem-customconnector1.png)

Şirket içi veri ağ geçidini (kişisel mod) kullanıyorsanız, bu noktada Power BI raporunuzu Power BI hizmetine yükleyebilir ve bunu yenilemek için ağ geçidini kullanabilirsiniz.

Şirket içi veri ağ geçidinde, özel bağlayıcınız için bir veri kaynağı oluşturmanız gerekir. Power BI hizmetinin ağ geçidi ayarları sayfasında ağ geçidi kümesini seçtiğinizde bu kümeyle özel bağlayıcı kullanmanızı sağlayan yeni bir seçenek görmeniz gerekir. Bu seçeneği kullanabilmek için kümedeki tüm ağ geçitlerinin Temmuz 2018 güncelleştirmesine veya daha yeni bir sürüme sahip olduğundan emin olun. Şimdi bu kümeyle özel bağlayıcı kullanma seçeneğini etkinleştirin.

![Özel bağlayıcı 2](media/service-gateway-custom-connectors/gateway-onprem-customconnector2.png)

Bu seçenek etkinleştirildiğinde özel bağlayıcılarınızı bu ağ geçidi kümesinde oluşturabileceğiniz veri kaynaklarının arasında görmeniz gerekir. Özel bağlayıcınızı kullanarak bir veri kaynağı oluşturduktan sonra bu özel bağlayıcıyı kullanan Power BI raporlarını Power BI hizmetinden yenileyebilirsiniz.

![Özel bağlayıcı 3](media/service-gateway-custom-connectors/gateway-onprem-customconnector3.png)

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Oluşturduğunuz klasöre arka plan ağ geçidi hizmeti tarafından erişilebildiğinden emin olun. Genellikle kullanıcınızın Windows klasörü veya sistem klasörleri içindeki klasörler erişilebilir durumda olmayacaktır. Klasörün erişilebilir olmaması halinde şirket içi veri ağ geçidi bir hata iletisi gösterir (bu durum ağ geçidinin kişisel sürümü için geçerli değildir)
* Özel bağlayıcıların şirket içi veri ağ geçidi ile çalışabilmesi için özel bağlayıcı kodunda “TestConnection” bölümü oluşturulması gerekir. Bu durum özel bağlayıcıların Power BI Desktop'ta kullanılması durumunda geçerli değildir. Bu nedenle Desktop uygulamasıyla çalışan ancak ağ geçidiyle çalışmayan bir sürüme sahip olabilirsiniz. TestConnection bölümü oluşturma hakkında bilgi için lütfen [bu belgeye](https://github.com/Microsoft/DataConnectors/blob/master/docs/m-extensions.md#implementing-testconnection-for-gateway-support) bakın.

## <a name="next-steps"></a>Sonraki adımlar

* [Veri kaynağınızı yönetme - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [Veri kaynağınızı yönetme - SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [Veri kaynağınızı yönetme - SQL Server](service-gateway-enterprise-manage-sql.md)  
* [Veri kaynağınızı yönetme - Oracle](service-gateway-onprem-manage-oracle.md)  
* [Veri kaynağınızı yönetme - İçeri aktarma/Zamanlanmış yenileme](service-gateway-enterprise-manage-scheduled-refresh.md)  

* [Şirket içi veri ağ geçidi için ara sunucu ayarlarını yapılandırma](/data-integration/gateway/service-gateway-proxy)  
* [Power BI’dan şirket içi veri kaynaklarına kadar SSO (çoklu oturum açma) için Kerberos’u kullanma](service-gateway-sso-kerberos.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
