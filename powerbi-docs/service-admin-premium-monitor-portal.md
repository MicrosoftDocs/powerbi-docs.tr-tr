---
title: Yönetim portalını kullanarak Power BI Premium kapasitelerini izleme
description: Premium kapasitelerinizi izlemek için Power BI yönetim portalını kullanın.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
LocalizationGroup: Premium
ms.openlocfilehash: 36b03a67e7c02702a70b6486880cc8eabf93e823
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65564887"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Yönetim portalında kapasiteleri izleme

**Sistem durumu** sekmesinde **kapasite ayarlarını** alanı Yönetim Portalı'nda, kapasite ve etkin iş yükleri hakkında özet bir ölçüm sağlar.  

![Portalda kapasite sistem durumu sekmesi](media/service-admin-premium-monitor-portal/admin-portal-health.png)

Daha kapsamlı ölçüler ihtiyacınız varsa, [Power BI Premium kapasite ölçümleri](service-admin-premium-monitor-capacity.md) uygulama. En ayrıntılı ölçümler için neredeyse her açıdan kapasite performansını ve uygulama detaya gitme ve filtreleme sağlar. Daha fazla bilgi için bkz. [İzleyici Premium kapasiteleri uygulamasıyla](service-admin-premium-monitor-capacity.md).

## <a name="system-metrics"></a>Sistem ölçümlerini

Üzerinde **sistem durumu** sekmesinde, yüksek düzeyde CPU kullanımı ve bellek kullanım kapasitesi için en önemli ölçümler hızlı bir görünümünü sağlar. Bu ölçümler toplu, dahil olmak üzere tüm iş yükleri kapasite için etkindir.

| **Ölçüm** | **Açıklama** |
| --- | --- |
| CPU KULLANIMI | Toplam kullanılabilir CPU yüzdesi cinsinden ortalama CPU kullanımı. |
| BELLEK KULLANIMI | Gigabayt (GB) cinsinden ortalama bellek kullanımı.|

## <a name="workload-metrics"></a>İş yükü ölçümleri

Kapasiteyi etkin her iş yükü için. CPU kullanımı ve bellek kullanımı gösterilmektedir.

| **Ölçüm** | **Açıklama** |
| --- | --- |
| CPU KULLANIMI | Toplam kullanılabilir CPU yüzdesi cinsinden ortalama CPU kullanımı. |
| BELLEK KULLANIMI | Gigabayt (GB) cinsinden ortalama bellek kullanımı.|

### <a name="detailed-workload-metrics"></a>Ayrıntılı iş yükü ölçümleri

Her iş yükünün ek ölçümler vardır. Gösterilen ölçümleri türü iş yüküne bağlıdır. Bir iş yükü için ayrıntılı ölçümler görmek için Genişlet (basılı) oka tıklayın.

![İş yükü sistem durumu genişletin](media/service-admin-premium-monitor-portal/admin-portal-health-expand.png)

#### <a name="dataflows"></a>Veri akışları

##### <a name="dataflow-operations"></a>Veri akışı işlem

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Toplam Sayı | Her veri akışı için toplam yenileme sayısı. |
| Başarı Sayısı | Her veri akışı için toplam başarılı yeniler.|
| Ortalama süre (dk) | Veri akışı yenilemesinin ortalama süresi (dakika cinsinden) |
| En uzun süre (dk) | Veri akışında en uzun zamandır çalışan yenilemenin süresi (dakika cinsinden). |
| Ortalama Bekleme süresi (dak) | Zamanlanan saat ve veri akışının yenileme başlangıcı arasındaki ortalama gecikme süresi (dakika cinsinden). |
| En fazla bekleme süresi (dk) | Veri akışının en uzun bekleme süresi (dakika cinsinden).  |

#### <a name="datasets"></a>Veri kümeleri

##### <a name="refresh"></a>Yenile

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Toplam Sayı | Her veri kümesi için toplam yenileme sayısı. |
| Başarı Sayısı | Toplam her veri kümesi için yenileme başarılı. |
| Hata Sayısı | Toplam, her veri kümesi için yenileme başarısız oldu. |
| Başarı oranı  | Başarılı yenileme ölçmek için toplam yenilemelerinde bölünmüş sayısı. Güvenilirlik. |
| Ortalama süre (dk) | Veri kümesi yenilemesinin ortalama süresi (dakika cinsinden).  |
| En uzun süre (dk) | Veri kümesinin en uzun çalışan yenilemesinin süresi (dakika cinsinden). |
| Ortalama Bekleme süresi (dak) | Zamanlanan saat ve veri kümesinin yenileme başlangıcı arasındaki ortalama gecikme süresi (dakika cinsinden). |
| En fazla bekleme süresi (dk) | Veri kümesi için en uzun bekleme süresi (dakika cinsinden). |

##### <a name="query"></a>Sorgu

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Toplam Sayı | Veri kümesi için çalıştırılan sorguların toplam sayısı. |
| Ortalama Süre (ms) |Veri kümesi için ortalama sorgu süresi (milisaniye cinsinden)|
| En Uzun Süre (ms) |Veri kümesinde en uzun süre çalışan sorgunun süresi (milisaniye cinsinden). |
| Ortalama Bekleme Süresi (ms) |Veri kümesi için ortalama sorgu bekleme süresi (milisaniye cinsinden). |
| En fazla bekleme süresi (ms) |Veri kümesinde en uzun süre bekleyen sorgunun süresi (milisaniye cinsinden). |

##### <a name="eviction"></a>Çıkarma

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Model sayısı | Bu kapasite için veri kümesi çıkarmaları toplam sayısı. Kapasite, bellek baskısıyla karşı karşıya kaldığında düğüm bir veya daha fazla veri kümesini bellekten çıkarır. Devre dışı olan veri kümeleri (sorgu/yenileme işlemi yürütülmeyen) önce çıkarılır. Çıkarma sırası, 'en önce kullanılan' (LRU) ölçütüne göre belirlenir. |

#### <a name="paginated-reports"></a>Sayfalandırılmış Raporlar

##### <a name="report-execution"></a>Rapor yürütme

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Yürütme sayısı  | Rapor yürütüldü sayısı ve kullanıcılar tarafından görüntülenebilir.|

##### <a name="report-usage"></a>Rapor kullanım

| **Ölçüm** | **Açıklama** |
| --- | --- |
| Başarı Sayısı | Rapor, bir kullanıcı tarafından görüntülenmiş sayısı. |
| Hata Sayısı |Rapor, bir kullanıcı tarafından görüntülenmiş sayısı.|
| Satır Sayısı |Rapordaki veri satırlarının sayısı. |
| Veri alma süresi (ms) |Raporun verilerini almak için gereken ortalama süre (milisaniye cinsinden). Uzun süreler yavaş çalışan sorgulara veya başka veri kaynağı sorunlarına işaret ediyor olabilir.  |
| İşleme süresi (ms) |Raporun verileri üzerinde işlem yapmak için gereken ortalama süre (milisaniye cinsinden). |
| İşleme süresi (ms) |Raporu tarayıcıda işlemek için gereken ortalama süre (milisaniye cinsinden). |

> [!NOTE]
> Ayrıntılı ölçümler için **AI** iş yükü henüz mevcut değildir.

## <a name="next-steps"></a>Sonraki adımlar

Power BI Premium kapasitelerini izlemeyi anladığınıza göre kapasiteleri iyileştirme konusunda daha fazla bilgi edinebilirsiniz.

> [!div class="nextstepaction"]
> [Power BI Premium kapasiteleri en iyi duruma getirme](service-premium-capacity-optimize.md)
