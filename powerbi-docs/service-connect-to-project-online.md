---
title: Power BI ile Project Online'a bağlanma
description: Power BI için Project Online
author: SarinaJoan
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 07/25/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 941981e1f84cf3d7a74a156e4f1c88f57e061ad2
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73854650"
---
# <a name="connect-to-project-web-app-with-power-bi"></a>Power BI ile Project Web App’e bağlanma
Microsoft Project Web App, proje portföy yönetimi (PPM) ve günlük çalışmalara yönelik esnek bir çevrimiçi çözümdür. Project Web App, kuruluşların çalışmaya başlayarak proje portföy yatırımlarını önceliklendirmesine ve planlanan iş değerini sunmasına olanak sağlar. Power BI için Project Web App Şablon Uygulaması, projelerin, portföylerin ve kaynakların yönetimine yardımcı olmak için Project Web App’te içgörü ortaya çıkarmanıza olanak sağlar.

Power BI için [Project Web App Şablon Uygulaması](https://appsource.microsoft.com/product/power-bi/pbi_msprojectonline.pbi-microsoftprojectwebapp)’na bağlanın.

## <a name="how-to-connect"></a>Bağlanma

1. Gezinti bölmesinde **Uygulamalar**'ı seçin ve ardından sağ üst köşedeki **Uygulama edinin** seçeneğini belirleyin.

    ![Uygulamaları edinin](media/service-connect-to-project-online/GetApps.png)

2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![AppSource](media/service-connect-to-project-online/AppSource.png)
3. AppSource’ta **Uygulamalar** sekmesini belirleyip **Microsoft Project Web App**’i arayın/seçin.
   
4. Şöyle bir ileti alırsınız: **Bu Power BI uygulaması yüklensin mi?** Ardından, **Yükle** seçeneğini belirleyin. 

   ![Project Web yükleme](media/service-connect-to-project-online/ProjectTile.png)
5. **Uygulamalar** bölmesinde **Microsoft Project Web App** kutucuğunu seçin. 
   
   ![Microsoft Project Web App](media/service-connect-to-project-online/getstarted.png)
6. **Yeni uygulamanızı kullanmaya başlayın** alanında **Verileri bağla** seçeneğini belirleyin.
   
   ![Verilere bağlanma](media/service-connect-to-project-online/mproject.png)
7. **Project Web App URL’si** metin kutusuna bağlanmak istediğiniz Project Web App’in (PWA) URL’sini girin.  Özel bir etki alanına sahipseniz bu URL'nin örnektekinden farklı olabileceğini göz önünde bulundurun. **PWA Site Dili** metin kutusuna, PWA site dilinize karşılık gelen numarayı yazın. İngilizce için tek basamaklı '1', Fransızca için '2', Almanca için '3', Portekizce (Brezilya) için '4', Portekizce (Portekiz) için '5' ve İspanyolca için '6' yazın. 
   
   ![Microsoft Project Online’a bağlanma](media/service-connect-to-project-online/params.png)
8. Kimlik Doğrulama Yöntemi için **OAuth2** \> **Oturum aç** seçeneğini belirleyin. İstendiğinde Project Web App kimlik bilgilerinizi girin ve kimlik doğrulama işlemindeki diğer adımları uygulayın.

    > [!NOTE]
    > Bağlandığınız Project Web App için Portföy Görüntüleyicisi, Portföy Yöneticisi veya Yönetici izinlerine sahip olmanız gerekir.

9. Verilerinizin yüklendiğini belirten bir bildirim görürsünüz. Bu işlem, hesabınızın boyutuna bağlı olarak biraz zaman alabilir. Power BI verileri içeri aktardıktan sonra yeni çalışma alanınızın içeriklerini görürsünüz. En son güncelleştirmeleri almak için veri kümesini yenilemeniz gerekebilir. 

    Veriler Power BI tarafından içeri aktarıldıktan sonra gezinti bölmesinde 13 sayfalık raporu ve veri kümesini görürsünüz. 

10. Raporlarınız hazır olduktan sonra, devam edin ve Project Web App verilerinizi incelemeye başlayın! Şablon Uygulaması’nda Portföye Genel Bakış (6 rapor sayfası), Kaynağa Genel Bakış (5 rapor sayfası) ve Proje Durumu (2 rapor sayfası) için 13 zengin ve ayrıntılı rapor yer alır. 

    ![Portföy Panosu](media/service-connect-to-project-online/report1.png)
   
    ![Kullanılabilirlik](media/service-connect-to-project-online/report3.png)
   
    ![Proje Durumu](media/service-connect-to-project-online/report2.png)

**Sırada ne var?**

* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

**Şablon Uygulaması’nı genişletme**

İçerik Paketi'ni daha da fazla özelleştirmek ve güncelleştirmek için [GitHub PBIT dosyasını](https://github.com/OfficeDev/Project-Power-BI-Content-Packs) indirin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

