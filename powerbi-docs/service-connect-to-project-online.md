---
title: Power BI ile Project Online'a bağlanma
description: Power BI için Project Online
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: a6ada87813593fd0f06d7870fa1727bc35fe7d47
ms.sourcegitcommit: fe8a25a79f7c6fe794d1a30224741e5281e82357
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68324904"
---
# <a name="connect-to-project-web-app-with-power-bi"></a>Power BI ile Project Web App’e bağlanma
Microsoft Project Web App, proje portföy yönetimi (PPM) ve günlük çalışmalara yönelik esnek bir çevrimiçi çözümdür. Project Web App, kuruluşların çalışmaya başlayarak proje portföy yatırımlarını önceliklendirmesine ve planlanan iş değerini sunmasına olanak sağlar. Power BI için Project Web App Şablon Uygulaması, projelerin, portföylerin ve kaynakların yönetimine yardımcı olmak için Project Web App’te içgörü ortaya çıkarmanıza olanak sağlar.

Power BI için [Project Web App Şablon Uygulaması](https://appsource.microsoft.com/product/power-bi/pbi_msprojectonline.pbi-microsoftprojectwebapp)’na bağlanın.

## <a name="how-to-connect"></a>Bağlanma

   ![](media/service-connect-to-project-online/GetApps.png)
1. Sol gezinti bölmesinde **Uygulamalar**'ı seçin ve ardından sağ üst köşedeki **Uygulama edinin** seçeneğini belirleyin.
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-project-online/AppSource.png)
3. AppSource’ta **Uygulamalar** sekmesini belirleyip **Microsoft Project Web App**’i arayın/seçin.
   
4. Şöyle bir ileti alırsınız: **Bu Power BI uygulaması yüklensin mi?** Ardından, **Yükle** seçeneğini belirleyin. 

   ![](media/service-connect-to-project-online/ProjectTile.png)
5. **Uygulamalar** bölmesinde **Microsoft Project Web App** kutucuğunu seçin. 
   
   ![](media/service-connect-to-project-online/getstarted.png)
6. **Yeni uygulamanızı kullanmaya başlayın** alanında **Verileri bağla** seçeneğini belirleyin.
   
   ![](media/service-connect-to-project-online/mproject.png)
7. **Project Web App URL’si** metin kutusuna bağlanmak istediğiniz Project Web App’in (PWA) URL’sini girin.  Özel bir etki alanına sahipseniz bu URL'nin örnektekinden farklı olabileceğini göz önünde bulundurun. **PWA Site Dili** metin kutusuna, PWA site dilinize karşılık gelen numarayı yazın. İngilizce için tek basamaklı '1', Fransızca için '2', Almanca için '3', Portekizce (Brezilya) için '4', Portekizce (Portekiz) için '5' ve İspanyolca için '6' yazın. 
   
   ![](media/service-connect-to-project-online/params.png)
8. Kimlik Doğrulama Yöntemi için **OAuth2** \> **Oturum aç** seçeneğini belirleyin. İstendiğinde Project Web App kimlik bilgilerinizi girin ve kimlik doğrulama işlemindeki diğer adımları uygulayın.

    
Bağlandığınız Project Web App için Portföy Görüntüleyicisi, Portföy Yöneticisi veya Yönetici izinlerine sahip olmanız gerektiğini unutmayın.

9. Verilerinizin yüklendiğini belirten bir bildirim görürsünüz. Bu işlem, hesabınızın boyutuna bağlı olarak biraz zaman alabilir. Power BI verileri içeri aktardıktan sonra yeni çalışma alanınızın içeriklerini görürsünüz. En son güncelleştirmeleri almak için veri kümesini yenilemeniz gerekebilir. 

Veriler Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde 13 sayfalık raporu ve veri kümesini görürsünüz. 

10. Raporlarınız hazır olduktan sonra, devam edin ve Project Web App verilerinizi incelemeye başlayın! Şablon Uygulaması’nda Portföye Genel Bakış (6 rapor sayfası), Kaynağa Genel Bakış (5 rapor sayfası) ve Proje Durumu (2 rapor sayfası) için 13 zengin ve ayrıntılı rapor yer alır. 

   ![](media/service-connect-to-project-online/report1.png)
   
   ![](media/service-connect-to-project-online/report3.png)
   
   ![](media/service-connect-to-project-online/report2.png)

**Sırada ne var?**

* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

**Şablon Uygulaması’nı genişletme**

İçerik Paketi'ni daha da fazla özelleştirmek ve güncelleştirmek için [GitHub PBIT dosyasını](https://github.com/OfficeDev/Project-Power-BI-Content-Packs) indirin

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

