---
title: Performans açısından en iyi Power BI yöntemleri
description: Bu makalede, Power BI’da hızlı ve güvenilir raporlar oluşturmaya yönelik rehberlik sağlanır
author: Bhavik-MSFT
ms.author: bhmerc
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/30/2018
LocalizationGroup: Reports
ms.openlocfilehash: 736c1ee1b1998ec7f991167352313a05061b3f3c
ms.sourcegitcommit: 226b47f64e6749061cd54bf8d4436f7deaed7691
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2019
ms.locfileid: "70841489"
---
# <a name="power-bi-performance-best-practices"></a>Performans açısından en iyi Power BI yöntemleri

Bu makalede, Power BI’da hızlı ve güvenilir raporlar oluşturmaya yönelik rehberlik sunulur.  

## <a name="choose-an-appropriate-storage-mode-import-directquery"></a>Uygun bir depolama modu seçin: İçeri aktarma, DirectQuery

Çoğu durumda İçeri aktarma modu, sütunlu depolama kullanılarak sıkıştırılan, yerel olarak önbelleğe alınmış bellek verilerini kullanarak en yüksek hızı sunan en iyi seçenektir. İçeri aktarma modu tam DAX özelliğine de izin verir. Kaynak veri hacmi Power BI kapasitenize sığamayacak kadar büyükse DirectQuery (ve Bileşik modelleri) düşünün. DirectQuery ayrıca bir rapor her yüklendiğinde kaynaktan en son verileri almanız gerektiğinde faydalıdır. Bu gereksinimlere sahip değilseniz ve kullanıcıların yalnızca günde birkaç kez veya daha az (örneğin, bir kurumsal veri ambarından) güncelleştirilmiş verileri görmesi gerekiyorsa, İçeri aktarma yöntemi daha fazla önerilir. DirectQuery modunda, kullanıcılar, kaynaktan tam olarak aynı verileri aldıklarını fark etmeden raporu yenilemeyi deneyebilir.      

## <a name="use-filters-to-limit-report-visuals-to-display-only-whats-needed"></a>Filtreleri kullanarak rapordaki görsel öğelerini yalnızca gerekli öğelerle sınırlayın 

Bir görsel öğenin görüntülemesi gereken veri arttıkça yüklenme hızı düşer. Bu ilke açıkça anlaşılır olsa da sık sık unutulur. Örneğin, büyük bir veri kümeniz olduğunu varsayalım. Bu veri kümesinin üzerinde tablonun tablosunu içeren bir rapor oluşturuyorsunuz. Çoğu birkaç düzine satırla ilgilenen son kullanıcılar, sayfadaki dilimleyicileri kullanarak istedikleri satırlara gidebiliyor.

Sık yapılan bir hata, tablonun filtrelenmemiş varsayılan görünümünü (100 milyondan fazla satır) olduğu gibi bırakmaktır. Her yenilemede bu satırlara ait veriler belleğe yüklenir ve sıkıştırması açılır. Bu işlem muazzam büyüklükte bellek yükleri oluşturur. Çözüm: “İlk N” filtresini kullanarak tablonun görüntülediği öğe sayısı üst sınırını azaltın. Öğe sayısı üst sınırını kullanıcılar için gerekenden çok daha yüksek bir sayıya (örneğin 10.000) ayarlayabilirsiniz. Sonuçta son kullanıcı deneyimi değişmez ama bellek kullanımı önemli ölçüde azalır. Ayrıca performans da gelişir.

Raporlarınızdaki tüm görsel öğeler için yukarıdakine benzer bir yaklaşım önerilir. Kendinize bir görsel öğedeki tüm verilerin gerekli olup olmadığını sorun. Son kullanıcı deneyimini çok az etkileyerek görselde gösterilen veri miktarını filtrelemenin yolları var mı? Özellikle tablolar pahalı olabilir.

## <a name="limit-visuals-on-report-pages"></a>Rapor sayfalarındaki görsel öğeleri sınırlama

