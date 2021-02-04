---
title: Power BI tümleşik analizlerindeki, daha iyi tümleşik BI içgörüleri sağlayan Kapasite ve SKU'lar
description: Power BI tümleşik analize ilişkin kapasite ve SKU’lar hakkında bilgi edinin. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/14/2021
ms.openlocfilehash: b37182cbdf030e8b32fdfe307d0a652fef678b9b
ms.sourcegitcommit: c33e53e1fab1f29872297524a7b4f5af6c806798
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99533039"
---
# <a name="capacity-and-skus-in-power-bi-embedded-analytics"></a>Power BI Embedded Analytics’te kapasite ve SKU’lar

Üretim ortamına geçerken, Power BI tümleşik analiz ile ekli Power BI içeriği yayımlamak için bir kapasite (*A*, *EM* veya *P* SKU’su) gerekir.

Kapasite, yalnızca özel kullanım için ayrılmış kaynak kümesidir. Kullanıcı başına lisans satın almak zorunda kalmadan, kullanıcılara pano, rapor ve veri kümesi yayımlamanıza olanak tanır. Ayrıca, içeriğiniz için güvenilir ve tutarlı performans sunar.

>[!NOTE]
>Yayımlamak için bir Power BI Pro hesabı gerekir.

## <a name="what-is-embedded-analytics"></a>Tümleşik analiz nedir?

Power BI tümleşik analiz iki çözümü içerir:

* *Power BI Embedded*: Azure teklifi

* *Power BI Premium*’un bir parçası olarak Power BI ekleme: Microsoft Office teklifi

### <a name="power-bi-embedded"></a>Power BI Embedded

Power BI Embedded, uygulamalarına görsel eklemek isteyen ISV’lere ve geliştiricilere yöneliktir.

Power BI Embedded kullanan uygulamalar, kullanıcılara Power BI Embedded kapasitesinde depolanan içerikleri tüketme olanağı tanır.

>[!NOTE]
>Kısa bir süre önce **Embedded 2. Nesil** adıyla yeni bir Power BI Embedded sürümü kullanıma sunuldu. Embedded 2. Nesil, Embedded kapasitelerinin yönetilmesini kolaylaştıracak ve Power BI Embedded deneyimini geliştirecek. Daha fazla bilgi için bkz. [Power BI Embedded 2. Nesil](power-bi-embedded-generation-2.md).

### <a name="power-bi-premium"></a>Power BI Premium

[Power BI Premium](../../admin/service-premium-what-is.md), kuruluşunu, iş ortaklarını, müşterilerini ve sağlayıcılarını tek bir görünümde sunan eksiksiz bir BI çözümü isteyen kuruluşlar için tasarlanmıştır.

Power BI Premium, kullanıcıların mobil uygulamalar ve şirket içinde geliştirilen uygulamalar aracılığıyla veya Power BI portalında (Power BI hizmeti) içerik tüketmesine olanak tanıyan bir SaaS ürünüdür. Bu, Power BI Premium ile hem iç hem de dış müşterilere yönelik bir çözüm sunulmasına olanak tanır.

## <a name="capacity-and-skus"></a>Kapasite ve SKU’lar

Her kapasite çeşitli SKU’ları içerir. Her SKU, bellek ve işlem gücü için farklı kaynak katmanları sunar. İhtiyaç duyduğunuz SKU türü, dağıtmak istediğiniz çözüm türüne bağlıdır.

Her katman için hangi iş yüklerinin desteklendiğini öğrenmek üzere [Premium kapasitedeki iş yüklerini yapılandırma](../../admin/service-admin-premium-workloads.md) makalesine bakın

