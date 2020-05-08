---
title: Power BI Embedded Analytics’te kapasite ve SKU’lar
description: Power BI tümleşik analize ilişkin kapasite ve SKU’lar hakkında bilgi edinin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/11/2020
ms.openlocfilehash: 27d6ddd9b24e09805bd22150a22347e5cd93c8e0
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79492848"
---
# <a name="capacity-and-skus-in-power-bi-embedded-analytics"></a>Power BI Embedded Analytics’te kapasite ve SKU’lar

Üretim ortamına geçerken, Power BI tümleşik analiz ile ekli Power BI içeriği yayımlamak için ayrılmış bir kapasite (*A*, *EM* veya *P* SKU’su) gerekir.

Kapasite, yalnızca özel kullanım için ayrılmış kaynak kümesidir. Kullanıcı başına lisans satın almak zorunda kalmadan, kullanıcılara pano, rapor ve veri kümesi yayımlamanıza olanak tanır. Ayrıca, içeriğiniz için güvenilir ve tutarlı performans sunar.

>[!NOTE]
>Yayımlamak için bir Power BI Pro hesabı gerekir.

## <a name="what-is-embedded-analytics"></a>Tümleşik analiz nedir?

Power BI tümleşik analiz iki çözümü içerir:
* *Power BI Embedded*: Azure teklifi
* *Power BI Premium*’un bir parçası olarak Power BI ekleme: Office teklifi

### <a name="power-bi-embedded"></a>Power BI Embedded

Power BI Embedded, uygulamalarına görsel eklemek isteyen ISV’lere ve geliştiricilere yöneliktir.

Power BI Embedded kullanan uygulamalar, kullanıcılara Power BI Embedded kapasitesinde depolanan içerikleri tüketme olanağı tanır.

### <a name="power-bi-premium"></a>Power BI Premium

[Power BI Premium](../../service-premium-what-is.md), kuruluşunu, iş ortaklarını, müşterilerini ve sağlayıcılarını tek bir görünümde sunan eksiksiz bir BI çözümü isteyen kuruluşlar için tasarlanmıştır.

Power BI Premium, kullanıcıların mobil uygulamalar ve şirket içinde geliştirilen uygulamalar aracılığıyla veya Power BI portalında (Power BI hizmeti) içerik tüketmesine olanak tanıyan bir SaaS ürünüdür. Bu, Power BI Premium ile hem iç hem de dış müşterilere yönelik bir çözüm sunulmasına olanak tanır.

## <a name="capacity-and-skus"></a>Kapasite ve SKU’lar

Her kapasite çeşitli SKU’ları içerir. Her SKU, bellek ve işlem gücü için farklı kaynak katmanları sunar. İhtiyaç duyduğunuz SKU türü, dağıtmak istediğiniz çözüm türüne bağlıdır.

Her katman için hangi iş yüklerinin desteklendiğini öğrenmek üzere [Premium kapasitedeki iş yüklerini yapılandırma](../../service-admin-premium-workloads.md) makalesine bakın

