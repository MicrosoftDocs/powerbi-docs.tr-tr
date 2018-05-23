---
title: Power BI Desktop'ta koşullu tablo biçimlendirme
description: Tablolara özel biçimlendirme uygulama
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 9599b40940c9d9cca254bb2ed2e87c161cce371f
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="conditional-formatting-in-tables"></a>Tablolarda koşullu biçimlendirme
Tablolar için koşullu biçimlendirme sayesinde hücre değerlerine göre (veya başka değerlere ya da alanlara göre) özel hücre arka plan renkleri belirtebilir ve gradyan renklerini kullanabilirsiniz. Koşullu biçimlendirme seçeneklerine erişmek için Power BI Desktop'ın **Görsel Öğeler** bölmesinin **Alanlar** kutusundaki **Değerler** kutusunda yer alan değerlerden biçimlendirmek istediğinizin yanındaki aşağı oku seçin (veya alana sağ tıklayın). Koşullu biçimlendirmeyi yalnızca **Alanlar** kutusunun **Değerler** alanındaki alanlar için yönetebilirsiniz.

![koşullu tablo biçimlendirmesi](media/desktop-conditional-table-formatting/table-formatting_1.png)

Açılan iletişim kutusunda rengin yanı sıra *Minimum* ve *Maksimum* değerleri yapılandırabilirsiniz. **Ayrılan** kutusunu seçerseniz isteğe bağlı bir *Orta* değeri de yapılandırabilirsiniz.

![ayrılan renkler](media/desktop-conditional-table-formatting/table-formatting_2.png)

Renk gradyanı için, veri modelinizdeki bir alanı da temel alabilirsiniz. Ayrıca, seçilen alan için toplama türünü belirtebilirsiniz (seçilen alan, **Rengi şuna uygula:** alanında belirtilir; böylece takip edebilirsiniz).

![renkler için bir alanı temel alma](media/desktop-conditional-table-formatting/table-formatting_2b.png)

Yukarıdaki adımlarla uygulanan özelleştirilmiş biçimlendirme bir tabloya uygulandığında, koşullu biçimlendirilmiş hücrelere uygulanmış olan özel tablo stillerini geçersiz kılar.

![tablo biçimlendirmesi](media/desktop-conditional-table-formatting/table-formatting_3.png)

Biçimlendirme temeli olarak sayısal bir değer seçtiğiniz sürece, metin ve tarih alanlarına koşullu biçimlendirme de uygulayabilirsiniz. 

Bir görselleştirmedeki koşullu biçimlendirmeyi kaldırmak için alana tekrar sağ tıklayın ve **Koşullu Biçimlendirmeyi Kaldır**'ı seçin.

![tablo biçimlendirmesini kaldırma](media/desktop-conditional-table-formatting/table-formatting_4.png)