Yukarıdaki ilke, aynı şekilde belirli bir rapordaki görsel öğe sayısı için de geçerlidir. Bir rapordaki görsel öğe sayısını yalnızca gerekli olanla kısıtlamanız kesinlikle önerilir. Detaylandırma sayfaları, raporu tıka basa görselle doldurmadan ek ayrıntı sağlamanın harika bir yoludur.  

## <a name="optimize-your-model"></a>Modelinizi iyileştirin

En iyi yöntemlerden bazıları:

- Kullanılmayan tabloları veya sütunları mümkün olduğunca kaldırın. 
- Kardinalitesi yüksek olan (örneğin, milyonlarca ayrı değer) sütunlarda ayrı sayımlardan kaçının.  
- Gereksiz düzeyde hassaslığa ve yüksek kardinaliteye sahip alanlardan kaçınmak için gerekli adımları uygulayın. Örneğin son derece benzersiz olan tarih saat değerlerini (örneğin ay, yıl ve tarih) ayrı sütunlara bölebilirsiniz. Mümkün olduğunda yüksek duyarlıklı alanları düşük kardinaliteye yuvarlama da kullanabilirsiniz (örneğin, 13,29889 -> 13,3).
- Mümkün oldukça dize yerine tamsayı kullanın.
- Bir tablodaki tüm satırları test etmesi gereken RANKX gibi DAX işlevlerine dikkat edin. En kötü senaryoda, tablo boyutundaki doğrusal artışlar nedeniyle bu işlevler çalışma sürenizi ve bellek gereksinimlerinizi birkaç katına çıkarabilir.
- Veri kaynaklarına DirectQuery yoluyla bağlandığınızda yaygın olarak yeniden filtrelenen veya dilimlenen sütunların dizinini oluşturmayı göz önünde bulundurun. Dizin oluşturma raporun yanıt süresini önemli ölçüde geliştirir.  

DirectQuery'de veri kaynaklarını iyileştirme hakkında daha fazla bilgi için bkz. [SQL Server 2016 Analysis Services'te DirectQuery](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/).

## <a name="directquery-and-live-connection-understand-underlying-data-source-performance"></a>DirectQuery ve canlı bağlantı: temel veri kaynağının performansını anlama

DirectQuery veya canlı bağlantı örneğinde, kullanıcılar bir Power BI raporunu ziyaret ettiğinde Power BI tarafından temel veri kaynağına gerçek zamanlı olarak sorgular gönderilir. Veri kaynağı sorgu verilerini döndürdükten sonra rapor işlenir. Sonuç olarak, rapor performansınız büyük ölçüde temel veri kaynağının performansına bağlıdır.

Bu gibi durumlarda temel veri kaynağınızın performansını anlamanız önemlidir. Farklı veri kaynaklarının sorgu performansını anlamak için farklı araçları vardır. Örneğin, SQL Server ve Azure SQL tarafından sorguların geçmişini ve çalışma zamanı istatistiklerini yakalayan Query Store sağlanır.

DirectQuery ve canlı bağlantı üzerinde oluşturulmuş Power BI raporlarını dağıtırken, son kullanıcılarınızın Power BI Desktop'ta ne yapacağını deneyin. Rapor Power BI Desktop'ta yavaş yükleniyorsa, büyük olasılıkla son kullanıcılarınız için de hizmette yavaş yüklenecektir. 

## <a name="directquery-best-practices"></a>En iyi DirectQuery yöntemleri

Aşağıdaki bölümde, DirectQuery aracılığıyla bağlanmak için genel olarak en iyi yöntemler açıklanmıştır.

### <a name="db-design-guidance"></a>Veritabanı tasarım kılavuzu

- Hesaplanan sütunları ve ölçüleri mümkün olduğunca kaynağa doğru itin. Kaynağa ne kadar yakın olursa performansın yüksek olma olasılığı da o kadar yüksektir.
- En iyi duruma getirin! Sorgularınız için yürütme planlarını öğrenin, sık filtrelenen sütunlar için dizinler ekleyin ve bunun gibi başka çalışmalar yapın.

