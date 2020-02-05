---
title: Power BI Desktop'ta koşullu tablo biçimlendirme
description: Tablolara özel biçimlendirme uygulama
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/26/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: c79a8ddd68fa64b0a16663500a3f02e9a991835b
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2020
ms.locfileid: "75730534"
---
# <a name="use-conditional-formatting-in-tables"></a>Tablolarda koşullu biçimlendirme kullanma 

Power BI Desktop'taki tablolar için koşullu biçimlendirme özellikleri sayesinde gradyan renklerini kullanma dahil olmak üzere alan değerlerine göre özel hücre renkleri belirtebilirsiniz. Ayrıca hücre değerlerini veri çubukları veya KPI simgeleri olarak ya da etkin web bağlantıları şeklinde gösterebilirsiniz. Biçimlendirme için sayısal, renk adı veya onaltılık kod ya da web URL değeri içeren bir alanı kullandığınız sürece koşullu biçimlendirmeyi istediğiniz metin veya veri alanına uygulayabilirsiniz. 

Koşullu biçimlendirme uygulamak için Power BI Desktop'ta bir **Tablo** veya **Matris** görselleştirmesi seçin. **Görselleştirmeler** bölmesinin **Alanlar** bölümünde sağ tıklayın veya biçimlendirmek istediğiniz alanın yanındaki **Değerler** kutusunda bulunan aşağı oku seçin. **Koşullu biçimlendirme**'yi ve ardından uygulamak istediğiniz biçimlendirme türünü seçin.

