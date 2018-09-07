---
title: Kuruluşunuzdaki Power BI Premium kapasitelerini izleme
description: Power BI yönetici portalını ve Power BI Premium Capacity Metrics uygulamasını kullanma
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 08/29/2018
LocalizationGroup: Premium
ms.openlocfilehash: 8e19bc596bef3862dca79ac92ffbd74954a9c756
ms.sourcegitcommit: 6be2c54f2703f307457360baef32aee16f338067
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43300173"
---
# <a name="monitor-power-bi-premium-capacities-in-your-organization"></a>Kuruluşunuzdaki Power BI Premium kapasitelerini izleme

Bu makalede, Power BI Premium kapasitelerinizin ölçümlerini izlemeyle ilgili genel bakış bilgilerine yer verilmiştir. Kapasite kullanımını izleyerek kapasitelerinizi yönetme konusunda bilgiye dayalı bir yaklaşım sergileyebilirsiniz. 

Kapasiteyi izlemek için Power BI Premium Capacity Metrics uygulamasını veya yönetici portalını kullanabilirsiniz. Daha fazla ayrıntı sunduğu için uygulamayı kullanmanızı öneririz ancak bu makalede iki seçeneğe de bakacağız.

## <a name="install-the-premium-capacity-metrics-app"></a>Premium Capacity Metrics uygulamasını yükleme

Doğrudan [Premium Capacity Metrics uygulamasına](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) gidebilir veya Power BI'daki diğer uygulamalar gibi yükleyebilirsiniz.

> [!IMPORTANT]
> Bu uygulamayı yüklemek ve kullanmak için en az bir kapasitede kapasite yöneticisi olmanız gerekir. Power BI yöneticisi olmanız yeterli değildir. 

1. Power BI'da **Uygulamalar**'a tıklayın.

    ![Uygulamalar bölümüne gidin](media/service-admin-premium-monitor-capacity/apps.png)

2. Sağ taraftaki **Uygulama edinin**'e tıklayın.

3. **Uygulamalar** kategorisinde **Power BI Premium Capacity Metrics uygulamasını** arayın.

4. Uygulamayı yüklemek için abone olun.

Uygulamayı yükledikten sonra kuruluşunuzdaki kapasitelere ait ölçümleri görebilirsiniz. Şimdi kullanılabilir durumdaki bazı önemli ölçümlere göz atalım.

## <a name="use-the-metrics-app"></a>Ölçümler uygulamasını kullanma 
Uygulamayı ilk açtığınızda yönetici haklarına sahip olduğunuz tüm kapasitelerin özetini kapsayan bir pano gösterilir.

![Premium raporuna genel bakış](media/service-admin-premium-monitor-capacity/app-dashboard.png)

### <a name="filtering"></a>Filtreleme

**Filters applied to all pages** (Tüm sayfalara uygulanmış olan filtreler) sekmesinden kapasite, veri kümesi ve/veya son yedi gün içindeki bir tarih aralığını seçebilirsiniz. Seçtiğiniz filtreler bu raporla ilgili tüm sayfalara ve kutucuklara uygulanır. Seçim yapılmadığında rapor, varsayılan olarak sahip olduğunuz tüm kapasiteler için son haftanın ölçümlerini gösterir.

![Premium raporuna genel bakış](media/service-admin-premium-monitor-capacity/premium-report-overview.png)

### <a name="summary-tab"></a>Summary (Özet) sekmesi

**Summary** (Özet) sekmesinde varlıklar, sistem ve veri kümelerine göre kapasiteler gösterilir.

![Tüm sayfalara uygulanan filtreler](media/service-admin-premium-monitor-capacity/premium-summary-report.png)

