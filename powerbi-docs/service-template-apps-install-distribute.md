---
title: Kuruluşunuzda şablon uygulamalarını dağıtma - Power BI (önizleme)
description: Power BI’da şablon uygulamalarını kuruluşunuzda yükleme, özelleştirme ve dağıtma hakkında bilgi edinin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/07/2019
ms.author: maggies
ms.openlocfilehash: cd3a1f94aa4c965327ea3e5bcb7271326aa3514d
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56250048"
---
# <a name="install-and-distribute-template-apps-in-your-organization---power-bi-preview"></a>Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma - Power BI (önizleme)

Yeni Power BI *şablon uygulamaları* Power BI iş ortaklarının çok az kodlamayla veya hiç kodlama kullanmadan Power BI uygulamaları oluşturmasını ve bunları Power BI müşterilerine dağıtmasını sağlar. Bu makale Power BI analistlerine yöneliktir. Power BI iş ortağının oluşturduğu bir şablon uygulamasını nasıl yükleyeceğinizi, özelleştireceğinizi ve dağıtacağınızı açıklar. Kendiniz dağıtmak üzere şablon uygulamaları oluşturmak ilginizi çekiyorsa, bkz. [Power BI’da şablon uygulaması oluşturma](service-template-apps-create.md).

![Power BI uygulaması yüklendi](media/service-template-apps-install-distribute/power-bi-get-apps.png)

Power BI iş ortağının oluşturduğu bir şablon uygulamasını yüklediğinizde, kuruluşunuzun gereksinimlerine uyacak şekilde uygulamayı değiştirebilir ve ardından bir uygulama olarak iş arkadaşlarınıza dağıtabilirsiniz.  

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





. 

 