![Koşullu biçimlendirme menüsü](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

> [!NOTE]
> Koşullu biçimlendirme, koşullu olarak biçimlendirilen hücredeki özel arka plan veya yazı tipi rengini geçersiz kılar.

Bir görselleştirmedeki koşullu biçimlendirmeyi kaldırmak için alanın açılan menüsünden **Koşullu biçimlendirmeyi kaldır**'ı ve sonra kaldırılacak biçimlendirme türünü seçin.

![Koşullu biçimlendirmeyi kaldır menüsü](media/desktop-conditional-table-formatting/table-formatting-1-remove.png)

Aşağıdaki bölümlerde koşullu biçimlendirme seçeneklerinin her biri açıklanmaktadır. Tek bir tablo sütununda birden fazla seçeneği birlikte kullanabilirsiniz.

## <a name="format-background-or-font-color"></a>Arka plan veya yazı tipi rengi

Hücre arka plan veya yazı tipi rengini biçimlendirmek için, bir alanda **Koşullu biçimlendirme**'yi seçtikten sonra açılan menüden **Arka plan rengi** veya **Yazı tipi rengi** seçeneğini belirtin. 

![Arka plan rengi veya Yazı tipi rengi seçeneğini belirtin](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-dialog.png)

**Arka plan rengi** veya **Yazı tipi rengi** iletişim kutusu açılır ve başlık olarak biçimlendirdiğiniz alanın adı görünür. Koşullu biçimlendirme seçeneklerini belirledikten sonra **Tamam**'ı seçin. 

![Arka plan rengi ve Yazı tipi rengi iletişim kutuları](media/desktop-conditional-table-formatting/table-formatting-2-diverging.png)

**Arka plan rengi** ve **Yazı tipi rengi** seçenekleri aynıdır ancak birisi hücrenin arka plan rengini, diğeri de yazı tipi rengini etkiler. Bir alanın yazı tipi rengi ve arka plan rengi için aynı veya farklı koşullu biçimlendirme seçenekleri uygulayabilirsiniz. Alanın hem yazı tipi hem de arka planı için aynı rengi seçerseniz yazı tipi arka plana karışacağından tablo sütununda yalnızca renkler görünür.

## <a name="color-by-color-scale"></a>Renk ölçeğine göre renklendirme

Arka plan veya yazı tipi rengini renk ölçeğine göre biçimlendirmek için **Arka plan rengi** veya **Yazı tipi rengi** iletişim kutusunun **Şuna göre biçimlendir** iletişim kutusunda **Renk ölçeği**'ni seçin. **Şu alana göre** bölümünde biçimlendirmenin temel alacağı alanı seçin. Biçimlendirme için geçerli alanı veya modelinizdeki sayısal veriler veya renk verileri içeren herhangi bir alanı temel alabilirsiniz. 

**Özetleme**'nin altında seçili alan için kullanmak istediğiniz toplama türünü belirtin. **Varsayılan biçimlendirme**'nin altında boş değerlere uygulanacak biçimlendirmeyi seçin. 

**En Düşük** ve **En Yüksek** alanlarında renk şemasının en düşük ve en yüksek alan değerlerine göre mi yoksa girdiğiniz özel değerlere göre mi uygulanacağını belirleyin. Menüyü açıp en düşük ve en yüksek değerlere uygulamak istediğiniz renk örneklerini seçin. **Ayrılan** onay kutusunu işaretleyerek **Orta** değer ve renk de belirtin. 

![Hücre arka planını renk ölçeğiyle ayarlama](media/desktop-conditional-table-formatting/table-formatting-1-diverging-table.png)

**Affordability** sütununa renk ölçeği arka plan biçimlendirmesi uygulanmış bir tablo şöyle görünür:

![Ayrılan arka plan renk ölçeğine sahip örnek tablo](media/desktop-conditional-table-formatting/table-formatting-1-apply-color-to.png)

**Affordability** sütununa renk ölçeği yazı tipi biçimlendirmesi uygulanmış bir tablo şöyle görünür:

![Ayrılan yazı tipi renk ölçeğine sahip örnek tablo](media/desktop-conditional-table-formatting/table-formatting-2-table.png)

## <a name="color-by-rules"></a>Kurallara göre renk

Arka plan veya yazı tipi rengini kurallara göre biçimlendirmek için **Arka plan rengi** veya **Yazı tipi rengi** iletişim kutusunun **Şuna göre biçimlendir** iletişim kutusunda **Kurallar**'ı seçin. **Şu alana göre** bölümünde biçimlendirme için temel alınacak olan alan, **Özetleme** bölümünde ise alanın toplama türü gösterilir. 

**Kurallar** bölümüne bir veya daha fazla değer aralığı girin ve her biri için bir değer belirtin. Her değer aralığı bir *If* değer koşulu, bir *and* değer koşulu ve bir renk içerir. Her bir değer aralığındaki hücre arka planları veya yazı tipleri, belirtilen renkle renklendirilir. Aşağıdaki örnekte üç kural kullanılmıştır:

![Kurallara göre renk](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-if-value.png)

**Affordability** sütununa kural tabanlı arka plan renk biçimlendirmesi uygulanmış bir tablo şöyle görünür:

![Kurallara göre renk içeren örnek tablo](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-table.png)

## <a name="color-by-color-values"></a>Renk değerlerine göre renklendirme

Renk adı veya onaltılık değer verileri içeren bir alanınız veya ölçünüz varsa koşullu biçimlendirmeyi kullanarak bu renklerin otomatik olarak sütunun arka plan veya yazı tipi rengi olmasını sağlayabilirsiniz. Ayrıca özel mantık uygulayarak renklerin yazı tipine veya arka plana uygulanmasını da sağlayabilirsiniz.

Alanda [https://www.w3.org/TR/css-color-3/](https://www.w3.org/TR/css-color-3/) adresinde yer alan CSS renk belirtiminde listelenen tüm değerler kullanabilir. Bu renk değerleri şunları içerebilir:
- 3, 6 veya 8 haneli onaltılık kodlar; örneğin, #3E4AFF. Kodun başına # sembolünü eklediğinizden emin olun. 
- RGB veya RGBA değerleri, örn. RGBA(234, 234, 234, 0,5).
- HSL veya HSLA değerleri, örn. HSLA(123, %75, %75, 0,5).
- Green, SkyBlue veya PeachPuff gibi renk adları. 

Aşağıdaki tabloda her eyalet bir renk adıyla ilişkilendirilmiştir: 

![Renk adlarının yer aldığı eyaletler tablosu](media/desktop-conditional-table-formatting/conditional-table-formatting_01.png)

**Color** sütununu alan değerlerine göre biçimlendirmek için **Color** alanı için **Koşullu biçimlendirme**'yi ve ardından **Arka plan rengi** veya **Yazı tipi rengi**'ni seçin. 

**Arka plan rengi** veya **Yazı tipi rengi** iletişim kutusunda **Şuna göre biçimlendir** açılan alanından **Alan değeri**'ni seçin.

![Alan değerine göre biçimlendirme](media/desktop-conditional-table-formatting/conditional-table-formatting_02.png)

**Color** alanına göre renk alanı değerini temel alan **Arka plan rengi** biçimlendirmesine sahip bir tablo şöyle görünür:

![Alan değerine göre arka plan biçimlendirmesine sahip örnek tablo](media/desktop-conditional-table-formatting/conditional-table-formatting_03.png)

Sütunun **Yazı tipi rengi** için de **Alan değeri**'ni kullanırsanız **Color** sütunu düz renk olacaktır:

![Arka planı ve yazı tipini alan değerine göre biçimlendirme](media/desktop-conditional-table-formatting/conditional-table-formatting_04.png)

## <a name="color-based-on-a-calculation"></a>Hesaplamayı temel alan renk

Seçtiğiniz iş mantığı koşullarına göre farklı değerler veren bir DAX hesaplaması da oluşturabilirsiniz. DAX formülü oluşturma genellikle koşullu biçimlendirme iletişim kutusunda birden fazla kural oluşturmaktan daha kolaydır. 

Örneğin aşağıdaki DAX formülü, yeni **Affordability rank** sütununa var olan **Affordability** sütunu değerlerini temel alan onaltılık renk değerleri uygular:

![DAX hesaplaması](media/desktop-conditional-table-formatting/conditional-table-formatting_05.png)

Renkleri uygulamak için **Affordability** sütununda **Arka plan rengi** veya **Yazı tipi rengi** koşullu biçimlendirmesini seçin ve biçimlendirme için **Affordability rank** sütununun **Alan değeri** alanını temel alın. 

![Arka plan rengi için hesaplanmış sütunu temel alma](media/desktop-conditional-table-formatting/conditional-table-formatting_06.png)

Hesaplanmış **Affordability rank** değerlerini temel alan **Affordability** arka plan rengine sahip tablo şöyle görünür:

![Hesaplanmış değeri temel alan renge sahip örnek tablo](media/desktop-conditional-table-formatting/conditional-table-formatting_07.png)

Yalnızca hayal gücünüzü ve DAX bilginizi kullanarak birçok farklı kullanım oluşturabilirsiniz.

## <a name="add-data-bars"></a>Veri çubuğu ekleme

Hücre değerlerini temel alan veri çubukları göstermek için **Affordability** alanında **Koşullu biçimlendirme**'yi ve ardından açılan menüden **Veri çubukları**'nı seçin. 

**Veri çubukları** iletişim kutusunda **Yalnızca çubuğu göster** seçeneği varsayılan olarak işaretli değildir ve bu nedenle tablo hücreleri hem çubukları hem de gerçek değerleri gösterir. Yalnızca veri çubuklarını göstermek için **Yalnızca çubuğu göster** onay kutusunu seçin.

**En düşük** ve **En yüksek** değerleri, veri çubuğunun rengini, yönünü ve eksen rengini belirtebilirsiniz. 

![Veri çubukları iletişim kutusu](media/desktop-conditional-table-formatting/table-formatting-3-default.png)

**Affordability** sütununa veri çubukları uygulandıktan sonra tablo şöyle görünür:

![Veri çubukları içeren örnek tablo](media/desktop-conditional-table-formatting/table-formatting-3-default-table-bars.png)

## <a name="add-icons"></a>Simge ekleme

Hücre değerlerini temel alan simgeler göstermek için alanda **Koşullu biçimlendirme**'yi ve ardından açılan menüden **Simgeler**'i seçin. 

**Simgeler** iletişim kutusunun **Şuna göre biçimlendir** bölümünde **Kurallar**'ı veya **Alan değeri**'ni seçin. 

Kurallara göre biçimlendirmek için **Şu alana göre**, **Özetleme** yöntemi, **Simge düzeni**, **Simge hizalaması**, simge **Stili** ve bir veya daha fazla **Kural** seçin. **Kurallar**'ın altında *If değer* koşuluna sahip bir veya daha fazla kural ve bir *and* değer koşulu girin ve her bir kurala uygulanacak simgeleri belirleyin. 

Alan değerlerine göre biçimlendirmek için **Şu alana göre**, **Özetleme** yöntemi, **Simge düzeni** ve **Simge hizalaması** seçin.

Aşağıdaki örnekte üç kuralı temel alan simgeler eklenmiştir:

![Simgeler iletişim kutusu](media/desktop-conditional-table-formatting/table-formatting-1-default-table.png)

**Tamam**’ı seçin. **Affordability** sütununa kurallara göre simgeler uygulandıktan sonra tablo şöyle görünür:

![Simgeler içeren örnek tablo](media/desktop-conditional-table-formatting/table-formatting-1-default-dialog.png)

## <a name="format-as-web-urls"></a>Web URL'si olarak biçimlendirme

Web sitesi URL'leri içeren bir sütununuz veya ölçünüz varsa koşullu biçimlendirmeyi kullanarak bu URL'leri alanlara etkin bağlantılar olarak uygulayabilirsiniz. Örneğin aşağıdaki tablonun **Website** sütununda eyaletlerin Web sitelerinin URL'leri bulunmaktadır:

![Web URL'si sütununa sahip tablo](media/desktop-conditional-table-formatting/table-formatting-1-diverging.png)

Her eyaletin adını web sitesine canlı bağlantı olarak görüntülemek için **State** alanında **Koşullu biçimlendirme**'yi ve ardından **Web URL'si** girişini seçin. **Web URL'si** iletişim kutusunun **Şu alana göre** bölümünde **Web sitesi**'ni ve ardından **Tamam**'ı seçin. 

**Web URL'si** biçimlendirmesi **State** alanına uygulandığında eyalet adları Web sitesi bağlantısı haline dönüşür. Aşağıdaki örnek tabloda **State** sütununa **Web URL'si** biçimlendirmesi, **Affordability** sütununa ise koşullu **Veri çubukları** ve **Arka plan biçimlendirmesi** uygulanmıştır. 

![Web URL'si, veri çubukları ve arka plan rengi içeren tablo](media/desktop-conditional-table-formatting/table-formatting-3-default-table.png)

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar
Koşul tablo biçimlendirme ile çalışırken dikkat etmeniz gereken birkaç önemli nokta vardır:

- Koşullu biçimlendirme yalnızca Tablo veya Matris görsellerinin değerlerine uygulanır ve alt toplamlar, genel toplamlar ya da **Toplam** satırı için uygulanmaz. 
- Gruplandırması olmayan tablolar, koşullu biçimlendirmeyi desteklemeyen tek bir satır olarak görüntülenir.
- Verilerinizde *NaN* değerleri varsa otomatik en yüksek/en düşük değerler ile gradyan biçimlendirmesi veya yüzde kurallarıyla kural tabanlı biçimlendirme uygulayamazsınız. NaN, "Sayı değil" anlamına gelir ve genellikle sıfıra bölme hatasından kaynaklanır. Bu hataları engellemek için [DIVIDE() DAX işlevini](https://docs.microsoft.com/dax/divide-function-dax) kullanabilirsiniz.
- Koşullu biçimlendirme için değere bir toplama veya ölçüm uygulanması gerekir. Bu nedenle **Değere göre renk** örneğinde "İlk" veya "Son" değerler görünmektedir. Bir Analysis Service çok boyutlu küpü için rapor oluşturuyorsanız, küp sahibi değeri sağlayan bir ölçü oluşturmadığı sürece koşullu biçimlendirme için öznitelik kullanamazsınız.

## <a name="next-steps"></a>Sonraki adımlar

Renk biçimlendirme hakkında daha fazla bilgi için bkz. [Power BI'da renk biçimlendirmeye ilişkin ipuçları ve püf noktaları](visuals/service-tips-and-tricks-for-color-formatting.md)  