### <a name="modeling-guidance"></a>Modelleme kılavuzu

- Çalışmaya Power BI Desktop'ta başlayın.
- Sorgu Düzenleyicisi'nde karmaşık sorgular kullanmayın.
- Sorgu Düzenleyicisi'nde göreli tarih filtrelemesi kullanmayın.  
- Başlangıçta ölçüleri basit tutun ve kademeli olarak karmaşıklık ekleyin.
- Hesaplanmış sütunlar ve benzersiz tanımlayıcı sütunlarında ilişki kullanmayın.
- İlişkilerde “Bilgi Tutarlılığı Varsay” ayarını yapmayı deneyin; birçok durumda bu ayar sorgu performansını önemli ölçüde geliştirir.  

### <a name="general"></a>Genel

- Önce filtre uygulayın.
- Görsel öğeler arası etkileşimi kapatmayı göz önünde bulundurun; bunun yapılması, kullanıcılar çapraz vurgulama uygularken sorgu yükünü azaltır.
- Yukarıda açıklandığı gibi, görsel öğe sayısını ve görsel öğe başına veri miktarını kısıtlayın.
- Satır düzeyi güvenliğin etkinleştirilmesi, performansta büyük değişikliklere neden olabilir. Kullanıcılarınızın üstleneceği çeşitli satır düzeyi güvenlik rollerini test etmeyi unutmayın.
- Uzun süre çalışan sorguların sistem kaynaklarını tekeline alamamasını sağlamak için hizmet tarafından sorgu düzeyinde zaman aşımları zorunlu tutulur. 225 saniyeden uzun süren sorgular zaman aşımına uğrar ve görsel öğe düzeyinde bir hataya yol açar.

## <a name="understand-dashboards-and-query-caches"></a>Panoları ve sorgu önbelleklerini anlama

Panolara sabitlenen görsel öğeler, pano yüklendiğinde sorgu önbelleği tarafından sunulur. Buna karşılık olarak, bir rapor ziyaret edildiği sırada, Power BI hizmetine (içeri aktarma durumunda) veya belirttiğiniz veri kaynağına (DirectQuery veya canlı bağlantı durumunda) yönelik sorgular anlık olarak gerçekleştirilir.  

> [!NOTE]
> Panoya canlı rapor kutucukları sabitlediğinizde bunlar sorgu önbelleğinden sunulmaz; bunun yerine rapor gibi davranır ve anlık olarak arka uç çekirdeklerine sorgu gerçekleştirir.

Adından da anlaşılacağı gibi, veri kaynağını kullanmak yerine verilerin sorgu önbelleğinden alınması daha iyi ve daha tutarlı performans sağlar. Bu işlevin avantajından yararlanmanın bir yolu, panoları kullanıcılarınız için ilk giriş sayfası yapmaktır. Sık kullanılan ve istenen görsel öğeleri panolara sabitleyin. Bu sayede, panolar değerli bir “ilk savunma hattı” olur ve kapasite üzerinde daha az yük oluşturarak tutarlı performans sağlar. Kullanıcılar raporda gezinerek ayrıntıları araştırabilir.  
 

DirectQuery ve canlı bağlantı için, sorgu önbelleği veri kaynağı sorgulanarak düzenli aralıklarla güncelleştirilir. Varsayılan olarak bu işlem saat başı gerçekleşir, ancak veri kümesi ayarlarından yapılandırılabilir. Her sorgu önbelleği güncelleştirmesi, önbelleği güncelleştirmek için temel veri kaynağına sorgu gönderir. Oluşturulan sorgu sayısı, panoya sabitlenen ve veri kaynağını kullanan görsel öğe sayısına bağlıdır. Satır düzeyi güvenliğin etkin olması durumunda her farklı güvenlik bağlamı için sorgu oluşturulduğunu unutmayın. Örneğin, kullanıcılarınızı kategorilere ayıran iki farklı rolünüz ve bunların iki farklı veri görünümü varsa, sorgu önbelleğini yenileme sırasında Power BI iki sorgu kümesi oluşturur. 

