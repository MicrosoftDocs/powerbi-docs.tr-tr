---
title: Veri kümesi paylaşma (Önizleme)
description: Veri kümesi sahibi olarak diğer kişilerin kullanabilmesi için veri kümelerinizi oluşturup paylaşabilirsiniz. Oluşturma iznini kullanarak verilere kimin erişimi olduğunu denetlemeyi öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/14/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c5b880132255fbdf37996273dc6c70029e548df6
ms.sourcegitcommit: 4a3afe761d2f4a5bd897fafb36b53961739e8466
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69654910"
---
# <a name="share-a-dataset-preview"></a>Veri kümesi paylaşma (Önizleme)

Power BI Desktop’ta *veri modeli* oluşturucusu olarak bunları Power BI hizmetinde *veri kümeleri* olarak paylaşabilirsiniz. Ardından, rapor oluşturucuları paylaştığınız veri kümelerini kolayca keşfedip yeniden kullanabilir. Oluşturma iznini kullanarak bunları paylaşmayı ve verilere kimin erişimi olduğunu denetlemeyi öğrenin.

## <a name="steps-to-sharing-your-dataset"></a>Veri kümenizi paylaşmaya yönelik adımlar

1. Power BI Desktop’taki bir veri modelinde .pbix dosyası oluşturarak başlayın. Bu veri kümesini diğerlerinin rapor oluşturması için sunmayı planlıyorsanız .pbix dosyasında rapor tasarlamasanız da olur.

    .pbix dosyasını bir Office 365 grubuna kaydetmek en iyi yöntemlerden biridir.

1. .pbix dosyasını Power BI hizmetindeki bir [yeni deneyim çalışma alanında](service-create-the-new-workspaces.md) yayımlayın.
    
    Bu çalışma alanının diğer üyeleri, zaten bu veri kümesini temel alarak diğer çalışma alanlarında rapor oluşturabiliyor.

1. Ayrıca, bu çalışma alanından [bir uygulama yayımlayabilirsiniz](service-create-distribute-apps.md). Bunu yaptığınızda, kimlerin izinleri olduğunu ve neler yapabileceklerini **İzinler** sayfasından siz belirlersiniz.

    > [!NOTE]
    > **Tüm kuruluş** seçeneğini belirlerseniz kuruluştaki kimsenin Oluşturma izni olmaz. Bu sorun zaten biliniyor. Bunun yerine, **Belirli bireyler ve gruplardaki** e-posta adreslerini belirtin.  Kuruluşunuzdaki herkesin Oluşturma izni olmasını istiyorsanız, tüm kuruluş için bir e-posta diğer adı belirtin.

    ![Uygulama izinlerini ayarlama](media/service-datasets-build-permissions/power-bi-dataset-app-permissions.png)

1. **Uygulamayı yayımla**seçeneğini belirleyin. Uygulama zaten yayımlandıysa, **Uygulamayı güncelleştir**’i seçin.

## <a name="build-permissions-for-shared-datasets"></a>Paylaşılan veri kümeleri için oluşturma izinleri

Oluşturma izni türü sadece veri kümeleri için geçerlidir. Kullanıcılar bununla bir veri kümesi üzerinde, raporlar, panolar, Soru-Cevap bölmesinden sabitlenmiş kutucuklar ve Insights Discovery gibi içerikler derleyebilir. Excel’de Çözümleme, XMLA ve temel verileri dışarı aktarma aracılığıyla Excel sayfaları gibi Power BI dışındaki bir veri kümesinde de yeni içerik oluşturabilirler.

Kullanıcılar farklı şekillerde Oluşturma izni alır:

- En az bir Katkıda Bulunan rolüne sahip bir çalışma alanının üyesiyseniz, bir veri kümesi için otomatik olarak Derleme iznine ve bir raporu kopyalama iznine sahip olursunuz.
 
