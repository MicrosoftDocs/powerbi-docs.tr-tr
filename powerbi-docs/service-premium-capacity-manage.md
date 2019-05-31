---
title: Microsoft Power BI Premium kapasiteleri yönetme
description: Power BI Premium kapasiteleri için yönetim görevleri açıklanır.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: e4bb907e12d3c0b07408f069d9b238599756e8e0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565238"
---
# <a name="managing-premium-capacities"></a>Premium kapasite yönetimi

Power BI Premium'u yönetme, oluşturma, yönetme ve izleme Premium kapasiteleri içerir.

## <a name="creating-and-managing-capacities"></a>Oluşturma ve kapasite yönetme

**Kapasite ayarlarını** Power BI Yönetici portalı'nın sayfasında, satın alınan sanal çekirdek ve Premium kapasiteler sayısını görüntüler. Sayfa, Office 365 genel yöneticileri veya hizmet yöneticilerinin Power BI Premium kapasiteleri kullanılabilir çekirdek oluşturmak veya var olan Premium kapasiteleri değiştirmek için sağlar.

Premium kapasiteye oluşturulurken, yöneticilerin tanımlamak için gereklidir:

- Kapasite adı (kiracıda benzersiz).
- Kapasite admin(s).
- Kapasite boyutu.
- Veri yerleşikliği için bölge.

En az bir kapasite Yöneticisi atanması gerekir. Kapasite Yöneticisi olarak atanabilmek kullanıcılar şunları yapabilir:

- Çalışma alanları kapasiteye atayın.
- Ek kapasite yöneticileri veya (kapasiteye çalışma alanlarını atamak bunları etkinleştirmek için) atama izinleri olan kullanıcılar eklemek için kullanıcı izinleri yönetin.
- Sayfalandırılmış raporlar ve veri akışlarını iş yükleri için en fazla bellek kullanımını yapılandırmak için iş yüklerini yönetin.
- Tüm işlemler nedeniyle bir sistem aşırı sıfırlama yeteneği, yeniden başlatın.

Kapasite yöneticileri, çalışma alanı izinlerini açıkça atanmadığı sürece çalışma içeriğe erişemez. Bunlar ayrıca tüm Power BI yönetici alanlarına (açıkça atanan sürece) kullanım ölçümleri, Denetim günlükleri veya Kiracı ayarları gibi erişiminiz yok. Önemlisi, kapasite yöneticileri yeni kapasiteler oluşturun veya mevcut kapasitelerin ölçeklendirmek için izniniz yok. Tek başına kapasite temelinde Yöneticiler atanan, bunlar için sağlama yalnızca görüntüleme ve atanmış olan kapasiteleri yönetme.

Kapasite boyutu havuzunda kullanılabilir sanal çekirdek sayısına göre kısıtlı bir kullanılabilir SKU seçenekleri listesi seçilir. Bilgisayarından kaynağı havuzdan birden çok kapasiteler oluşturmak mümkündür veya daha fazla SKU satın. Örneğin, bir P3 SKU (32 çekirdek), üç kapasiteler oluşturmak için kullanılabilir: bir P2 (16 çekirdek) ve iki P1 (2 x 8 çekirdek). Gelişmiş performans ve ölçek elde edilebilir daha küçük boyutlu kapasiteler oluşturarak açıklandığı [en iyi duruma getirme Premium kapasiteleri](service-premium-capacity-optimize.md) makalesi. Aşağıdaki görüntüde bir örnek kurulumu için beş Premium kapasiteleri oluşan kurgusal Contoso kuruluşundaki gösterilmektedir (P1 ve 2 x 3 x P3) içeren her uygulama çalışma alanları ve paylaşılan kapasiteye birkaç çalışma alanları.

![Kurgusal Contoso kuruluş için bir örnek Kurulumu](media/service-premium-capacity-manage/contoso-organization-example.png)

Premium kapasite, Power BI kiracınızın çoklu coğrafi bilinen, giriş bölgesi dışında bir bölgeye atanabilir. Çoklu coğrafi hangi Power BI içeriğinizi bulunduğu tanımlı coğrafi bölgedeki veri merkezleri üzerinde yönetimsel denetime sağlar. Çoklu coğrafi dağıtımı için stratejinin için genellikle Kurumsal veya kamu uyumluluk yerine performans ve ölçek. Rapor ve Pano yükleme, giriş bölgesini meta veri isteklerine yine de içerir. Daha fazla bilgi için bkz. [çoklu coğrafi Power BI Premium desteği](service-admin-premium-multi-geo.md).

