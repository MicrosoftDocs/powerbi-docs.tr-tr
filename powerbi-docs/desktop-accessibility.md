---
title: Power BI Desktop raporlarında erişilebilirlik
description: Özellikler ve erişilebilir Power BI Desktop raporları oluşturmaya yönelik öneriler
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: bd0565420382fc22af67b1363b41f6d8ed6e92ab
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290764"
---
# <a name="accessibility-in-power-bi-desktop-reports"></a>Power BI Desktop raporlarında erişilebilirlik
**Power BI Desktop**'ta, engelli kullanıcıların **Power BI Desktop** raporlarını daha kolay bir şekilde kullanmasına ve bunlarla etkileşime geçmesine olanak sağlayan özellikler bulunur. Bu özellikler, klavye veya ekran okuyucu aracılığıyla raporları kullanabilme ve sayfalardaki çeşitli nesnelere odaklanmak için sekmeyle gezinebilme özelliklerinin yanı sıra görselleştirmelerde işaretçilerin verimli bir şekilde kullanılabilmesini içerir.

![Erişilebilirliği iyileştirmek üzere çizgi grafikler ve alan grafikleri için farklı işaretçiler kullanma](media/desktop-accessibility/accessibility_01.png)

> [!NOTE]
> Bu erişilebilirlik özellikleri Haziran 2017'de kullanıma sunulan **Power BI Desktop** sürümüyle ve sonraki sürümlerle kullanılabilir. Gelecek sürümlerle birlikte daha fazla erişilebilirlik özelliğini kullanıma sunmayı planlıyoruz.
> 
> 

## <a name="consuming-a-power-bi-desktop-report-with-a-keyboard-or-screen-reader"></a>Klavye veya ekran okuyucu ile Power BI Desktop raporlarını kullanma
**Power BI Desktop**'ın Eylül 2017 sürümünden itibaren, **?** tuşuna basarak, **Power BI Desktop**'ta kullanılabilen, erişilebilirliğe yönelik klavye kısayollarının açıklandığı bir pencerenin gösterilmesini sağlayabilirsiniz.

