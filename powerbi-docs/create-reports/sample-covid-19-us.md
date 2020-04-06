---
title: ABD eyalet ve yerel hükümetlere yönelik COVID-19 izleme örneği
description: ABD eyalet ve yerel hükümetlerinin verilerini içeren örnek raporu indirip COVID-19 pandemisine uygun şekilde değiştirin.
author: LukaszPawlowski-MS
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/31/2020
ms.author: lukaszp
LocalizationGroup: Samples
ms.openlocfilehash: 432312b5ceb7632e0249d1d7dda6158bf97d0224
ms.sourcegitcommit: 3c51431d85793b71f378c4b0b74483dfdd8411b3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/31/2020
ms.locfileid: "80472072"
---
# <a name="covid-19-tracking-sample-for-us-state-and-local-governments"></a>ABD eyalet ve yerel hükümetlere yönelik COVID-19 izleme örneği

Power BI ekibi, ABD eyalet ve yerel hükümetlerinin COVID-19 hakkında etkileşimli bir rapor yayımlayıp özelleştirmesine olanak veren bir COVID-19 izleme örneği oluşturdu. Hükümetler Power BI Desktop kullanarak COVID-19 verilerini analiz edip görselleştirebilir ve bu sayede topluluklarının şehir, ilçe, eyalet ve ulusal düzeyde bilgilendirebilirler. Ardından Power BI - Web’de Yayımlama özelliğini kullanarak vatandaşları bilgilendirmek amacıyla raporu herkese açık bir şekilde paylaşabilirler. Bu makalede, Power BI etkileşimli görselleştirmeleri herkese ait hikayeniz, blogunuz veya web sitenizde kullanmaya yönelik üç farklı seçenek sunulmaktadır.

:::image type="content" source="media/sample-covid-19-us/covid-19-us-tracking-sample.png" alt-text="ABD verilerini içeren COVID-19 örneği":::

Bu makalede şunları nasıl yapılacağı ele alınır:

- Ekleme kodunu kopyalayıp kendi sitenize koyma. 
- Belirli bir eyaleti biçimlendirme gibi özelleştirmeler yapma.
- Power BI hizmetinde yayımlama.
- Web’de yayımlama. 
- Başka bir kaynaktan toplanan verileri bu verilerle birleştirme. 

## <a name="prerequisites"></a>Önkoşullar

Hikayenizi anlatmak için Power BI’ı kullanmaya başlamadan önce şu önkoşulları sağlamanız gerekir:

