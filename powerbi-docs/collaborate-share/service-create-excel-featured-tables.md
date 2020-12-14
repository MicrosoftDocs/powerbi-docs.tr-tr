---
title: Power BI Desktop'ta öne çıkan tabloları ayarlama
description: Power BI Desktop'ta Excel Kuruluş Veri Türleri Galerisinde gösterilecek öne çıkan tablolar oluşturun.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
ms.date: 12/07/2020
LocalizationGroup: Share your work
ms.openlocfilehash: 8c03263e7cc3a8833c06523601fcc12ef14484e1
ms.sourcegitcommit: 30d0668434283c633bda9ae03bc2aca75401ab94
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96906900"
---
# <a name="set-featured-tables-in-power-bi-desktop-to-show-in-excel-organization-data-types-gallery"></a>Power BI Desktop'ta Excel Kuruluş Veri Türleri Galerisinde gösterilecek öne çıkan tablolar ayarlama

Excel’de Veri Türleri Galerisinde kullanıcılarınız sizin Power BI veri kümelerinizden gelen *öne çıkan tablo* verilerini bulabilir. Bu makalede, veri kümelerinizde tabloları *öne çıkan* olarak ayarlamayı öğreneceksiniz. Bu etiketler kullanıcılarınızın Excel sayfalarına kurumsal verileri eklemesini kolaylaştırır. Öne çıkan tabloları ayarlamaya ve paylaşmaya yönelik temel adımlar burada verilmiştir.

1. Power BI Desktop’taki veri kümelerinizde öne çıkan tabloları belirlersiniz (bu makale)
1. Öne çıkan tabloları içeren bu veri kümelerini yeni çalışma alanlarından birine kaydedersiniz. Rapor oluşturucuları bu öne çıkan tablolarla rapor oluşturabilir. 
1. Kuruluşun geri kalanı ilgili ve yenilenebilir veriler için Excel'de *veri türleri* olarak başvurulan bu öne çıkan tablolara bağlanabilir. [Excel’de Power BI öne çıkan tablolarına erişme](service-excel-featured-tables.md) makalesinde, bu öne çıkan tabloların Excel’de nasıl kullanılacağı açıklanır.

> [!NOTE]
> [Power BI’da veri kümelerini yükseltebilir veya onaylayabilirsiniz](../collaborate-share/service-endorse-content.md). Buna *destekleme* adı verilir. Excel, Veri Türleri Galerisindeki desteklenen veri kümelerinde tabloları önceliklendirir. Excel, önce sertifikalı veri kümelerindeki öne çıkan tabloları, ardından yükseltilen veri kümelerindeki tabloları listeler. Excel daha sonra desteklenmeyen veri kümelerindeki öne çıkan tabloları listeler. 

> [!NOTE]
> Power BI Desktop'ın Aralık 2020 sürümünden itibaren öne çıkan tablo oluşturma seçeneği varsayılan olarak kullanılabilir durumda olacaktır. Daha eski bir sürüm kullanıyorsanız Power BI Desktop uygulamasını yükseltin veya **Dosya** > **Seçenekler ve Ayarlar** > **Seçenekler** > **Önizleme Özellikleri** yolunu izleyerek **Öne çıkan tablolar** özelliğini etkinleştirin.

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
    - Bazı veri kümeleri desteklenmez. Bu veri kümelerinde tanımlanmış olan öne çıkan tablolar Excel'de görünmez. Ayrıntılar için sonraki Önemli noktalar ve Sınırlamalar bölümüne bakın.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Geçerli sınırlamalar şunlardır:

- Tümleştirme geçerli kanaldaki Excel ile kullanılabilir.
- Aşağıdaki özelliklerin kullanıldığı Power BI veri kümelerindeki öne çıkan tablolar Excel’de gösterilmez: 

    - DirectQuery veri kümeleri.
    - Canlı bağlantısı olan veri kümeleri.

- Excel yalnızca öne çıkan tablonun sütunlarında, hesaplanan sütunlarında ve tanımlanmış ölçülerde bulunan verileri gösterir. Aşağıdakiler sağlanmaz:
   
    - İlgili tablolarda tanımlanmış ölçüler.
    - İlişkilerden hesaplanan örtülü ölçüler.

