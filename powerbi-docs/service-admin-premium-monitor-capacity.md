---
title: Kuruluşunuzdaki Power BI Premium kapasitelerini izleme
description: Power BI yönetici portalını ve Power BI Premium Capacity Metrics uygulamasını kullanma
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/13/2018
LocalizationGroup: Premium
ms.openlocfilehash: e8e69cdacb9ee54cdf19724c590f994f66c4dff7
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54290648"
---
# <a name="monitor-power-bi-premium-and-power-bi-embedded-capacities"></a>Power BI Premium ve Power BI Embedded kapasitelerini izleme

Bu makalede, Power BI Premium kapasitelerinizin ölçümlerini izlemeyle ilgili genel bakış bilgilerine yer verilmiştir. Kapasite kullanımını izleyerek kapasitelerinizi yönetme konusunda bilgiye dayalı bir yaklaşım sergileyebilirsiniz.

Kapasiteyi izlemek için Power BI Premium Capacity Metrics uygulamasını veya yönetici portalını kullanabilirsiniz. Daha fazla ayrıntı sunduğu için uygulamayı kullanmanızı öneririz ancak bu makalede iki seçeneğe de bakacağız.

**Uygulamanın geçerli sürümü, 13 Aralık 2018 tarihinde yayımlanan 1.10’dur.**

geçin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UgsjMbhi_Bk?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="install-the-premium-capacity-metrics-app"></a>Premium Capacity Metrics uygulamasını yükleme

Doğrudan [Premium Capacity Metrics uygulamasına](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) gidebilir veya Power BI'daki diğer uygulamalar gibi yükleyebilirsiniz.

1. Power BI'da **Uygulamalar**'a tıklayın.

    ![Uygulamalar bölümüne gidin](media/service-admin-premium-monitor-capacity/apps.png)

1. Sağ taraftaki **Uygulama edinin**'e tıklayın.

1. **Uygulamalar** kategorisinde **Power BI Premium Capacity Metrics uygulamasını** arayın.

1. Uygulamayı yüklemek için abone olun.

Uygulamayı yükledikten sonra kuruluşunuzdaki kapasitelere ait ölçümleri görebilirsiniz. Şimdi kullanılabilir durumdaki bazı önemli ölçümlere göz atalım.

## <a name="use-the-metrics-app"></a>Ölçümler uygulamasını kullanma

### <a name="metrics-dashboard"></a>Ölçümler panosu

Uygulamayı ilk açtığınızda yönetici haklarına sahip olduğunuz tüm kapasitelerin özetini kapsayan bir pano gösterilir.

