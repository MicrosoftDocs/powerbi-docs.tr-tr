---
title: Veri kümesi paylaşma (önizleme)
description: Veri kümesi sahibi olarak diğer kişilerin kullanabilmesi için veri kümelerinizi oluşturup paylaşabilirsiniz. Bunları nasıl paylaşacağınızı öğrenin.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 4114287099300c371a6b02961a968702acb98f92
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565472"
---
# <a name="share-a-dataset-preview"></a>Veri kümesi paylaşma (önizleme)

Power BI Desktop’ta *veri modeli* oluşturucusu olarak Power BI hizmetinde dağıtabileceğiniz *veri kümeleri* oluşturuyorsunuz. Böylece, diğer rapor oluşturucuları veri kümelerinizi kendi raporlarının temeli olarak kullanabilir. Bu makalede veri kümelerinizi paylaşmayı öğreneceksiniz. Paylaşılan veri kümelerinize erişim vermeyi ve bu erişimi kaldırmayı öğrenmek için [Oluşturma izni](service-datasets-build-permissions.md) bölümüne bakın.

## <a name="steps-to-sharing-your-dataset"></a>Veri kümenizi paylaşmaya yönelik adımlar

1. Power BI Desktop’taki bir veri modelinde .pbix dosyası oluşturarak başlayın. Bu veri kümesini diğerlerinin rapor oluşturması için sunmayı planlıyorsanız .pbix dosyasında rapor tasarlamasanız da olur.

    .pbix dosyasını bir Microsoft 365 grubuna kaydetmek en iyi yöntemlerden biridir.

1. .pbix dosyasını Power BI hizmetindeki bir [yeni deneyim çalışma alanında](../collaborate-share/service-create-the-new-workspaces.md) yayımlayın.
    
    Bu çalışma alanının diğer üyeleri, zaten bu veri kümesini temel alarak diğer çalışma alanlarında rapor oluşturabiliyor.

1. Ayrıca, bu çalışma alanından [bir uygulama yayımlayabilirsiniz](../collaborate-share/service-create-distribute-apps.md). Bunu yaptığınızda, kimlerin izinleri olduğunu ve neler yapabileceklerini **İzinler** sayfasından siz belirlersiniz.

    > [!NOTE]
    > **Tüm kuruluş** seçeneğini belirlerseniz kuruluştaki kimsenin Oluşturma izni olmaz. Bu sorun zaten biliniyor. Bunun yerine, **Belirli bireyler ve gruplardaki** e-posta adreslerini belirtin.  Kuruluşunuzdaki herkesin Oluşturma izni olmasını istiyorsanız, tüm kuruluş için bir e-posta diğer adı belirtin.

    ![Uygulama izinlerini ayarlama](media/service-datasets-build-permissions/power-bi-dataset-app-permission-new-look.png)

1. **Uygulamayı yayımla**seçeneğini belirleyin. Uygulama zaten yayımlandıysa, **Uygulamayı güncelleştir**’i seçin.

## <a name="track-your-dataset-usage"></a>Veri kümesi kullanımınızı izleme

Çalışma alanınızda bir paylaşılan veri kümesi bulunduğunda, diğer çalışma alanlarındaki hangi raporların bunu temel aldığını bilmeniz gerekebilir.

1. Veri kümeleri liste görünümünde **İlgili olanları görüntüle** seçeneğini belirleyin.

    ![İlişkilileri görüntüle simgesini](media/service-datasets-build-permissions/power-bi-dataset-view-related-to-dataset.png)

1. **İlgili içerik** iletişim kutusu tüm ilgili öğeleri gösterir. Bu çalışma alanı ve **Diğer çalışma alanlarındaki** ilgili öğeleri bu listede görürsünüz.
 
    ![İlgili içerik iletişim kutusu](media/service-datasets-build-permissions/power-bi-dataset-related-workspaces.png)

## <a name="next-steps"></a>Sonraki adımlar

- [Çalışma alanları genelinde veri kümeleri kullanma (Önizleme)](service-datasets-across-workspaces.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