Kapasitenizi planlayıp test etmek için şu bağlantıları kullanın:
* [Kapasite planlaması](embedded-capacity-planning.md)
* [Test yaklaşımları](../../service-premium-capacity-optimize.md#testing-approaches)

### <a name="power-bi-embedded-skus"></a>Power BI Embedded SKU’ları

Power BI Embedded, bir [*a* SKU’su](../../service-admin-premium-purchase.md#purchase-a-skus-for-testing-and-other-scenarios) ile sunulur.

### <a name="power-bi-premium-skus"></a>Power BI Premium SKU’ları

Power BI Premium, *P* ve *EM* olmak üzere iki SKU sunar.
* [*P* ve *EM* SKU’ları arasındaki farkları öğrenin](../../service-premium-what-is.md#subscriptions-and-licensing)
* [Premium SKU satın alın](../../service-admin-premium-purchase.md)

### <a name="which-sku-should-i-use"></a>Hangi SKU’yu kullanmam gerekir?

Bu tablo, özelliklerin özetini, gereken kapasiteyi ve her birinin gerektirdiği belirli SKU’yu sunar. 

</br>
<table>
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<tbody>
<tr>
<td style="text-align: center"; colspan="2"><p><b>Özellik</b></p></td>
<td style="text-align: center">
<p><b>Power BI Embedded</b></p>
</td>
<td style="text-align: center"; colspan="2">
<p><b>Power BI Premium</b></p>
</td>
</tr>
<tr>
<td><p><em>Ne tüketilir?</em><p></td>
<td><p><em>Bunu ne tüketir?</em><p></td>
<td style="text-align: center"><p><em>A SKU’ları</br>(Azure)</em></p></td>
<td style="text-align: center"><p><em>EM SKU’ları</br>(Office)</em></p></td>
<td style="text-align: center"><p><em>P SKU’ları</br>(Office)</em></p></td>
</tr>
<tr>
<td>Power BI çalışma alanından yapıtları ekleme</td>
<td>
</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="2">Power BI raporları</td>
<td>Kuruluşunuza yönelik ekli uygulama</br>(veriler kullanıcıya aittir)</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Müşterilerinize yönelik ekli uygulama</br>(veriler uygulamaya aittir)</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="3">Power BI içeriği<br>(ücretsiz Power BI lisansı içerir)</td>
<td>Power BI hizmeti</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Power BI Mobil</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>MS Office uygulamaları</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
</tbody>
</table>

### <a name="capacity-considerations"></a>Kapasiteye ilişkin önemli noktalar

Aşağıdaki tablo, kapasite başına ödeme ve kullanıma ilişkin önemli noktaları içerir.

</br>
<table>
<tbody>
<tr>
<td></td>
<td style="text-align: center;"><p><strong>Power BI Embedded</strong></p></td>
<td style="text-align: center;" colspan="2"><p><strong>Power BI Premium</strong></p></td>
</tr>
<tr>
<td><p><strong>Teklif</strong></p></td>
<td style="text-align: center;"><p>Azure</p></td>
<td style="text-align: center;" colspan="2"><p>Office</p></td>
</tr>
<tr>
<td><p><strong>SKU</strong></p></td>
<td style="text-align: center;"><p>A</p></td>
<td style="text-align: center;"><p>EM</p></td>
<td style="text-align: center;"><p>P</p></td>
</tr>
<tr>
<td><p><strong>Faturalandırma</strong></td>
<td style="text-align: center;">Saatlik</td>
<td style="text-align: center;">Aylık</td>
<td style="text-align: center;">Aylık</td>
</tr>
<tr>
<td><p><strong>Taahhüt</strong></td>
<td style="text-align: center;">Yok</td>
<td style="text-align: center;">Yıllık</td>
<td style="text-align: center;">Aylık veya yıllık</td>
</tr>
<tr>
<td valign="top"><p><strong>Kullanım</strong></td>
<td style="text-align: center;">Azure kaynaklarında şunlar yapılabilir:</br>- <a href="azure-pbie-scale-capacity.md">Ölçeği büyütme veya küçültme</a></br>- <a href="azure-pbie-pause-start.md">Duraklatma ve sürdürme</a>
</td>
<td style="text-align: center;">Uygulamalara ve</br> Microsoft uygulamalarına ekleme</td>
<td style="text-align: center;">Uygulamalara ve</br> Power BI hizmetine ekleme</td>
</tr>
</tbody>
</table>

### <a name="sku-memory-and-computing-power"></a>SKU belleği ve işlem gücü

Aşağıdaki tabloda her SKU'nun kaynakları ve limitleri açıklanmaktadır.

| Kapasite Düğümleri | Toplam sanal çekirdek sayısı | Arka uç sanal çekirdek sayısı | RAM (GB) | Ön uç sanal çekirdek sayısı | DirectQuery/Canlı Bağlantı (saniyede) | Model Yenileme Paralelliği |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0,5 | 2.5 | 0,5 | 3,75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7,5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| P4 | 64 | 32 | 200 | 32 | 240 | 48 |
| P5 | 128 | 64 | 400 | 64 | 480 | 96 |
| | | | | | | |

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Uygulamalardan ekleme](embed-from-apps.md)