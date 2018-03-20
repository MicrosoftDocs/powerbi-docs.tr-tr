---
title: "Performans açısından en iyi Power BI yöntemleri"
description: "Bu makalede, Power BI’da hızlı ve güvenilir raporlar oluşturmaya yönelik rehberlik sağlanır"
services: powerbi
documentationcenter: 
author: MarkMcGeeAtAquent
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/12/2017
ms.author: v-mamcge
LocalizationGroup: Reports
ms.openlocfilehash: e584f48f5d3650821aac094ebfde7eef5261cc36
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="power-bi-performance-best-practices"></a>Performans Açısından En İyi Power BI Yöntemleri 
Bu makalede, Power BI’da hızlı ve güvenilir raporlar oluşturmaya yönelik rehberlik sunulur.  

## <a name="use-filters-to-limit-report-visuals-to-display-only-whats-needed"></a>Filtreleri kullanarak rapordaki görsel öğelerini yalnızca gerekli öğelerle sınırlayın 

Bir görsel öğenin görüntülemesi gereken veri arttıkça yüklenme hızı düşer. Bu ilke açık olsa da sık sık unutulur. Örneğin, büyük bir veri kümeniz olduğunu varsayalım. Bunun üzerine, tablonun tablosunu içeren bir rapor oluşturuyorsunuz. Çoğu birkaç düzine satırla ilgilenen son kullanıcılar, sayfadaki dilimleyicileri kullanarak istedikleri satırlara gidebiliyor.

Sık yapılan bir hata, tablonun varsayılan görünümünün filtrelenmemiş (100 milyondan fazla satır) olmasıdır. Her yenilemede bu satırlara ait verilerin belleğe yüklenmesi ve sıkıştırmasının açılması gerekir. Bu, çok büyük bellek yüklerine yol açar. Çözüm: “İlk N” filtresini kullanarak tablonun görüntülediği en fazla öğe sayısını azaltın. En fazla öğe sayısı, kullanıcılar için gerekenden çok daha fazla (örneğin 10.000) olabilir. Bunun sonucunda, son kullanıcı deneyimi değişmez ancak raporun bellek kullanımı birkaç kat azalır ve performans da buna göre artar. 
 
Raporlarınızdaki tüm görsel öğeler için yukarıdakine benzer bir yaklaşım kesinlikle önerilir. Kendinize bir görsel öğedeki tüm verilerin gerekli olup olmadığını sorun. Son kullanıcı deneyimini olabildiğince az etkileyecek şekilde filtre uygulayarak görsel öğede gösterilen veri miktarını azaltmanın bir yolu var mı? Özellikle de tabloların çok pahalı olabileceğini unutmayın. 
 
## <a name="limit-visuals-on-report-pages"></a>Rapor sayfalarındaki görsel öğeleri sınırlama 
Yukarıdaki ilke, aynı şekilde belirli bir rapordaki görsel öğe sayısı için de geçerlidir. Bir rapordaki görsel öğe sayısını yalnızca gerekli olanla kısıtlamanız kesinlikle önerilir. Detaylandırma sayfaları, raporu tıka basa görselle doldurmadan ek ayrıntı sağlamanın harika bir yoludur.  
 
## <a name="optimize-your-model"></a>Modelinizi iyileştirin 
En iyi yöntemlerden bazıları: 
 
- Kullanılmayan tablo veya sütunlar mümkünse kaldırılmalıdır. 
- Kardinalitesi yüksek olan (örneğin, milyonlarca ayrı değer) sütunlarda ayrı sayımlardan kaçının.  
- Gereksiz düzeyde hassaslığa ve yüksek kardinaliteye sahip alanlardan kaçınmak için gerekli adımları uygulayın. Örneğin, yüksek oranda benzersiz datetime değerlerini ay, yıl, tarih, vb. gibi ayrı sütunlara bölebilirsiniz. Veya mümkün olduğunda kardinaliteyi azaltmak için yüksek hassaslığa sahip alanlarda yuvarlamayı (örneğin, 13.29889 -> 13.3) kullanabilirsiniz. 
- Mümkün oldukça dize yerine tamsayı kullanın. 
- Bir tablodaki tüm satırları test etmesi gereken RANKX gibi DAX işlevlerine dikkat edin. En kötü senaryoda, tablo boyutundaki doğrusal artışlar nedeniyle bu işlevler çalışma sürenizi ve bellek gereksinimlerinizi birkaç katına çıkarabilir. 
- DirectQuery aracılığıyla veri kaynaklarına bağlanırken yaygın olarak filtrelenen veya dilimlenen sütunları yeniden dizine eklemeyi deneyin. Bu, raporun yanıt verme hızını önemli oranda artırır.  
 

