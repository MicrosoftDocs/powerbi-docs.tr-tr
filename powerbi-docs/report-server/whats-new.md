---
title: Power BI Rapor Sunucusu'ndaki yenilikler
description: Power BI Rapor Sunucusu'ndaki yenilikler hakkında bilgi edinin. Önemli özelliklere yer verilen bu belge, yeni sürümlerle birlikte güncelleştirilmektedir.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/22/2019
ms.openlocfilehash: e645cd84b646e180114027464ea4781277d5245f
ms.sourcegitcommit: a054782370dec56d49bb205ee10b7e2018f22693
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56662469"
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI Rapor Sunucusu'ndaki yenilikler

Power BI Rapor Sunucusu'ndaki yenilikler hakkında bilgi edinin. Önemli özelliklere yer verilen bu makale, yeni sürümlerle birlikte güncelleştirilmektedir.

Power BI Rapor Sunucusu'nun en son sürümünü ve Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop'ı indirmek için [Power BI Rapor Sunucusu ile şirket içi raporlama](https://powerbi.microsoft.com/report-server/) sayfasına gidin.

İlgili Power BI "Yenilikleri" hakkında bilgi için bkz.:

* [Power BI hizmetindeki yenilikler](../service-whats-new.md)
* [Power BI Desktop'taki yenilikler](../desktop-latest-update.md)
* [Power BI mobil uygulamalarındaki yenilikler](../consumer/mobile/mobile-whats-new-in-the-mobile-apps.md)

## <a name="january-2019"></a>Ocak 2019

Power BI raporlarında bu özellikler için destek:

[**Satır düzeyi güvenlik**](row-level-security-report-server.md) Power BI Rapor Sunucusu ile satır düzeyi güvenlik (RLS) ayarlandığında, belirli kullanıcıların veri erişimi kısıtlanabilir. Filtreler, veri erişimini satır düzeyinde sınırlar ve rollerin içinde filtre tanımlayabilirsiniz.

[**Matris satır üst bilgilerini genişletme ve daraltma**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#expandCollapse) Tek tek satır üst bilgilerini genişletebilme ve daraltabilme özelliği ekledik. Bu, en çok istenen görsel özelliklerden biriydi.

[**.pbix dosyaları arasında kopyalama ve yapıştırma**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#copyPaste) Görselin bağlam menüsünden veya standart Ctrl+C klavye kısayoluyla görselleri .pbix dosyaları arasında kopyalayabilir ve Ctrl+V ile başka bir rapora yapıştırabilirsiniz.

[**Akıllı hizalama kılavuzları**](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#smartGuides) Rapor sayfanızdaki her şeyi hizalamanıza yardımcı olması için, sayfanızda nesneleri taşırken PowerPoint'teki gibi akıllı hizalama kılavuzları görürsünüz. Sayfanızdaki bir nesneyi her sürüklediğinizde veya yeniden boyutlandırdığınızda akıllı kılavuzları görürsünüz. Bir nesneyi başka bir nesnenin yakınına taşıdığınızda, taşınan nesne diğeriyle hizalı bir konuma yerleştirilir.

**Erişilebilirlik özellikleri** Listelenemeyecek kadar çok erişilebilirlik özelliği var: örneğin, [alan listesi bölmesi erişilebilirlik desteği](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#fieldList). Alan listesi bölmesi tümüyle erişilebilirdir. Yalnızca klavyenizi ve ekran okuyucuyu kullanarak bölmede gezinebilir ve bağlam menüsünü kullanarak rapor sayfanıza alanlar ekleyebilirsiniz.

#### <a name="custom-visuals"></a>Özel Görseller

- Bu yayınla birlikte 2.3 API sürümü kullanılmıştır.

### <a name="administrator-settings"></a>Yönetici ayarları

Yöneticiler sunucu grubunun SSMS Gelişmiş Özellikleri bölümünde aşağıdaki ayarları yapabilir:

**AllowedResourceExtensionsForUpload** Rapor sunucusuna yüklenebilecek kaynakların uzantılarını ayarlayın. Yerleşik dosya türlerinin uzantılarını (&ast;.rdl ve &ast;.pbix gibi) eklemek gerekmez. Varsayılan uzantılar “&ast;, &ast;.xml, &ast;.xsd, &ast;.xsl, &ast;.png, &ast;.gif, &ast;.jpg, &ast;.tif, &ast;.jpeg, &ast;.tiff, &ast;.bmp, &ast;.pdf, &ast;.svg, &ast;.rtf, &ast;.txt, &ast;.doc, &ast;.docx, &ast;.pps, &ast;.ppt, &ast;.pptx” uzantılarıdır. 

**SupportedHyperlinkSchemes** İşlenmesine izin verilen Köprü eylemlerinde tanımlanmasına izin verilen URI şemalarının virgülle ayrılmış listesini ayarlar veya tüm köprü şemalarına izin vermek için “&ast;” kullanılır. Örneğin, “http,https” ayarlandığında “https://www. contoso.com” köprülerine izin verilir ama “mailto:bill@contoso.com” veya “javascript:window.open(‘www.contoso.com’, ‘_blank’)” köprülerine izin verilmez. Varsayılan değer “&ast;” ayarıdır.

## <a name="august-2018"></a>Ağustos 2018

Ağustos 2018 yayınında, Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop sürümüne çok fazla sayıda yeni özellik eklenmiştir. Alana göre ayrıştırılmış şekilde bu yenilikler aşağıdaki gibidir:

- [Raporlama](#reporting)
- [Analiz](#analytics)
- [Modelleme](#modeling)

### <a name="highlights-of-the-august-2018-release"></a>Ağustos 2018 yayının öne çıkan özellikleri

Yeni özelliklerin uzun listesinde öne çıkan ilginç özellikler şunlardır. Daha fazla bilgi için [blog gönderimize](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/) bakın.

#### <a name="report-theming"></a>Rapor teması oluşturma

Raporunuzun tamamını belirli bir tema veya kurumsal kimlikle eşleştirecek şekilde hızlıca renklendirmenizi sağlayan rapor teması oluşturma özelliği, Power BI Rapor Sunucusu'nun Ağustos 2018 yayınına eklenmiştir. Bir temayı içeri aktardığınızda tüm grafikleriniz tema renklerini kullanacak şekilde otomatik olarak güncelleştirilir ve tema renklerine renk paletinden erişebilirsiniz. Tema dosyasını yüklemek için **Temayı Değiştir** düğmesinin altındaki **Temayı İçeri Aktar** seçeneğini kullanabilirsiniz.

Tema dosyası, raporunuzda kullanmak istediğiniz tüm renklere ek olarak görsellere uygulamak istediğiniz varsayılan biçimlendirmeyi içeren bir JSON dosyasıdır.
Raporun varsayılan renklerini güncelleştiren örnek bir JSON teması aşağıda verilmiştir:

```json
{
"name": "waveform",
"dataColors": [ "#31B6FD", "#4584D3", "#5BD078", "#A5D028", "#F5C040", "#05E0DB", "#3153FD", "#4C45D3", "#5BD0B0", "#54D028", "#D0F540", "#057BE0" ],
"background":"#FFFFFF",
"foreground": "#F2F2F2",
"tableAccent":"#5BD078"
}
```

#### <a name="conditional-formatting-by-a-different-field"></a>Farklı bir alan ile koşullu biçimlendirme

Bir sütunu modelinizdeki farklı bir alana göre biçimlendirme özelliği, koşullu biçimlendirmede yapılan önemli geliştirmelerden biridir.

#### <a name="conditional-formatting-by-values"></a>Değerlere göre koşullu biçimlendirme

Yeni eklenen koşullu biçimlendirme türlerinden biri de **Alana göre biçimlendir** değeridir. Alana göre biçimlendir değeri, onaltılık kod veya ad ile renk belirten bir ölçüyü veya sütunu kullanmanızı ve bu rengi arka plana veya yazı tipi rengine uygulamanızı sağlar.

#### <a name="report-page-tooltips"></a>Rapor sayfası araç ipuçları

Rapor sayfası araç ipuçları özelliği, Power BI Rapor Sunucusu'nun Ağustos 2018 güncelleştirmesine eklenmiştir. Bu özellik, raporunuzdaki diğer görseller için özel araç ipucu olarak kullanılacak bir rapor sayfası tasarlamanızı sağlar.

#### <a name="log-axis-improvements"></a>Günlük ekseni iyileştirmeleri

Kartezyen grafiklerinizdeki günlük ekseninde önemli geliştirmeler yaptık. Artık verileriniz tamamen pozitif veya tamamen negatif olduğunda birleşik harita dahil olmak üzere tüm kartezyen grafiklerin sayısal ekseni için günlük eksenini seçebilirsiniz.

#### <a name="sap-hana-sso-direct-query"></a>SAP HANA SSO Doğrudan Sorgu

Power BI Raporlarında artık Kerberos ile SAP HANA SSO Doğrudan Sorgu desteği sunulmaktadır.

>[!Note]
>Bu senaryo yalnızca SAP HANA, Power BI'da oluşturduğunuz raporlarla ilişkisel veri kaynağı olarak kullanıldığında desteklenir.  Bu özelliği Power BI Desktop uygulamasında etkinleştirmek için DirectQuery menüsünün Seçenekler bölümünden “SAP HANA’ya bir ilişkisel kaynak olarak davranma” seçeneğini işaretleyin ve Tamam'a tıklayın.

#### <a name="custom-visuals"></a>Özel Görseller

- Bu yayınla birlikte 1.13.0 API sürümü kullanılmıştır.

- Artık özel görseller sunucu API'sinin geçerli sürümüyle uyumlu eski bir sürüme geri dönebilir (varsa).

### <a name="reporting"></a>Raporlama 

- [Rapor Teması Oluşturma](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#theming)
- [Eylem tetikleme düğmeleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#buttons)
- [Birleşik grafik çizgisi stilleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLines)
- [Görseller için varsayılan sıralama iyileştirildi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sort)
- [Sayısal dilimleyici](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#numericSlicer)
- [Gelişmiş dilimleyici eşitleme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerSync)
- [Günlük ekseni iyileştirmeleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#logAxis)
- [Huni grafiği için veri etiketi seçenekleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#funnelChart)
- [Çizgi darbe genişliğini sıfıra ayarlama](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#lineStroke)
- [Raporlar için yüksek karşıtlık desteği](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#highContrast)
- [Halka yarıçap denetimi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#donutRadius)
- [Pasta ve halka ayrıntı etiketleri konumlandırma denetimi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#detailLabels)
- [Bir birleşik haritadaki her ölçüm için veri etiketlerini ayrı ayrı biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLabels)
- [Daha fazla esneklik ve biçimlendirmeyle yeni görsel üst bilgi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#visualHeader)
- [Duvar kağıdı biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#wallpaper)
- [Tablo ve matris için araç ipuçları](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tableTooltips)
- [Görsellerde araç ipuçlarını kapatma](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tooltips)
- [Dilimleyici erişilebilirliği](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerAccessibility)
- [Biçimlendirme bölmesi geliştirmeleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#formattingPane)
- [Çizgi grafikler ve bileşik haritalar için basamaklı çizgi desteği](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#steppedLine)
- [Sıralama deneyimi geliştirmesi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sorting)
- [PDF'ye dışarı aktar özelliğiyle rapor yazdırma (Power BI Desktop uygulamasında)](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#print)
- [Yer işareti grubu oluşturma](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#bookmarks)
- [Dilimleyici yeniden belirleme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicer)
- [Rapor sayfası araç ipuçları](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#reportPageTooltips)

### <a name="analytics"></a>Analiz

- [Yeni DAX işlevi: COMBINEVALUES()](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#combineValues)
- [Ölçü detaylandırma](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#measureDrillthrough)
- [Farklı bir alan ile koşullu biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingField)
- [Değerlere göre koşullu biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingValue)

### <a name="modeling"></a>Modelleme

- [Veri görünümünde filtreleme ve sıralama](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#filterAndSort)
- [Geliştirilmiş yerel ayar biçimlendirmesi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#locale)
- [Ölçüler için veri kategorileri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dataCategory)
- [İstatistiksel DAX işlevleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dax)

## <a name="may-2018"></a>Mayıs 2018

### <a name="configure-power-bi-ios-mobile-apps-for-report-servers-remotely"></a>Uzaktan rapor sunucuları için Power BI iOS mobil uygulamalarını yapılandırma

BT yöneticisi olarak artık kuruluşunuzun MDM aracını kullanarak bir rapor sunucusuna Power BI iOS mobil uygulama erişimini uzaktan yapılandırabilirsiniz. Ayrıntılı bilgi için bkz. [Uzaktan bir rapor sunucusuna Power BI iOS mobil uygulama erişimini yapılandırma](configure-powerbi-mobile-apps-remote.md).

## <a name="march-2018"></a>Mart 2018

Mart 2018 yayınında, Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop sürümüne çok fazla sayıda yeni özellik eklenmiştir. Alana göre ayrıştırılmış şekilde bu yenilikler aşağıdaki gibidir:

- [Görseller](#visuals-updates)
- [Raporlama](#reporting)
- [Analiz](#analytics)
- [Performans](#performance)
- [Rapor sunucusu](#report-server)
- [Diğerleri](#other-improvements)

### <a name="highlights-of-the-march-2018-release"></a>Mart 2018 yayının öne çıkan özellikleri

Yeni özelliklerin uzun listesinde öne çıkan ilginç özellikler şunlardır.

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[Tablo ve matris için kural tabanlı koşullu biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)

Tablo veya matrisinizdeki özel iş mantığına dayalı bir sütunun yazı tipi rengini veya arka planı koşullu olarak renklendirmek için kurallar oluşturun.

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[Sayfaları gösterme ve gizleme](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

Okuyucularınızın raporunuza erişim elde etmesini istiyorsunuz, ancak sayfalardan bazıları henüz tamamlanmamış. Artık hazır oluncaya kadar bunları gizleyebilirsiniz. Alternatif olarak, sayfaları normal gezintiden gizleyebilirsiniz ve okuyucular yer işaretlerini veya detaylandırmayı kullanarak sayfaya erişebilir.

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[Yer işareti ekleme](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

Yer işareti demişken, raporunuzdaki verilerle bir hikaye anlatmak için yer işaretleri oluşturabilirsiniz.

- [Yer işaretleri için çapraz vurgulama](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): Yer işaretleri, yer işaretini oluşturduğunuz anda rapor sayfasının çapraz vurgulanan durumunu korur ve görüntüler.
- [Daha fazla yer işareti esnekliği](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): Yer işaretleri, raporunuzda ayarladığınız özellikleri yansıtır ve yalnızca seçtiğiniz görselleri etkiler.

#### <a name="multi-select-data-points-across-multiple-chartshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarycrosshighlight"></a>[Birden çok grafikte çoklu seçim noktaları](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

Birden çok grafikte çoklu veri noktası seçip sayfanın tamamına çapraz filtreleme uygulayabilirsiniz.

#### <a name="sync-slicers-across-multiple-pages-of-your-reporthttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarysyncslicers"></a>[Raporunuzun birden çok sayfasında dilimleyicileri eşitleme](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

Dilimleyici, bir rapordaki bir, iki veya daha fazla sayfaya uygulanabilir.

#### <a name="quick-measureshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summaryquickmeasures"></a>[Hızlı ölçümler](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

Bir tablodaki mevcut ölçümlere ve sayısal sütunlara dayalı yeni ölçümler oluşturabilirsiniz.

#### <a name="drilling-down-filters-other-visualshttpspowerbimicrosoftcomblogpower-bi-desktop-december-feature-summarydrillfiltersothervisuals"></a>[Detaya gidildiğinde diğer görselleri de filtreleme](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

Bir görselde belirtilen bir kategoride detaya gittiğinizde, sayfadaki tüm görselleri aynı kategoriye göre filtreleyebilirsiniz.

### <a name="visuals-updates"></a>Görsellerin güncelleştirmeleri

- [Tablo ve matris için hücre hizalaması](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [Tablo ve matris sütunları için birimleri ve duyarlık denetimini görüntüleme](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [Çubuk ve sütun grafikleri için taşma veri etiketleri](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [Kartezyen ve eşleme görselleri için veri etiketi arka plan rengini denetleme](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [Çubuk/sütun doldurma denetimi](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [Grafiklerde eksen etiketleri için kullanılan alanı artırma](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [x ve y eksen gruplandırmalarıyla dağılım görseli](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [Enlem ve boylam temelli haritalar için yüksek yoğunluklu örnekleme](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [Esnek dilimleyiciler](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [Göreli tarih dilimleyici için yer işareti tarihi ekleme](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>Raporlama

- [Rapor için okuma modunda görsel üst bilgiyi kapatma](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [Yavaş veri kaynakları için rapor seçenekleri](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [Gelişmiş varsayılan görsel yerleşimi](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [Seçim bölmesi aracılığıyla görsel sıralamasını denetleme](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [Raporunuzdaki nesneleri kilitleme](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [Biçimlendirme ve analiz bölmelerinde arama](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [Alan özellikleri bölmesi ve alan açıklamaları](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>Analiz

- [UTCNOW() ve UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [Özel tarih tablosu işaretleme](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [Detaya gidildiğinde diğer görselleri de filtreleme](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [Çok satırlı kart için çok boyutlu AS modellerini hücre düzeyinde biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)

### <a name="performance"></a>Performans

- [Filtrelemeye ilişkin performans iyileştirmeleri](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [DirectQuery’ye ilişkin performans iyileştirmeleri](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [Açma ve kaydetmeye ilişkin performans iyileştirmeleri](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [“Veri içermeyen öğeleri göstermeye” ilişkin iyileştirmeler](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)

### <a name="report-server"></a>Rapor sunucusu

#### <a name="export-to-accessible-pdf"></a>Erişilebilir PDF'ye dışa aktarma

Sayfalandırılmış (RDL) raporu PDF’ye dışarı aktardığınızda artık erişilebilir/etiketlenmiş bir PDF dosyası elde edebilirsiniz. Boyutu daha büyüktür, ancak ekran okuyucularının ve diğer yardımcı teknolojilerin okuması ve gezinmesi daha kolaydır. **AccessiblePDF** cihaz bilgileri ayarını **True** olarak belirleyerek erişilebilir PDF’yi etkinleştirebilirsiniz. Bkz. [PDF Cihaz Bilgileri Ayarları](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings) ve [Cihaz Bilgileri Ayarlarını Değiştirme](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings).

### <a name="other-improvements"></a>Diğer iyileştirmeler

- [Örneklerden Sütun Eklemeye ilişkin iyileştirmeler](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [Danışmanlık Hizmetleri hızlı bağlantısı](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [Gelişmiş hata raporlama](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [Daha önce karşılaştığınız hataları görüntüleme](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

## <a name="october-2017"></a>Ekim 2017

### <a name="power-bi-report-data-sources"></a>Power BI raporu veri kaynakları

Power BI Rapor Sunucusu'ndaki Power BI raporları çeşitli veri kaynaklarına bağlanabilir. Verileri içeri aktarabilir, veri yenileme zamanlayabilir veya DirectQuery ya da SQL Server Analysis Services canlı bağlantısı kullanarak doğrudan sorgulayabilirsiniz. Zamanlanmış yenileme ve DirectQuery desteği sunan veri kaynaklarının listesi için bkz. "Power BI Rapor Sunucusu'ndaki Power BI raporu veri kaynakları".

### <a name="scheduled-data-refresh-for-imported-data"></a>İçeri aktarılan veriler için zamanlanmış veri yenileme

Power BI Rapor Sunucusu'nda canlı bağlantı veya DirectQuery yerine ekli bir model kullanarak Power BI raporlarındaki verileri güncel tutmak için zamanlanmış veri yenileme özelliğini kullanabilirsiniz. Ekli bir model ile verileri içeri aktarırsınız ve verilerin, özgün veri kaynağıyla bağlantısı kesilir. Verilerin güncel tutulması için güncelleştirilmesi gerekir ve bunu zamanlamış yenileme ile gerçekleştirebilirsiniz. "Power BI Rapor Sunucusu'ndaki Power BI raporları için zamanlanmış yenileme" hakkında daha fazla bilgi edinin.

### <a name="editing-power-bi-reports-from-the-server"></a>Power BI raporlarını sunucuda düzenleme

Power BI raporu (.pbix) dosyalarını sunucuda açıp düzenleyebilirsiniz ancak bu durumda, karşıya yüklediğiniz özgün dosyaya dönersiniz.  Başka bir deyişle **veriler sunucu tarafından yenilenmişse dosyayı ilk açtığınızda veriler yenilenmez**. Değişiklikleri görmek için dosyayı el ile yenilemeniz gerekir.

### <a name="large-file-uploaddownload"></a>Büyük dosyaları karşıya yükleme/indirme

SQL Server Management Studio'daki (SSMS) Rapor Sunucusu ayarlarında sınır 1 GB olarak belirtilmiş olsa da en fazla 2 GB boyutundaki dosyaları karşıya yükleyebilirsiniz.  Bu dosyalar veritabanında SharePoint'te olduğu gibi depolanır ve SQL Server kataloğu için özel bir yapılandırma gerekmez.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Paylaşılan veri kümelerine OData akışı olarak erişme

Paylaşılan veri kümelerine Power BI Desktop'tan OData akışı ile erişebilirsiniz. Daha fazla bilgi için bkz. [Power BI Rapor Sunucusu'nda, paylaşılan veri kümelerine OData akışları olarak erişme](access-dataset-odata.md).

### <a name="scale-out"></a>Ölçeği genişletme

Bu sürüm, ölçeği genişletme desteği sunmaktadır. En iyi deneyim için yük dengeleyici kullanın ve sunucu benzeşimi oluşturun. Senaryonun henüz ölçeği genişletme için en iyi duruma getirilmediğini unutmayın. Bu nedenle, modellerin birden fazla düğümde çoğaltıldığını görebilirsiniz. Bu senaryo Ağ Yükü Dengeleyici ve kalıcı oturum desteği olmadan çalışacaktır. Ancak, bu durumda model N kez yüklendiği için düğümler arasında fazla bellek kullanımının yanı sıra model, istekler arasında yeni bir düğümle karşılaştığında akış yapılacağından bağlantılar arası performans düşüklüğü yaşanacaktır.  

### <a name="administrator-settings"></a>Yönetici ayarları

Yöneticiler sunucu grubunun SSMS Gelişmiş Özellikleri bölümünde aşağıdaki ayarları yapabilir:

* EnableCustomVisuals: True/False
* EnablePowerBIReportEmbeddedModels: True/False
* EnablePowerBIReportExportData: True/False
* MaxFileSizeMb: Varsayılan değer şimdi 1000'dir
* ModelCleanupCycleMinutes: Bellekteki modelleri çıkarmak için denetleme sıklığı
* ModelExpirationMinutes: Son kullanılma zamanına bağlı olarak modelin süresinin dolması ve çıkarılması için beklenecek süre
* ScheduleRefreshTimeoutMinutes: Modelde veri yenilemenin ne kadar sürebileceği. Bu süre varsayılan olarak iki saattir.  Kesin bir üst sınır yoktur.

**rsreportserver.config yapılandırma dosyası**

```xml
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Geliştirici API'si

SSRS 2017 için yayımlanmış olan geliştirici API'si (REST API), Power BI Rapor Sunucusu için genişletilerek hem Excel dosyaları hem de .pbix dosyalarıyla çalışacak şekilde geliştirilmiştir. Olası kullanım senaryolarından biri sunucudaki dosyaları programlama yoluyla indirmek, yenilemek ve yeniden yayımlamaktır. Örneğin, bu, PowerPivot modellerine sahip Excel çalışma kitaplarını yenilemenin tek yoludur.

Daha büyük dosyalar için yeni bir API olduğunu ve bunun, Swagger'ın Power BI Rapor Sunucusu sürümünde güncelleştirileceğini unutmayın. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) ve Power BI Rapor Sunucusu bellek ayak izi

SQL Server Analysis Services (SSAS) artık Power BI Rapor Sunucusu içinde barındırılmaktadır. Bu durum zamanlanmış yenilemeye özgü değildir. SSAS hizmetinin barındırılması sayesinde rapor sunucusu bellek ayak izi önemli ölçüde genişletilebilir. AS.ini yapılandırma dosyası sunucu düğümleri üzerinde mevcuttur. Bu nedenle SSAS konusunda bilgi sahibiyseniz maksimum bellek sınırı ve diski önbelleğe alma gibi özellikler de dahil olmak üzere bu ayarları güncelleştirebilirsiniz. Ayrıntılar için bkz. [Analysis Services'deki sunucu özellikleri](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services).

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Excel çalışma kitaplarını görüntüleme ve bunlarla etkileşim kurma

Excel ve Power BI, sektörde benzeri olmayan bir araç portföyü sunabilir. Bu iki uygulama bir arada kullanıldığında iş analistlerine verileri toplama, şekillendirme, çözümleme ve görsel olarak inceleme konusunda kolaylık sunar. İş kullanıcıları, Power BI raporlarını web portalında görüntülemenin yanı sıra Power BI Rapor Sunucusu'nda Excel çalışma kitaplarını görüntüleyerek tek noktadan kendilerine ait Microsoft BI içeriğini yayımlayabilir ve görüntüleyebilir.

[Power BI Rapor Sunucusu önizleme ortamınıza Office Online Server (OOS) eklemeye ilişkin adım adım yönergelerin sağlandığı bir kılavuz](excel-oos.md) yayımladık. Toplu Lisanslama hesabına sahip müşteriler OOS uygulamasını Toplu Lisanslama Hizmeti Merkezi'nden ücretsiz indirerek yalnızca görüntüleme işlevini kullanabilir. Kullanıcılar, yapılandırmanın ardından aşağıdaki koşulları karşılayan Excel çalışma kitaplarını görüntüleyebilir ve bunlarla etkileşim kurabilir:

* Dış veri kaynağı bağımlılıklarına sahip olmayan
* Dış SQL Server Analysis Services veri kaynağına yönelik bir canlı bağlantıya sahip olan
* PowerPivot veri modeline sahip olan

### <a name="support-for-new-table-and-matrix-visuals"></a>Yeni tablo ve matris görselleri için destek

Power BI Rapor Sunucusu artık yeni Power BI tablo ve matris görsellerini desteklemektedir. Bu görsellerle rapor oluşturmak için Power BI Desktop uygulamasının Ekim 2017 sürümünü kullanmanız gerekir. Bu sürümü Power BI Desktop (Haziran 2017) yan yana yükleyebilirsiniz. Power BI Desktop uygulamasının en güncel sürümü için [Power BI Rapor Sunucusu indirme sayfasında](https://powerbi.microsoft.com/report-server/) **Gelişmiş indirme seçenekleri**'ne tıklayın.

## <a name="june-2017"></a>Haziran 2017

* Power BI Rapor Sunucusu genel kullanıma (GA) sunuldu.

## <a name="may-2017"></a>Mayıs 2017

* Power BI Rapor Sunucusu Önizleme kullanıma sunuldu
* Power BI raporlarını şirket içi ortamda yayımlama olanağı
  * Özel görseller için destek
  * Daha fazla veri kaynağı için **Analysis Services canlı bağlantı** desteği yakında kullanıma sunulacaktır.
  * Power BI Mobil uygulaması Power BI Rapor Sunucusu'nda barındırılan Power BI raporlarını görüntüleyecek şekilde güncelleştirildi
* Yorumlar eklenerek raporlardaki işbirliği özellikleri geliştirildi

## <a name="next-steps"></a>Sonraki adımlar

Power BI Rapor Sunucusu'ndaki yeni özelliklerden sürekli olarak haberdar olmak için bu kaynakları kontrol edin.

* [Microsoft Power BI Blog (Microsoft Power BI Blogu)](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services Team Blog (SQL Server Reporting Services Ekip Blogu)](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Guy in a Cube YouTube kanalı](https://aka.ms/guyinacube)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
