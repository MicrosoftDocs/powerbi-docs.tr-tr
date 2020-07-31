---
title: Veri kümesini paylaşma
description: Veri kümesi sahibi olarak diğer kişilerin kullanabilmesi için veri kümelerinizi oluşturup paylaşabilirsiniz. Bunları nasıl paylaşacağınızı öğrenin.
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 04/30/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: fd31c3b97eef80b0e4457fe6e61c1a8bf101db7b
ms.sourcegitcommit: 65025ab7ae57e338bdbd94be795886e5affd45b4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87252671"
---
# <a name="share-a-dataset"></a>Veri kümesini paylaşma

Power BI Desktop’ta *veri modeli* oluşturucusu olarak Power BI hizmetinde dağıtabileceğiniz *veri kümeleri* oluşturuyorsunuz. Böylece, diğer rapor oluşturucuları veri kümelerinizi kendi raporlarının temeli olarak kullanabilir. Bu makalede veri kümelerinizi paylaşmayı öğreneceksiniz. Paylaşılan veri kümelerinize erişim vermeyi ve bu erişimi kaldırmayı öğrenmek için [Oluşturma izni](service-datasets-build-permissions.md) bölümüne bakın.

## <a name="steps-to-sharing-your-dataset"></a>Veri kümenizi paylaşmaya yönelik adımlar

1. Power BI Desktop’taki bir veri modelinde .pbix dosyası oluşturarak başlayın. Bu veri kümesini diğerlerinin rapor oluşturması için sunmayı planlıyorsanız .pbix dosyasında rapor tasarlamasanız da olur.

    .pbix dosyasını bir Microsoft 365 grubuna kaydetmek en iyi yöntemlerden biridir.

1. .pbix dosyasını Power BI hizmetindeki [yeni bir çalışma alanı deneyiminde](../collaborate-share/service-create-the-new-workspaces.md) yayımlayın.
    
    Bu çalışma alanının diğer üyeleri, zaten bu veri kümesini temel alarak diğer çalışma alanlarında rapor oluşturabiliyor. Veri kümesine erişmeleri amacıyla daha fazla kullanıcıya erişim vermek için çalışma alanındaki veri kümesinde İzinleri Yönet seçeneğini kullanın. 

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

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
Veri kümelerini paylaşma ile ilgili olarak dikkat edilmesi gerekenler:

* İzinleri yöneterek, rapor veya panoları paylaşarak ya da uygulama yayımlayarak bir veri kümesi paylaştığınızda, [satır düzeyi güvenlik (RLS)](../admin/service-admin-rls.md) tarafından erişimleri sınırlanmadığı sürece tüm veri kümesine erişim vermiş olursunuz. Rapor yazarları, raporları görüntüleyip bunlarla etkileşim kurarken sütunları gizleme, görsellerdeki eylemleri sınırlandırma ve diğerleri gibi kullanıcı deneyimini özelleştiren özellikleri kullanabilir. Bu özelleştirilmiş kullanıcı deneyimi, veri kullanıcılarının veri kümesinde erişebileceği öğeleri kısıtlamaz. Her bir kullanıcının kimlik bilgilerinin erişebilecekleri verileri belirlemesini sağlamak için veri kümesinde [satır düzeyi güvenlik (RLS)](../admin/service-admin-rls.md) kullanın.

## <a name="next-steps"></a>Sonraki adımlar

- [Veri kümelerini çalışma alanları arasında kullanma](service-datasets-across-workspaces.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
