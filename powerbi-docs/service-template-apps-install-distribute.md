---
title: Kuruluşunuzda şablon uygulamalarını dağıtma - Power BI (önizleme)
description: Power BI’da şablon uygulamalarını kuruluşunuzda yükleme, özelleştirme ve dağıtma hakkında bilgi edinin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/19/2019
ms.author: maggies
ms.openlocfilehash: 2b7b2630e665fca9013920718ff58dd973f01392
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578558"
---
# <a name="install-and-distribute-template-apps-in-your-organization---power-bi-preview"></a>Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma - Power BI (önizleme)

Power BI analist misiniz? Varsa, bu nedenle, bu makalede nasıl yükleneceği açıklanmaktadır *şablon uygulamaları* birçok iş, Salesforce, Microsoft Dynamics ve Google Analytics gibi çalıştırmak için kullandığınız hizmetlere bağlanmak için. Pano ve raporları kuruluşunuzun ihtiyaçlarını karşılayacak şekilde değiştirin ve ardından iş arkadaşlarınıza önerilmesini sağlayın dağıtabilir bir *uygulama*. 

![Power BI uygulaması yüklendi](media/service-template-apps-install-distribute/power-bi-get-apps.png)

Kendiniz dağıtmak üzere şablon uygulamaları oluşturmak ilginizi çekiyorsa, bkz. [Power BI’da şablon uygulaması oluşturma](service-template-apps-create.md). Power BI iş ortakları, çok az kayıpla veya hiç kodlama ile Power BI uygulamaları oluşturun ve bunları Power BI müşterilere dağıtın. 

## <a name="prerequisites"></a>Önkoşullar  

Şablon uygulamalarını yüklemek, özelleştirmek ve dağıtmak için şunlar gerekir: 

- [Power BI Pro lisansı](service-self-service-signup-for-power-bi.md)
- [Temel Power BI kavramlarını](service-basic-concepts.md) tanıma
- Şablon uygulaması oluşturucusundan veya AppSource’tan geçerli bir yükleme bağlantısı. 
- Şablon uygulamalarını yükleme izinleri. 

## <a name="install-a-template-app"></a>Şablon uygulamasını yükleme

Şablon uygulamasının bağlantısını alabilirsiniz. Almadıysanız, ilginizi çeken uygulamayı bulmak için AppSource’ta arama yapabilirsiniz. Her iki durumda da, uygulamayı yükledikten sonra değiştirebilir ve kendi kuruluşunuzda dağıtabilirsiniz.

### <a name="search-appsource-from-a-browser"></a>Tarayıcıdan AppSource araması yapma

Tarayıcıda, Power BI uygulamalarını gösterecek şekilde filtrelenmiş AppSource’u açmak için bu bağlantıyı seçin:

- https://appsource.microsoft.com/marketplace/apps?product=power-bi

### <a name="search-appsource-from-the-power-bi-service"></a>Power BI hizmetinde AppSource’u arama

1. Power BI hizmetinin sol gezinti bölmesinde **Uygulamalar** > **Uygulama edinin**’i seçin.

    ![Uygulamaları edinin](media/service-template-apps-install-distribute/power-bi-get-apps-arrow.png)

2. AppSource’ta **Uygulamalar**’ı seçin.

    ![AppSource'ta arama](media/service-template-apps-install-distribute/power-bi-appsource.png)

3. Uygulamaya göz atın veya uygulama için arama yapın, ardından **Şimdi edinin**’i seçin.

2. İletişim kutusunda **Yükle**'yi seçin.

    Power BI Pro lisansınız varsa, uygulama kendisiyle ilişkilendirilmiş uygulama çalışma alanına yüklenir. Uygulamayı, ilişkilendirilmiş çalışma alanında özelleştirirsiniz.

    Yükleme başarılı olduğunda yeni uygulamanızın hazır olduğuna ilişkin bir bildirim görürsünüz. 

3. **Uygulamaya git**’i seçin.
4. **Yeni uygulamanızı kullanmaya başlayın** alanında üç seçenekten birini belirtin:

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-template-apps-create/power-bi-template-app-get-started.png)

    - **Uygulamayı keşfet**: Örnek verilerle temel keşif. Uygulamanın genel görünümünü elde etmek için buradan başlayın. 
    - **Verilere bağlan**: Veri kaynağını örnek verilerden kendi veri kaynağınıza geçirin. Veri kümesi parametrelerini ve veri kaynağı kimlik bilgilerini yeniden tanımlayabilirsiniz. Şablon uygulaması ipuçları makalesinde [Bilinen sınırlamalar](service-template-apps-tips.md#known-limitations) bölümüne bakın. 
    - **Çalışma alanına git** (en gelişmiş seçenek): uygulama oluşturucusunun izin verdiği tüm değişiklikleri yapabilirsiniz.

    İsterseniz bu iletişim kutusunu atlayın ve sol gezinti bölmesindeki **Çalışma Alanları** yoluyla doğrudan ilişkili çalışma alanına erişin.   
 
5. İş arkadaşlarınızla paylaşmadan önce, kendi verilerinize bağlanmak istersiniz. Ayrıca kuruluşunuza uygun olması için raporu veya panoyu değiştirmek de isteyebilirsiniz. Bu noktada başka raporlar ve panolar eklemeniz de mümkündür.

## <a name="update-and-distribute-the-app"></a>Uygulamayı güncelleştirme ve dağıtma

Uygulamayı kuruluşunuz için güncelleştirdikten sonra, yayımlamaya hazır olursunuz. Adımlar, diğer herhangi bir uygulamayı yayımlamakla aynıdır. 

1. Özelleştirmeyi tamamladığınızda, çalışma alanı liste görünümünde sağ üst köşedeki **Uygulamayı güncelleştir**’i seçin.  

    ![Uygulama yüklemesini başlatma](media/service-template-apps-install-distribute/power-bi-start-install-app.png)

2. **Ayrıntılar** bölümünde, açıklamayı ve arka plan rengini değiştirebilirsiniz.

   ![Uygulama açıklamasını ve rengini ayarlama](media/service-template-apps-install-distribute/power-bi-install-app-details.png)

3. **İçerik** bölümünde, giriş sayfasını (pano veya rapor) seçebilirsiniz.

   ![Uygulama giriş sayfasını ayarlama](media/service-template-apps-install-distribute/power-bi-install-app-content.png)

4. **Erişim** bölümünde, seçilen kullanıcılara veya kuruluşun tamamına izin verirsiniz.  

   ![Uygulama erişimini ayarlama](media/service-template-apps-install-distribute/power-bi-install-access.png)

5. **Uygulamayı güncelleştir**’i seçin. 

6. Uygulama başarıyla yayımlandıktan sonra bağlantıyı kopyalayabilir ve erişim verdiğiniz herkesle paylaşabilirsiniz. Bağlantıyı paylaşırsanız, bunu AppSource’taki **Kuruluşum** sekmesinde de görürler.

## <a name="next-steps"></a>Sonraki adımlar 

[Power BI'da çalışma arkadaşlarınızla çalışma alanları oluşturma](service-create-workspaces.md)





￼ 

 
