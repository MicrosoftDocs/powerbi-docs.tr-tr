---
title: Power BI için iyileştirme kılavuzu
description: Power BI için iyileştirme kılavuzu.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/16/2020
ms.author: v-pemyer
ms.openlocfilehash: 0f29b70a42375be945d206672116219b7d5a3b48
ms.sourcegitcommit: 032a77f2367ca937f45e7e751997d7b7d0e89ee2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77610007"
---
# <a name="optimization-guide-for-power-bi"></a>Power BI için iyileştirme kılavuzu

Bu makalede geliştiricilerin ve yöneticilerin iyileştirilmiş Power BI çözümleri oluşturmasına ve bunların bakımını yapmasına olanak tanıyan yönergeler sağlanır. Çözümünüzü farklı mimari katmanlarında iyileştirebilirsiniz. Katmanlar şunlardır:

- Veri kaynakları
- Veri modeli
- Görselleştirmeler; diğer bir deyişle panolar, Power BI raporları ve Power BI sayfalandırılmış raporları
- Ortam; diğer bir deyişle kapasiteler, veri ağ geçitleri ve ağ

## <a name="optimizing-the-data-model"></a>Veri modelini iyileştirme

Veri modeli görselleştirme deneyiminin tamamını destekler. Veri modelleri dışarıda veya içeride barındırılır ve Power BI’da bunlara _veri kümeleri_ denir. Seçeneklerinizi anlamanız ve çözümünüze uygun veri kümesi türünü seçmeniz önemlidir. Üç veri kümesi modu vardır: İçeri Aktarma, DirectQuery ve Bileşik. Daha fazla bilgi için bkz. [Power BI hizmetinde veri kümeleri](../service-datasets-understand.md) ve [Power BI hizmetinde veri kümesi modları](../service-dataset-modes-understand.md).

Belirli bir veri kümesi moduyla ilgili kılavuz için bkz:

- [İçeri Aktarma modellemesi için veri azaltma teknikleri](import-modeling-data-reduction.md)
- [Power BI Desktop’ta DirectQuery modeli kılavuzu](directquery-model-guidance.md)
- [Power BI Desktop’ta Bileşik model kılavuzu](composite-model-guidance.md)

## <a name="optimizing-visualizations"></a>Görselleştirmeleri iyileştirme

Power BI görselleştirmeleri panolar, Power BI raporları veya Power BI sayfalandırılmış raporları olabilir. Her birinin farklı mimarileri olduğundan her birinin kendi kılavuzu vardır. 

### <a name="dashboards"></a>Panolar