Power BI hizmeti yöneticileri ve Office 365 genel yöneticileri, Premium kapasiteleri değiştirebilirsiniz. Özellikle, yönetici şunları yapabilir:

- Kapasite boyutunu ölçek artırmayı veya ölçek azaltma kaynakları değiştirin.
- Kapasite yöneticileri ekleyip yeniden açın.
- Atama izinleri olan kullanıcılar ekleyip yeniden açın.
- Ek iş yüklerinin ekleyip yeniden açın.
- Bölgeleri değiştirin.

Atama izinleri, belirli bir Premium kapasiteye çalışma alanı atamak için gereklidir. Kuruluşun tamamı, belirli kullanıcılar veya gruplar için izinleri verilebilir.

Varsayılan olarak, Power BI sorgularını çalıştırmayla ilgili iş yükleri Premium kapasiteleri destekler. Premium kapasiteler ayrıca ek iş yüklerinin destekler: **Yapay ZEKA (Bilişsel hizmetler)** , **sayfalandırılmış raporlar**, ve **veri akışlarını**. Her iş yükü, iş yükü tarafından kullanılabilecek maksimum bellek (olarak, toplam kullanılabilir belleğin yüzdesi cinsinden) yapılandırma gerektirir. En fazla bellek ayırmaları artırma'nün barındırılabilir etkin modelleri sayısı ve aktarım hızını yenilemeleri etkileyebilir anlamak önemlidir. 

