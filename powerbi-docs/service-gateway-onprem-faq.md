---
title: "Şirket içi veri ağ geçidi hakkında SSS"
description: "Bu makalede şirket içi veri ağ geçidi ile ilgili sıkça sorulan sorulara yer verilmiştir. Ağ geçidi ile ilgili sıkça sorulan sorular tek bir noktada toplanmıştır."
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 626a99467dc02481e004e0472d38cb733f836332
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="on-premises-data-gateway-faq"></a>Şirket içi veri ağ geçidi hakkında SSS
<!-- Shared FAQ shared Include -->
[!INCLUDE [gateway-onprem-faq-shared-include](./includes/gateway-onprem-faq-shared-include.md)]

## <a name="analysis-services"></a>Analysis Services
**Soru:** Analysis Services'e yönelik özel etkin kullanıcı adı eşlemeleri oluşturmak için msdmpump.dll kullanabilir miyim?  
**Cevap:** Hayır. Bu özellik şu anda desteklenmiyor.

**Soru:** Ağ geçidini kullanarak çok boyutlu (OLAP) bir örneğe bağlanabilir miyim?  
**Cevap:** Evet! Şirket içi veri ağ geçidi, Analysis Services Tablolu ve Çok Boyutlu modellere yönelik canlı bağlantıları desteklemektedir.

**Soru:** Ağ geçidini, Windows kimlik doğrulaması kullanan şirket içi sunucumdan farklı etki alanındaki bir bilgisayara yüklersem ne olur?  
**Cevap:** Bununla ilgili kesin bir cevap verilemez. Bu tamamen iki etki alanı arasındaki güven ilişkisine dayalıdır. İki farklı etki alanı bir güvenilir etki alanı modelindeyse ağ geçidi, Analysis Services sunucusuna bağlanabilir ve etkin kullanıcı adı çözümlenebilir. Aksi halde oturum açma hatasıyla karşılaşabilirsiniz.

**Soru:** Şirket içi Analysis Services sunucuma geçirilen etkin kullanıcı adını nasıl bulabilirim?  
**Cevap:** Bu sorunun cevabı [sorun giderme makalesinde](service-gateway-onprem-tshoot.md) verilmiştir.

**Soru:** Analysis Services'de 25 veritabanım var, bunların hepsini ağ geçidi için tek seferde etkinleştirmenin bir yolu var mı?  
**Cevap:** Hayır. Yol haritasında buna yer verilmiştir ancak henüz bir zaman aralığı belirlenmemiştir.

## <a name="administration"></a>Yönetim
**Soru:** Bir ağ geçidinin birden çok yöneticisi olabilir mi?  
**Cevap:** Evet! Bir ağ geçidini yönetirken yönetici sekmesine giderek başka yöneticiler ekleyebilirsiniz.

**Soru:** Ağ geçidi yöneticisi, ağ geçidinin yüklü olduğu makinede de yönetici olmalı mıdır?  
**Cevap:** Hayır. Ağ geçidi yöneticisi, ağ geçidini hizmetten yönetmek için kullanılır.

**Soru:** Kuruluşumdaki kullanıcıların bir ağ geçidi oluşturmasını engelleyebilir miyim?  
**Cevap:** Hayır. Yol haritasında buna yer verilmiştir ancak henüz bir zaman aralığı belirlenmemiştir.

**Soru:** Kuruluşumdaki ağ geçitlerinin kullanım ve istatistik bilgilerini edinebilir miyim?  
**Cevap:** Hayır. Yol haritasında buna yer verilmiştir ancak henüz bir zaman aralığı belirlenmemiştir.

## <a name="power-bi"></a>Power BI
**Soru:** Kişisel ağ geçidini yükseltmem gerekiyor mu?
**Cevap:** Hayır, Power BI için kişisel ağ geçidini kullanmaya devam edebilirsiniz.

**Soru:** Power BI'daki bir panoda bulunan kutucuklar, şirket içi veri ağ geçidi yoluyla bağlanıldığında ne sıklıkla yenilenir?  
**Cevap:** Yaklaşık on dakikada bir. DirectQuery bağlantıları tam olarak bu şekilde çalışır. Bu, bir kutucuğun her on dakikada bir şirket içi sunucunuza sorgu göndereceği ve yeni veriler göstereceği anlamına gelmez.

**Soru:** Şirket içi veri kaynaklarına bağlanan Power Pivot veri modelleri içeren Excel çalışma kitaplarını karşıya yükleyebilir miyim? Bu senaryo için bir ağ geçidi gerekir mi?  
**Cevap:** Evet, çalışma kitabını karşıya yükleyebilirsiniz. Ayrıca, bunun için bir ağ geçidi gerekmez. Ancak, veriler Excel veri modelinde yer alacağı için Power BI'da Excel çalışma kitabını temel alan raporlar canlı olmaz. Power BI'daki raporları yenilemek için her seferinde, güncelleştirilmiş bir çalışma kitabını yeniden karşıya yüklemeniz gerekir. Alternatif olarak, zamanlanmış yenileme ile ağ geçidini de kullanabilirsiniz.

**Soru:** Kullanıcılar bir DirectQuery bağlantısı içeren panolar paylaşırsa diğer kullanıcılar aynı izinlere sahip olmasa bile verileri görebilir mi?  
**Cevap:** Analysis Services'e bağlı bir pano ile ilgili olarak kullanıcılar, yalnızca erişim sahibi oldukları verileri görebilir. Kullanıcılar aynı izinlere sahip değilse herhangi bir veri göremez. Diğer veri kaynaklarında ise tüm kullanıcılar, veri kaynağı için yönetici tarafından girilen kimlik bilgilerini paylaşır.

**Soru:** Oracle sunucuma neden bağlanamıyorum?  
**Cevap:** Oracle sunucunuza bağlanmak için Oracle istemcisini yüklemeniz ve tnsnames.ora dosyasını doğru sunucu bilgileriyle yapılandırmanız gerekebilir. Bu, ağ geçidinin dışında ayrı bir yüklemedir. Daha fazla bilgi için bkz. [Installing the Oracle Client (Oracle İstemcisini yükleme)](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client).

**Soru:** Ağ geçidi ExpressRoute ile çalışır mı?  
**Cevap:** Evet. ExpressRoute ve Power BI hakkında daha fazla bilgi için bkz. [Power BI ve ExpressRoute](service-admin-power-bi-expressroute.md).

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidi](service-gateway-onprem.md)  
[Şirket içi veri ağ geçidi (ayrıntılı)](service-gateway-onprem-indepth.md)  
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

