---
title: Yönetim portalını kullanarak Power BI Premium kapasitelerini izleme
description: Premium kapasitelerinizi izlemek için Power BI yönetim portalını kullanın.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
LocalizationGroup: Premium
ms.openlocfilehash: 51d7b29eee1394ec1bbcad8d69b39b4e45ecdb18
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "74700085"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Yönetim portalında kapasiteleri izleme

Yönetim portalının **Kapasite ayarları** alanındaki **Sistem durumu** sekmesi, kapasiteniz ve etkin iş yükleriniz ile ilgili ölçümler hakkında özet bilgiler sunar.  

![Portaldaki Kapasite Sistem Durumu sekmesi](media/service-admin-premium-monitor-portal/admin-portal-health.png)

Daha kapsamlı ölçümlere ihtiyacınız varsa [Power BI Premium Kapasite Ölçümleri](service-admin-premium-monitor-capacity.md) uygulamasını kullanın. Bu uygulama detaya gitme ve filtreleme özelliklerine ek olarak kapasite performansını etkileyen neredeyse tüm etmenler için en ayrıntılı ölçümleri sunar. Daha fazla bilgi edinmek için bkz. [Uygulama ile Premium kapasiteleri izleme](service-admin-premium-monitor-capacity.md).

## <a name="system-metrics"></a>Sistem Ölçümleri

**Sistem durumu** sekmesinde en üst düzeyde görüntülenen CPU ve bellek kullanımı, kapasiteyle ilgili en önemli ölçümler hakkında hızlı bir görünüm sunar. Bu ölçümler, kapasitede etkinleştirilmiş olan tüm iş yüklerinin birikimidir.

| **Ölçüm** | **Açıklama** |
| --- | --- |
| CPU KULLANIMI | Kullanılabilir toplam CPU değerinin yüzdesi olarak görüntülenen ortalama CPU kullanımı. |
| BELLEK KULLANIMI | Gigabayt (GB) cinsinden ortalama bellek kullanımı.|

## <a name="workload-metrics"></a>İş yükü ölçümleri

Kapasitede etkinleştirilen her bir iş yükü için. CPU ve bellek kullanımı gösterilir.

| **Ölçüm** | **Açıklama** |
| --- | --- |
| CPU KULLANIMI | Kullanılabilir toplam CPU değerinin yüzdesi olarak görüntülenen ortalama CPU kullanımı. |
| BELLEK KULLANIMI | Gigabayt (GB) cinsinden ortalama bellek kullanımı.|

### <a name="detailed-workload-metrics"></a>Ayrıntılı iş yükü ölçümleri

Her iş yükü el ölçümlere sahiptir. Gösterilen ölçüm türleri, iş yüküne göre değişir. Bir iş yükünün ayrıntılı ölçümlerini görmek için genişlet (aşağı) okuna tıklayın.

![İş yükü durumunu genişletme](media/service-admin-premium-monitor-portal/admin-portal-health-expand.png)

#### <a name="dataflows"></a>Veri akışları

##### <a name="dataflow-operations"></a>Veri Akışı İşlemleri

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Toplam Sayı | Her veri akışı için toplam yenileme sayısı. |
| Başarı Sayısı | Her veri akışı için toplam başarılı yenileme sayısı.|
| Ortalama Süre (dk) | Veri akışı yenilemesinin ortalama süresi (dakika cinsinden) |
| En Uzun Süre (dk) | Veri akışında en uzun zamandır çalışan yenilemenin süresi (dakika cinsinden). |
| Ortalama Bekleme Süresi (dk) | Zamanlanan saat ve veri akışının yenileme başlangıcı arasındaki ortalama gecikme süresi (dakika cinsinden). |
| En Fazla Bekleme Süresi (dk) | Veri akışının en uzun bekleme süresi (dakika cinsinden).  |

#### <a name="datasets"></a>Veri kümeleri