## <a name="understand-custom-visual-performance"></a>Özel görsel öğe performansını anlama 

Her bir özel görsel öğeyi gerekli testlere tabi tutarak öğe performansının yüksek olduğundan emin olun. Hatalı bir şekilde iyileştirilmiş özel görsel öğeler, raporun tamamının performansını olumsuz yönde etkileyebilir. 

## <a name="deep-dive-into-query-performance-with-sql-profiler-and-power-bi-desktop"></a>SQL Profiler ve Power BI Desktop ile sorgu performansına ayrıntılı bakış

En çok zamanı ve kaynağı hangi görsel öğelerin harcadığına yönelik daha ayrıntılı bir bakış için Power BI Desktop’a SQL Profiler’ı bağlayarak sorgu performansının tam görünümünü elde edebilirsiniz.

> [!NOTE]
> Power BI Desktop bir tanılama bağlantı noktasına bağlanmayı destekler. Tanılama bağlantı noktası, diğer araçların tanılama amacıyla bağlanmasına ve izleme gerçekleştirmesine imkan tanır. *Modele herhangi bir değişiklik yapılması desteklenmez! Modelde değişiklik yapılması bozulmaya veya veri kaybına yol açabilir.*

Yönergeler aşağıda verilmiştir:
  
1. **SQL Server Profiler’ı yükleyin ve Power BI Desktop’ı çalıştırın**

   SQL Server Profiler, SQL Server Management Studio’nun bir parçası olarak sunulmaktadır.

2. **Power BI Desktop tarafından kullanılmakta olan bağlantı noktasını belirleme**

   Komut istemini veya PowerShell'i yönetici ayrıcalıklarıyla çalıştırın. Ayrıca Power BI Desktop'ın analiz için kullandığı bağlantı noktasını bulmak için netstat kullanın:

   `> netstat -b -n`

   Çıktı, uygulamaların ve bunların açık bağlantı noktalarının listesi şeklinde olur. Örneğin,  

   `TCP    [::1]:55786            [::1]:55830            ESTABLISHED`

   [msmdsrv.exe]

   msmdsrv.exe tarafından kullanılan bağlantı noktasını bulun ve daha sonra kullanmak üzere not alın. Bu örnekte, 55786 numaralı bağlantı noktasını kullanırsınız.
3. **SQL Server Profiler’ı Power BI Desktop’a bağlayın**

   - **Başlangıç** menüsünden SQL Server Profiler’ı başlatın
   - **Dosya** > **Yeni İzleme**
   - Sunucu Türü: Analysis Services
   - Sunucu adı: localhost:[yukarıda bulunan bağlantı noktası numarası]
   - Sonraki ekranda **Çalıştır**’ı seçin
   - SQL Profiler çalışmaya ve etkin olarak Power BI Desktop tarafından gönderilen sorguların profilini oluşturmaya başlar. 
   - Sorgular yürütülürken her birinin süresini ve CPU kullanımını görebilir ve bu bilgileri kullanarak hangi sorguların performans sorunlarına yol açtığını belirleyebilirsiniz.  

SQL Profiler aracılığıyla en uzun CPU süresini alan sorguları belirleyebilirsiniz. Performans sorunlarına yol açan büyük olasılıkla bu sorgulardır. Devam eden iyileştirme çalışmaları için bu sorguları çalıştıran görsel öğelere odaklanılması gerekir.

## <a name="gateway-best-practices"></a>En iyi ağ geçidi yöntemleri

