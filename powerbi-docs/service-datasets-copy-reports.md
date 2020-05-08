---
title: Diğer uygulamalardan veya çalışma alanlarından raporları kopyalama (Önizleme) - Power BI
description: Raporun kopyasını oluşturmayı ve bunu kendi çalışma alanınıza kaydetmeyi öğrenin.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/16/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 8716a304e5b117c027d75db149ebcc8d95efebfe
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "76268955"
---
# <a name="copy-reports-from-other-workspaces-preview"></a>Diğer çalışma alanlarından raporları kopyalama (Önizleme)

Çalışma alanında veya uygulamada hoşunuza giden bir rapor bulduğunuzda kopyasını alabilir ve bunu farklı bir çalışma alanına kaydedebilirsiniz. Ardından, raporun kopyasını değiştirebilir veya görselleri ve diğer öğeleri ekleyip silebilirsiniz. Veri modelini oluşturma hakkında endişelenmeniz gerekmez. Bu zaten sizin için oluşturulur. Mevcut raporu değiştirmek, en baştan başlamaktan çok daha kolaydır. Ancak, bazı durumlarda çalışma alanınızdan bir uygulama oluştururken rapor kopyanızı uygulamada yayımlayamazsınız. Ayrıntılar için ["Veri kümelerini çalışma alanları arasında kullanma" makalesinde diğer dikkate alınacak noktalar ve sınırlamalara](service-datasets-across-workspaces.md#considerations-and-limitations) bakın.

> [!NOTE]
> Bir kopya oluşturmak için, özgün rapor Premium kapasitesi içindeki bir çalışma alanında olsa bile bir Pro lisansı gereklidir.

## <a name="save-a-copy-of-a-report-in-a-workspace"></a>Çalışma alanında raporun bir kopyasını kaydetme

1. Çalışma alanında Raporlar liste görünümüne gidin.

    ![Raporlar liste görünümü](media/service-datasets-copy-reports/power-bi-report-list-view.png)

1. **Eylemler**’in altından **Bir kopyasını kaydet** seçeneğini belirleyin.

    ![Raporun bir kopyasını kaydetme](media/service-datasets-copy-reports/power-bi-dataset-save-report-copy.png)

    **Bir kopyasını kaydet** simgesi, rapor bir yeni deneyim çalışma alanında bulunuyorsa ve [Oluşturma izniniz](service-datasets-build-permissions.md) varsa görünür. Çalışma alanına erişiminiz olsa bile veri kümesi için Oluşturma izninizin bulunması gerekir.

3. **Bu raporun bir kopyasını kaydet** seçeneğinde rapora bir ad verin ve hedef çalışma alanını belirleyin.

    ![Bir kopyasını kaydet iletişim kutusu](media/service-datasets-copy-reports/power-bi-dataset-save-report.png)

    Raporu, mevcut çalışma alanına veya Power BI hizmetindeki farklı bir çalışma alanına kaydedebilirsiniz. Sadece üyesi olduğunuz yeni deneyim çalışma alanları olan çalışma alanlarını görürsünüz. 
  
4. **Kaydet**’i seçin.

    Rapor çalışma alanının dışındaki bir veri kümesini temel alıyorsa, Power BI otomatik olarak raporun bir kopyasını oluşturur ve veri kümeleri listesine bir girdi ekler. Bu veri kümesinin simgesi, çalışma alanındaki veri kümelerinin simgesinden farklıdır: ![Paylaşılan veri kümesi simgesi](media/service-datasets-discover-across-workspaces/power-bi-shared-dataset-icon.png)
    
    Böylece, çalışma alanının üyeleri hangi raporların ve panoların çalışma alanının dışındaki veri kümelerini kullandığını ayırt edebilir. Giriş veri kümesiyle ilgili bilgileri ve birkaç seçme eylemini gösterir.

    ![Veri kümesi eylemleri](media/service-datasets-across-workspaces/power-bi-dataset-actions.png)

    Rapor ve ilgili veri kümesi hakkında daha fazla bilgi için bu makalenin [Rapor kopyanız](#your-copy-of-the-report) bölümüne bakın.

## <a name="copy-a-report-in-an-app"></a>Uygulamaya rapor kopyalama

1. Uygulamada, kopyalamak istediğiniz raporu açın.
2. Menü çubuğunda **Diğer seçenekler** ( **...** ) > **Kopyasını kaydet**’i seçin.

    ![Raporun kopyasını kaydetme](media/service-datasets-copy-reports/power-bi-save-copy.png)

    **Kopyasını kaydet** seçeneği, rapor yeni çalışma alanı deneyiminde bulunuyorsa ve [Oluşturma izniniz](service-datasets-build-permissions.md) varsa görünür.

3. Raporunuza bir ad verin > **Kaydet**’i seçin.

    ![Rapor kopyanızı adlandırma](media/service-datasets-copy-reports/power-bi-save-report-from-app.png)

    Kopyanız otomatik olarak Çalışma Alanım’a kaydedilir.

4. Kopyanızı açmak için **Rapora git**’i seçin.

## <a name="your-copy-of-the-report"></a>Rapor kopyanız

Raporun bir kopyasını kaydettiğinizde, veri kümesiyle canlı bir bağlantı oluşturursunuz ve rapor oluşturma deneyimini kullanılabilir olan tam veri kümesi ile açabilirsiniz. 

![Rapor kopyanızı düzenleme](media/service-datasets-copy-reports/power-bi-edit-report-copy.png)

Veri kümesinin bir kopyasını oluşturmadınız. Bu veri kümesi hala özgün konumunda bulunuyor. Veri kümesinde bulunan tüm tabloları ve ölçümleri kendi raporunuzda kullanabilirsiniz. Veri kümenizde satır düzeyi güvenlik (RLS) kısıtlamaları uygulandığı için, sadece RLS rolünüzün görme izni bulunan izinleri görürsünüz.

## <a name="view-related-datasets"></a>İlgili veri kümelerini görüntüle

Bir çalışma alanında yer alan ve başka bir çalışma alanındaki veri kümesini temel alan bir raporunuz olduğunda, raporun temel aldığı veri kümesi hakkında daha fazla bilginiz olmalıdır.

1. Raporlar liste görünümünde **İlgili olanları görüntüle** seçeneğini belirleyin.

    ![İlişkilileri görüntüle simgesini](media/service-datasets-copy-reports/power-bi-dataset-view-related.png)

1. **İlgili içerik** iletişim kutusu tüm ilgili öğeleri gösterir. Veri kümesi bu listede diğerleri gibi görünür. Farklı bir çalışma alanında bulunduğunu ayırt edemezsiniz. Bu sorun biliniyor.
 
    ![İlgili içerik iletişim kutusu](media/service-datasets-copy-reports/power-bi-dataset-related.png)

## <a name="delete-a-report-and-its-shared-dataset"></a>Raporu ve raporun paylaşılan veri kümesini silme

Raporu ve raporla ilişkilendirilmiş paylaşılan veri kümesini artık çalışma alanında istemediğinize karar verebilirsiniz.

1. Raporu silin. Çalışma alanındaki rapor listesinde **Sil** simgesini seçin.

    ![Raporu sil simgesi](media/service-datasets-across-workspaces/power-bi-datasets-delete-report.png)

2. Veri kümesi listesinde paylaşılan veri kümeleri için **Sil** simgelerinin olmadığını görürsünüz. Sayfayı yenileyin veya başka bir sayfaya gidin geri dönün. Veri kümesi görüntüden kaldırılır. Aksi takdirde **İlişkilileri görüntüle**'ye bakın. Çalışma alanınızdaki başka bir tabloyla ilişkili olabilir.

    ![İlişkilileri görüntüle simgesini](media/service-datasets-across-workspaces/power-bi-dataset-view-related-icon.png)

    > [!NOTE]
    > Bu çalışma alanındaki paylaşılan veri kümesinin silinmesi, veri kümesini silmez. Yalnızca bu veri kümesine başvuruyu siler.


## <a name="next-steps"></a>Sonraki adımlar

- [Çalışma alanları genelinde veri kümeleri kullanma (Önizleme)](service-datasets-across-workspaces.md)
- Sorular? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
