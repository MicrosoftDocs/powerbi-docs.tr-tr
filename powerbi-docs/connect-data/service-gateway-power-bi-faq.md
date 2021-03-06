---
title: Şirket içi veri ağ geçidi hakkında SSS - Power BI
description: Bu makale Power BI için şirket içi veri ağ geçidi ile ilgili SSS bölümüdür. Power BI’da kullanılan ağ geçidi ile ilgili sıkça sorulan sorular, bu makalede bir araya getirilmiştir.
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: f9a51e6150c7ae351cea968c0d7ea39d2d0d6c32
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96392232"
---
# <a name="on-premises-data-gateway-faq---power-bi"></a>Şirket içi veri ağ geçidi hakkında SSS - Power BI

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

## <a name="power-bi"></a>Power BI

**Soru:** Şirket içi veri ağ geçidini (kişisel mod) yükseltmem gerekir mi?

**Cevap:** Hayır, Power BI için ağ geçidini (kişisel mod) kullanmaya devam edebilirsiniz.

**Soru:** Ağ geçidini yüklemek ve bunu Power BI hizmetinde yönetmek için herhangi bir özel izin gerekir mi?

**Cevap:** Özel izin gerekmez.

**Soru:** Şirket içi veri kaynaklarına bağlanan Power Pivot veri modelleri içeren Excel çalışma kitaplarını karşıya yükleyebilir miyim? Bu senaryo için bir ağ geçidi gerekir mi? 

**Cevap:** Evet, çalışma kitabını karşıya yükleyebilirsiniz. Ayrıca, bunun için bir ağ geçidi gerekmez. Ancak, veriler Excel veri modelinde yer aldığı için Power BI'da Excel çalışma kitabını temel alan raporlar canlı olmaz. Power BI'daki raporları yenilemek için her seferinde, güncelleştirilmiş bir çalışma kitabını yeniden karşıya yüklemeniz gerekir. Alternatif olarak, zamanlanmış yenileme ile ağ geçidini de kullanabilirsiniz.

**Soru:** Kullanıcılar bir DirectQuery bağlantısı içeren panolar paylaşırsa diğer kullanıcılar aynı izinlere sahip olmasa bile verileri görebilir mi? 

**Cevap:** Azure Analysis Services'e bağlı bir pano ile ilgili olarak kullanıcılar, yalnızca erişim sahibi oldukları verileri görebilir. Kullanıcılar aynı izinlere sahip değilse herhangi bir veri göremez. Diğer veri kaynaklarında ise tüm kullanıcılar, veri kaynağı için yönetici tarafından girilen kimlik bilgilerini paylaşır.

**Soru:** Oracle sunucuma neden bağlanamıyorum? 

**Cevap:** Oracle sunucunuza bağlanmak için Oracle istemcisini yüklemeniz ve tnsnames.ora dosyasını doğru sunucu bilgileriyle yapılandırmanız gerekebilir. Bu, ağ geçidinin dışında ayrı bir yüklemedir. Daha fazla bilgi için bkz. [Oracle istemcisini yükleme](service-gateway-onprem-manage-oracle.md#install-the-oracle-client).

**Soru:** R betikleri kullanıyorum. Bu destekleniyor mu?

**Yanıt**: R betikleri yalnızca kişisel mod için desteklenir.

## <a name="analysis-services-in-power-bi"></a>Power BI’da Analysis Services

**Soru:** Analysis Services’a yönelik özel etkin kullanıcı adı eşlemeleri oluşturmak için msmdpump.dll kullanabilir miyim? 

**Cevap:** Hayır. Bu kullanım şu anda desteklenmiyor.

**Soru:** Ağ geçidini kullanarak çok boyutlu (OLAP) bir örneğe bağlanabilir miyim? 

**Cevap:** Evet. Şirket içi veri ağ geçidi, Analysis Services Tablolu ve Çok Boyutlu modellere yönelik canlı bağlantıları desteklemektedir.

**Soru:** Ağ geçidini, Windows kimlik doğrulaması kullanan şirket içi sunucumdan farklı etki alanındaki bir bilgisayara yüklersem ne olur? 

**Cevap:** Bununla ilgili kesin bir cevap verilemez. Bu tamamen iki etki alanı arasındaki güven ilişkisine dayalıdır. İki farklı etki alanı bir güvenilir etki alanı modelindeyse ağ geçidi, Analysis Services sunucusuna bağlanabilir ve etkin kullanıcı adı çözümlenebilir. Aksi takdirde oturum açma hatasıyla karşılaşabilirsiniz.

**Soru:** Şirket içi Analysis Services sunucuma geçirilen etkili kullanıcı adını nasıl bulabilirim? 

**Cevap:** Bu sorunun yanıtı [sorun giderme makalesinde](service-gateway-onprem-tshoot.md) verilmiştir.

## <a name="next-steps"></a>Sonraki adımlar

* [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](/data-integration/gateway/service-gateway-tshoot)

Başka bir sorunuz mu var? [Power BI Topluluğu](https://community.powerbi.com/)'nu deneyin.
