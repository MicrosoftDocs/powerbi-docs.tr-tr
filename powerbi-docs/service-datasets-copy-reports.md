---
title: Diğer çalışma alanlarından raporları kopyalama (Önizleme) - Power BI
description: Bir veri kümesini kuruluşunuzdaki kullanıcılarla nasıl paylaşabileceğinizi öğrenin. Veri kümenizi temel alarak kendi çalışma alanlarında rapor oluşturabilirler.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/03/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 2db4c23b50071e387913ed79b4d01daeafb928a4
ms.sourcegitcommit: b439ded53bfbbb58be27ecedf93d618f5158df33
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/04/2019
ms.locfileid: "67567418"
---
# <a name="copy-reports-from-other-workspaces-preview"></a>Diğer çalışma alanlarından raporları kopyalama (Önizleme)

Çalışma alanında veya uygulamada hoşunuza giden bir rapor bulduğunuzda kopyasını alabilir ve bunu farklı bir çalışma alanına kaydedebilirsiniz. Ardından, o raporu değiştirebilir veya görselleri ve diğer öğeleri ekleyip silebilirsiniz. Veri modelini oluşturmaya kafa yormanız gerekmez. Bu zaten sizin için oluşturulur. Mevcut raporu değiştirmek, en baştan başlamaktan çok daha kolaydır. Öte yandan rapor kopyanızı yeni çalışma alanından bir uygulamaya yayımlayamazsınız. "Veri kümelerini çalışma alanları arasında kullanma" makalesinde diğer [dikkate alınacak noktalar ve sınırlamalar](service-datasets-across-workspaces.md#considerations-and-limitations) listesine bakın.

## <a name="save-a-copy-of-a-report"></a>Raporun bir kopyasını kaydetme

1. Bir uygulamada veya çalışma alanında Raporlar liste görünümüne gidin.

1. **Eylemler**’in altından **Bir kopyasını kaydet** seçeneğini belirleyin.

    ![Raporun bir kopyasını kaydetme](media/service-datasets-copy-reports/power-bi-dataset-save-report-copy.png)

    **Bir kopyasını kaydet** simgesi, rapor bir yeni deneyim çalışma alanında bulunuyorsa ve [Oluşturma izniniz](service-datasets-build-permissions.md#build-permissions-for-shared-datasets) varsa görünür. Çalışma alanına erişiminiz olsa bile veri kümesi için Oluşturma izninizin bulunması gerekir.

3. **Bu raporun bir kopyasını kaydet** seçeneğinde rapora bir ad verin ve hedef çalışma alanını belirleyin.

    ![Bir kopyasını kaydet iletişim kutusu](media/service-datasets-copy-reports/power-bi-dataset-save-report.png)

    Raporu, mevcut çalışma alanına veya Power BI hizmetindeki farklı bir çalışma alanına kaydedebilirsiniz. Sadece üyesi olduğunuz yeni deneyim çalışma alanları olan çalışma alanlarını görürsünüz.
  
4. **Kaydet**'i seçin.

    Raporun bir kopyasını kaydettiğinizde, veri kümesiyle canlı bir bağlantı oluşturursunuz ve rapor oluşturma deneyimini kullanılabilir olan tam veri kümesi ile açabilirsiniz. Veri kümesinin bir kopyasını oluşturmadınız. Bu veri kümesi hala özgün konumunda bulunuyor. Veri kümesinde bulunan tüm tabloları ve ölçümleri kendi raporunuzda kullanabilirsiniz. Veri kümenizde satır düzeyi güvenlik (RLS) kısıtlamaları uygulandığı için, sadece RLS rolünüzün görme izni bulunan izinleri görürsünüz.

    Rapor çalışma alanının dışındaki bir veri kümesini temel alıyorsa, Power BI veri kümeleri listesinde otomatik olarak bir giriş oluşturur. Bu veri kümesinin simgesi, çalışma alanındaki veri kümelerinin simgesinden farklıdır: ![Paylaşılan veri kümesi simgesi](media/service-datasets-discover-across-workspaces/power-bi-shared-dataset-icon.png)


    Böylece, çalışma alanının üyeleri hangi raporların ve panoların çalışma alanının dışındaki veri kümelerini kullandığını ayırt edebilir. Giriş veri kümesiyle ilgili bilgileri ve birkaç seçme eylemini gösterir.

    ![Veri kümesi eylemleri](media/service-datasets-across-workspaces/power-bi-dataset-actions.png)

## <a name="view-related-datasets"></a>İlgili veri kümelerini görüntüle

Çalışma alanınızda bir raporunuz bulunduğunda hangi veri kümesini temel aldığını bilmeniz gerekebilir.

1. Raporlar liste görünümünde **İlgili olanları görüntüle** seçeneğini belirleyin.

    ![İlişkilileri görüntüle simgesini](media/service-datasets-copy-reports/power-bi-dataset-view-related.png)

1. **İlgili içerik** iletişim kutusu tüm ilgili öğeleri gösterir. Veri kümesi bu listede diğerleri gibi görünür. Farklı bir çalışma alanında bulunduğunu ayırt edemezsiniz. Bu sorun biliniyor.
 
    ![İlgili içerik iletişim kutusu](media/service-datasets-copy-reports/power-bi-dataset-related.png)

## <a name="delete-a-report-and-its-shared-dataset"></a>Raporu ve raporun paylaşılan veri kümesini silme

Raporu ve raporla ilişkilendirilmiş paylaşılan veri kümesini artık çalışma alanında istemediğinize karar verebilirsiniz.

1. Raporu silin. Çalışma alanındaki rapor listesinde **Sil** simgesini seçin.

    ![Raporu sil simgesi](media/service-datasets-across-workspaces/power-bi-datasets-delete-report.png)

2. Veri kümesi listesinde paylaşılan veri kümeleri için **Sil** simgelerinin olmadığını görürsünüz. Sayfayı yenileyin veya başka bir sayfaya gidin geri dönün. Veri kümesi görüntüden kaldırılır. Aksi takdirde **İlişkilileri görüntüle**'ye bakın. Çalışma alanınızdaki başka bir tabloyla ilişkili olabilir.

    ![İlişkilileri görüntüle simgesi](media/service-datasets-across-workspaces/power-bi-dataset-view-related-icon.png)

    > [!NOTE]
    > Bu çalışma alanındaki paylaşılan veri kümesinin silinmesi, veri kümesini silmez. Yalnızca bu veri kümesine başvuruyu siler.


## <a name="next-steps"></a>Sonraki adımlar

- [Çalışma alanları genelinde veri kümeleri kullanma (Önizleme)](service-datasets-across-workspaces.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
