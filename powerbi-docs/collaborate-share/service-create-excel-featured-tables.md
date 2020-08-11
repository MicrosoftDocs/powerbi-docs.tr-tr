---
title: Power BI Desktop’ta öne çıkan tabloları ayarlama (önizleme)
description: Öne çıkan tabloların Excel’de Veri Türü Galerisinde gösterilmesi için bunları Power BI Desktop'da oluşturun.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 07/30/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c74c618eb4c748d94260573c1ddd4266d3cf5c0e
ms.sourcegitcommit: d9d67ee47954379c2df8db8d0dc8302de4c9f1e5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2020
ms.locfileid: "87478096"
---
# <a name="set-featured-tables-in-power-bi-desktop-preview"></a>Power BI Desktop’ta öne çıkan tabloları ayarlama (önizleme)

Excel’de Veri Türleri Galerisinde kullanıcılarınız sizin Power BI veri kümelerinizden gelen *öne çıkan tablo* verilerini bulabilir. Bu makalede, veri kümelerinizde tabloları *öne çıkan* olarak ayarlamayı öğreneceksiniz. Bu etiketler kullanıcılarınızın Excel sayfalarına kurumsal verileri eklemesini kolaylaştırır. Öne çıkan tabloları ayarlamaya ve paylaşmaya yönelik temel adımlar burada verilmiştir.

1. Power BI Desktop’taki veri kümelerinizde öne çıkan tabloları belirlersiniz (bu makale)
1. Öne çıkan tabloları içeren bu veri kümelerini yeni çalışma alanlarından birine kaydedersiniz. Rapor oluşturucuları bu öne çıkan tablolarla rapor oluşturabilir. 
1. Kuruluşun geri kalanı ilgili ve yenilenebilir veriler için Excel'de *veri türleri* olarak başvurulan bu öne çıkan tablolara bağlanabilir. [Excel’de Power BI öne çıkan tablolarına erişme (önizleme)](service-excel-featured-tables.md) makalesinde, bu öne çıkan tabloların Excel’de nasıl kullanılacağı açıklanır.

> [!NOTE]
> [Power BI’da veri kümelerini yükseltebilir veya onaylayabilirsiniz](../connect-data/service-datasets-promote.md). Buna *destekleme* adı verilir. Excel, Veri Türleri Galerisindeki desteklenen veri kümelerinde tabloları önceliklendirir. Excel, önce sertifikalı veri kümelerindeki öne çıkan tabloları, ardından yükseltilen veri kümelerindeki tabloları listeler. Excel daha sonra desteklenmeyen veri kümelerindeki öne çıkan tabloları listeler. 

## <a name="turn-on-the-featured-table-preview"></a>Öne çıkan tablo önizlemesini açma

1. Power BI Desktop'ta **Dosya** > **Seçenekler ve Ayarlar** > **Seçenekler** > **Önizleme Özellikleri**'ni seçin.
2. **Öne çıkan tablolar** onay kutusunu seçin.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-preview-featured-tables.png" alt-text="Öne çıkan tablolar önizleme seçeneği":::

3. Power BI Desktop'ı yeniden başlatın.

## <a name="select-a-table"></a>Tablo seçme

1. Power BI Desktop'ta Model görünümüne gidin.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-model-view.png" alt-text="Model görünümü":::
 
2. Tablo seçin ve **Öne çıkan tablo** öğesini **Evet** olarak ayarlayın.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-featured-table-yes.png" alt-text="Öne çıkan tablo seçeneğini Evet olarak ayarlama":::

4. **Bu öne çıkan tabloyu ayarla** bölümünde gerekli alanları sağlayın:

    - **Açıklama**. 
        > [!TIP]
        > Power BI rapor oluşturucularının bunu belirlemesine yardımcı olmak için açıklamaya “Öne çıkan tablo” ile başlayın.
    - **Satır etiketi** alanının değeri Excel’de kullanılır ve böylece kullanıcılar satırı kolayca belirleyebilir. **Veri Seçicisi** bölmesinde ve **Bilgi** kartında bağlı hücre için hücre değeri olarak görüntülenir. 
    - **Anahtar sütunu** alanının değeri satır için benzersiz bir kimlik sağlar. Bu değer Excel’in bir hücreyi tablodaki belirli bir satıra bağlamasına olanak tanır.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-set-up-featured-table.png" alt-text="Öne çıkan tabloyu ayarlama":::

1. Veri kümesini Power BI hizmetine yayımladıktan veya içeri aktardıktan sonra öne çıkan tablo Excel Veri Türleri Galerisi’nde görüntülenir. Siz ve diğer rapor oluşturucuları da bu veri kümesine dayanan raporlar da oluşturabilirsiniz.

1. Excel’de: 
    - Excel veri türleri listesini önbelleğe aldığından, yeni yayımlanan önce çıkan tabloları görmek için Excel’i yeniden başlatmanız gerekir.
    - Bazı veri kümeleri önizlemede desteklenmez; söz konusu veri kümelerinde tanımlanan öne çıkan tablolar Excel’de görüntülenmez. Ayrıntılar için sonraki Önemli noktalar ve Sınırlamalar bölümüne bakın.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

İlk önizlemenin sınırlamaları şunlardır.

- Aşağıdaki özelliklerin kullanıldığı Power BI veri kümelerindeki öne çıkan tablolar Excel’de gösterilmez: 

    - Satır düzeyi güvenlik veri kümeleri.
    - Microsoft Information Protection’ın etkinleştirildiği veri kümeleri.
    - DirectQuery veri kümeleri.
    - Canlı bağlantısı olan veri kümeleri.

- Excel yalnızca öne çıkan tablonun sütunlarında ve hesaplanan sütunlarında bulunan verileri gösterir. İlk önizlemede aşağıdakiler sağlanmaz:

    - Öne çıkan tabloda tanımlanan ölçüler.
    - İlgili tablolarda tanımlanan ölçüler ve ilişkilerden hesaplanan örtük ölçüler.

- Excel yalnızca yeni Power BI çalışma alanlarında depolanan öne çıkan tabloları görüntüler. Klasik çalışma alanlarında veya Çalışma Alanım’da depolanan öne çıkan tablolar Excel’de veri türleri olarak gösterilmez. Power BI'da [klasik çalışma alanlarını yeni çalışma alanlarına yükseltebilirsiniz](service-upgrade-workspaces.md).
- Excel'le ilgili diğer konular için “Excel’de Power BI öne çıkan tablolarına erişme” makalesinin [Önemli noktalar ve sınırlamalar](service-excel-featured-tables.md#considerations-and-limitations) bölümüne bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Excel’de Power BI öne çıkan tablolarına erişme](service-excel-featured-tables.md)
- Excel belgelerinde [Power BI’dan Excel veri türlerini kullanma](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) hakkında bilgi edinebilirsiniz.
- Sorularınız mı var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
