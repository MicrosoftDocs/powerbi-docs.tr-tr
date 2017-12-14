---
title: "Power BI ile MailChimp'e bağlanma"
description: "Power BI için MailChimp"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 2781dc7088824cb00f5dcd174fbfc3677c0f13a6
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-mailchimp-with-power-bi"></a>Power BI ile MailChimp'e bağlanma
Power BI içerik paketi MailChimp hesabınızdan veri çeker ve bir pano, raporlar kümesi ve veri kümesi oluşturarak verilerinizi araştırmanıza olanak sağlar. Analiz verileri çekerek [MailChimp panoları](https://powerbi.microsoft.com/integrations/mailchimp) oluşturun ve kampanyalarınızda, raporlarınızda ve bireysel abonelerinizde görülen eğilimleri hızla tanımlayın. Veriler, güncel bir izleme deneyimi elde etmenizi sağlamak üzere günlük olarak yenilenir.

Power BI için [MailChimp içerik paketine](https://app.powerbi.com/getdata/services/mailchimp) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki **Veri Al**'ı seçin.
   
    ![](media/service-connect-to-mailchimp/pbi_getdata.png)
2. **Hizmetler** kutusundaki **Al**'ı seçin.
   
   ![](media/service-connect-to-mailchimp/pbi_getservices.png)
3. **MailChimp** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-mailchimp/mailchimp.png)
4. Kimlik doğrulama yöntemi için **OAuth2** \> **Oturum aç** seçeneklerini belirleyin.
   
    İstendiğinde, MailChimp kimlik bilgilerinizi girin ve kimlik doğrulaması işlemini gerçekleştirin.
   
    İlk kez bağlandığınızda Power BI'ın hesabınıza salt okunur şekilde erişimine izin vermeniz istenir. İçeri aktarma işlemine başlamak için **İzin Ver**'i seçin, bu işlem hesabınızdaki verilerin hacmine bağlı olarak birkaç dakika sürebilir.
   
    ![](media/service-connect-to-mailchimp/allow.png)
5. Power BI verileri içeri aktardıktan sonra sol gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Bu, Power BI'ın verilerinizi görüntülemek için oluşturduğu varsayılan panodur. Bu panoyu, verilerinizi istediğiniz herhangi bir biçimde görüntüleyecek şekilde değiştirebilirsiniz.
   
   ![](media/service-connect-to-mailchimp/pbi_mailchimpnewdash.png)

**Sırada ne var?**

* Panonun üst kısmındaki [Soru-Cevap kutusunda soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenmeye zamanlanacak olsa da yenileme zamanlamasını değiştirebilir veya **Şimdi Yenile** ile istediğiniz zaman yenileme yapabilirsiniz

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

