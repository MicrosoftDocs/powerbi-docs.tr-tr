---
title: Power BI hizmetinde sayfalandırılmış raporlara abone olma
description: Bu makalede Power BI hizmetinde sayfalandırılmış raporlara abone olma hakkında aklınızda tutmanız gereken noktaları öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: pbi-explore
ms.topic: how-to
ms.date: 01/22/2021
ms.openlocfilehash: 88293bbfc39f75472422e6785099421efcd45802
ms.sourcegitcommit: e8c3f327ac0fc73c118874a24d2601733f8f9e45
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2021
ms.locfileid: "98718543"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Kendinizi ve başkalarını Power BI hizmetinde sayfalandırılmış raporlara abone yapma 

Artık Power BI hizmetinde sayfalandırılmış raporlar için kendinize ve başkalarına e-posta abonelikleri ayarlayabilirsiniz. Bu işlem genel olarak [Power BI hizmetinde raporlara ve panolara abone olmakla](end-user-subscribe.md) aynıdır. Bu makalede farklılıklar ve dikkat edilecek noktalar ortaya konur. 

Abonelikleri ayarlarken ne sıklıkta e-posta almak istediğinizi seçersiniz: günlük, haftalık, aylık veya saatlik. Aboneliğin çalışmasını istediğiniz saatleri de seçebilirsiniz. Raporlar için ayarlayabileceğiniz aboneliklerin sayısında bir sınırlama yoktur. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Sayfalandırılmış rapor abonelikleriyle ilgili önemli noktalar 

- Kendiniz için bir abonelik oluşturmak üzere sayfalandırılmış raporda düzenleme izinlerine sahip olmanız gerekmez, ancak başka birisi için bir tane oluşturmak için düzenleme izinlerine sahip olmanız gerekir. Çalışma alanında sayfalandırılmış raporun olduğu en az bir katkıda bulunan rolüne sahipseniz diğerleri için abonelikler oluşturabilirsiniz. [Çalışma alanlarındaki roller](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces)hakkında daha fazla bilgi edinin.

- Pano ve Power BI raporu aboneliklerinden farklı olarak, aboneliğiniz tüm rapor çıkışının ekini içerir.  Aşağıdaki ek türleri desteklenir: PDF, PowerPoint sunusu (PPTX), Excel Çalışma Kitabı (XLSX), Word Belgesi (DOCX), CSV dosyası ve XML.

- E-posta gövdesine raporun önizleme görüntüsünü ekleyebilirsiniz.  Bu isteğe bağlıdır ve seçtiğiniz ek biçimine bağlı olarak ekli rapor belgenizin ilk sayfasından biraz farklı olabilir. 

- Rapor eki boyutu üst sınırı 24 MB'tır. 

- Diğer kullanıcılara, Azure Analysis Services veya Power BI veri kümeleri dahil olmak üzere, şu anda desteklenen herhangi bir veri kaynağına bağlanan sayfalandırılmış raporlara abone olabilirsiniz. SQL Server Reporting Services'in bugün yaptığı gibi, rapor ekinin sizin izinleriniz temelinde verileri yansıttığını unutmayın. 

- E-posta abonelikleri, raporunuz için şu anda seçili olan veya varsayılan parametrelerle gönderilebilir.  Raporunuz için oluşturduğunuz her abonelik için farklı parametre değerleri ayarlayabilirsiniz. 

- Rapor yazarınız ifade tabanlı parametreler ayarladıysa (örneğin, varsayılan ayar her zaman bugünün tarihiyse), abonelik varsayılan değer olarak bunu kullanır. Diğer parametre değerlerini değiştirebilir ve mevcut değerleri kullanmayı seçebilirsiniz. Ancak, o değeri de açıkça değiştirmediğiniz sürece, abonelik ifade tabanlı parametreyi kullanır.

- Sayfalandırılmış raporlarda sıklık için **Veri Yenilemesinden Sonra** seçeneği yoktur. Temel veri kümesinden her zaman en son değerleri alırsınız. 

## <a name="next-steps"></a>Sonraki adımlar

[Kendinizi ve başkalarını Power BI hizmetinde raporlara ve panolara abone yapma](../collaborate-share/service-report-subscribe.md)

[Power BI hizmetinde sayfalandırılmış raporlar](end-user-paginated-report.md)
