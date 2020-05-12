---
title: Power BI çalışma alanı rolleri
description: Power BI çalışma alanı rolleri tablosu
services: powerbi
author: maggiesMSFT
ms.service: powerbi
ms.topic: include
ms.date: 04/23/2020
ms.author: maggies
ms.custom: include file
ms.openlocfilehash: 5ed3a65f1ef65640c76ada765931a85714aad3af
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82781374"
---
Dört rolün yetenekleri şunlardır: yöneticiler, üyeler, katkıda bulunanlar ve görüntüleyiciler. Görüntüleme ve etkileşim dışında bu özelliklerin tamamı için bir Power BI Pro lisansı gerekir.

|Özellik   | Yönetici  | Üye  | Katılımcı  | Görüntüleyici |
|---|---|---|---|---|
| Çalışma alanını güncelleştirebilir ve silebilir.  | X  |   |   |   | 
| Diğer yöneticiler de dahil olmak üzere kişileri ekleyebilir/kaldırabilir.  | X  |   |   |   |
| Üyeleri ve düşük izinlere sahip diğer kişileri ekleyebilir.  |  X | X  |   |   |
| Uygulama yayımlayabilir ve güncelleştirebilir. |  X | X  |   |   |
| Öğe veya uygulama paylaşabilir.<sup>1</sup> |  X | X  |   |   |
| Diğer kişilerin öğeleri yeniden paylaşmasına izin verebilir.<sup>1</sup> |  X | X  |   |   |
| İş arkadaşlarının Giriş Sayfasında uygulamaları öne çıkarabilir |  X | X  |   |   |
| İş arkadaşlarının Giriş Sayfasında panoları ve raporları öne çıkarabilir |  X | X  | X |   |
| Çalışma alanında içerik oluşturabilir, düzenleyebilir ve silebilir.  |  X | X  | X  |   |
| Çalışma alanında rapor yayımlayabilir, içeriği silebilir.  |  X | X  | X  |   |
| Başka bir çalışma alanında, bu çalışma alanındaki bir veri kümesini temel alan rapor oluşturun.<sup>1</sup> |  X | X  | X  |   |
| Bir raporu kopyalayın.<sup>2</sup> | X | X | X |  |
| Şirket içi ağ geçidi yoluyla veri yenilemeleri zamanlayabilir.<sup>3</sup> | X | X | X |  |
| Ağ geçidi bağlantı ayarlarını değiştirebilir.<sup>3</sup> | X | X | X |  |
| Öğeyi açabilir ve öğelerle etkileşim kurabilir.<sup>4</sup> |  X | X  | X  | X  |
| Çalışma alanı veri akışlarında depolanan verileri okuma | X | X | X | X |

1. Katkıda Bulunanlar ve Görüntüleyiciler, bir çalışma alanındaki öğeleri ancak yeniden paylaşma izinleri varsa paylaşabilir.
2. Raporu kopyalamak ve bu çalışma alanındaki veri kümesini temel alarak başka bir çalışma alanında rapor oluşturmak için veri kümesine yönelik Oluşturma iznine sahip olmanız gerekir. Bu çalışma alanındaki veri kümeleri için Yönetici, Üye ve Katkıda Bulunan rollerine sahip kişilerin çalışma alanı rolleri aracılığıyla Oluşturma izinleri olur.
3. Ağ geçidi üzerinde de izinlerinizin olması gerektiğini unutmayın. Söz konusu izinler başka bir yerde, çalışma alanı rolleri ve izinlerinden bağımsız olarak yönetilir. Ayrıntılar için bkz. [Şirket içi ağ geçidini yönetme](https://docs.microsoft.com/data-integration/gateway/service-gateway-manage).
4. Power BI Pro lisansınız olmasa bile, öğeler Premium kapasitedeki bir çalışma alanında yer alıyorsa Power BI hizmetinde öğeleri görüntüleyebilir ve bunlarla etkileşim kurabilirsiniz.

