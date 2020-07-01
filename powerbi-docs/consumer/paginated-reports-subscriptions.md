---
title: Power BI hizmetinde sayfalandırılmış raporlara abone olma
description: Bu makalede Power BI hizmetinde sayfalandırılmış raporlara abone olma hakkında aklınızda tutmanız gereken noktaları öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: how-to
ms.date: 12/03/2019
ms.openlocfilehash: 22c36ff3ff14f67d84d2e3aa227dfe1a4c14b266
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85240300"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Kendinizi ve başkalarını Power BI hizmetinde sayfalandırılmış raporlara abone yapma 

Artık Power BI hizmetinde sayfalandırılmış raporlar için kendinize ve başkalarına e-posta abonelikleri ayarlayabilirsiniz. Bu işlem genel olarak [Power BI hizmetinde raporlara ve panolara abone olmakla](end-user-subscribe.md) aynıdır. Bu makalede farklılıklar ve dikkat edilecek noktalar ortaya konur. 

Abonelikleri ayarlarken ne sıklıkta e-posta almak istediğinizi seçersiniz: günlük, haftalık, aylık veya saatlik. Aboneliğin çalışmasını istediğiniz saatleri de seçebilirsiniz. Toplamda, her rapor için en fazla 24 farklı abonelik ayarlayabilirsiniz. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Sayfalandırılmış rapor abonelikleriyle ilgili önemli noktalar 

- Pano ve Power BI raporu aboneliklerinden farklı olarak, aboneliğiniz tüm rapor çıkışının ekini içerir.  Aşağıdaki ek türleri desteklenir: PDF, PowerPoint sunusu (PPTX), Excel Çalışma Kitabı (XLSX), Word Belgesi (DOCX), CSV dosyası ve XML.

- E-posta gövdesine raporun önizleme görüntüsünü ekleyebilirsiniz.  Bu isteğe bağlıdır ve seçtiğiniz ek biçimine bağlı olarak ekli rapor belgenizin ilk sayfasından biraz farklı olabilir. 

- Rapor eki boyutu üst sınırı 25 MB'tır. 

- Azure Analysis Services veya Power BI veri kümeleri gibi şu anda desteklenen veri kaynaklarına bağlanan sayfalandırılmış raporlara başka kullanıcıları da abone yapabilirsiniz. SQL Server Reporting Services'in bugün yaptığı gibi, rapor ekinin sizin izinleriniz temelinde verileri yansıttığını unutmayın. 

- E-posta abonelikleri, raporunuz için şu anda seçili olan veya varsayılan parametrelerle gönderilebilir.  Raporunuz için oluşturduğunuz her abonelik için farklı parametre değerleri ayarlayabilirsiniz. 

- Rapor yazarınız ifade tabanlı parametreler ayarladıysa (örneğin, varsayılan ayar her zaman bugünün tarihiyse), abonelik varsayılan değer olarak bunu kullanır. Diğer parametre değerlerini değiştirebilir ve mevcut değerleri kullanmayı seçebilirsiniz. Ancak, o değeri de açıkça değiştirmediğiniz sürece, abonelik ifade tabanlı parametreyi kullanır.

- Sayfalandırılmış raporlarda sıklık için **Veri Yenilemesinden Sonra** seçeneği yoktur. Temel veri kümesinden her zaman en son değerleri alırsınız. 

## <a name="next-steps"></a>Sonraki adımlar

[Kendinizi ve başkalarını Power BI hizmetinde raporlara ve panolara abone yapma](../collaborate-share/service-report-subscribe.md)

[Power BI hizmetinde sayfalandırılmış raporlar](end-user-paginated-report.md)