Power BI’ın, canlı rapor kutucukları ve akış kutucukları hariç pano kutucuklarınız için bir önbellek tuttuğunu anlamanız önemlidir. Daha fazla bilgi için bkz. [Power BI’da veri yenileme (Kutucuk yenileme)](../refresh-data.md#tile-refresh). Veri kümeniz dinamik [satır düzeyi güvenliği (RLS)](../service-admin-rls.md) zorunlu tutuyorsa, kutucuklar kullanıcı başına önbelleğe alındığından bunun performans üzerindeki etkilerini anladığınızdan emin olun.

Canlı rapor kutucuklarını panoya sabitlediğinizde bunlar sorgu önbelleğinden kullanıma sunulmaz. Bunun yerine raporlarla aynı şekilde davranırlar ve arka uç çekirdeklerinde anında sorgular çalıştırırlar.

Adından da anlaşılacağı gibi, veri kaynağını kullanmak yerine verilerin önbellekten alınması daha iyi ve daha tutarlı performans sağlar. Bu işlevin avantajından yararlanmanın bir yolu, panoları kullanıcılarınız için ilk giriş sayfası yapmaktır. Sık kullanılan ve istenen görsel öğeleri panolara sabitleyin. Bu sayede, panolar değerli bir "ilk savunma hattı" olur ve kapasite üzerinde daha az yük oluşturarak tutarlı performans sağlar. Kullanıcılar yine raporda tıklayıp gezinerek ayrıntıları analiz edebilir.

DirectQuery ve canlı bağlantı veri kümeleri için, veri kaynağı sorgulanarak önbellek düzenli aralıklarla güncelleştirilir. Varsayılan olarak bu saatte bir gerçekleşir ama veri kümesi ayarlarında farklı bir sıklık yapılandırabilirsiniz. Her önbellek güncelleştirmesi, önbelleği güncelleştirmek için temel veri kaynağına sorgu gönderir. Oluşturulan sorgu sayısı, panoya sabitlenen ve veri kaynağını kullanan görsel öğe sayısına bağlıdır. Satır düzeyi güvenliğin etkin olması durumunda her farklı güvenlik bağlamı için sorgu oluşturulduğunu unutmayın. Örneğin kullanıcılarınızı kategorilere ayırmak için iki farklı rol olduğunu ve verilerin iki farklı görünümü olduğunu düşünün. Sorgu önbelleğini yenileme işlemi sırasında Power BI iki sorgu kümesi oluşturur.

### <a name="power-bi-reports"></a>Power BI raporları

Power BI rapor tasarımlarını iyileştirmeye yönelik çeşitli öneriler vardır.

> [!NOTE]
> Raporlar bir DirectQuery veri kümesine dayandığında, ek rapor tasarımı iyileştirmeleri için bkz. [Power BI Desktop’ta DirectQuery model kılavuzu (Rapor tasarımlarını iyileştirme)](directquery-model-guidance.md#optimize-report-designs).

#### <a name="apply-the-most-restrictive-filters"></a>En kısıtlayıcı filtreleri uygulama

Bir görsel öğenin görüntülemesi gereken veri arttıkça yüklenme hızı düşer. Bu ilke açıkça anlaşılır olsa da sık sık unutulur. Örneğin, büyük bir veri kümeniz olduğunu varsayalım. Bu veri kümesinin üzerinde tablo içeren bir rapor oluşturuyorsunuz. Çoğu birkaç düzine satırla ilgilenen son kullanıcılar, sayfadaki dilimleyicileri kullanarak istedikleri satırlara gidebiliyor.

Sık yapılan bir hata, tablonun filtrelenmemiş varsayılan görünümünü (100 milyondan fazla satır) olduğu gibi bırakmaktır. Her yenilemede bu satırlara ait veriler belleğe yüklenir ve sıkıştırması açılır. Bu işlem bellek için muazzam büyüklükte talepler oluşturur. Çözüm: "İlk N" filtresini kullanarak tablonun görüntülediği öğe sayısı üst sınırını azaltın. Öğe sayısı üst sınırını kullanıcılar için gerekenden çok daha yüksek bir sayıya (örneğin 10.000) ayarlayabilirsiniz. Sonuçta son kullanıcı deneyimi değişmez ama bellek kullanımı önemli ölçüde azalır. En önemlisi de, performans gelişir.

Raporunuzdaki tüm görsel öğeler için yukarıdakine benzer bir tasarım yaklaşımı önerilir. Kendinize bir görsel öğedeki tüm verilerin gerekli olup olmadığını sorun. Son kullanıcı deneyimini çok az etkileyerek görselde gösterilen veri miktarını filtrelemenin yolları var mı? Unutmayın, özellikle tablolar pahalıya gelebilir.

#### <a name="limit-visuals-on-report-pages"></a>Rapor sayfalarındaki görsel öğeleri sınırlama

Yukarıdaki ilke, aynı şekilde rapor sayfasına eklenen görsel öğe sayısı için de geçerlidir. Belirli bir rapor sayfasındaki görsel öğe sayısını yalnızca gerekli olanla kısıtlamanız kesinlikle önerilir. [Detaylandırma sayfaları](report-drillthrough.md) ve [rapor sayfası araç ipuçları](report-page-tooltips.md) sayfayı tıka basa görselle doldurmadan ek ayrıntı sağlamanın harika yollarıdır.

#### <a name="evaluate-custom-visual-performance"></a>Özel görsel öğe performansını değerlendirme

Her bir özel görsel öğeyi gerekli testlere tabi tutarak öğe performansının yüksek olduğundan emin olun. Hatalı bir şekilde iyileştirilmiş özel görsel öğeler, raporun tamamının performansını olumsuz yönde etkileyebilir.

### <a name="power-bi-paginated-reports"></a>Power BI sayfalandırılmış raporlar

Power BI sayfalandırılmış rapor tasarımları, raporun veri alma işlemine en iyi yöntem tasarımı uygulanarak iyileştirilebilir. Daha fazla bilgi için bkz. [Sayfalandırılmış raporlar için veri alma kılavuzu](report-paginated-data-retrieval.md).

Ayrıca kapasitenizde [sayfalandırılmış rapor iş yüküne](../service-admin-premium-workloads.md#paginated-reports) ayrılmış yeterli bellek bulunduğundan emin olun.

## <a name="optimizing-the-environment"></a>Ortamı iyileştirme

Kapasite ayarlarını yapılandırarak, veri ağ geçitlerini boyutlandırarak ve ağ gecikmesini azaltarak Power BI ortamını iyileştirebilirsiniz.

### <a name="capacity-settings"></a>Kapasite ayarları

Power BI Premium (P SKU’ları) veya Power BI Embedded (A SKU’ları, A4-A6) ile sağlanan ayrılmış kapasiteleri kullanırken kapasite ayarlarını yönetebilirsiniz. Daha fazla bilgi için bkz. [Premium kapasiteleri yönetme](../service-premium-capacity-manage.md). Kapasitenizi nasıl iyileştireceğinize ilişkin yönergeler için bkz. [Premium kapasiteleri iyileştirme](../service-premium-capacity-optimize.md).

### <a name="gateway-sizing"></a>Ağ geçidini boyutlandırma

Power BI’ın doğrudan İnternet üzerinden erişilemeyen verilere erişmesi gereken her durumda ağ geçidi gereklidir. [Şirket içi veri ağ geçidini](../service-gateway-onprem.md) şirket içindeki sunucuya veya VM’de barındırılan Hizmet Olarak Altyapı’ya (IaaS) yükleyebilirsiniz.

Ağ geçidi iş yüklerini ve boyutlandırma önerilerini anlamak için bkz. [Şirket içi veri ağ geçidini boyutlandırma](gateway-onprem-sizing.md).

### <a name="network-latency"></a>Ağ gecikmesi

Ağ gecikmesi, isteklerin Power BI hizmete ulaşması ve yanıtların teslim edilmesi için gereken süreyi artırarak rapor performansını etkileyebilir. Power BI'da kiracılar belirli bir bölgeye atanır.

> [!TIP]
> Kiracınızın bulunduğu yeri belirlemek için bkz. [Power BI kiracım nerede bulunur?](../service-admin-where-is-my-tenant-located.md)

Kiracıdaki kullanıcıların Power BI hizmetine erişirken gerçekleştirdiği istekler her zaman bu bölgeye yönlendirilir. İstekler Power BI hizmetine ulaştığında, hizmet yine ağ gecikmesine yol açabilecek ek istekler (örneğin, temel veri kaynağına veya veri ağ geçidine) gönderebilir.

[Azure Hız Testi](https://azurespeedtest.azurewebsites.net/) gibi araçlar, istemci ile Azure bölgesi arasındaki ağ gecikmesini gösterir. Genel olarak ağ gecikmesinin etkisini en aza indirmek için veri kaynaklarını, ağ geçitlerini ve Power BI kümenizi mümkün olduğunca yakın tutun. Bunların aynı bölgede yer alması tercih edilir. Ağ gecikmesi sorunu yaşıyorsanız, ağ geçitlerini ve veri kaynaklarını bulutta barındırılan sanal makinelere yerleştirerek Power BI kümenize yakınlaştırmayı deneyin.

## <a name="monitoring-performance"></a>Performansı izleme

Performans sorunlarını belirlemek için performansı izleyebilirsiniz. Yavaş sorgular veya rapor görselleri, devam eden iyileştirme çalışmalarının odak noktası olmalıdır. İzleme işlemi Power BI Desktop’ta tasarım zamanında veya Power BI Premium kapasitelerde üretim iş yükleri üzerinde yapılabilir. Daha fazla bilgi için bkz. [Power BI’da rapor performansını izleme](monitor-report-performance.md).

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI kılavuzu](index.yml)
- [Rapor performansını izleme](monitor-report-performance.md)
- Teknik İnceleme: [Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama)](https://go.microsoft.com/fwlink/?linkid=2057861)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