- Excel yalnızca yeni Power BI çalışma alanlarında depolanan öne çıkan tabloları (*veri türlerini*) görüntüler. Klasik çalışma alanlarında depolanan öne çıkan tablolar Excel’de veri türleri olarak gösterilmez. Power BI'da [klasik çalışma alanlarını yeni çalışma alanlarına yükseltebilirsiniz](service-upgrade-workspaces.md).

Excel’deki Veri Türleri deneyimi arama işlevine benzer. Excel sayfası tarafından sağlanan bir hücre değerini alır ve Power BI öne çıkan tablolardaki eşleşen satırlar için arama yapar. Arama deneyiminin şöyle davranışları vardır:

- Satır eşleşmesi öne çıkan tablodaki metin sütunlarına dayanır. Power BI Soru-Cevap özelliğiyle aynı dizini kullanır. Bu dizin İngilizce dilinde yapılan aramalar için iyileştirilmiştir. Başka dillerde yapılan aramaların sonucunda doğru eşleşmeler bulunamayabilir. 
- Eşleşmede çoğu sayısal sütun dikkate alınmaz. Satır Etiketi veya Anahtar Sütunu sayısal ise eşleşme için dahil edilir.
- Eşleşme tek tek arama terimlerinin Tam ve Ön Ek eşleşmelerine dayanır. Hücrenin değeri boşluklara ve sekme gibi boşluk karakterlerine göre bölünür. Sonra da her sözcük bir arama terimi olarak kabul edilir. Satırın metin alanı değerleri, Tam ve Ön Ek eşleşmeleri için her arama terimiyle karşılaştırılır. Satırın metin alanı arama terimiyle başlıyorsa Ön Ek eşleşmesi döndürülür. Örneğin hücre “Bölgesel Harita” ifadesini içeriyorsa, “Bölgesel” ve “Harita” ayrı arama terimleridir. 

    - Metin sütunlarının değeri “Bölgesel” veya “Harita” ile tam olarak eşleşen satırlar döndürülür. 
    - Metin sütunlarının değeri “Bölgesel” veya “Harita” ile başlayan satırlar döndürülür. 
    - Burada önemli olan, “Bölgesel” veya “Harita” terimini içeren ama bu terimlerle başlamayan satırlar döndürülmez.

- Power BI her hücre için en çok 100 satır önerisi döndürür.
- Bazı simgeler desteklenmez.
- Öne çıkan tablonun ayarlanması veya güncelleştirilmesi XMLA uç noktasında desteklenmez
- Öne çıkan tabloları yayımlamak için veri modeli olan Excel dosyaları kullanılabilir. Verileri Power BI Desktop’a yükleyin ve ardından öne çıkan tabloyu yayımlayın.
- Öne çıkan tabloda Tablo Adı, Satır Etiketi veya Anahtar Sütunu’nun değiştirilmesi, tablodaki satırlara bağlı hücreleri olan Excel kullanıcılarını etkileyebilir. 
- Excel verilerin Power BI veri kümesinden ne zaman alındığını gösterir. Bu, Power BI’da verilerin yenilendiği zaman veya veri kümesindeki en son veri noktası olmayabilir. Örneğin veri kümesinin Power BI’da bir hafta önce yenilendiğini ama yenileme yapıldığında temel kaynak verilerin bir haftalık olduğunu düşünün. Gerçek veriler iki haftalık olacaktır ama Excel verilerin alınma zamanı olarak, verilerin Excel’e alındığı tarihi/saati gösterecektir.
- Excel'le ilgili diğer konular için “Excel’de Power BI öne çıkan tablolarına erişme” makalesinin [Önemli noktalar ve sınırlamalar](service-excel-featured-tables.md#considerations-and-limitations) bölümüne bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Excel’de Power BI öne çıkan tablolarına erişme](service-excel-featured-tables.md)
- Excel belgelerinde [Power BI’dan Excel veri türlerini kullanma](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) hakkında bilgi edinebilirsiniz.
- Sorularınız mı var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