DirectQuery için veri kaynaklarını iyileştirme hakkında daha fazla yönerge için bkz. [SQL Server 2016 Analysis Services’da DirectQuery](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/). 
 
## <a name="directquery-and-live-connection-understand-underlying-data-source-performance"></a>DirectQuery ve canlı bağlantı: temel veri kaynağının performansını anlama 

DirectQuery veya canlı bağlantı örneğinde, kullanıcılar bir Power BI raporunu ziyaret ettiğinde Power BI tarafından temel veri kaynağına gerçek zamanlı olarak sorgular gönderilir. Veri kaynağı sorgu verilerini döndürdüğünde rapor işlenir. Bunun sonucunda, bu durumlarda raporunuzun performansı büyük oranda temel veri kaynağına bağlıdır. 
 
Böyle durumlarda temel veri kaynağınızın performansını anlamanız önemli olur. Sorgu performansının anlaşılması için her veri kaynağının farklı araçları vardır. Örneğin, SQL Server ve Azure SQL tarafından sorguların geçmişini ve çalışma zamanı istatistiklerini yakalayan Query Store sağlanır. 
 
Genel bir kural olarak DirectQuery ve canlı bağlantı üzerinde oluşturulmuş Power BI raporlarını dağıtırken son kullanıcılarınızın Power BI Desktop’ta yapacağı işlemleri deneyin. Power BI Desktop’ta rapor yavaş yükleniyorsa, son kullanıcılarınız için hizmette de yavaş yükleneceği neredeyse kesindir. 
 
## <a name="directquery-best-practices"></a>En iyi DirectQuery yöntemleri 
Aşağıdaki bölümde, DirectQuery aracılığıyla bağlanmak için genel olarak en iyi yöntemler açıklanmıştır.
  
### <a name="db-design-guidance"></a>Veritabanı tasarım kılavuzu 
- Mümkün oldukça hesaplanmış sütunları ve ölçüleri kaynağa gönderin; bunlar kaynağa ne kadar yakın olursa performans olasılığı o kadar artar. 
- En iyi duruma getirin! Sorgularınız için yürütme planlarını anlayın, sık filtrelenen sütunlar için dizin ekleyin, vs. 

### <a name="modelling-guidance"></a>Modelleme kılavuzu 
- Çalışmaya Power BI Desktop'ta başlayın. 
- Sorgu Düzenleyicisi'nde karmaşık sorgular kullanmayın. 
- Sorgu Düzenleyicisi'nde göreli veri filtreleme kullanmayın.  
- Başlangıçta ölçüleri basit tutun ve kademeli olarak karmaşıklık ekleyin. 
- Hesaplanmış sütunlar ve benzersiz tanımlayıcı sütunlarında ilişki kullanmayın. 
- İlişkiler üzerinde “Bilgi Tutarlılığı Varsay” ayarını kullanmayı deneyin; çoğu durumda bunun yapılması sorgu performansını önemli ölçüde artırabilir.  

### <a name="general"></a>Genel 
- Önce filtre uygulayın. 
- Görsel öğeler arası etkileşimi kapatmayı göz önünde bulundurun; bunun yapılması, kullanıcılar çapraz vurgulama uygularken sorgu yükünü azaltır. 
- Yukarıda açıklandığı gibi, görsel öğe sayısını ve görsel öğe başına veri miktarını kısıtlayın. 
- Satır düzeyi güvenliğin etkinleştirilmesi, performansta önemli değişikliklere neden olabilir. Kullanıcılarınızın üstleneceği çeşitli satır düzeyi güvenlik rollerini test etmeyi unutmayın. 
- Uzun süre çalışan sorguların sistem kaynaklarını tekeline alamamasını sağlamak için sorgu düzeyinde zaman aşımlar uygulandığını unutmayın. 225 saniyeden uzun süren sorgular zaman aşımına uğrar ve görsel öğe düzeyinde bir hataya yol açar. 

## <a name="understanding-dashboards-and-query-caches"></a>Panoları ve sorgu önbelleklerini anlama 
Panolara sabitlenen görsel öğeler, pano yüklendiğinde sorgu önbelleği tarafından sunulur. Buna karşılık olarak, bir rapor ziyaret edildiği sırada, Power BI hizmetine (içeri aktarma durumunda) veya belirttiğiniz veri kaynağına (DirectQuery veya canlı bağlantı durumunda) yönelik sorgular anlık olarak gerçekleştirilir.  
 
