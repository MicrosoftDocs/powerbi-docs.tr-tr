---
title: Power BI ve ExpressRoute
description: Power BI ve ExpressRoute
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Administration
ms.openlocfilehash: faf438e9f76a7a929f7369dc91ef4edb4fbef42d
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="power-bi-and-expressroute"></a>Power BI ve ExpressRoute
**Power BI** ve **ExpressRoute** ile gizli Power BI verileriniz ve bağlantılarınız için daha yüksek düzeyde güvenlik sağlamak üzere, İnternet kullanmadan (veya bir ISP ortak konum özelliği kullanarak) kuruluşunuz ile Power BI arasında özel bir ağ bağlantısı oluşturabilirsiniz.

**ExpressRoute**, Azure veri merkezleri (Power BI'ın bulunduğu) ile şirket içi altyapınız veya Azure veri merkezleri ile ortak konum ortamınız arasında özel bağlantılar oluşturmanıza olanak sağlayan bir Azure hizmetidir.

![](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)

[ExpressRoute ile ilgili daha fazla bilgi](https://azure.microsoft.com/services/expressroute/) edinebilir veya [nasıl oturum açılacağını](https://azure.microsoft.com/pricing/details/expressroute/) öğrenebilirsiniz.

> [!NOTE]
> Power BI, [bu SSS](https://docs.microsoft.com/azure/expressroute/expressroute-faqs)'de açıklandığı şekilde Ortak eşleme modunda desteklenmektedir.
> 
> 

## <a name="power-bi-expressroute-exceptions"></a>Power BI ExpressRoute Özel Durumları
Power BI, Power BI'ın genel İnternet üzerinden veri aldığı veya gönderdiği birkaç özel durum hariç olmak üzere ExpressRoute ile uyumludur. Bu özel durumlar genellikle, en yakın **Content Delivery Network (CDN)** düğümünden indirilen tarayıcı yapılandırma dosyaları gibi statik veriler içerir. Power BI'ın tamamı için geçerli olan geniş kapsamlı özel durumların yanı sıra hizmete veya özelliğe özgü özel durumlar da mevcuttur. Bunların tamamı, aşağıdaki bölümlerde verilmiştir.

### <a name="overall-exceptions-to-power-bi-and-expressroute"></a>Power BI ve ExpressRoute ile ilgili Geniş Kapsamlı Özel Durumlar
Power BI'dan veya Power BI'a iletilen verilerin, özel ExpressRoute bağlantısı yerine genel İnternet üzerinden gönderilmesi **Power BI** ile **ExpressRoute** arasındaki özel durumlardan biridir.

ExpressRoute'un kullanıldığı Power BI'a ilişkin iki özel durum söz konusudur:

* **Content Delivery Network (CDN)** ve web sitelerinden indirilen statik dosyalar
* Genel İnternet üzerinden gönderilen **Telemetri** verileri

Power BI, gerekli statik içeriği ve dosyaları, coğrafi yerel ayara göre kullanıcılara genel İnternet üzerinden verimli bir şekilde dağıtmak için birden çok **Content Delivery Network (CDN)** veya web sitesi kullanır. Bu statik dosyalar ürün indirmelerini (**Power BI Desktop**, **şirket içi veri ağ geçidi** veya çeşitli bağımsız hizmet sağlayıcılarından **Power BI İçerik Paketleri** gibi), Power BI ile sonraki bağlantıları başlatmak ve kurmak için kullanılan tarayıcı yapılandırma dosyalarını, başlangıçtaki güvenli Power BI oturum açma sayfasını (gerçek kimlik bilgileri yalnızca ExpressRoute üzerinden gönderilir) içerir.   

Belirli **telemetri verileri** de genel İnternet ve ExpressRoute üzerinden gönderilir. Telemetri verileri; kullanımı ve etkinliği izlemek için kullanılan hizmetlere iletilen kullanım istatistiklerini ve benzeri verileri içerir.

### <a name="power-bi-saas-application-and-expressroute"></a>Power BI SaaS Uygulaması ve ExpressRoute
Kullanıcı, Power BI hizmetine yönelik bir bağlantı başlattığında (powerbi.com veya Cortana yoluyla) Power BI Giriş Sayfası, oturum açma sayfası ve tarayıcıyı Power BI'a bağlanmaya ve Power BI ile etkileşim kurmaya hazırlayan statik dosyalar genel İnternet üzerinden bağlantı kuran bir CDN veya web sitelerinden alınır.

Oturum açma işlemi gerçekleştiğinde, sonraki Power BI veri etkileşimleri, genel İnternet verilerine bağlı belirli özellikler ve hizmetlere ilişkin bir özel durum ile ExpressRoute üzerinden gerçekleşir:

* **Harita görselleri** için Bing Virtual Earth hizmeti veya Bing coğrafi kodlama hizmeti ile genel İnternet üzerinden kurulan bağlantı ve veri iletimi gereklidir.
* **Cortana** ile Power BI tümleştirmesi için genel İnternet üzerinden Bing erişimi gereklidir.
* Bir kullanıcı tarafından resim pencere öğesi veya video gibi **özel bağlantılar** eklendiğinde Power BI, ExpressRoute kullanımından bağımsız olarak kullanıcı tarafından sağlanan bağlantıya dayalı verileri ister.
* Kullanıcılar **geri bildirimlerini Power BI'a**, iletim için genel İnternet kullanan User Voice geri bildirim mekanizması ile metin (ve isteğe bağlı olarak resim) biçiminde gönderebilir.
* **Bing News içerik sağlayıcısı** Bing'den içerik indirirken genel İnternet'i kullanır.
* **Uygulamalara** (örneğin, içerik paketleri) bağlanırken genellikle kullanıcıların, SaaS sağlayıcısı tarafından sunulan sayfaları kullanarak kimlik bilgilerini ve ayarları girmesi gerekir. Bu tür sayfalar ExpressRoute kullanabilir veya kullanmayabilir.

| Kullanıcı Etkinliği | Hedef |
| --- | --- |
| Giriş sayfası (oturum açmadan önceki) |`maxcdn.bootstrapcdn.com ; ajax.aspnetcdn.com ; netdna.bootstrapcdn.com ; cdn.optimizely.com; google-analytics.com ` |
| Oturum açma |`*.mktoresp.com ; *.aadcdn.microsoftonline-p.com ; *.msecnd.com ; *.localytics.com ; ajax.aspnetcdn.com` |
| Pano, rapor, veri kümesi yönetimi (haritaları ve coğrafi kodlamayı içerir) |`*.localytics.com ; *.virtualearth.net ; platform.bing.com; powerbi.microsoft.com; c.microsoft.com; app.powerbi.com; *.powerbi.com; dc.services.visualstudio.com ` |
| Destek |`support.powerbi.com ; powerbi.uservoice.com ; go.microsoft.com ` |

### <a name="power-bi-desktop-and-expressroute"></a>Power BI Desktop ve ExpressRoute
Aşağıdaki listede verilen birkaç özel durum dışında Power BI Desktop da ExpressRoute ile uyumludur:

* Kullanıcıların Power BI Desktop'ın en son sürümünü kullanıp kullanmadığını belirlemek için kullanılan **güncelleştirme bildirimleri**, genel İnternet üzerinden gönderilir.
* Bazı **telemetri verileri**, genel İnternet üzerinden gönderilir.
* **Harita görselleri** için **Bing Virtual Earth** hizmeti veya **Bing coğrafi kodlama** hizmeti ile her biri genel İnternet üzerinden kurulan bağlantı ve veri iletimi gereklidir.
* **Web** veya üçüncü taraf SaaS sağlayıcıları gibi çeşitli veri kaynaklarından yapılan **Veri Al** işlemi, genel İnternet üzerinden gerçekleştirilir.

### <a name="power-bi-paas-and-expressroute"></a>Power BI PaaS ve ExpressRoute
Power BI, geliştiricilerin özelleştirilmiş Power BI çözümleri ve uygulamaları oluşturmasına olanak sağlayan API'ler ve diğer platform temelli özellikler sunar. Power BI PaaS verileri genel İnternet üzerinden iletilirken, bu konu başlığında bahsedilen telemetri ve CDN verilerine ek olarak aşağıdaki hizmetler kullanılır:

| PaaS Etkinliği | Kullanılan ek hedefler |
| --- | --- |
| Genel kullanıma açık şekilde ekleme (telemetri) |`c1.microsoft.com` |
| Özel görseller (CDN) |`*.azureedge.net` |

Bazı **özel görseller** üçüncü taraflarca oluşturulurken bazıları Microsoft tarafından oluşturulur. Bunlar ExpressRoute kullanabilir veya kullanmayabilir.

### <a name="power-bi-mobile-and-expressroute"></a>Power BI Mobil ve ExpressRoute
Bu belge, Power BI Mobil uygulamalarına ilişkin kullanımı içermez.  

### <a name="on-premises-data-gateway-and-expressroute"></a>Şirket içi veri ağ geçidi ve ExpressRoute
Power BI ile bir **şirket içi ağ veri geçidi** kullanıldığında iletimler, ExpressRoute ile uyumludur ancak bu konu başlığındaki **Power BI SaaS Uygulaması ve ExpressRoute** bölümünde belirtilen kullanıcı etkinlikleri ile ilgili özel durum burada da geçerlidir.  

