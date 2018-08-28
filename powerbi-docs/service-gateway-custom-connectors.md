---
title: Şirket içi veri ağ geçidinde özel veri bağlayıcılarını kullanma
description: Şirket içi veri ağ geçidinde özel veri bağlayıcılarını kullanabilirsiniz.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 08/08/2018
LocalizationGroup: Gateways
ms.openlocfilehash: 9c36034ad5e8175e08f1d16c2f5148c5dab0ebbd
ms.sourcegitcommit: 640382408111d6e9cd1b9dfad0b484e3c727e454
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42702893"
---
# <a name="use-custom-data-connectors-with-the-on-premises-data-gateway"></a>Şirket içi veri ağ geçidinde özel veri bağlayıcılarını kullanma

Power BI veri bağlayıcıları bir uygulamadan, hizmetten veya veri kaynağından verilere bağlanmanızı ve erişmenizi sağlar. Özel veri bağlayıcıları geliştirebilir ve bunları Power BI Desktop'ta kullanabilirsiniz.

Power BI için özel veri bağlayıcıları geliştirme hakkında daha fazla bilgi edinmek için [buradaki](http://aka.ms/dataconnectors) belgeleri inceleyin.

Power BI Desktop'ta özel veri bağlayıcıları kullanan raporlar oluşturduğunuzda, Şirket içi veri ağ geçidini kullanarak bu raporları Power BI hizmetinden yenileyebilirsiniz.

## <a name="here-is-a-guide-on-how-to-enable-and-use-this-capability"></a>Veri bağlayıcıları özelliğini etkinleştirme ve kullanma kılavuzu

Şirket içi veri ağ geçidinin Temmuz 2018 veya üzeri bir sürümünü yüklediğinizde, özel bağlayıcıların yükleneceği klasörü belirleme seçeneğinin bulunduğu "Bağlayıcılar" sekmesini yapılandırıcıda görebilirsiniz. Ağ geçidi hizmetini çalıştıran kullanıcının (varsayılan olarak “NT SERVICE\PBIEgwService”) erişebileceği bir klasör seçtiğinizden emin olun. Ağ geçidi bu klasörde bulunan özel bağlayıcı dosyalarını otomatik olarak yükler ve bağlayıcıyı veri bağlayıcıları listesine ekler.

![Özel bağlayıcı 1](media/service-gateway-custom-connectors/gateway-onprem-customconnector1.png)

Şirket içi veri ağ geçidinin kişisel sürümünü kullanıyorsanız, bu noktada Power BI raporunuzu Power BI hizmetine yükleyebilir ve ağ geçidini kullanarak bu raporu yenileyebilmeniz gerekir.

Ağ geçidinin kurumsal sürümünde özel bağlayıcınız için bir veri kaynağı oluşturmanız gerekir. Power BI hizmetinin ağ geçidi ayarları sayfasında ağ geçidi kümesini seçtiğinizde bu kümeyle özel bağlayıcı kullanmanızı sağlayan yeni bir seçenek görmeniz gerekir. Bu seçeneği kullanabilmek için kümedeki tüm ağ geçitlerinin Temmuz 2018 güncelleştirmesine veya daha yeni bir sürüme sahip olduğundan emin olun. Şimdi bu kümeyle özel bağlayıcı kullanma seçeneğini etkinleştirin.

![Özel bağlayıcı 2](media/service-gateway-custom-connectors/gateway-onprem-customconnector2.png)

Bu seçenek etkinleştirildiğinde özel bağlayıcılarınızı bu ağ geçidi kümesinde oluşturabileceğiniz veri kaynaklarının arasında görmeniz gerekir. Özel bağlayıcınızı kullanarak bir veri kaynağı oluşturduktan sonra bu özel bağlayıcıyı kullanan Power BI raporlarını Power BI hizmetinden yenileyebilirsiniz.

![Özel bağlayıcı 3](media/service-gateway-custom-connectors/gateway-onprem-customconnector3.png)

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Oluşturduğunuz klasöre arka plan ağ geçidi hizmeti tarafından erişilebildiğinden emin olun. Genellikle kullanıcınızın Windows klasörü veya sistem klasörleri içindeki klasörler erişilebilir durumda olmayacaktır. Klasörün erişilebilir olmaması halinde ağ geçidi yapılandırıcısı bir hata iletisi gösterir (bu durum ağ geçidinin kişisel sürümü için geçerli değildir)
* Özel bağlayıcıların Şirket içi veri ağ geçidi ile çalışabilmesi için özel bağlayıcı kodunda “TestConnection” bölümü oluşturulması gerekir. Bu durum özel bağlayıcıların Power BI Desktop'ta kullanılması durumunda geçerli değildir. Bu nedenle Desktop uygulamasıyla çalışan ancak ağ geçidiyle çalışmayan bir sürüme sahip olabilirsiniz. TestConnection bölümü oluşturma hakkında bilgi için lütfen [bu belgeye](https://github.com/Microsoft/DataConnectors/blob/master/docs/m-extensions.md#implementing-testconnection-for-gateway-support) bakın.
* OAuth kimlik doğrulaması kullanan özel bağlayıcılar desteklenmez.
* Doğrudan Sorgu kullanan özel bağlayıcılar desteklenmez.

## <a name="next-steps"></a>Sonraki adımlar

* [Veri kaynağınızı yönetme - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [Veri kaynağınızı yönetme - SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [Veri kaynağınızı yönetme - SQL Server](service-gateway-enterprise-manage-sql.md)  
* [Veri kaynağınızı yönetme - Oracle](service-gateway-onprem-manage-oracle.md)  
* [Veri kaynağınızı yönetme - İçeri aktarma/Zamanlanmış yenileme](service-gateway-enterprise-manage-scheduled-refresh.md)  
* [Şirket içi veri ağ geçidi ayrıntıları](service-gateway-onprem-indepth.md)  
* [Şirket içi veri ağ geçidi (kişisel mod)](service-gateway-personal-mode.md)
* [Şirket içi veri ağ geçidi için ara sunucu ayarlarını yapılandırma](service-gateway-proxy.md)  
* [Power BI’dan şirket içi veri kaynaklarına kadar SSO (çoklu oturum açma) için Kerberos’u kullanma](service-gateway-kerberos-for-sso-pbi-to-on-premises-data.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