- Veri kümesinin bulunduğu çalışma alanının bir üyesi, izin merkezindeki belirli kullanıcılara veya güvenlik gruplarına izni atayabilir. Veri kümesinin yanındaki üç nokta (...) simgesini seçin > **İzinleri Yönet** seçeneğini belirleyin.

    ![Üç nokta simgesini seçin](media/service-datasets-build-permissions/power-bi-dataset-manage-permissions.png)

    Bu, izinleri ayarlayabildiğiniz ve değiştirebildiğiniz İzin merkezini o veri kümesi için açar.

    ![İzin merkezi](media/service-datasets-build-permissions/power-bi-dataset-permissions.png)

- Veri kümesinin bulunduğu iş alanının yöneticisi veya üyesi, uygulama için izni olan kullanıcıların temel alınan veri kümeleri için de izni olup olmayacağına uygulamanın yayımlanması esnasında karar verebilir. Ayrıntılı bilgi için bu makaledeki [Veri kümenizi paylaşmaya yönelik adımlar](#steps-to-sharing-your-dataset) bölümüne bakın.

- Bir veri kümesinde Yeniden Paylaşma ve Oluşturma izinlerinizin olduğunu varsayalım. Bu veri kümesinin üzerinde derlenmiş bir raporu veya panoyu paylaştığınızda, alıcıların temel olarak alınan veri kümesi için de Oluşturma izni aldıklarını belirtebilirsiniz.

    ![Oluşturma izinleri](media/service-datasets-build-permissions/power-bi-share-report-allow-users.png)

Kişinin bir veri kümesine ilişkin Derleme izinlerini kaldırabilirsiniz. Bunu yaparsanız, paylaşılan veri kümesinde derlenen raporu görebilirler ancak bunu artık düzenleyemezler.

## <a name="more-granular-permissions"></a>Daha ayrıntılı izinler

Power BI, mevcut izinler olan Okuma ve Yeniden paylaşma izinlerini tamamlayan Oluşturma iznini Haziran 2019’da sundu. O zamanda uygulama izinleri, paylaşım veya çalışma alanı erişimi aracılığıyla veri kümeleri için Okuma iznine sahip olan tüm kullanıcılar aynı veri kümeleri için Oluşturma iznine de sahip oldu. Okuma izni, Excel’de Çözümleme veya Dışarı aktarma kullanarak veri kümesinde yeni içerik oluşturma hakkını onlara zaten tanıdığı için Oluşturma iznine otomatik olarak sahip oldular.

Daha ayrıntılı bu Oluşturma izni ile mevcut rapor veya panodaki içeriği kimlerin görüntüleyebileceğini ve temel alınan veri kümelerine bağlı olan içerikleri kimlerin oluşturabileceğini seçebilirsiniz.

Veri kümeniz veri kümesi çalışma alanının dışındaki bir rapor tarafından kullanılıyorsa o veri kümesini silemezsiniz. Bunun yerine bir hata iletisi görürsünüz.

Oluşturma izinlerini kaldırabilirsiniz. Bunu yaparsanız, izinlerini iptal ettiğiniz kişiler raporu görmeye devam eder ancak raporu artık düzenleyemez veya temel verileri dışarı aktaramaz. Yalnızca okuma izni olan kullanıcılar özetlenmiş verileri yine dışarı aktarabilir. 

## <a name="track-your-dataset-usage"></a>Veri kümesi kullanımınızı izleme

Çalışma alanınızda bir paylaşılan veri kümesi bulunduğunda, diğer çalışma alanlarındaki hangi raporların bunu temel aldığını bilmeniz gerekebilir.

1. Veri kümeleri liste görünümünde **İlgili olanları görüntüle** seçeneğini belirleyin.

    ![İlişkilileri görüntüle simgesini](media/service-datasets-build-permissions/power-bi-dataset-view-related-to-dataset.png)

1. **İlgili içerik** iletişim kutusu tüm ilgili öğeleri gösterir. Bu çalışma alanı ve **Diğer çalışma alanlarındaki** ilgili öğeleri bu listede görürsünüz.
 
    ![İlgili içerik iletişim kutusu](media/service-datasets-build-permissions/power-bi-dataset-related-workspaces.png)

## <a name="next-steps"></a>Sonraki adımlar

- [Çalışma alanları genelinde veri kümeleri kullanma (Önizleme)](service-datasets-across-workspaces.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
