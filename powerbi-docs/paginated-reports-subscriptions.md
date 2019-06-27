---
title: Power BI hizmetinde sayfalandırılmış raporlara abone olma
description: Bu makalede Power BI hizmetinde sayfalandırılmış raporlara abone olma hakkında aklınızda tutmanız gereken noktaları öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/24/2019
ms.openlocfilehash: 472606fcb3b823cdcb722c9d8d6421d0ec652d24
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/12/2019
ms.locfileid: "66839565"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Kendinizi ve başkalarını Power BI hizmetinde sayfalandırılmış raporlara abone yapma 

Artık Power BI hizmetinde sayfalandırılmış raporlar için kendinize ve başkalarına e-posta abonelikleri ayarlayabilirsiniz. Bu işlem genel olarak [Power BI hizmetinde raporlara ve panolara abone olmakla](service-report-subscribe.md) aynıdır. Bu makalede farklılıklar ve dikkat edilecek noktalar ortaya konur. 

Abonelikleri ayarlarken ne sıklıkta e-posta almak istediğinizi seçersiniz: günlük, haftalık veya saatlik. Günlük veya haftalığı seçerseniz, aboneliğin çalıştırılmasını istediğiniz saati seçebilirsiniz. Toplamda her rapor için günde en fazla 24 farklı abonelik ayarlayabilirsiniz. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Sayfalandırılmış rapor abonelikleriyle ilgili önemli noktalar 

- Pano ve Power BI raporu aboneliklerinden farklı olarak, aboneliğiniz tüm rapor çıkışının ekini içerir.  Aşağıdaki ek türleri desteklenir: PDF, PowerPoint sunusu (PPTX), Excel Çalışma Kitabı (XLSX), Word Belgesi (DOCX), CSV dosyası ve XML.

- E-posta gövdesinde raporu önizleme resmi yer almaz.  İsteğe bağlı bir öğe olarak raporun ilk sayfasının resmini eklemeyi planlıyoruz. 

- Rapor eki boyutu üst sınırı 25 MB'tır. 

- Azure Analysis Services veya Power BI veri kümeleri gibi şu anda desteklenen veri kaynaklarına bağlanan sayfalandırılmış raporlara başka kullanıcıları da abone yapabilirsiniz. SQL Server Reporting Services'in bugün yaptığı gibi, rapor ekinin sizin izinleriniz temelinde verileri yansıttığını unutmayın. 

- Rapor sayfası abonelikleri raporun adıyla ilişkilidir.  

- E-posta abonelikleri raporun varsayılan parametre değerleriyle gönderilir. 

- Sayfalandırılmış raporlarda sıklık için **Veri Yenilemesinden Sonra** seçeneği yoktur. Temel veri kümesinden her zaman en son değerleri alırsınız. 

## <a name="next-steps"></a>Sonraki adımlar

[Kendinizi ve başkalarını Power BI hizmetinde raporlara ve panolara abone yapma](service-report-subscribe.md)

[Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