- Ücretsiz [Power BI Desktop](https://powerbi.microsoft.com/desktop/) uygulamasını indirme.
- [Power BI hizmetine](https://powerbi.microsoft.com/get-started/) kaydolma.

## <a name="option-1-pre-built-embed-code"></a>1\. Seçenek: Önceden oluşturulmuş ekleme kodu

Microsoft örnek raporu yayımladı ve web’de yayımlamaya yönelik bir ekleme kod oluşturdu. Ulusal görünüm dahil olmak üzere örneğin tamamını eklemek için ekleme kodunu kullanabilir ve kendi web sitenizde eyalet ve ilçe düzeyinde ayrıntıya inebilirsiniz. Bu verileri yayımlamadan önce, bu makaledeki [sorumluluk reddini](#disclaimers) gözden geçirmenizi öneririz.

Sitenize etkileşimli grafikleri dahil etmek için, şu ekleme kodunu kopyalayıp grafiğin web sayfanızda görüntülenmesini istediğiniz yere yapıştırın.  

```
<iframe width="800" height="600" src="https://app.powerbi.com/view?r=eyJrIjoiMmI2ZjExMzItZTcwNy00YmUwLWFlMTAtYTUxYzVjODZmYjA5IiwidCI6ImMxMzZlZWMwLWZlOTItNDVlMC1iZWFlLTQ2OTg0OTczZTIzMiIsImMiOjF9" frameborder="0" allowFullScreen="true"></iframe>
```

Ekleme kodu, tüm HTML sayfalarına ekleyebileceğiniz bir HTML iFrame öğesidir. Sağlanan iFrame’in genişliğini ve yüksekliğini web sitenize sığacak şekilde ayarlayın. Örnek rapor 16:9 bölümler halinde yazılır, bu boyutu uygun bir seçim yapın. Doğru şekilde uygulandığında, grafikler ek gri kenarlıklar olmadan görünür. Bu değişiklikleri yaparken [iFrame boyutlandırmasına yönelik ipuçlarını ve püf noktalarını gözden geçirmeniz](https://docs.microsoft.com/power-bi/service-publish-to-web#tips-and-tricks-for-iframe-height-and-width) yararlı olur.

## <a name="option-2-customize-the-sample-power-bi-file"></a>2\. Seçenek: Örnek Power BI dosyasını özelleştirme

Power BI dosyası, Power BI Desktop’ta düzenleyebileceğiniz verileri ve etkileşimli grafiği .pbix dosya biçiminde içerir.  

Tipik özelleştirme, raporu belirli bir duruma filtreleme ve sonra özelleştirilmiş raporunuz için kendi web’de yayımlamaya yönelik ekleme kodunuzu oluşturmaktır.

USAFacts verileri, atıf gerektiren bir Creative Commons License kapsamında sunulur. Bu verileri yayımlamadan önce [sorumluluk reddini](#disclaimers) gözden geçirin.

Çalışmaya başlamak için [.pbix dosyasını (buradan) indirin](https://go.microsoft.com/fwlink/?linkid=2125058).

### <a name="update-your-report"></a>Raporunuzu güncelleştirme 

1. Henüz indirmediyseniz ücretsiz [Power BI Desktop](https://powerbi.microsoft.com/desktop/) uygulamasının en son sürümünü indirin. 

2. Henüz indirmediyseniz [.pbix dosyasını](https://go.microsoft.com/fwlink/?linkid=2125058) indirip Power BI Desktop’ta açın.

3. Raporunuzu belirli bir duruma filtrelemek için genişletme okunu seçerek Filtreler bölmesini genişletin.

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-filters-pane.png" alt-text="Filtreler bölmesini genişletme":::

4. İlgilendiğiniz bir durumu seçin. 

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-filter-selection.png" alt-text="Durum seçme":::

5. Dosyanızı kaydetmek için **Dosya** > **Kaydet**’e tıklayın. 

### <a name="refresh-your-report"></a>Raporunuzu yenileme 

1. **Yenile** düğmesini seçin.

    :::image type="content" source="media/sample-covid-19-us/power-bi-desktop-refresh-button.png" alt-text="Yenile düğmesi":::

2. **Anonim** > **Bağlan**’ı seçin. 

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-azure-blob.png" alt-text="Anonimi seçme":::

 
3. **Gizlilik Düzeylerini Yoksay**’ı seçin, ardından gösterilirse **Kaydet**’i seçin. 

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-privacy-levels.png" alt-text="Gizlilik düzeylerini seçme":::

### <a name="publish-your-report-to-the-power-bi-service"></a>Raporunuzu Power BI hizmetinde yayımlama

Raporunuzu dilediğiniz şekilde özelleştirdikten sonra, [raporunuzu Power BI hizmetinde yayımlamak için burada özetlenen adımları izleyin](../desktop-upload-desktop-files.md).

### <a name="configure-scheduled-refresh"></a>Zamanlanmış yenileme yapılandırma

Rapordaki verileri güncel tutmak için, raporunuzu yayımladıktan sonra [zamanlanmış yenileme yapılandırabilirsiniz](../refresh-scheduled-refresh.md).

Adımları izlerken şu seçenekleri belirleyin:

1. Veri Kaynağı Kimlik Bilgileri Kimlik Doğrulaması Yöntemi: Anonim
2. Bu veri kaynağına ilişkin gizlilik düzeyi ayarı: Genel

Yenileme ayarınızı test etmek için, [Veri kümesi öğesindeki Şimdi Yenile seçeneğini](../refresh-data.md#data-refresh) belirleyin.

Yenileme verileri, zamanlama her çalıştığında yüklenir. Temel alınan verilerin USAFacts tarafından sağlandığını ve zamanlamanızı yenilediğiniz sıklıkta güncelleştirilmeyebileceğini unutmayın. Sağlanan verilerin en son ne zaman güncelleştirildiğini öğrenmek için [USAFacts web sitesine](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/) göz atın. 

Özelleştirilmiş raporu web sitenizde yayımlamak istiyorsanız zamanlanmış yenilemenizi USAFacts veri güncelleştirmeleriyle aynı sıklıkta olacak şekilde yapılandırmak en iyisidir. USAFacts, verilerini her gün farklı zamanlarda yenileyeceğinden her gün birkaç yenileme yapılandırmanız gerekebilir. 

### <a name="create-a-publish-to-web-embed-code"></a>Web’de yayımlama ekleme kodu oluşturma 

Özelleştirilmiş raporunuzu kendi web sitenize eklemek için [Kendi web’de yayımlama ekleme kodunuzu oluşturmaya](../service-publish-to-web.md#how-to-use-publish-to-web) yönelik yönergeleri izleyin.

Ekleme kodunuzu yayımladıktan sonra, web sitenize eklemek için onay iletişim penceresindeki iFrame’i kullanırsınız.

Power BI Desktop’taki raporda değişiklik yaparsanız raporu yayımlayabilir ve Power BI hizmetindeki mevcut raporla değiştirebilirsiniz. Ekleme kodu değişmez. Raporda veya yenilenen verilerde yapılan değişikliklerin web sitenizde görüntülenmesi yaklaşık bir saat sürer. 

## <a name="option-3-mash-up-data-from-another-source"></a>3\. Seçenek: Başka bir kaynaktan veriler toplama 

Ayrıca, bu rapordaki verileri başka bir kaynaktan alınan verilerle de birleştirebilirsiniz. Aşağıdaki örnek [Johns Hopkins Üniversitesi](https://github.com/CSSEGISandData/COVID-19) verileri temel alınarak oluşturulmuştur. Bu verileri yayımlamadan önce, bu makaledeki [sorumluluk reddini](#disclaimers) gözden geçirmenizi öneririz.

1. **Veri Al** > **Web**’i seçin.

    :::image type="content" source="media/sample-covid-19-us/power-bi-desktop-get-data.png" alt-text="Veri al düğmesi":::

2. Şu URL’yi girin:

    ```
    https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv
    ```

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-from-web.png" alt-text="Web'den veri al":::

3. **Tamam**’ı seçin. 

    > [!NOTE]
    > Johns Hopkins Üniversitesi tarafından yayımlanan bağlantı değişebilir. En son bilgileri almak için [Johns Hopkins GitHub sayfasını](https://github.com/CSSEGISandData/COVID-19) ziyaret edin.

4. Dünya genelinde toplam onaylanmış vaka sayısına ilişkin veri kümesini yüklemek için **Yükle**’yi seçin.  

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-load-data.png" alt-text="Web’den veri yükleme":::

    [Power BI Desktop’tan web sayfalarına bağlanma](../desktop-connect-to-web.md) adlı bu makalede web’den veri yükleme hakkında daha fazla bilgi sağlanır.
    
Daha sonra Power BI Desktop kullanarak verileri görselleştirebilirsiniz. Son olarak, **2. Seçenek**’teki adımları kullanın: Raporu yayımlayıp özel bir ekleme kodu oluşturmak için [raporunuzu Power BI hizmetinde yayımlayın](#publish-your-report-to-the-power-bi-service). 


## <a name="about-the-data-source-for-this-report"></a>Bu raporun veri kaynağı hakkında
Bu etkileşimli raporda, ABD Hastalık Kontrol ve Korunma Merkezleri’nden (Centers for Disease Control and Prevention, CDC) ve eyalet/yerel hükümet düzeyinde genel sağlık kurumlarından alınan veriler toplanmıştır. İlçe düzeyinde veriler, başvurulan eyalet ve yerel sağlık kurumları tarafından onaylanmıştır (bağlantı).

Veriler, USAFacts tarafından sağlanır. Veriler sıkça güncelleştirildiğinden, kamu kurumları veya haber yayın organları tarafından bildirilen tam sayıları yansıtmayabilir. Daha fazla bilgi edinmek veya verileri indirmek için [USAFacts web sitesini](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/) ziyaret edin. 

## <a name="disclaimers"></a>Bildirimler

Bu rapor ve veriler “olduğu gibi”, “tüm hatalarıyla birlikte” ve herhangi bir garanti sunulmadan sağlanmaktadır. Microsoft hiçbir açık garanti sunmaz ve satılabilirlik, belirli bir amaca uygunluk ve hak ihlali bulunmaması dahil olmak üzere tüm zımni garantileri açık bir şekilde reddeder.

USAFacts verileri bir Creative Commons lisansı kapsamında sunulur. Bu verileri kullanmak için USAFacts’i veri sağlayıcısı olarak tanımlayın ve USAFacts’e geri bağlantı oluşturun. Atıf adımlarının tamamı için USAFacts sayfasının **#MadewithUSAFacts**, [Coronavirus in the United States: Mapping the COVID-19 outbreak in the states and counties](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/).

Johns Hopkins University data is copyright 2020 Johns Hopkins University, all rights reserved (Amerika Birleşik Devletleri’nde Koronavirüs: Eyalet ve ilçelerde COVID-19 salgınını eşleme. John Hopkins Üniversitesi verileri, Telif Hakkı 2020 Johns Hopkins Üniversitesi, tüm hakları saklıdır.) bölümüne bakın. Bu veriler, yalnızca eğitim ve akademik araştırma amacıyla herkese açık bir şekilde sunulmuştur. Toplama örneğinde gösterilen verilerin [Kullanım Koşulları](https://github.com/CSSEGISandData/COVID-19/blob/master/README.md)’nın tamamına buradan ulaşabilirsiniz. Daha fazla bilgi için [Johns Hopkins Üniversitesi web sitesini](https://coronavirus.jhu.edu/map-faq.html) ziyaret edin.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI için örnek alma](../sample-datasets.md)