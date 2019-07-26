---
title: Şirket içi veri ağ geçidi hakkında SSS - Power BI
description: Bu, Power BI için şirket içi veri ağ geçidi ile ilgili SSS bölümüdür. Power BI’da kullanılan ağ geçidi ile ilgili sıkça sorulan sorular, burada tek bir noktada toplanır.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 99a03f88ed5f6585ca8ed6d64f396e70cdd046e5
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68272758"
---
# <a name="on-premises-data-gateway-faq---power-bi"></a>Şirket içi veri ağ geçidi hakkında SSS - Power BI

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

## <a name="power-bi"></a>Power BI

**Soru:** Kişisel ağ geçidini yükseltmem gerekiyor mu?  
**Cevap:** Hayır, Power BI için kişisel ağ geçidini kullanmaya devam edebilirsiniz.

**Soru:** Ağ geçidini yüklemek ve bunu Power BI hizmetinde yönetmek için herhangi bir özel izin gerekir mi?
**Cevap:** Özel izin gerekmez.

**Soru:** Şirket içi veri kaynaklarına bağlanan Power Pivot veri modelleri içeren Excel çalışma kitaplarını karşıya yükleyebilir miyim? Bu senaryo için bir ağ geçidi gerekir mi?  
**Cevap:** Evet, çalışma kitabını karşıya yükleyebilirsiniz. Ayrıca, bunun için bir ağ geçidi gerekmez. Ancak, veriler Excel veri modelinde yer alacağı için Power BI'da Excel çalışma kitabını temel alan raporlar canlı olmaz. Power BI'daki raporları yenilemek için her seferinde, güncelleştirilmiş bir çalışma kitabını yeniden karşıya yüklemeniz gerekir. Alternatif olarak, zamanlanmış yenileme ile ağ geçidini de kullanabilirsiniz.

**Soru:** Kullanıcılar bir DirectQuery bağlantısı içeren panolar paylaşırsa diğer kullanıcılar aynı izinlere sahip olmasa bile verileri görebilir mi?  
**Cevap:** Analysis Services'e bağlı bir pano ile ilgili olarak kullanıcılar, yalnızca erişim sahibi oldukları verileri görebilir. Kullanıcılar aynı izinlere sahip değilse herhangi bir veri göremez. Diğer veri kaynaklarında ise tüm kullanıcılar, veri kaynağı için yönetici tarafından girilen kimlik bilgilerini paylaşır.

**Soru:** Oracle sunucuma neden bağlanamıyorum?  
**Cevap:** Oracle sunucunuza bağlanmak için Oracle istemcisini yüklemeniz ve tnsnames.ora dosyasını doğru sunucu bilgileriyle yapılandırmanız gerekebilir. Bu, ağ geçidinin dışında ayrı bir yüklemedir. Daha fazla bilgi için bkz. [Oracle İstemcisini Yükleme](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client).

**Soru:** Ağ geçidi ExpressRoute ile çalışır mı?  
**Cevap:** Evet. ExpressRoute ve Power BI hakkında daha fazla bilgi için bkz. [Power BI ve ExpressRoute](service-admin-power-bi-expressroute.md).

**Soru:** R betikleri kullanıyorum. Bu destekleniyor mu?
**Yanıt**: R betikleri yalnızca kişisel mod için desteklenir.

## <a name="analysis-services-in-power-bi"></a>Power BI’da Analysis Services

**Soru:** Analysis Services'e yönelik özel etkin kullanıcı adı eşlemeleri oluşturmak için msdmpump.dll kullanabilir miyim?  
**Cevap:** Hayır. Bu özellik şu anda desteklenmiyor.

**Soru:** Ağ geçidini kullanarak çok boyutlu (OLAP) bir örneğe bağlanabilir miyim?  
**Cevap:** Evet! Şirket içi veri ağ geçidi, Analysis Services Tablolu ve Çok Boyutlu modellere yönelik canlı bağlantıları desteklemektedir.

**Soru:** Ağ geçidini, Windows kimlik doğrulaması kullanan şirket içi sunucumdan farklı etki alanındaki bir bilgisayara yüklersem ne olur?  
**Cevap:** Bununla ilgili kesin bir cevap verilemez. Bu tamamen iki etki alanı arasındaki güven ilişkisine dayalıdır. İki farklı etki alanı bir güvenilir etki alanı modelindeyse ağ geçidi, Analysis Services sunucusuna bağlanabilir ve etkin kullanıcı adı çözümlenebilir. Aksi halde oturum açma hatasıyla karşılaşabilirsiniz.

**Soru:** Şirket içi Analysis Services sunucuma geçirilen etkili kullanıcı adını nasıl bulabilirim?  
**Cevap:** Bu sorunun cevabı [sorun giderme makalesinde](service-gateway-onprem-tshoot.md) verilmiştir.

## <a name="next-steps"></a>Sonraki adımlar

* [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](/data-integration/gateway/service-gateway-tshoot)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