> [!NOTE]
> Panoya canlı rapor kutucukları sabitlediğinizde bunlar sorgu önbelleğinden sunulmaz, bunun yerine rapor gibi davranır ve anlık olarak arka uç çekirdeklerine sorgu gerçekleştirir. 
 

Adından da anlaşılacağı gibi, veri kaynağını kullanmak yerine verilerin sorgu önbelleğinden alınması daha iyi ve daha tutarlı performans sağlar. Bu işlevin avantajından yararlanmanın bir yolu, panoları kullanıcılarınız için ilk giriş sayfası yapmaktır. Sık kullanılan ve istenen görsel öğeleri panolara sabitleyin. Bu sayede, panolar değerli bir “ilk savunma hattı” olur ve kapasite üzerinde daha az yük oluşturarak tutarlı performans sağlar. Kullanıcılar raporda gezinerek ayrıntıları araştırabilir.  
 

DirectQuery ve canlı bağlantı için bu sorgu önbelleğinin veri kaynağı sorgulanarak düzenli aralıklarla güncelleştirildiğini unutmayın. Varsayılan olarak bu işlem saat başı gerçekleşir, ancak veri kümesi ayarlarından yapılandırılabilir. Her sorgu önbelleği güncelleştirmesi, önbelleği güncelleştirmek için temel veri kaynağına sorgu gönderir. Oluşturulan sorgu sayısı, panoya sabitlenen ve bu veri kaynağını kullanan görsel öğe sayısına bağlıdır. Satır düzeyi güvenliğin etkin olması durumunda her farklı güvenlik bağlamı için sorgu oluşturulduğunu unutmayın. Örneğin, kullanıcılarınız iki farklı role ayrılıyorsa ve verilerin iki farklı görünümü varsa, sorgu önbelleği yenilendiği sırada iki sorgu kümesi oluşturulur. 
 
## <a name="understand-custom-visual-performance"></a>Özel görsel öğe performansını anlama 
Her bir özel görsel öğeyi gerekli testlere tabi tutarak öğe performansının yüksek olduğundan emin olun. Hatalı bir şekilde iyileştirilmiş özel görsel öğeler, raporun tamamının performansını olumsuz yönde etkileyebilir. 
 
## <a name="deep-dive-into-query-performance-with-sql-profiler-and-power-bi-desktop"></a>SQL Profiler ve Power BI Desktop ile sorgu performansına ayrıntılı bakış 
En çok zamanı ve kaynağı hangi görsel öğelerin harcadığına yönelik daha ayrıntılı bir bakış için Power BI Desktop’a SQL Profiler’ı bağlayarak sorgu performansının tam görünümünü elde edebilirsiniz. Yönergeler aşağıda verilmiştir: 
  
1. **SQL Server Profiler’ı yükleyin ve Power BI Desktop’ı çalıştırın** 

   SQL Server Profiler, SQL Server Management Studio’nun bir parçası olarak sunulmaktadır. 
 
2. **Power BI Desktop tarafından kullanılmakta olan bağlantı noktasını belirleme** 

   Komut istemini veya PowerShell’i yönetici ayrıcalıklarıyla çalıştırın ve netstat ile Power BI Desktop’ın analiz için kullandığı bağlantı noktasını bulun:

   `> netstat -b -n` 

   Çıktı, uygulamaların ve bunların açık bağlantı noktalarının listesi şeklinde olur. Örneğin,  

   TCP    [::1]:55786            [::1]:55830            ESTABLISHED 

   [msmdsrv.exe] 

   msmdsrv.exe tarafından kullanılan bağlantı noktasını bulun ve daha sonra kullanmak üzere not alın. Bu örnekte, 55786 numaralı bağlantı noktasını kullanabilirsiniz. 
3.  **SQL Server Profiler’ı Power BI Desktop’a bağlayın** 

   - **Başlangıç** menüsünden SQL Server Profiler’ı başlatın 
   - **Dosya** > **Yeni İzleme** 
   - Sunucu Türü: Analysis Services 
   - Sunucu adı: localhost:[yukarıda bulunan bağlantı noktası numarası] 
   - Sonraki ekranda **Çalıştır**’ı seçin 
   - SQL Profiler çalışmaya ve etkin olarak Power BI Desktop tarafından gönderilen sorguların profilini oluşturmaya başlar. 
   - Sorgular yürütülürken her birinin süresini ve CPU kullanımını görebilir ve bu bilgileri kullanarak hangi sorguların performans sorunlarına yol açtığını belirleyebilirsiniz.  