![Power BI Desktop'taki ? tuşuna basarak erişilebilirliğe yönelik klavye kısayollarını gösterebilirsiniz](media/desktop-accessibility/accessibility_03.png)

Erişilebilirlik iyileştirmeleri sayesinde, aşağıdaki teknikleri uygulayarak bir klavye veya ekran okuyucu ile **Power BI Desktop** raporlarını kullanabilirsiniz:

**Ctrl+F6** tuş birleşimini kullanarak bir rapordaki rapor sayfası sekmeleri veya nesneler arasında odağı çevirebilirsiniz.

* Odak *rapor sayfası sekmeleri* üzerindeyken, odağı bir rapor sayfasından sıradaki rapor sayfasına çevirmek için *Sekme* veya *Ok* tuşlarını kullanın. Rapor sayfasının başlığı ve sayfanın seçili olup olmadığı ekran okuyucusu tarafından sesli bir şekilde okunur. Odaklanılmış olan rapor sayfasını yüklemek için *Enter* veya *Boşluk* tuşunu kullanın.
* Odak bir *rapor sayfası* üzerinde olduğunda, odağı sayfadaki her bir nesneye (tüm metin kutuları, resimler, şekiller ve grafikler dahil) yöneltmek için *Sekme* tuşunu kullanın. Ekran okuyucu nesnenin türünün yanı sıra yazarı tarafından sağlanan açıklamasını okur. 

Odağı bir görsel menüsüne çevirmek için **Alt+Shift+F10** tuşlarına basabilirsiniz.

*Verileri gör* penceresinin erişilebilir bir sürümünün sunulması için **Alt+Shift+F11** tuşlarına basabilirsiniz.

![Power BI Desktop'ta bir görsele yönelik erişilebilir bir Verileri Gör penceresinin görüntülenmesi için Alt+Shift+F11 tuşlarına basma](media/desktop-accessibility/accessibility_04.png)

Bu erişilebilirlik eklemeleri, kullanıcıların ekran okuyucu ve klavye gezintisi aracılığıyla **Power BI Desktop** raporlarını tam olarak kullanabilmesine olanak sağlamak için oluşturulmuştur.

## <a name="tips-for-creating-accessible-reports"></a>Erişilebilir raporlar oluşturmaya yönelik ipuçları
Aşağıdaki ipuçları, daha erişilebilir **Power BI Desktop** raporları oluşturmanıza yardımcı olabilir.

* **Çizgi**, **Alan** ve **Birleşik** görsellerin yanı sıra **Dağılım** ve **Kabarcık** görselleri için işaretçileri açın ve her bir çizgi için farklı *İşaretçi şekilleri* kullanın.
  
  * *İşaretçileri* etkinleştirmek için, **Görsel Öğeler** bölmesindeki **Biçim** bölümünü açın, **Şekiller** bölümünü genişletin ve ardından **İşaretçiler**'e ilişkin geçiş tuşuna gidip *Açık* seçeneğini belirleyin.
  * Ardından, bu **Şekiller** bölümündeki açılan kutudan her bir çizginin (veya bir **Alan** grafiği kullanıyorsanız her bir alanın) adını seçin. Açılan kutunun altında, seçili çizgi için kullanılan işaretçinin birçok özelliğini (şekli, rengi ve boyutu dahil) ayarlayabilirsiniz.
  
  ![Erişilebilirliği iyileştirmek üzere çizgi grafikler ve alan grafikleri için farklı işaretçiler kullanma](media/desktop-accessibility/accessibility_01.png)
  
  * Her bir çizgi için farklı bir *İşaretçi şekli* kullanılması, rapor kullanıcılarının çizgileri (veya alanları) daha kolay bir şekilde ayırt edebilmesini sağlar.
* Önceki maddeye ek olarak, bilgileri ifade etmek için renkleri kullanmamanızı öneririz. Çizgilerde şekilleri (önceki maddede açıklandığı gibi, işaretçiler) kullanmakta yarar vardır.
* Tema galerisinden yüksek karşıtlığı bulunan ve renkleri ayırt etmekte zorlanan kişiler için uygun bir *tema* seçin ve temayı [**Tema Oluşturma** önizleme özelliğini](desktop-report-themes.md) kullanarak içeri aktarın.
* Rapordaki her bir nesne için *Diğer Metin* sağlayın. Böylece, raporunuzu kullanan kişiler; ilgili görseli, resmi, şekli veya metin kutusunu görmese bile bu görselle ne amaçladığınızı anlayabilir. Nesneyi (görsel, şekil vb.) seçip **Görsel Öğeler** bölmesindeki **Biçim** bölümünde bulunan **Genel**'i genişleterek ve ardından en alt kısma gidip **Diğer Metin** metin kutusunu doldurarak bir **Power BI Desktop** raporundaki herhangi bir nesne için *Diğer Metin* sağlayabilirsiniz.
  
  ![Görsel Öğeler > Biçim > Genel > Diğer Metin kutusu yolu izlenerek rapordaki herhangi bir nesne için diğer metin eklenebilir](media/desktop-accessibility/accessibility_02.png)
* Raporlarınızdaki metinler ve arka plan renkleri arasında yeterli düzeyde karşıtlık bulunduğundan emin olun.
* Kolay okunabilir metin boyutları ve yazı tipleri kullanın. Okunması zor olabilecek kadar küçük boyutlu metinler ve yazı tipleri erişilebilirlik açısından kullanışsızdır.
* Tüm görsellere başlık, eksen etiketleri ve veri etiketleri ekleyin.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar
Erişilebilirlik özelliklerine ilişkin sınırlamalar ve bilinen birkaç sorun aşağıdaki listede açıklanmıştır:

* JAWS, tüm eklenen raporlar da dahil olmak üzere **Power BI hizmetinde** görüntülenen raporlarda desteklenir. JAWS **Power BI Desktop**'ta da desteklenir ancak ekran okuyucunun düzgün bir şekilde çalışması için, okuyucuyu, herhangi bir **Power BI Desktop** dosyasını açmadan önce açmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI Desktop'ta Rapor Temalarını Kullanma (Önizleme)](desktop-report-themes.md)

