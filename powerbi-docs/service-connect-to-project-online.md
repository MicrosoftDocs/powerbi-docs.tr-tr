---
title: "Power BI ile Project Online'a bağlanma"
description: "Power BI için Project Online"
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
ms.openlocfilehash: 778453840e5ab311f635fd20228186ac3f3fc39c
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-project-online-with-power-bi"></a>Power BI ile Project Online'a bağlanma
Microsoft Project Online, proje portföy yönetimi (PPM) ve günlük çalışmalara yönelik esnek bir çevrimiçi çözümdür. Project Online, kuruluşların çalışmaya başlayarak proje portföy yatırımlarını önceliklendirmesine ve planlanan iş değerini sunmasına olanak sağlar. Power BI için Project Online içerik paketi sayesinde portföy durumu ve proje uyumluluğu gibi kullanıma hazır ölçümlerle proje verilerinizi araştırırsınız.

Power BI için [Project Online içerik paketine](https://app.powerbi.com/getdata/services/project-online) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
    ![](media/service-connect-to-project-online/getdata.png)
2. **Hizmetler** kutusundaki **Al** düğmesini seçin.
   
   ![](media/service-connect-to-project-online/services.png)
3. **Microsoft Project Online** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-project-online/mproject.png)
4. **Project Web App URL'si** metin kutusuna, bağlanmak istediğiniz Project Web App (PWA) URL'sini girin ve **Sonraki** seçeneğini belirleyin. Özel bir etki alanına sahipseniz bu URL'nin örnektekinden farklı olabileceğini göz önünde bulundurun.
   
    ![](media/service-connect-to-project-online/params.png)
5. Kimlik Doğrulama Yöntemi için **OAuth2** \> **Oturum aç** seçeneğini belirleyin. İstendiğinde Project Online kimlik bilgilerinizi girin ve kimlik doğrulama işlemindeki diğer adımları uygulayın.
   
    ![](media/service-connect-to-project-online/creds.png)
6. Verilerinizin yüklendiğini belirten bir bildirim görürsünüz. Bu işlem, hesabınızın boyutuna bağlı olarak biraz zaman alabilir. Veriler Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Bu, Power BI'ın verilerinizi görüntülemek için oluşturduğu varsayılan panodur. Bu panoyu, verilerinizi istediğiniz herhangi bir biçimde görüntüleyecek şekilde değiştirebilirsiniz.
   
   ![](media/service-connect-to-project-online/dashboard2.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