Şirket içi veri ağ geçidi, Power BI hizmetini şirket içi verilerinize bağlamak için harika bir araçtır. Aynı zamanda, kötü planlama nedeniyle rapor performansı için performans sorunlarına da yol açabilir. Bu, özellikle de tüm sorguların ve sorgu yanıtlarının ağ geçidinden geçtiği DirectQuery ve canlı bağlantı veri kümeleri için geçerlidir. Ağ geçidi performansının yüksek olmasını sağlamak için en iyi yöntemlerden bazıları aşağıda verilmiştir: 

- Kişisel mod yerine **Kurumsal modu kullanın**.
- **Ağ geçidi için önerilen donanım özellikleri** – sekiz CPU çekirdeği, 16 GB RAM.
- **İzleme ayarlayın**: Ağ geçidinin aşırı yüklenerek performans sorunlarına yol açıp açmadığını anlamak için ağ geçidi makinesi üzerinde performans izleme ayarlayın. Daha fazla bilgi için bkz. [Şirket içi veri ağ geçidi sorunlarını giderme](service-gateway-onprem-tshoot.md).
- **Ölçeği büyütün veya genişletin**: Ağ geçidi gerçekten de performans sorunlarına yol açıyorsa, ölçeği büyütmeyi (yani, ağ geçidini daha fazla CPU ve RAM içeren daha güçlü bir makineye taşımayı) veya ölçeği genişletmeyi (örneğin, iki veri kümesini farklı ağ geçitlerine bölme) göz önünde bulundurun. 
- **İçeri aktarma ile DirectQuery’yi ayırın** – Ölçeği genişletiyorsanız, içeri aktarmadan sorumlu olan ağ geçitleri ile DirectQuery’den sorumlu olan ağ geçitlerini birbirinden ayırmayı göz önünde bulundurun.

## <a name="network-latency"></a>Ağ gecikmesi

Ağ gecikmesi, isteklerin Power BI hizmete ulaşması ve yanıtların teslim edilmesi için gereken süreyi artırarak rapor performansını etkileyebilir. Power BI'da kiracılara belirli bir bölge atanır. Kiracınızın “ev” bölgesini powerbi.com adresine gidip sağ üstteki **?** işaretini ve sonra **Power BI Hakkında**’yı seçerek görüntüleyebilirsiniz. Kiracıdaki kullanıcıların Power BI hizmetine erişirken gerçekleştirdiği istekler her zaman bu bölgeye yönlendirilir. İstekler Power BI hizmetine ulaştığında, hizmet yine ağ gecikmesine yol açabilecek ek istekler (örneğin, temel veri kaynağına veya ağ geçidine) gönderebilir.

[Azure Hız Testi](http://azurespeedtest.azurewebsites.net/) gibi araçlar, istemci ile Azure bölgesi arasındaki ağ gecikmesini gösterir. Genel olarak ağ gecikmesinin etkisini en aza indirmek için veri kaynaklarını, ağ geçitlerini ve Power BI kümenizi mümkün olduğunca yakın tutun. Ağ gecikmesi sorunu yaşıyorsanız, ağ geçitlerini ve veri kaynaklarını sanal makinelere yerleştirerek Power BI kümenize yakınlaştırmayı deneyin.

Ağ gecikmesini daha da azaltmak için istemcilerinizle Azure veri merkezleri arasında daha hızlı, daha güvenilir ağ bağlantıları oluşturabilen [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)’u kullanmayı göz önünde bulundurun.

## <a name="next-steps"></a>Sonraki adımlar

- Büyük ölçekli Power BI dağıtımlarına yönelik eksiksiz yönergelerle [Power BI Enterprise Dağıtımı Planlama](https://aka.ms/pbienterprisedeploy)
- [SQL Server 2016 Analysis Services'da DirectQuery](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/)
- [[YouTube] Power BI’da hızlı ve güvenilir raporlar oluşturma](https://www.youtube.com/watch?v=GhiJABR7XX0)
- [[YouTube] Power BI Enterprise Dağıtımları](https://www.youtube.com/watch?v=K-zEWICvICM)