![Ölçüm uygulama panosu](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Panoda aşağıdaki ölçümler bulunur.

| **Rapor bölümü** | **Metrics** (Ölçümler) |
| --- | --- |
| **Sistem Özeti** | * Uygulamanın sürümü<br> * Yöneticisi olduğunuz kapasitelerin sayısı<br> * Ölçümleri bildiren kapasitelerinizdeki çalışma alanlarının sayısı<br> * GB cinsinden son yedi gün içindeki ortalama bellek tüketimi<br> * GB cinsinden son yedi gün içindeki maksimum bellek tüketimi<br> * Maksimum bellek tüketiminin gerçekleştiği yerel saat<br> * Son yedi gün içinde CPU kullanımının eşik değerlerin %80'ini aşma sayısı (üç dakikalık demetlere ayrılmıştır)<br> * Son yedi gün içinde CPU kullanımının %80'i en çok aştığı zaman (bir saatlik demetlere ayrılmıştır)<br> * CPU kullanımının bir saat içinde %80'i aştığı yerel saat |
| **Veri Kümesi Özeti** | * Kapasitelerinizdeki tüm çalışma alanlarında yer alan veri kümelerinin toplam sayısı<br> * Son yedi gün içinde Doğrudan sorgu/Canlı bağlantı kullanımının eşik değerlerin %80'ini aşma sayısı (üç dakikalık demetlere ayrılmıştır)<br> * Son yedi gün içinde Doğrudan sorgu/Canlı bağlantı kullanımının %80'i en çok aştığı zaman (bir saatlik demetlere ayrılmıştır)<br> * Doğrudan sorgu/Canlı bağlantı kullanımının bir saat içinde %80'i en çok aştığı yerel saat<br> * Son yedi gün içinde gerçekleştirilen toplam yenileme sayısı<br> * Yenileme için ortalama bekleme süresi: planlanan zamanla yenilemenin başlatılması arasındaki ortalama gecikme süresi (dakika cinsinden)<br> * Ortalama yenileme süresi: yenilemenin tamamlanması için geçen süre (dakika cinsinden)<br> * Son yedi gün içinde çalıştırılan toplam sorgu sayısı<br> * Sorgu için ortalama bekleme süresi: bir sorgunun yürütülmeden önce sistem kaynaklarında beklediği süre (milisaniye cinsinden)<br> * Ortalama sorgu süresi: sorgunun tamamlanması için geçen süre (milisaniye cinsinden)<br> * Bellek baskısı nedeniyle çıkarılan toplam model sayısı<br> * Veri kümelerinin ortalama boyutu <br> * Belleğe yüklenen veri kümelerinin ortalama sayısı |
| **Veri Akışı Özeti** | * Kapasitelerinizdeki tüm çalışma alanlarında yer alan veri akışlarının toplam sayısı<br> * Son yedi gün içinde gerçekleştirilen toplam yenileme sayısı<br> * Yenileme için ortalama bekleme süresi: planlanan zamanla yenilemenin başlatılması arasındaki ortalama gecikme süresi (dakika cinsinden)<br> * Ortalama yenileme süresi: yenilemenin tamamlanması için geçen süre (dakika cinsinden) |
| **Sayfalandırılmış Rapor Özeti** | * Kapasitelerinizdeki tüm çalışma alanlarında yer alan sayfalandırılmış raporların toplam sayısı<br> * Tüm raporların kullanıcılarınız tarafından toplamda kaç kez görüntülendiğini gösteren sayı<br> * Tüm raporlardaki veri satırlarının toplam sayısı<br> * Tüm raporların veri alma, işlemden geçirme ve işleme gibi tüm aşamaları için geçen toplam süre (milisaniye cinsinden) |
|  |  |

### <a name="metrics-report"></a>Ölçümler raporu

Temel alınan rapora dönmek için panoya tıklayın. Raporda beş sekme vardır ve bunlar aşağıdaki bölümlerde daha ayrıntılı olarak açıklanmaktadır.

* **Veri kümeleri**: kapasitelerinizdeki Power BI veri kümelerinin durumu hakkında ayrıntılı ölçümler.

* **Sayfalandırılmış Raporlar**: kapasitelerinizdeki sayfalandırılmış raporların durumu hakkında ayrıntılı ölçümler.

* **Veri akışları**: kapasitelerinizdeki veri akışlarının ayrıntılı yenileme ölçümleri.

* **Kaynak Tüketimi**: bellek ve CPU’nun yüksek kullanımı gibi genel kapasite ölçümleri.

* **Kimlikler ve Bilgiler**: kapasiteler, çalışma alanları ve iş yüklerinin adları, kimlikleri ve sahipleri.

Her sekmede ölçümleri kapasiteye veya tarih aralığına göre filtreleyebilirsiniz. Hiçbir filtre seçilmezse, rapor varsayılan olarak ölçümleri bildiren tüm kapasiteler için son haftanın ölçümlerini gösterir.

#### <a name="datasets-tab"></a>Veri Kümeleri sekmesi

Farklı alanlara gitmek için **Veri Kümeleri** sekmesinin en üstündeki düğmeleri kullanın: **Özet**, **Yenilemeler**, **Sorgu Süreleri**, **Sorgu Bekleme Süreleri** ve **Veri Kümeleri**.

![Veri Kümeleri sekmesi](media/service-admin-premium-monitor-capacity/datasets-tab.png)

##### <a name="refreshes-area"></a>Yenilemeler alanı

**Yenilemeler** alanı aşağıdaki ölçümleri içerir.

| **Rapor bölümü** | **Metrics** (Ölçümler) |
| --- | --- |
| **Yenileme güvenilirliği** | * Toplam Sayı: Her veri kümesi için toplam yenileme sayısı<br> * Güvenilirlik: Her veri kümesi için tamamlanan yenilemelerin yüzdesi<br> * Ortalama Bekleme Süresi: Zamanlanan saat ve veri kümesinin yenileme başlangıcı arasındaki ortalama gecikme süresi (dakika cinsinden)<br> * En Uzun Bekleme Süresi: Veri kümesi için en uzun bekleme süresi (dakika cinsinden) <br> * Ortalama Süre: Veri kümesi yenilemesinin ortalama süresi (dakika cinsinden)<br> * En Uzun Süre: Veri kümesinin en uzun çalışan yenilemesinin süresi (dakika cinsinden) |
| **Ortalama Yenileme Süresine Göre En İyi 5 Veri Kümesi** | * Dakika cinsinden en uzun ortalama yenileme süresine sahip beş veri kümesi |
| **Ortalama Bekleme Süresine Göre En İyi 5 Veri Kümesi** | * Dakika cinsinden en uzun ortalama yenileme bekleme süresine sahip beş veri kümesi |
| **Saatlik Ortalama Yenileme Bekleme Süreleri** | * Bir saatlik demetlere ayrılmış ve yerel saatle bildirilen ortalama yenileme bekleme süresi. Yüksek yenileme bekleme süresi getiren birden çok ani artış, kapasiteye sık erişildiğini gösterir. |
| **Saatlik Yenileme Sayısı ve Bellek Tüketimi** | * Bir saatlik demetlere ayrılan ve yerel saatle raporlanan başarılar, başarısızlıklar ve bellek tüketimi |
|  |  |

##### <a name="query-durations-area"></a>Sorgu Süreleri alanı

**Sorgu Süreleri** alanı aşağıdaki ölçümleri içerir.

| **Rapor bölümü** | **Metrics** (Ölçümler) |
| --- | --- |
| **Sorgu Süreleri** | * Bu bölümdeki veriler, çalışma alanı ve son yedi gün içindeki saatlik demetlere göre ayrılmıştır<br> * Toplam: Veri kümesi için çalıştırılan sorguların toplam sayısı<br> * Ortalama: Veri kümesi için ortalama sorgu süresi (milisaniye cinsinden)<br> * Maksimum: Veri kümesinde en uzun süre çalışan sorgunun süresi (milisaniye cinsinden)|
| **Sorgu Süresi Dağılımı** | * Sorgu süresi histogramında sorgu süreleri şu kategorilere göre ayrılmış şekilde (milisaniye cinsinden) gösterilir: <= 30 ms, 30-100 ms, 100-300 ms, 300 ms-1 sn, 1 sn-3 sn, 3 sn-10 sn, 10 sn-30 sn ve > 30 saniyelik aralıklar. Uzun sorgu ve bekleme süreleri, kapasitede az yer kaldığının göstergesidir. Tek bir veri kümesinin sorunlara yol açtığı ve daha fazla araştırma gerektiği anlamına da gelebilir. |
| **Ortalama Süreye Göre En İyi 5 Veri Kümesi** | * Milisaniye cinsinden en uzun ortalama sorgu süresine sahip beş veri kümesi |
| **Doğrudan Sorgu / Canlı Bağlantılar (> %80 Kullanım)** | * Doğrudan sorgunun veya canlı bağlantının %80 CPU kullanımını kaç kez aştığı (yerel saatte bir saatlik aralıklara bölünmüş olarak) |
| **Saatlik Sorgu Süresi Dağılımları** | * Sorgu sayıları ve ortalama süre (milisaniye) ile GB olarak bellek tüketimi arasındaki karşılaştırma (yerel saatte bir saatlik aralıklara bölünmüş olarak) |
|  |  |

##### <a name="query-waits-area"></a>Sorgu Beklemeleri alanı

**Sorgu Beklemeleri** alanı aşağıdaki ölçümleri içerir.

| **Rapor bölümü** | **Metrics** (Ölçümler) |
| --- | --- |
| **Sorgu Bekleme Süreleri** | * Bu bölümdeki veriler, çalışma alanı ve son yedi gün içindeki saatlik demetlere göre ayrılmıştır<br> * Toplam: Veri kümesi için çalıştırılan sorguların toplam sayısı<br> * Bekleme sayısı: Veri kümesinde yürütülmeye başlamadan önce sistem kaynaklarında bekletilen sorguların sayısı <br> * Ortalama: Veri kümesi için ortalama sorgu bekleme süresi (milisaniye cinsinden)<br> * Maksimum: Veri kümesinde en uzun süre bekleyen sorgunun süresi (milisaniye cinsinden)|
| **Bekleme Süresi Dağılımı** | * Sorgu süresi histogramında sorgu süreleri şu kategorilere göre ayrılmış şekilde (milisaniye cinsinden) gösterilir: <= 50 ms , 50-100 ms , 100-200 ms , 200-400 ms 400 ms-1 sn, 1 sn-5 sn ve > 5 saniyelik aralıklar |
| **Ortalama Bekleme Süresine Göre En İyi 5 Veri Kümesi** | * Sorgunun yürütülmesi için ortalama bekleme süresi (milisaniye cinsinden) en uzun olan beş veri kümesi |
| **Saatlik Sorgu Bekleme Süresi Sayıları ve Süreleri** | * Sorgu bekleme sayıları ve ortalama bekleme süresi (milisaniye) ile GB olarak bellek tüketimi arasındaki karşılaştırma (yerel saatte bir saatlik aralıklara bölünmüş olarak) |
|  |  |

##### <a name="datasets-area"></a>Veri kümeleri alanı

**Veri kümeleri** alanı aşağıdaki ölçümleri içerir.

| **Rapor bölümü** | **Metrics** (Ölçümler) |
| --- | --- |
| **Veri Kümesi Çıkarma Sayıları** | * Toplam: Her kapasite için veri kümesi *çıkarmalarının* toplam sayısı. Kapasite, bellek baskısıyla karşı karşıya kaldığında düğüm bir veya daha fazla veri kümesini bellekten çıkarır. Devre dışı olan veri kümeleri (sorgu/yenileme işlemi yürütülmeyen) önce çıkarılır. Çıkarma sırası, 'en önce kullanılan' (LRU) ölçütüne göre belirlenir.|
| **Saatlik Veri Kümesi Çıkarmaları ve Bellek Tüketimi** | * Bir saatlik demetlere ayrılan ve yerel saatle raporlanan veri kümesi çıkarmaları ile GB cinsinden bellek tüketimi karşılaştırması |
| **Saatlik Yüklenen Veri Kümesi Sayısı** | * Bir saatlik demetlere ayrılan ve yerel saat cinsinden raporlanan, belleğe yüklenen veri kümesi sayısı ile GB cinsinden bellek tüketimi karşılaştırması |
| **Veri Boyutları**  | * En büyük boyut: Gösterilen zaman aralığında en büyük veri kümesinin MB cinsinden boyutu |
|  |  |

#### <a name="paginated-reports-tab"></a>Sayfalandırılmış raporlar sekmesi

**Sayfalandırılmış raporlar** sekmesinde, kapasitelerinizdeki sayfalandırılmış raporların durumu hakkında ayrıntılı ölçümler gösterilir.

![Sayfalandırılmış raporlar sekmesi](media/service-admin-premium-monitor-capacity/paginated-reports-tab.png)

**Sayfalandırılmış raporlar** sekmesi aşağıdaki ölçümleri içerir.

| **Rapor bölümü** | **Metrics** (Ölçümler) |
| --- | --- |
| **Genel kullanım** | * Toplam Görüntüleme Sayısı: Raporun bir kullanıcı tarafından toplam görüntülenme sayısı<br> * Satır Sayısı: Rapordaki veri satırlarının sayısı<br> * Alma (ortalama): Raporun verilerini almak için gereken ortalama süre (milisaniye cinsinden). Uzun süreler yavaş çalışan sorgulara veya başka veri kaynağı sorunlarına işaret ediyor olabilir. <br> * İşlem yapma (ortalama): Raporun verileri üzerinde işlem yapmak için gereken ortalama süre (milisaniye cinsinden)<br>* İşleme (ortalama): Raporu tarayıcıda işlemek için gereken ortalama süre (milisaniye cinsinden)<br> * Toplam süre: Raporun tüm aşamaları için gereken süre (milisaniye cinsinden)|
| **Ortalama Veri Alma Süresine Göre İlk 5 Rapor** | * Milisaniye cinsinden ortalama veri alma süresi en uzun olan beş rapor |
| **Ortalama Rapor İşlem Yapma Süresine Göre İlk 5 Rapor** | * Milisaniye cinsinden ortalama raporda işlem yapma süresi en uzun olan beş rapor |
| **Saatlik Süreler** | * Bir saatlik demetlere ayrılmış olarak ve yerel saatle bildirilen veri alma süresiyle işlem yapma ve işleme sürelerinin karşılaştırması |
| **Saatlik Sonuçlar** | * Bir saatlik demetlere ayrılan ve yerel saatle raporlanan başarılar, başarısızlıklar ve bellek tüketimi |
|  |  |

#### <a name="dataflows-tab"></a>Veri Akışları sekmesi

**Veri Akışları** sekmesinde, kapasitelerinizdeki veri akışlarının ayrıntılı yenileme ölçümleri gösterilir.

![Veri Akışları sekmesi](media/service-admin-premium-monitor-capacity/dataflows-tab.png)

**Veri Akışları** sekmesi aşağıdaki ölçümleri içerir.

| **Rapor bölümü** | **Metrics** (Ölçümler) |
| --- | --- |
| **Yenile** | * Toplam: Her veri akışı için toplam yenileme sayısı<br> * Güvenilirlik: Her veri akışı için tamamlanan yenilemelerin yüzdesi<br> * Ortalama Bekleme Süresi: Zamanlanan saat ve veri akışının yenileme başlangıcı arasındaki ortalama gecikme süresi (dakika cinsinden)<br> * En Uzun Bekleme Süresi: Veri akışının en uzun bekleme süresi (dakika cinsinden) <br> * Ortalama Süre: Veri akışı yenilemesinin ortalama süresi (dakika cinsinden)<br> * En Uzun Süre: Veri akışında en uzun zamandır çalışan yenilemenin süresi (dakika cinsinden) |
| **Ortalama Yenileme Süresine Göre En İyi 5 Veri Akışı** | * Dakika cinsinden ortalama yenileme süresi en uzun olan beş veri akışı |
| **Ortalama Bekleme Süresine Göre En iyi 5 Veri Akışı** | * Dakika cinsinden ortalama yenileme bekleme süresi en uzun olan beş veri akışı |
| **Saatlik Ortalama Yenileme Bekleme Süreleri** | * Bir saatlik demetlere ayrılmış ve yerel saatle bildirilen ortalama yenileme bekleme süresi. Yüksek yenileme bekleme süresi getiren birden çok ani artış, kapasiteye sık erişildiğini gösterir. |
| **Saatlik Yenileme Sayısı ve Bellek Tüketimi** | * Bir saatlik demetlere ayrılan ve yerel saatle raporlanan başarılar, başarısızlıklar ve bellek tüketimi |
|  |  |

#### <a name="resource-consumption-tab"></a>Kaynak Tüketimi sekmesi

**Kaynak Tüketimi** sekmesi tüm kapasite ve iş yüklerindeki CPU ve bellek tüketimini gösterir.

![Kaynak Tüketimi sekmesi](media/service-admin-premium-monitor-capacity/resource-consumption-tab.png)

**Kaynak Tüketimi** sekmesinde aşağıdaki ölçümler yer alır.

| **Rapor bölümü** | **Metrics** (Ölçümler) |
| --- | --- |
| **CPU tüketimi** | * Son yedi gün içinde CPU kullanımının eşik değerlerin %80'ini aşma sayısı, üç dakikalık parçalara ayrılmıştır |
| **Bellek tüketimi** | * Son yedi günün üç dakikalık demetlere ayrılmış bellek tüketimi |
|  |  |

#### <a name="ids-and-info-tab"></a>Kimlikler ve Bilgiler sekmesi

**Kimlikler ve Bilgiler** sekmesinde kapasitelerin, çalışma alanlarının ve iş yüklerinin adları, kimlikleri ve sahipleri yer alır.

![Kimlikler ve Bilgiler sekmesi](media/service-admin-premium-monitor-capacity/info-tab.png)

## <a name="monitor-power-bi-embedded-capacity"></a>Power BI Embedded kapasitesini izleme

Power BI Premium Capacity Metrics uygulamasını kullanarak Power BI Embedded içindeki *A SKU* kapasitelerini de izleyebilirsiniz. Yöneticisi olduğunuz kapasiteler raporda gösterilir. Ancak Power BI'a A SKU'larınız üzerinde belirli izinleri vermediğiniz sürece raporun yenilenmesi başarısız olur:

1. Azure portalda kapasitenizi açın.

1. **Erişim denetimi (IAM)** öğesine tıklayın ve “Power BI Premium” uygulamasını okuyucu rolüne ekleyin. Uygulamayı adıyla bulamazsanız istemci kimliğini kullanın: cb4dc29f-0bf4-402a-8b30-7511498ed654.

    ![Power BI Embedded izinleri](media/service-admin-premium-monitor-capacity/embedded-permissions.png)

> [!NOTE]
> Power BI Embedded kapasitesi kullanımını uygulamadan veya Azure portaldan izleyebilirsiniz ancak bu işlemi Power BI yönetici portalından gerçekleştiremezsiniz.

## <a name="basic-monitoring-in-the-admin-portal"></a>Yönetici portalında temel izleme

Yönetici portalının **Kapasite ayarları** bölümünde kapasitenize tarafından kullanılan kaynakların son yedi gün içindeki yükünü gösteren dört gösterge bulunur. Bu dört kutucuk saat ortalamasını baz alır ve son yedi günde ilgili ölçümün %80'in üzerinde olduğu saat sayısını gösterir. Bu ölçüm, son kullanıcı deneyimindeki olası düşüşleri ifade eder.

![Son 7 gün içindeki kullanım](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **Ölçüm** | **Açıklama** |
| --- | --- |
| CPU |CPU’nun %80 kullanımı aşma sayısı. |
| Bellek Temizleme |Arka uç çekirdeklerinizdeki bellek baskısını gösterir. Bu, özellikle birden çok veri kümesinin kullanılmasından kaynaklanan bellek baskısı nedeniyle veri kümelerinin bellekten ne sıklıkta çıkarıldığına ilişkin bir ölçümdür. |
| Memory Usage |Gigabayt (GB) olarak temsil edilen ortalama bellek kullanımı. |
| DQ/s | Direct Query ve Canlı Bağlantı sayısının, sınırın %80’ini aşma sayısı. <br> * Saniye başına toplam DirectQuery ve canlı bağlantı sorgusu sayısını sınırlarız. * Sınırlar şu şekildedir: P1 için 30/s, P2 için 60/s ve P3 için 120/s. * Direct Query ve canlı bağlantı sorguları sayısı yukarıdaki kısıtlamaya yönelik olarak birlikte hesaplanır. Örneğin, saniyede 15 DirectQuery bağlantısı ve 15 canlı bağlantıya sahipseniz kısıtlama noktanıza varmış olursunuz<br>* Bu, şirket içi ve bulut bağlantıları için aynı ölçüde geçerlidir. |
|  |  |

Ölçümler, geçen hafta içindeki kullanımı yansıtır.  Ölçümlerin daha ayrıntılı bir görünümünü görmek istiyorsanız, özet kutucuklarının herhangi birine tıklayarak bunu yapabilirsiniz.  Böylece, premium kapasitenize yönelik her bir ölçüm için ayrıntılı grafiklere gidersiniz. Aşağıdaki grafikte CPU ölçümünün ayrıntıları gösterilmektedir.

![CPU için ayrıntılı kullanım grafiği](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

Bu grafikler, geçen hafta için saatlik olarak özetlenir ve premium kapasitenizde performansla ilgili belirli olaylar olduğunda sorunu ayrıştırmanıza yardımcı olabilir.

Herhangi bir ölçüme yönelik temel verileri bir csv dosyasına da dışarı aktarabilirsiniz.  Bu dışarı aktarma, geçen haftanın her günü için üçer dakikalık aralıklarla size ayrıntılı bilgi sunar.

## <a name="next-steps"></a>Sonraki adımlar

Power BI Premium kapasitelerini izlemeyi anladığınıza göre kapasiteleri iyileştirme konusunda daha fazla bilgi edinebilirsiniz.

> [!div class="nextstepaction"]
> [Power BI Premium kapasite kaynak yönetimi ve en iyi duruma getirme](service-premium-understand-how-it-works.md)
