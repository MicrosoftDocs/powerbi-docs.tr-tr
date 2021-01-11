---
title: Power BI hizmetinde sayfalandırılmış raporlara abone olma
description: Bu makalede Power BI hizmetinde sayfalandırılmış raporlara abone olma hakkında aklınızda tutmanız gereken noktaları öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: pbi-explore
ms.topic: how-to
ms.date: 01/04/2021
ms.openlocfilehash: 67efe0e7abd23792f46561f78b0b048b431561a4
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888018"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Kendinizi ve başkalarını Power BI hizmetinde sayfalandırılmış raporlara abone yapma 

Artık Power BI hizmetinde sayfalandırılmış raporlar için kendinize ve başkalarına e-posta abonelikleri ayarlayabilirsiniz. Bu işlem genel olarak [Power BI hizmetinde raporlara ve panolara abone olmakla](end-user-subscribe.md) aynıdır. Bu makalede farklılıklar ve dikkat edilecek noktalar ortaya konur. 

Abonelikleri ayarlarken ne sıklıkta e-posta almak istediğinizi seçersiniz: günlük, haftalık, aylık veya saatlik. Aboneliğin çalışmasını istediğiniz saatleri de seçebilirsiniz. Raporlar için ayarlayabileceğiniz aboneliklerin sayısında bir sınırlama yoktur. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Sayfalandırılmış rapor abonelikleriyle ilgili önemli noktalar 

- Pano ve Power BI raporu aboneliklerinden farklı olarak, aboneliğiniz tüm rapor çıkışının ekini içerir.  Aşağıdaki ek türleri desteklenir: PDF, PowerPoint sunusu (PPTX), Excel Çalışma Kitabı (XLSX), Word Belgesi (DOCX), CSV dosyası ve XML.

- E-posta gövdesine raporun önizleme görüntüsünü ekleyebilirsiniz.  Bu isteğe bağlıdır ve seçtiğiniz ek biçimine bağlı olarak ekli rapor belgenizin ilk sayfasından biraz farklı olabilir. 

- Rapor eki boyutu üst sınırı 24 MB'tır. 

- Azure Analysis Services veya Power BI veri kümeleri gibi şu anda desteklenen veri kaynaklarına bağlanan sayfalandırılmış raporlara başka kullanıcıları da abone yapabilirsiniz. SQL Server Reporting Services'in bugün yaptığı gibi, rapor ekinin sizin izinleriniz temelinde verileri yansıttığını unutmayın. 

- E-posta abonelikleri, raporunuz için şu anda seçili olan veya varsayılan parametrelerle gönderilebilir.  Raporunuz için oluşturduğunuz her abonelik için farklı parametre değerleri ayarlayabilirsiniz. 

- Rapor yazarınız ifade tabanlı parametreler ayarladıysa (örneğin, varsayılan ayar her zaman bugünün tarihiyse), abonelik varsayılan değer olarak bunu kullanır. Diğer parametre değerlerini değiştirebilir ve mevcut değerleri kullanmayı seçebilirsiniz. Ancak, o değeri de açıkça değiştirmediğiniz sürece, abonelik ifade tabanlı parametreyi kullanır.

- Sayfalandırılmış raporlarda sıklık için **Veri Yenilemesinden Sonra** seçeneği yoktur. Temel veri kümesinden her zaman en son değerleri alırsınız. 

## <a name="next-steps"></a>Sonraki adımlar

[Kendinizi ve başkalarını Power BI hizmetinde raporlara ve panolara abone yapma](../collaborate-share/service-report-subscribe.md)

[Power BI hizmetinde sayfalandırılmış raporlar](end-user-paginated-report.md)
