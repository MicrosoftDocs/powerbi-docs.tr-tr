---
title: Power BI ile Project Online'a bağlanma
description: Power BI için Project Online
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 60ca8d828d3bb33dced97213e2f135db364c35e5
ms.sourcegitcommit: ba447d7cc94418d7d3cf6fdcb686ec1a859258a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37145150"
---
# <a name="connect-to-project-online-with-power-bi"></a>Power BI ile Project Online'a bağlanma
Microsoft Project Online, proje portföy yönetimi (PPM) ve günlük çalışmalara yönelik esnek bir çevrimiçi çözümdür. Project Online, kuruluşların çalışmaya başlayarak proje portföy yatırımlarını önceliklendirmesine ve planlanan iş değerini sunmasına olanak sağlar. Power BI için Project Online içerik paketi projelerin, portföylerin ve kaynakların yönetimine yardımcı olmak için Project Online'da içgörüyü ortaya çıkarmanıza olanak sağlar.

Power BI için [Project Online içerik paketine](https://app.powerbi.com/getdata/services/project-online) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
    ![](media/service-connect-to-project-online/getdata.png)
2. **Hizmetler** kutusundaki **Al** düğmesini seçin.
   
   ![](media/service-connect-to-project-online/services.png)
3. **Microsoft Project Online** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-project-online/mproject.png)
4. **Project Web App URL'si** metin kutusuna, bağlanmak istediğiniz Project Web App (PWA) URL'sini girin ve **Sonraki** seçeneğini belirleyin. Özel bir etki alanına sahipseniz bu URL'nin örnektekinden farklı olabileceğini göz önünde bulundurun. **PWA Site Dili** metin kutusuna, PWA site dilinize karşılık gelen numarayı yazın. İngilizce için tek basamaklı '1', Fransızca için '2', Almanca için '3', Portekizce (Brezilya) için '4', Portekizce (Portekiz) için '5' ve İspanyolca için '6' yazın. 
   
    ![](media/service-connect-to-project-online/params.png)
5. Kimlik Doğrulama Yöntemi için **OAuth2** \> **Oturum aç** seçeneğini belirleyin. İstendiğinde Project Online kimlik bilgilerinizi girin ve kimlik doğrulama işlemindeki diğer adımları uygulayın.
   
    ![](media/service-connect-to-project-online/creds.png)
    
Bağlandığınız Project Web App için Portföy Görüntüleyicisi, Portföy Yöneticisi veya Yönetici izinlerine sahip olmanız gerektiğini unutmayın.

6. Verilerinizin yüklendiğini belirten bir bildirim görürsünüz. Bu işlem, hesabınızın boyutuna bağlı olarak biraz zaman alabilir. Veriler Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde yeni bir pano, 13 rapor ve veri kümesi görürsünüz. Bu, Power BI'ın verilerinizi görüntülemek için oluşturduğu varsayılan panodur. Bu panoyu, verilerinizi istediğiniz herhangi bir biçimde görüntüleyecek şekilde değiştirebilirsiniz.

   ![](media/service-connect-to-project-online/dashboard2.png)

7. Panonuz ve raporlarınız hazır olduktan sonra, devam edin ve Project Online verilerinizi incelemeye başlayın! İçerik Paketi'nde Portföye Genel Bakış (6 rapor sayfası), Kaynağa Genel Bakış (5 rapor sayfası) ve Proje Durumu (2 rapor sayfası) için 13 zengin ve ayrıntılı rapor yer alır. 

   ![](media/service-connect-to-project-online/report1.png)
   
   ![](media/service-connect-to-project-online/report3.png)
   
   ![](media/service-connect-to-project-online/report2.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

**İçerik Paketi'ni genişletme**

İçerik Paketi'ni daha da fazla özelleştirmek ve güncelleştirmek için [GitHub PBIT dosyasını](https://github.com/OfficeDev/Project-Power-BI-Content-Packs) indirin

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