Kapasitenizi planlayıp test etmek için şu bağlantıları kullanın:
* [Kapasite planlaması](embedded-capacity-planning.md)
* [Test yaklaşımları](../../admin/service-premium-capacity-optimize.md#testing-approaches)

### <a name="power-bi-embedded-skus"></a>Power BI Embedded SKU’ları

Power BI Embedded, bir [*a* SKU’su](../../admin/service-admin-premium-purchase.md#purchase-a-skus-for-testing-and-other-scenarios) ile sunulur.

### <a name="power-bi-premium-skus"></a>Power BI Premium SKU’ları

Power BI Premium, *P* ve *EM* olmak üzere iki SKU sunar.
* [*P* ve *EM* SKU’ları arasındaki farkları öğrenin](../../admin/service-premium-what-is.md#subscriptions-and-licensing)
* [Premium SKU satın alın](../../admin/service-admin-premium-purchase.md)

### <a name="which-sku-should-i-use"></a>Hangi SKU’yu kullanmam gerekir?

Aşağıdaki tablo özelliklerin özetini, gereken kapasiteyi ve her birinin gerektirdiği belirli SKU’yu sunar.

Bu tabloda özel bir uygulama, ekli analiz kullanılarak oluşturulan bir web uygulamasına başvurur. Geliştirici olarak özel web uygulamasına eklediğinizde (JavaScript veya .NET SDK’larını ya da REST API’leri kullanarak), UX’i denetleme ve özelleştirme olanağınız vardır. Power BI hizmeti ve Power BI Mobil gibi diğer ekleme seçeneklerini kullandığınızda bu olanak sağlanmaz.

| Senaryo | Azure   | Office          |
|----------|---------|-----------------|
|          | (A SKU’su) | (P ve EM SKU’ları) |
|[Müşterileriniz için ekleme](embed-sample-for-customers.md)</br>(veriler uygulamaya aittir)     |✔        |✔        |
|[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)</br>(veriler kullanıcıya aittir)     |✖        |✔         |
|Microsoft 365 uygulamaları</br>(eski adı Office 365 uygulamaları)<ul><li>[Teams’de ekleme](../../collaborate-share/service-embed-report-microsoft-teams.md)</li><li>[SharePoint’te ekleme](../../collaborate-share/service-embed-report-spo.md)</li></ul>     |✖        |✔        |
|[Güvenli URL ekleme](../../collaborate-share/service-embed-secure.md)</br>(Power BI hizmetinden ekleme)     |✖        |✔        |

>[!NOTE]
>* Power BI uygulama çalışma alanına içerik yayımlamak için [Power BI Pro lisansı](../../admin/service-admin-purchasing-power-bi-pro.md) gerekir.
>* Ücretsiz Power BI kullanıcılarının Power BI hizmetinde Power BI uygulamalarını ve paylaşılan içeriği kullanmasına yalnızca **P SKU’su** izin verir.

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
<td style="text-align: center"><p>Azure</p></td>
<td style="text-align: center" colspan="2"><p>Office</p></td>
</tr>
<tr>
<td><p><strong>SKU</strong></p></td>
<td style="text-align: center"><p>A</p></td>
<td style="text-align: center"><p>EM</p></td>
<td style="text-align: center"><p>P</p></td>
</tr>
<tr>
<td><p><strong>Faturalandırma</strong></td>
<td style="text-align: center">Saatlik</td>
<td style="text-align: center">Aylık</td>
<td style="text-align: center">Aylık</td>
</tr>
<tr>
<td><p><strong>Taahhüt</strong></td>
<td style="text-align: center">Yok</td>
<td style="text-align: center">Yıllık</td>
<td style="text-align: center">Aylık veya yıllık</td>
</tr>
<tr>
<td valign="top"><p><strong>Kullanım</strong></td>
<td style="text-align: center">Azure kaynaklarında şunlar yapılabilir:<li><a href="azure-pbie-scale-capacity.md">Ölçeği büyütme veya küçültme</a></li><li><a href="azure-pbie-pause-start.md">Duraklatma ve sürdürme</a>
</td></li>
<td style="text-align: center">Uygulamalara ve</br> Microsoft uygulamalarına ekleme</td>
<td style="text-align: center">Uygulamalara ve</br> Power BI hizmetine ekleme</td>
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

#### <a name="embedded-gen-2-memory-enhancements-preview"></a>Katıştırılmış Gen 2 bellek geliştirmeleri (Önizleme)

[Power BI Embedded oluşturma 2](power-bi-embedded-generation-2.md) ' de (katıştırılmış Gen 2 olarak da bilinir), her düğüm boyutunda kullanılabilir bellek miktarı, tek bir Power BI öğenin (rapor veya pano gibi) bellek kaplama sınırına ayarlanır ve bu da belleğin birikimli tüketimine uygulanmaz. Örneğin, gömülü bir Gen2 a4 kapasitesinde, yalnızca tek bir veri kümesi boyutu 25 Power BI Embedded GB ile sınırlıdır ve bu, aynı anda işlenen veri kümelerinin toplam bellek parmak izi 25 GB ile sınırlıdır.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Uygulamalardan ekleme](./index.yml)