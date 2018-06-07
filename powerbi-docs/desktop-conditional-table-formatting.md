---
title: Power BI Desktop'ta koşullu tablo biçimlendirme
description: Tablolara özel biçimlendirme uygulama
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 70aa61d6a02bea1b7058a68b20718008ace1b8c8
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34480900"
---
# <a name="conditional-formatting-in-tables"></a>Tablolarda koşullu biçimlendirme 
Tablolar için koşullu biçimlendirme sayesinde hücre değerlerine göre (veya başka değerlere ya da alanlara göre) özel hücre renkleri belirtebilir ve gradyan renklerini kullanabilirsiniz. Ayrıca, veri çubukları ile hücre değerlerini gösterebilirsiniz. 

Koşullu biçimlendirme seçeneklerine erişmek için Power BI Desktop'ın **Görsel Öğeler** bölmesinin **Alanlar** kutusundaki **Değerler** kutusunda yer alan değerlerden biçimlendirmek istediğinizin yanındaki aşağı oku seçin (veya alana sağ tıklayın). Koşullu biçimlendirmeyi yalnızca **Alanlar** kutusunun **Değerler** alanındaki alanlar için yönetebilirsiniz.

![Koşullu biçimlendirme menüsü](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

Aşağıdaki bölümlerde bu üç koşullu biçimlendirme seçeneğinin her biri açıklanmaktadır. Tek bir tablo sütununda bir veya daha fazla seçenek birleştirilebilir.

> [!NOTE]
> Koşullu biçimlendirme bir tabloya uygulandığında, koşullu biçimlendirilmiş hücrelere uygulanmış olan özel tablo stillerini geçersiz kılar.

Bir görselleştirmedeki koşullu biçimlendirmeyi kaldırmak için alana tekrar sağ tıklayın, **Koşullu biçimlendirmeyi kaldır**'ı ve sonra kaldırılacak biçimlendirme türünü seçin.

![Koşullu biçimlendirmeyi kaldır menüsü](media/desktop-conditional-table-formatting/table-formatting-1-remove.png)

## <a name="background-color-scales"></a>Arka plan renk ölçekleri

**Koşullu biçimlendirme** ve sonra **Arka plan renk ölçekleri** seçildiğinde aşağıdaki iletişim kutusu açılır.

![Arka plan renk ölçekleri iletişim kutusu](media/desktop-conditional-table-formatting/table-formatting-1-default-dialog.png)

Bir alanda **Renk temeli** ayarını yaparak veri modelinizden renklerin temel alacağı alanı seçebilirsiniz. Ayrıca, **Özetleme** değerleri ile birlikte seçili alan için toplama türünü belirtebilirsiniz. Renklendirilecek alan **Rengi şuraya uygula:** alanında belirtilir, böylece takip edebilirsiniz. Biçimlendirme temeli olarak sayısal bir değer seçtiğiniz sürece, metin ve tarih alanlarına koşullu biçimlendirme uygulayabilirsiniz.

![Renk temeli alanı](media/desktop-conditional-table-formatting/table-formatting-1-apply-color-to.png)

Belirtilen değer aralıkları için ayrı renk değerleri kullanmak istiyorsanız **Kurallara göre renk** öğesini seçin. Bir renk spektrumu kullanmak için **Kurallara göre renk** kutusunu işaretlenmemiş olarak bırakın. 

![Arka plan renk ölçekleri iletişim kutusu](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-dialog.png)

### <a name="color-by-rules"></a>Kurallara göre renk

**Kurallara göre renk** öğesini seçtiğinizde her biri ayarlanmış bir renge sahip bir veya daha fazla değer aralığı girebilirsiniz.  Her değer aralığı bir *If* değer koşulu, bir *and* değer koşulu ve bir renk ile başlar.

![Kurallara göre renk değer aralığı](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-if-value.png)

Her bir aralıkta değerleri olan tablo hücreleri, belirtilen renkle doldurulur. Aşağıdaki şekilde üç kural vardır.

![Kurallara göre renk örneği](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules.png)

Örnek tablo şimdi şu şekilde görünür:

![Kurallara göre renk içeren örnek tablo](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-table.png)


### <a name="color-minimum-to-maximum"></a>En düşükten en yükseğe renk

*En Düşük* ve *En Yüksek* değerler ile renklerini yapılandırabilirsiniz. **Ayrılan** kutusunu seçerseniz isteğe bağlı bir *Orta* değeri de yapılandırabilirsiniz.

![Ayrılan düğmesi](media/desktop-conditional-table-formatting/table-formatting-1-diverging.png)

Örnek tablo şimdi şu şekilde görünür:

![Ayrılan renkler içeren örnek tablo](media/desktop-conditional-table-formatting/table-formatting-1-diverging-table.png)

## <a name="font-color-scales"></a>Yazı tipi renk ölçekleri

**Koşullu biçimlendirme** ve sonra **Yazı tipi renk ölçekleri** seçildiğinde aşağıdaki iletişim kutusu açılır. Bu iletişim kutusu **Arka plan renk ölçekleri** iletişim kutusuna benzer ancak hücre arka plan rengi yerine yazı tipi rengini değiştirir.

![Yazı tipi renk ölçekleri iletişim kutusu](media/desktop-conditional-table-formatting/table-formatting-2-diverging.png)

Örnek tablo şimdi şu şekilde görünür:

![Yazı tipi renk ölçeklerini içeren örnek tablo](media/desktop-conditional-table-formatting/table-formatting-2-table.png)

## <a name="data-bars"></a>Veri çubukları

**Koşullu biçimlendirme** ve sonra **Veri çubukları** seçildiğinde aşağıdaki iletişim kutusu açılır. 

![Veri çubukları iletişim kutusu](media/desktop-conditional-table-formatting/table-formatting-3-default.png)

Varsayılan olarak, **Yalnızca çubuğu göster** seçeneği işaretli değildir ve bu nedenle tablo hücresi hem çubuğu hem de gerçek değeri gösterir.

![Veri çubukları ve değerlerini içeren örnek tablo](media/desktop-conditional-table-formatting/table-formatting-3-default-table.png)

**Yalnızca çubuğu göster** seçeneği işaretliyse tablo hücresi yalnızca çubuğu gösterir.

![Yalnızca veri çubukları içeren örnek tablo](media/desktop-conditional-table-formatting/table-formatting-3-default-table-bars.png)
