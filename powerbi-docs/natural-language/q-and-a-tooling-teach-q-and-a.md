---
title: Power BI Soru-Cevap'taki soru ve terimleri anlamak için Soru-Cevap Öğretimi
description: Verilerinizi araştırmak için Power BI Soru-Cevap kullanma
author: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/17/2019
ms.author: mohaali
LocalizationGroup: Ask questions of your datadefintion
ms.openlocfilehash: 695ad9143aa7074e079ae8606a9ad0eb6f6c964f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874919"
---
# <a name="teach-qa-to-understand-questions-and-terms-in-power-bi-qa"></a>Power BI Soru-Cevap'taki soru ve terimleri anlamak için Soru-Cevap Öğretimi

Soru-Cevap ayarının **Soru-Cevap Öğretimi** bölümünde, Soru-Cevap’ı tanımadığı doğal dil soru ve terimlerini anlaması için eğitebilirsiniz. Başlamak için, Soru-Cevap’ın tanımadığı bir veya daha fazla sözcüğü içeren bir soru gönderin. Soru-Cevap bu terimi tanımlamanızı ister. Sözcüğün temsil ettiği anlama karşılık gelen bir filtre veya alan adı girebilirsiniz. Bundan sonra Soru-Cevap özgün soruyu yeniden yorumlar. Sonuçlardan memnunsanız kaydedin.

> [!NOTE]
> Soru-Cevap Öğretimi işlevi yalnızca içeri aktarma modunu destekler. Ayrıca, henüz bir şirket içi veya Azure Analysis Services veri kaynağına bağlanmayı desteklememektedir. Bu sınırlama, Power BI’ın sonraki yayınlarında kaldırılacaktır.

## <a name="start-to-teach-qa"></a>Soru-Cevap öğretimine başlama

1. Power BI Desktop’ta **Modelleme** şeridindeki **Soru-Cevap Ayarı** > **Soru-Cevap Öğretimi**’ni seçin.

    ![Soru-Cevap Öğretimi eşanlamlısı kırmızı](media/qna-tooling-teach-synonym-red.png)

2. Soru-Cevap’ın tanımadığı terimle başlayan bir cümle yazın ve **Gönder**'i seçin.

3. Kırmızıyla altı çizili sözcüğü seçin. 

    Soru-Cevap, öneriler sunar ve terimin doğru tanımını sağlamanızı ister. 
    
3. **Soru-Cevap’ın anlamadığı terimleri tanımlayın** altında bir tanım belirtin.

    ![Soru-Cevap Öğretimi eşanlamlısı önizlemesi](media/qna-tooling-teach-fixpreview.png)

4. Güncelleştirilmiş görselin önizlemesini görmek için **Kaydet**'i seçin.

5. Sonraki soruyu girin veya kapatmak için **X** simgesini seçin.

Rapor tüketicileriniz, siz raporu hizmette geri yayımlayana kadar bu değişikliği görmez.

## <a name="define-nouns-and-adjectives"></a>İsimleri ve sıfatları tanımlama

Soru-Cevap’a iki tür terim öğretebilirsiniz:

- İsimler
- Sıfatlar

### <a name="define-a-noun-synonym"></a>İsim eşanlamlısı tanımlama

Verilerle çalışırken, genellikle alternatif adlarla başvurulabilen alan adlarıyla karşılaşabilirsiniz. 'Satış' buna örnek olabilir. 'Gelir' gibi satışı ifade eden birçok sözcük veya tümcecik olabilir. Bir sütunun adı 'Satış' ise ve rapor tüketicileri 'gelir' yazarsa Soru-Cevap, soruyu uygun şekilde yanıtlamak için doğru sütunu seçemeyebilir. Bu durumda, Soru-Cevap’a 'Satış' ve 'Gelir' sözcüklerinin aynı anlama geldiğini söylemeniz gerekir.

Soru-Cevap, tanınmayan bir sözcük isim olduğunda Microsoft Office’ten edindiği bilgiyi kullanarak otomatik olarak algılar. Soru-Cevap bir isim algılarsa sizi aşağıdaki şekilde uyarır:

- <your term>  **sözcüğünün anlamı** 

Bu kutuyu, verilerinizdeki terimle doldurun.

![Soru-Cevap Öğretimi eşanlamlısı sorma](media/qna-tooling-synonym-prompt.png)

Veri modelindeki bir alan dışında bir seçenek belirtirseniz istenmeyen sonuçlar alabilirsiniz.

### <a name="define-an-adjective-filter-condition"></a>Sıfat filtre koşulu tanımlama

Bazen, temel alınan verilerde koşul görevi gören terimleri tanımlamak isteyebilirsiniz. 'Başarılı Yayımcılar' buna örnek olabilir. 'Başarılı', yalnızca X ürün yayımlamış yayımcıları seçen bir koşul olabilir. Soru-Cevap, farklı bir soru göstererek sıfatları algılamaya çalışır:

- <field name> **şunu yapmış:**  

Kutuyu koşulla doldurursunuz.

![Soru-Cevap Öğretimi eşanlamlısı sorma](media/qna-tooling-adjectives.png)

Tanımlayabileceğiniz bazı örnek koşullar şunlardır:

- 'ABD' olan 'Ülke'
- 'ABD' olmayan 'Ülke'
- 'Ağırlık' > 2000
- 'Ağırlık' = 2000
- 'Ağırlık' < 2000

Araç içinde yalnızca tek bir koşul tanımlayabilirsiniz. Daha karmaşık koşullar tanımlamak için DAX kullanarak hesaplanmış bir sütun oluşturun ve ardından bu hesaplanan sütun için tek bir koşul oluşturmak üzere araç bölmesini kullanın. Ölçüler desteklenmez. Onun yerine hesaplanmış sütunları kullanın.

## <a name="manage-terms"></a>Terimleri yönetme

Tanımları sağladıktan sonra, yaptığınız tüm düzeltmeleri görmek ve düzenlemek veya silmek için geri gidebilirsiniz. 

1. **Soru-Cevap ayarı** adımında **Terimleri yönet** bölümüne gidin.

2. Artık istemediğiniz terimleri silin. Şu anda koşulları düzenleyemezsiniz. Bir terimi yeniden tanımlamak için terimi silin ve tanımlayın.

    ![Soru-Cevap ile terimleri yönetme](media/qna-manage-terms.png)

## <a name="next-steps"></a>Sonraki adımlar

Doğal dil altyapısını iyileştirmeye yönelik birkaç en iyi yöntem vardır. Daha fazla bilgi için aşağıdaki makaleyi inceleyin:

* [Soru-Cevap ile En İyi Yöntemler](q-and-a-best-practices.md)