Bellek, veri akışlarını için dinamik olarak ayrılır, ancak sayfalandırılmış raporlar için statik olarak ayrılır. Statik olarak en fazla belleği tahsis etme nedenini sayfalandırılmış raporlar içerdiği kapasite alanı güvenli içinde çalışmasıdır. Modelleri yükleme için kullanılabilir belleği azaltır gibi raporları bellek ayarı sayfalandırılmış dikkatli olunması. Daha fazla bilgi için bkz. [varsayılan bellek ayarları](service-admin-premium-workloads.md#default-memory-settings).

Premium kapasite siliniyor mümkündür ve kendi çalışma alanları ve içeriğinin silinmesine neden olmaz. Bunun yerine, tüm atanmış çalışma alanlarına paylaşılan kapasiteye taşınır. Premium kapasite farklı bir bölgede oluşturduğunuzda, çalışma alanı ana bölge paylaşılan kapasiteye taşınır.

### <a name="assigning-workspaces-to-capacities"></a>Kapasitelere artırmak için çalışma alanları atama

Çalışma alanı atanabilir bir Power BI Yönetici portalı'nda veya bir uygulama çalışma alanını Premium kapasiteye **çalışma** bölmesi.

Kapasite yöneticileri yanı sıra Office 365 genel Yöneticiler veya Power BI hizmet yöneticileri, çalışma alanlarını Power BI Yönetici portalı'nda topluca ekleyebilirsiniz. Atanan toplu uygulayabilirsiniz:

- **Kullanıcılara göre çalışma alanları** -kişisel çalışma alanlarını dahil olmak üzere söz konusu kullanıcıların sahip olduğu tüm çalışma alanlarını Premium kapasiteye atanır. Zaten farklı bir Premium kapasiteye atanmış eklediğinizde bu çalışma alanlarının yakaladığı eklersiniz. Ayrıca, kullanıcıların çalışma alanı atama izinleri atanır.

- **Belirli çalışma alanları**
- **Tüm kuruluşun çalışma alanlarını** -kişisel çalışma alanlarını dahil olmak üzere tüm çalışma alanlarını Premium kapasiteye atanır. Tüm mevcut ve gelecekteki kullanıcılara çalışma alanı atama izinleri atanır. Bu yaklaşım önerilmez. Daha fazla hedeflenen bir yaklaşım tercih edilir.

Kullanarak, bir çalışma alanı Premium kapasiteye eklenebilir **çalışma** kullanıcı bölmesinde hem bir çalışma alanı yöneticisi olan ve atama izinlerine sahip.

![Bir çalışma alanı Premium kapasiteye atamak için çalışma alanı bölmesinde kullanma](media/service-premium-capacity-manage/assign-workspace-capacity.png)

Çalışma alanı yöneticileri, bir çalışma alanına bir kapasiteden (paylaşılan kapasiteye) atama izni gerek kalmadan kaldırabilirsiniz. Çalışma alanını yeniden yerleştirir paylaşılan kapasiteye çalışma alanlarını adanmış kapasitelerini etkili bir şekilde kaldırılıyor. Desteklenen izinler'i aştığında kullanıcılar veya zamanlanmış yenileme askıya alınması, bir çalışma alanını Premium kapasiteden kaldırmak, örneğin, paylaşılan içeriği Power BI ücretsiz kullanılamaz hale výsledek olumsuz etkileri olabilecek bir not lisanslı Paylaşılan kapasite tarafından.

Power BI hizmetinde çalışma alanı Premium kapasiteye atanmış kolayca çalışma alanı adı daireler donatır baklava simgesi tarafından tanımlanır.

![Bir Premium kapasiteye atanmış bir çalışma alanı tanımlama](media/service-premium-capacity-manage/premium-diamond-icon.png)

## <a name="monitoring-capacities"></a>İzleme kapasiteleri

Premium kapasiteler izleme kapasiteleri nasıl performans gösterdiğini anlamak yöneticilerine sağlar. Kapasite Power BI Yönetici portalı kullanılarak izlenebilir veya **Power BI Premium kapasite ölçümleri** (Power BI) uygulama.

### <a name="power-bi-admin-portal"></a>Power BI Yönetim portalı

Her kapasiteye ilişkin Yönetim Portalı'nda **sistem durumu** sekmesi, kapasite ve etkinleştirilen her iş yükü için Özet ölçümleri sağlar. Ölçümler son yedi gün içindeki ortalama gösteriyor.  

Kapasite düzeyinde ölçümler, tüm etkin iş yüklerini toplu. Aşağıdaki ölçümler sağlanır:

- **CPU kullanımı** -toplam kullanılabilir CPU yüzdesi cinsinden ortalama CPU kullanımı için kapasite sağlar.  
- **BELLEK kullanımı** -sağlar ortalamayı kapasitesi için kullanılabilir belleğin toplam olarak bellek kullanımı (GB cinsinden). 

Etkin her iş yükü için CPU kullanımı ve bellek kullanımı, bir dizi belirli iş yükü ölçümlerinin yanı sıra sağlanır. Örneğin, veri akışı iş yükü için **toplam** toplam yenilemeler için her veri akışı gösterir ve **ortalama süresi** yenileme ortalama süresi için veri akışı gösterir.

![Portalda kapasite sistem durumu sekmesi](media/service-premium-capacity-manage/admin-portal-health-dataflows.png)

Her iş yükü için kullanılabilen tüm ölçümler hakkında daha fazla bilgi için bkz: [izleme kapasiteleri Yönetim Portalı'nda](service-admin-premium-monitor-portal.md).

İzleme özellikleri Power BI Yönetici portalı'nda, anahtar kapasite ölçümlerini hızlı bir özetini sağlamak üzere tasarlanmıştır. Daha ayrıntılı izleme için kullanmanız önerilir **Power BI Premium kapasite ölçümleri** uygulama.

### <a name="power-bi-premium-capacity-metrics-app"></a>Power BI Premium kapasite ölçümleri uygulama

[Power BI Premium kapasite ölçümleri uygulama](https://appsource.microsoft.com/product/power-bi/pbi_pcmm.pbi-premiumcapacitymonitoring?tab=Overview) bir Power BI uygulaması kapasite yöneticileri için kullanılabilir ve gibi başka bir Power BI uygulaması yüklü. Bu, bir Pano ve rapor içerir.

![Power BI Premium kapasite ölçümleri uygulama](media/service-premium-capacity-manage/capacity-metrics-app.png)

Uygulamayı açtığında, kullanıcının bir kapasite Yöneticisi olduğu tüm kapasitelerin toplu bir görünümünü ifade çok sayıda kutucukları sunmak için Pano yüklenir Pano Düzeni beş ana bölümleri içerir:

- **Genel Bakış** -uygulama sürümü, sayısı kapasitelerini ve çalışma alanları
- **Sistem Özet** -bellek ve CPU ölçümleri
- **Veri kümesi Özet** - sayı veri kümeleri, DQ/LC, yenileme ve sorgu ölçümleri
- **Veri akışı özeti** - sayı veri akışlarını ve veri kümesi ölçümleri
- **Sayfalandırılmış rapor özeti** - yenileyin ve ölçümleri görüntüleyin

Pano kutucukları da sabitlenmiş, temel alınan rapor, herhangi bir Pano kutucuğa tıklayarak erişilebilir. Bu Pano bölümlerin her birinde daha ayrıntılı bir bakış sağlar ve etkileşimli filtrelemeyi destekler. 

Filtreleme tarih aralığı, kapasite, çalışma ve iş yükü (rapor, veri kümesi, veri akışı) dilimleyicilerden ayarlayarak gerçekleştirilebilir ve rapor öğeleri seçerek geçilecek görselleri rapor sayfasını filtreleme. Çapraz filtreleme, belirli süreler, kapasite, çalışma alanları, veri kümeleri, vb. daraltmak için güçlü bir tekniktir ve kök neden analizi gerçekleştirirken çok yararlı olabilir.

Pano ve rapor ölçümler uygulama hakkında ayrıntılı bilgi için bkz. [İzleyici Premium kapasiteleri uygulamasıyla](service-admin-premium-monitor-capacity.md).

### <a name="interpreting-metrics"></a>Ölçümleri yorumlama

Ölçümler, kaynak kullanımı ve iş yükü etkinliği temel bir anlayış oluşturmak için izlenmelidir. Kapasite yavaşlar izlemek için hangi ölçümleri anlamak önemlidir ve sonuçları yapabilirsiniz.

İdeal olarak, sorgu rapor kullanıcıları duyarlı deneyimler sunun ve daha yüksek sorgu aktarım hızını sağlamak için bir saniye içinde tamamlanmalıdır. -Yenileme dahil olmak üzere - arka plan işlemlerini tamamlamak için daha uzun süreleri alırken genellikle daha düşük bir sorun olur.

Genel olarak, yavaş raporları bir Aşırı ısıtma kapasitesinin bir göstergesi olabilir. Raporları yüklenmesi başarısız olduğunda bir aşırı ısıtılan kapasitesinin bir göstergesi budur. Her iki durumda, kök nedeni de dahil olmak üzere birçok faktöre bağlı olabilir:

- **Sorguları başarısız** kesinlikle bellek baskısı belirtmek ve belleğe bir model yüklenemedi. Power BI hizmetinde, 30 saniye başarısız olmadan önce bir model yük dener.

- **Aşırı sorgu bekleme sürelerini** birkaç nedeni olabilir:
  - Power BI hizmete ilk gereksinimini modellere çıkarın ve How-to-edilecek sorgulanan modeli (tek başına daha yüksek veri kümesi çıkarma oranları göstergesidir kapasite stres uzun belirtmek bellek çok yavaş sorgu bekleme süresini tarafından eşlik sürece olmadığından geri çağırma) yükleyin.
  - Model yükleme süreleri (büyük bir modelin belleğe yüklemek için özellikle bekleme).
  - Uzun süre çalışan sorgular.
  - Çok fazla LC\DQ bağlantılar (kapasite sınırları aşan).
  - CPU doygunluğu.
  - Karmaşık rapor görselleri (her görsel için bir sorgu olduğunu geri çağırma) sayfasında aşırı sayıda ile tasarlar.

- **Uzun süreler'ı sorgu** modeli tasarımı, özellikle birden fazla veri kümesi bir kapasitede etkin olan ve yalnızca bir veri kümesi uzun sorgu süreleri üretme için optimize edilmediğinden emin belirtebilirsiniz. Bu, kapasite yeterince kaynak var olduğunu ve soru veri kümesi iyinin ya da yalnızca yavaş olduğunu önerir. Diğer işlemler tarafından gerekli kaynaklara erişim engelleyebileceği uzun süre çalışan sorguların sorunlara neden olabilir.
- **Uzun bekleme süresini'ni Yenile** yetersiz bellek nedeniyle bellek kullanan çok sayıda etkin model belirtin veya sorunlu bir yenileme diğer engelliyor (paralel yenileme sınırları aşan) yeniler.

Ölçümleri kullanma konusunda daha ayrıntılı bir açıklama ele alınmıştır [en iyi duruma getirme Premium kapasiteleri](service-premium-capacity-optimize.md) makalesi.

## <a name="acknowledgements"></a>Onayları

Bu makale, Peter Myers, veri platformu MVP ve bağımsız BI Uzmanı ile yazılmıştır [Bitsel çözümleri](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Premium kapasiteler en iyi duruma getirme](service-premium-capacity-optimize.md)   
> [!div class="nextstepaction"]
> [Premium kapasitede iş yüklerini yapılandırma](service-admin-premium-workloads.md)   

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

||||||