SQL Profiler aracılığıyla CPU’yu en uzun süre kullanan ve muhtemelen performans sorunlarına yol açan sorguları belirleyebilirsiniz. Daha sonraki iyileştirme çalışmaları için bu sorguları yürüten görsel öğelere odaklanılması gerekir. 

## <a name="gateway-best-practices"></a>En iyi ağ geçidi yöntemleri 

Şirket içi veri ağ geçidi, Power BI hizmetini şirket içi verilerinize bağlamak için harika bir araçtır. Aynı zamanda, kötü planlama nedeniyle rapor performansı için performans sorunlarına da yol açabilir. Bu, özellikle de tüm sorguların ve sorgu yanıtlarının ağ geçidinden geçtiği DirectQuery ve canlı bağlantı veri kümeleri için geçerlidir. Ağ geçidi performansının yüksek olmasını sağlamak için en iyi yöntemlerden bazıları aşağıda verilmiştir: 
 
- Kişisel mod yerine **Kurumsal modu kullanın**. 
- **Ağ geçidi için önerilen donanım özellikleri** – 8 CPU çekirdeği, 16 GB RAM. 
- **İzleme ayarlayın**: Ağ geçidinin aşırı yüklenerek performans sorunların yol açıp açmadığını anlamak için ağ geçidi makinesi üzerinde performans izleme ayarlayın. Daha fazla bilgi için bkz. [Şirket içi veri ağ geçidi sorunlarını giderme](service-gateway-onprem-tshoot.md).
- **Ölçeği büyütün veya genişletin**: Ağ geçidi gerçekten de performans sorunlarına yol açıyorsa, ölçeği büyütmeyi (yani, ağ geçidini daha fazla CPU ve RAM içeren daha güçlü bir makineye taşımayı) veya ölçeği genişletmeyi (örneğin, iki veri kümesini farklı ağ geçitlerine bölme) göz önünde bulundurun. 
- **İçeri aktarma ile DirectQuery’yi ayırın** – Ölçeği genişletiyorsanız, içeri aktarmadan sorumlu olan ağ geçitleri ile DirectQuery’den sorumlu olanları birbirinden ayırmayı göz önünde bulundurun. 
 
## <a name="network-latency"></a>Ağ gecikmesi 
Ağ gecikmesi, isteklerin Power BI hizmete ulaşması ve yanıtların teslim edilmesi için gereken süreyi artırarak rapor performansını etkileyebilir. Power BI'da kiracılara belirli bir bölge atanır. Kiracınızın “ev” bölgesini powerbi.com adresine gidip sağ üstteki **?** işaretini ve sonra **Power BI Hakkında**’yı seçerek görüntüleyebilirsiniz. Bir kiracıdaki kullanıcıların Power BI hizmetine erişirken gerçekleştirdiği istekler her zaman bu bölgeden yönlendirilir. İstekler Power BI hizmetine ulaştığında, hizmet yine ağ gecikmesine yol açabilecek ek istekler (örneğin, temel veri kaynağına veya ağ geçidine) gönderebilir. 

[Azure Hız Testi](http://azurespeedtest.azurewebsites.net/) gibi araçlar, istemci ile Azure bölgesi arasındaki ağ gecikmesini gösterir. Genel olarak ağ gecikmesinin etkisini en aza indirmek için veri kaynaklarını, ağ geçitlerini ve Power BI kümenizi mümkün olduğunca yakın tutun. Ağ gecikmesi sorunu yaşıyorsanız, ağ geçitlerini ve veri kaynaklarını sanal makinelere yerleştirerek Power BI kümenize yakınlaştırmayı deneyebilirsiniz. 

Ağ gecikmesini daha da azaltmak için istemcilerinizle Azure veri merkezleri arasında daha hızlı, daha güvenilir ağ bağlantıları oluşturabilen [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)’u kullanmayı göz önünde bulundurun. 

## <a name="next-steps"></a>Sonraki adımlar
- Büyük ölçekli Power BI dağıtımlarına yönelik eksiksiz yönergelerle [Power BI Enterprise Dağıtımı Planlama](https://aka.ms/pbienterprisedeploy) 
- [SQL Server 2016 Analysis Services'da DirectQuery](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/) 
- [[YouTube] Power BI’da hızlı ve güvenilir raporlar oluşturma](https://www.youtube.com/watch?v=GhiJABR7XX0) 
- [[YouTube] Power BI Enterprise Dağıtımları](https://www.youtube.com/watch?v=K-zEWICvICM)  
 
 