##### <a name="refresh"></a>Yenile

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Toplam Sayı | Her veri kümesi için toplam yenileme sayısı. |
| Başarı Sayısı | Her veri kümesi için toplam başarılı yenileme sayısı. |
| Hata Sayısı | Her veri kümesi için toplam başarısız yenileme sayısı. |
| Başarı Oranı  | Başarılı yenileme sayısının son toplam başarılı yenileme sayısına bölünmesiyle elde edilen sonuç. Güvenilirlik. |
| Ortalama Süre (dk) | Veri kümesi yenilemesinin ortalama süresi (dakika cinsinden).  |
| En Uzun Süre (dk) | Veri kümesinin en uzun çalışan yenilemesinin süresi (dakika cinsinden). |
| Ortalama Bekleme Süresi (dk) | Zamanlanan saat ve veri kümesinin yenileme başlangıcı arasındaki ortalama gecikme süresi (dakika cinsinden). |
| En Fazla Bekleme Süresi (dk) | Veri kümesi için en uzun bekleme süresi (dakika cinsinden). |

##### <a name="query"></a>Sorgu

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Toplam Sayı | Veri kümesi için çalıştırılan sorguların toplam sayısı. |
| Ortalama Süre (ms) |Veri kümesi için ortalama sorgu süresi (milisaniye cinsinden)|
| En Uzun Süre (ms) |Veri kümesinde en uzun süre çalışan sorgunun süresi (milisaniye cinsinden). |
| Ortalama Bekleme Süresi (ms) |Veri kümesi için ortalama sorgu bekleme süresi (milisaniye cinsinden). |
| En Fazla Bekleme Süresi (ms) |Veri kümesinde en uzun süre bekleyen sorgunun süresi (milisaniye cinsinden). |

##### <a name="eviction"></a>Çıkarma

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Model Sayısı | Bu kapasite için veri kümesi çıkarmalarının toplam sayısı. Kapasite, bellek baskısıyla karşı karşıya kaldığında düğüm bir veya daha fazla veri kümesini bellekten çıkarır. Devre dışı olan veri kümeleri (sorgu/yenileme işlemi yürütülmeyen) önce çıkarılır. Çıkarma sırası, 'en önce kullanılan' (LRU) ölçütüne göre belirlenir. |

#### <a name="paginated-reports"></a>Sayfalandırılmış Raporlar

##### <a name="report-execution"></a>Rapor Yürütme

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Yürütme Sayısı  | Raporun kullanıcılar tarafından toplam yürütülme ve görüntülenme sayısı.|

##### <a name="report-usage"></a>Rapor Kullanımı

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Başarı Sayısı | Raporun bir kullanıcı tarafından toplam görüntülenme sayısı. |
| Hata Sayısı |Raporun bir kullanıcı tarafından toplam görüntülenme sayısı.|
| Satır Sayısı |Rapordaki veri satırlarının sayısı. |
| Veri Alma Süresi (ms) |Raporun verilerini almak için gereken ortalama süre (milisaniye cinsinden). Uzun süreler yavaş çalışan sorgulara veya başka veri kaynağı sorunlarına işaret ediyor olabilir.  |
| İşlem Süresi (ms) |Raporun verileri üzerinde işlem yapmak için gereken ortalama süre (milisaniye cinsinden). |
| İşleme Süresi (ms) |Raporu tarayıcıda işlemek için gereken ortalama süre (milisaniye cinsinden). |

> [!NOTE]
> **Yapay zeka** iş yükü için ayrıntılı ölçümler henüz mevcut değildir.

## <a name="next-steps"></a>Sonraki adımlar

Power BI Premium kapasitelerini izlemeyi anladığınıza göre kapasiteleri iyileştirme konusunda daha fazla bilgi edinebilirsiniz.

> [!div class="nextstepaction"]
> [Power BI Premium kapasitelerini en iyi duruma getirme](service-premium-capacity-optimize.md)
