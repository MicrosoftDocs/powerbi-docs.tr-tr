---
title: Power BI hizmetinde sayfalandırılmış raporlara abone olma
description: Bu makalede, Power BI hizmetinde sayfalandırılmış raporlara abone olma hakkında aklınızda tutmanız gereken şey öğrenin.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/24/2019
ms.openlocfilehash: ccec6658808d94728f2a4f14de67c36da0f51def
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222191"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Kendinizi ve diğerlerini sayfalandırılmış raporları Power BI hizmetine abone olun 

Artık Power BI hizmetinde sayfalandırılmış raporlar için e-posta abonelikleri kendiniz ve başkaları için ayarlayabilirsiniz. Genel olarak, aynı işlemdir [raporları ve Power BI hizmetindeki panolara abone](service-report-subscribe.md). Bu makalede harfe dönüştüren farklılıklar ve dikkat edilmesi gerekenler. 

Abonelikleri ayarlamada size ne sıklıkta e-postaları almak istediğinizi seçin: günlük, haftalık veya saatlik. Günlük seçin ya da haftalık zaman seçebilirsiniz çalıştırmak için abonelik ister. Tüm, her rapor için günde en fazla 24 farklı Aboneliklerde ayarlayabilirsiniz. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Sayfalandırılmış rapor abonelikleri için dikkat edilmesi gerekenler 

- Panoları veya Power BI raporları için abonelikler farklı olarak, aboneliğiniz raporun tamamı çıktının bir ek içerir.  Aşağıdaki ek türleri desteklenir: PDF, PowerPoint Sunusu (PPTX), Excel çalışma kitabı (XLSX), Word belgesi (DOCX), CSV dosyası ve XML.

- Raporun e-posta gövdesindeki Önizleme resim yok.  İsteğe bağlı bir öğe olarak raporun ilk sayfası görüntüsü olması planlıyorsanız. 

- Rapor Maksimum ek boyutunu 25 MB'dir. 

- Diğer kullanıcılar, Azure Analysis Services veya Power BI veri kümeleri dahil olmak üzere tüm şu anda desteklenen veri kaynaklarına bağlanmak, sayfalandırılmış raporlar için abone olabilirsiniz. Yalnızca SQL Server Reporting Services'ı bugün olduğu gibi izinlerine göre verileri rapor eki gösteren göz önünde bulundurun. 

- Rapor sayfası abonelikleri rapor adına bağlıdır.  

- E-posta abonelikleri raporun varsayılan parametre değerleri ile gönderilir. 

- Var olan hiçbir **sonra veri yenileme** sayfalandırılmış raporlar sıklığı seçeneği. Her zaman en son değerleri temel alınan veri kaynağından alın. 

## <a name="next-steps"></a>Sonraki adımlar

[Kendinizi ve diğerlerini raporları ve Power BI hizmetindeki panolara abone olma](service-report-subscribe.md)

[Power BI Premium’da sayfalandırılmış raporlar nelerdir? (Önizleme)](paginated-reports-report-builder-power-bi.md)
