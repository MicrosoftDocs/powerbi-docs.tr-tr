---
title: Farklı çalışma alanlarını temel alarak raporlar oluşturma (Önizleme) - Power BI
description: Bir veri kümesini kuruluşunuzdaki kullanıcılarla nasıl paylaşabileceğinizi öğrenin. Veri kümenizi temel alarak kendi çalışma alanlarında rapor oluşturabilirler.
author: maggiesMSFT
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/03/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: af8cab7403a0ee34505ff395248aec188fd54666
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83284739"
---
# <a name="create-reports-based-on-datasets-from-different-workspaces-preview"></a>Farklı çalışma alanlarını temel alarak raporlar oluşturma (Önizleme)

Diğer çalışma alanlarındaki veri kümelerini temel alarak kendi çalışma alanınızda nasıl rapor oluşturabileceğinizi öğrenin. Mevcut bir veri kümesinin üzerinde rapor oluşturmak için Çalışma Alanım bölümünüzdeki veya [yeni bir çalışma alanı deneyimindeki](../collaborate-share/service-create-the-new-workspaces.md) Power BI Desktop veya Power BI hizmetinden başlayabilirsiniz.

- Power BI hizmetinde: **Veri alma** > **Paylaşılan veri kümeleri**.
- Power BI Desktop’ta: **Veri alma** > **Power BI veri kümeleri**.

    ![Mevcut bir veri kümesine bağlanma](media/service-datasets-across-workspaces/power-bi-connect-dataset-pk.png)
   
Her iki durumda da, veri kümesi keşfetme deneyimi **Rapor oluşturmak için bir veri kümesi seçin** iletişim kutusunda başlar. Nerede olurlarsa olsunlar, erişiminiz olan tüm veri kümelerini görürsünüz:

![Bir veri kümesi seçme](media/service-datasets-across-workspaces/power-bi-select-dataset.png)

İlkinde **Öne çıkarılan** etiketi olduğunu görüyorsunuz. Bu makalenin ilerleyen bölümlerinde ([desteklenen bir veri kümesi bulma](#find-an-endorsed-dataset) bölümünde) bunu ele alacağız.

Bu listede gördüğünüz veri kümeleri şu koşullardan en az birini karşılar:

- Veri kümesi yeni çalışma alanı deneyimi çalışma alanlarının birinde bulunuyor ve siz de bu çalışma alanının bir üyesisiniz. Bkz. [Önemli noktalar ve sınırlamalar](service-datasets-across-workspaces.md#considerations-and-limitations).
- Bir yeni çalışma alanı deneyimi çalışma alanında bulunan veri kümesi için Oluşturma izniniz var.
- Veri kümeniz Çalışma Alanım bölümünüzde bulunur.

> [!NOTE]
> Ücretsiz kullanıcıysanız, sadece My Workspace bölümünüzde bulunan veri kümelerini veya Premium kapasiteli çalışma alanlarında bulunan ve Oluşturma izniniz olan veri kümelerini görürsünüz.

**Oluştur**’a tıkladığınızda veri kümesiyle canlı bir bağlantı oluşturursunuz ve rapor oluşturma deneyimi kullanılabilir olan tam veri kümesi ile açılır. Veri kümesinin bir kopyasını oluşturmadınız. Bu veri kümesi hala özgün konumunda bulunuyor. Kendi raporlarınızı oluşturmak için veri kümesindeki tüm tabloları ve ölçümleri kullanabilirsiniz. Veri kümenizde satır düzeyi güvenlik (RLS) kısıtlamaları uygulandığı için, sadece RLS rolünüzün görme izni bulunan izinleri görürsünüz.

Raporu, Power BI hizmetindeki mevcut çalışma alanına kaydedebilir veya Power BI Desktop’tan bir çalışma alanında yayımlayabilirsiniz. Rapor çalışma alanının dışındaki bir veri kümesini temel alıyorsa, Power BI veri kümeleri listesinde otomatik olarak bir giriş oluşturur. Bu veri kümesinin simgesi, çalışma alanındaki veri kümelerinin simgesinden farklıdır: ![Paylaşılan veri kümesi simgesi](media/service-datasets-discover-across-workspaces/power-bi-shared-dataset-icon.png)

Böylece, çalışma alanının üyeleri hangi raporların ve panoların çalışma alanının dışındaki veri kümelerini kullandığını ayırt edebilir. Giriş veri kümesiyle ilgili bilgileri ve birkaç seçme eylemini gösterir.

![Veri kümesi eylemleri](media/service-datasets-across-workspaces/power-bi-dataset-actions.png)

## <a name="find-an-endorsed-dataset"></a>Desteklenen bir veri kümesi bulma

İki farklı türde desteklenen veri kümesi bulunur. Veri kümesi sahipleri size önerdikleri bir veri kümesini *yükseltebilir*. Ayrıca Power BI kiracı yöneticisi, kuruluşunuzda herkesin kullanabilmesi için veri kümelerini *onaylayan* uzmanlar belirleyebilir. Yükseltilen ve onaylanan veri kümelerinde, bir veri kümesini ararken veya bir çalışma alanındaki veri kümelerinin listesinde gördüğünüz *rozetler* görüntülenir. Veri kümesi bulma deneyimi sırasında veri kümesini onaylayan kişinin adı bir araç ipucunda görüntülenir; **Onaylandı** etiketinin üzerine gelirseniz bunu görürsünüz.

- Power BI hizmetinde: **Veri alma** > **Paylaşılan veri kümeleri**.
- Power BI Desktop’ta: **Veri alma** > **Power BI veri kümeleri**.

    **Bir veri kümesi seçin** iletişim kutusunda, desteklenen veri kümeleri varsayılan olarak en üstte görünür. 

    ![Yükseltilen veri kümesi](media/service-datasets-certify-promote/power-bi-dataset-promoted.png)

## <a name="next-steps"></a>Sonraki adımlar

- [Çalışma alanları genelinde veri kümeleri kullanma (Önizleme)](service-datasets-across-workspaces.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