| **Area** (Alan) | **Metrics** (Ölçümler) |
| --- | --- |
| **Entities** (Varlıklar) | * Sahip olduğunuz kapasite sayısı<br> * Kapasitenizdeki benzersiz veri kümesi sayısı<br> * Kapasitenizdeki benzersiz çalışma alanı sayısı |
| **System** (Sistem) | * GB cinsinden son yedi gün içindeki ortalama bellek kullanımı<br> * GB cinsinden son yedi gün içindeki en yüksek bellek tüketimi ve gerçekleştiği yerel saat<br> * Son yedi gün içinde CPU kullanımının eşik değerlerin %80'ini aşma sayısı, üç dakikalık parçalara ayrılmıştır<br> * Son yedi gün içinde CPU kullanımının %80'ini en çok aştığı zaman, bir saatlik parçalara ayrılmıştır ve yerel saatte gösterilir<br> * Son yedi gün içinde Doğrudan sorgu/Canlı bağlantı kullanımının eşik değerlerin %80'ini aşma sayısı, üç dakikalık parçalara ayrılmıştır<br> * Son yedi gün içinde Doğrudan sorgu/Canlı bağlantı kullanımının %80'ini en çok aştığı zaman, bir saatlik parçalara ayrılmıştır ve yerel saatte gösterilir |
| **Veri Kümesi İş Yükleri** | * Son yedi gün içinde gerçekleştirilen toplam yenileme sayısı<br> * Son yedi gün içinde gerçekleştirilen toplam başarılı yenileme sayısı<br> * Son yedi gün içinde gerçekleştirilen toplam başarısız yenileme sayısı<br> * Yetersiz bellek nedeniyle başarısız olan toplam yenileme sayısı<br> * Dakika cinsinden ortalama yenileme süresi, işlemin tamamlanması için geçen süre<br> * Dakika cinsinden ortalama yenileme bekleme süresi, planlanan zamanla işlemin başlatılması arasındaki ortalama gecikme<br> * Son yedi gün içinde çalıştırılan toplam sorgu sayısı<br> * Son yedi gün içinde gerçekleştirilen toplam başarılı sorgu sayısı<br> * Son yedi gün içinde gerçekleştirilen toplam başarısız sorgu sayısı<br> * Dakika cinsinden ortalama sorgu süresi, işlemin tamamlanması için geçen süre<br> * Bellek baskısı nedeniyle çıkarılan toplam model sayısı |
|  |  |

### <a name="refreshes-tab"></a>Refreshes (Yenilemeler) sekmesi

**Refreshes** (Yenilemeler) sekmesinde son yedi gün içindeki toplam yenileme sayısı, başarılı ölçümler, ortalama/maksimum yenileme bekleme süresi ve ortalama/maksimum yenileme süresi veri kümelerine ayrılmış şekilde gösterilir. En alttaki iki grafikte yenilemelerle GB cinsinden bellek tüketiminin karşılaştırması gösterilir. Ortalama bekleme süreleri bir saatlik parçalara ayrılır ve yerel saate göre belirtilir. Üstteki çubukta veri kümesinin yenilenmesinin tamamlanması için geçen maksimum süre (yenileme süresi) ve maksimum yenileme bekleme süresi toplamına göre ilk beş veri kümesi listelenir. Birden çok yüksek yenileme bekleme süresi artışı kapasiteye sık erişildiğini gösterir.

![Premium yenileme raporu](media/service-admin-premium-monitor-capacity/premium-refresh-report.png)

### <a name="datasets-tab"></a>Veri Kümeleri sekmesi

**Datasets** (Veri kümeleri) sekmesinde saatlere göre bellek baskısı nedeniyle çıkarılan tam veri kümeleri gösterilir.

![Premium veri kümesi raporu](media/service-admin-premium-monitor-capacity/premium-datasets-report.png)

### <a name="system-tab"></a>System (Sistem) sekmesi

**System** (Sistem) sekmesi yüksek CPU kullanımını (%80 kullanımın aşıldığı durumların sayısını), yüksek Doğrudan Sorgu/Canlı bağlantı kullanımını ve Bellek Tüketimini gösterir.

![Premium sistem raporu](media/service-admin-premium-monitor-capacity/premium-system-report.png)

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
