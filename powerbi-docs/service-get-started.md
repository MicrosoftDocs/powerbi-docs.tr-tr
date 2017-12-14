---
title: "Power BI hizmeti ile çalışmaya başlama"
description: "Power BI hizmeti ile çalışmaya başlama"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: B2vd4MQrz4M
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/31/2017
ms.author: mihart
ms.openlocfilehash: 6714283ea4590ac9c2f3728121e05d03d4aa646e
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="get-started-with-power-bi-service"></a>Power BI hizmeti ile çalışmaya başlama
Bu eğitim, ***Power BI hizmeti*** ile çalışmaya başlamanıza yardımcı olur. Power BI hizmetinin, diğer Power BI teklifleri ile nasıl bir uyum içinde çalıştığını anlamanız için ilk olarak [Power BI nedir?](guided-learning/gettingstarted.yml#step-1) makalesini okumanızı öneririz.

![](media/service-get-started/power-bi-components.png)

Power BI hizmetinin ücretsiz ve Pro sürümleri mevcuttur. Hangi sürümü kullanırsanız kullanın, çalışmaya başlamak için bir tarayıcıyı açıp www.powerbi.com yazmanız yeterli. Zaten kaydolduysanız sağ üst köşedeki **Oturum aç** bağlantısını seçin. Power BI hizmetine henüz kaydolmadıysanız bunun yerine **Sign up free** (Ücretsiz kaydolun) bağlantısını seçin.

![](media/service-get-started/power-bi-sign-up.png)

Power BI Desktop ile ilgili yardım almak isterseniz bkz. [Desktop ile çalışmaya başlama](desktop-getting-started.md). Power BI Mobil ile ilgili yardım almak isterseniz bkz. [Mobil cihazlar için Power BI uygulamaları](mobile-apps-for-mobile-devices.md).

> [!TIP]
> Bunun yerine kendi kendinize ilerleyebileceğiniz ücretsiz bir eğitim almayı mı tercih edersiniz? [EdX'teki Analyzing and Visualizing Data (Verileri Çözümleme ve Görselleştirme) kursumuza kaydolun](http://aka.ms/edxpbi).

[YouTube'daki oynatma listemizi](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP) ziyaret edin. Introduction to Power BI service (Power BI hizmetine giriş) başlangıç için uygun bir videodur:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 
> 
> 

Microsoft Power BI, önem verdiğiniz bilgileri edinmenize ve her zaman en güncel bilgilere sahip olmanıza yardımcı olur.  Power BI hizmetindeki ***panolar***, işletmenizin nabzını tutmanıza yardımcı olur.  Panolarınızda görüntülenen ***kutucuklara*** tıkladığınızda ***raporlar*** açılır ve böylece daha fazla araştırma yapabilirsiniz.  Birden çok ***veri kümesine*** bağlanarak tüm ilgili verileri bir yerde toplayın. Power BI'ı oluşturan yapı taşlarını anlamak için yardıma mı ihtiyacınız var?  Bkz. [Power BI - Temel Kavramlar](service-basic-concepts.md).

Excel veya CSV dosyalarında önemli verileriniz varsa, bilgilere her yerden erişmek ve öngörülerinizi başkalarıyla paylaşmak için bir Power BI panosu oluşturabilirsiniz.  Salesforce gibi bir SaaS uygulaması aboneliğiniz var mı?  [Salesforce'a bağlanıp](service-connect-to-salesforce.md) ilgili verilerden otomatik olarak bir pano oluşturarak başlayın veya bağlanabileceğiniz [diğer tüm SaaS uygulamalarına göz atın](service-get-data.md). Bir kuruluşa bağlıysanız sizin için yayımlanan herhangi bir [uygulama](service-create-distribute-apps.md) olup olmadığına bakın.

[Power BI'a veri almak](service-get-data.md) için kullanabileceğiniz diğer tüm yöntemlerle ilgili bilgi edinin.

## <a name="step-1-get-data"></a>1. Adım: Veri alma
Aşağıda, CSV dosyasından veri almaya ilişkin bir örnek verilmiştir. Bu eğitimle birlikte ilerlemek ister misiniz? [Bu örnek CSV dosyasını indirin](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Power BI'da oturum açın](http://www.powerbi.com/). Hesabınız yok mu? Endişelenmeyin, ücretsiz kaydolabilirsiniz.
2. Power BI, tarayıcınızda açılır. Sol gezinti bölmesinin alt kısmındaki **Veri Al**'ı seçin.
   
   ![](media/service-get-started/getdata3.png)
3. **Dosyalar**'ı seçin. 
   
   ![](media/service-get-started/gs1.png)
4. **Yerel Dosya** seçeneğini belirleyin, bilgisayarınızda dosyanın bulunduğu konuma gidin ve **Aç** düğmesini seçin.
   
   ![](media/service-get-started/gs2.png)
5. Bu eğitimde; Excel dosyasını, raporlar ve panolar oluşturmak için kullanabileceğimiz bir veri kümesi olarak eklemek için **İçeri aktar** seçeneğini belirleyeceğiz.  
   
   > [!NOTE]
   > **Karşıya yükle** seçeneğini belirlerseniz Excel çalışma kitabının tamamı Power BI'a yüklenir. Daha sonra çalışma kitabını Excel Online'da açıp düzenleyebilirsiniz.
   > 
   > 
   
   ![](media/service-get-started/power-bi-import.png)
6. Veri kümeniz hazır olduğunda, **Veri kümesini görüntüle**'yi seçerek veri kümesini rapor düzenleyicisinde açın. ![](media/service-get-started/power-bi-gs.png).
   
   > [!TIP]
   > Rapor düzenleyicisi ile ilgili bilgi edinmenin en iyi yollarından biri de [tura katılmaktır](service-the-report-editor-take-a-tour.md)
   > 
   > 

## <a name="step-2-start-exploring-your-dataset"></a>2. Adım: Veri kümenizi araştırmaya başlama
Artık verilere bağlı olduğunuza göre öngörüler elde etmek için araştırmaya başlayabilirsiniz.  İzlemek istediğiniz bir veri bulduğunuzda değişiklikleri takip etmek için bir pano oluşturabilirsiniz.

1. Bağlandığınız verileri araştırmak için panodaki veri kümesi resmini seçin veya **Veri kümeleri** bölümünde veri kümesi adını seçip veri kümesini açın. Bu işlemin ardından veri kümesi, boş bir rapor olarak açılır.
   
   ![](media/service-get-started/power-bi-report-editor.png)
   
   > [!NOTE]
> Verileri araştırmanın diğer bir yolu da **Hızlı Öngörüler**'dir.  Daha fazla bilgi için bkz. [Hızlı Öngörüler'e Giriş](service-insights.md)
   > 
   > 
2. Bir görselleştirme oluşturmak için sayfanın sağ tarafındaki **Alanlar** listesinden alan seçin.  **Gross Sales** ve **Date** alanlarının yanındaki onay kutusunu işaretleyin.
   
   ![](media/service-get-started/fields.png)
3. Power BI, verileri çözümler ve bir görsel oluşturur.  İlk olarak **Date**'i seçtiyseniz bir tablo görürsünüz.  **Gross Sale**'i daha önce seçtiyseniz bir grafik görüntülenir. Verilerinizi farklı şekillerde görüntüleyin. Çizgi grafik seçeneğini belirleyerek görselleştirmenizi bir çizgi grafiğe dönüştürün.
   
   ![](media/service-get-started/gettingstart5new.png)
4. Panonuzda olmasını istediğiniz bir görselleştirme varsa görselleştirmenin üzerine gelerek **Raptiye** simgesini seçin.  Görselleştirme sabitlendiğinde panonuzda depolanır. Böylece, en güncel değerleri bir bakışta izleyebilirsiniz.
   
   ![](media/service-get-started/pinnew.png)
5. Bu yeni bir rapor olduğundan, rapordaki bir görselleştirmeyi panoya sabitleyebilmeniz için öncelikle raporu kaydetmeniz gerekir. Raporunuza bir ad verin (ör. *Sales Over Time*), ardından **Kaydet ve Devam Et**'i seçin. 
   
   ![](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
   Yeni rapor, gezinti bölmesindeki **Raporlar** bölümünde görünür.
6. Kutucuğu, var olan bir panoya veya yeni bir panoya sabitleyin. 
   
   ![](media/service-get-started/power-bi-pin.png)
   
   * **Var olan pano**: Açılan listeden panonun adını seçin.
   * **Yeni pano**: Yeni panonun adını girin.
7. **Raptiye** düğmesini seçin.
   
   Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.
   
   ![](media/service-get-started/power-bi-pin-success.png)
8. Sabitlenen kutucuğu içeren yeni panonuzu görmek için **Panoya git**'i seçin. Çizgi grafik bir kutucuk olarak panoya sabitlenmiştir. [Kutucukları yeniden adlandırma, yeniden boyutlandırma, bağlantılı hale getirme ve yeniden konumlandırma](service-dashboard-edit-tile.md) yoluyla panonuzu iyileştirin.
   
   ![](media/service-get-started/power-bi-new-dashboard.png)
   
   İstediğiniz zaman rapora geri dönmek için panonuzdaki yeni kutucuğu seçin.

## <a name="step-3-continue-exploring-with-qa-natural-language-querying"></a>3. Adım: Soru-Cevap ile araştırmaya devam etme (doğal dil sorgusu)
1. Verilerinizi hızla araştırmak için Soru-Cevap kutusunda soru sormayı deneyin. Soru-Cevap soru kutusu panonuzun en üstünde bulunur. Örneğin, "**what segment had the most revenue**" (en çok gelir elde eden segment) yazın.
   
   ![](media/service-get-started/powerbi-qna.png)
2. Bu görselleştirmeyi de panonuzda göstermek için raptiye simgesini ![](media/service-get-started/pbi_pinicon.png) seçin.
3. Görselleştirmeyi Financial Sample panosuna sabitleyin.
   
    ![](media/service-get-started/power-bi-pin2.png)
4. Yeni kutucuğu göreceğiniz panonuza geri dönmek için **Soru-Cevap'tan çık** geri okunu ![](media/service-get-started/pbi_qabackarrow.png) seçin.

## <a name="next-steps"></a>Sonraki adımlar
Daha fazlasını denemeye hazır mısınız?  Power BI ile ilgili daha fazla keşif yapmak için uygulayabileceğiniz bazı harika yöntemler:

* [Başka bir veri kümesine bağlanın](service-get-data.md).
* İş arkadaşlarınızla [panonuzu paylaşın](service-share-dashboards.md).
* [Pano tasarlamaya ilişkin ipuçlarını](service-dashboards-design-tips.md) okuyun.
* Panolarınızı [mobil cihazdaki bir Power BI uygulamasında](mobile-apps-for-mobile-devices.md) görüntüleyin.

Henüz hazır değil misiniz? Power BI ile kolayca çalışmanıza yardımcı olmak için tasarlanan şu konu başlıklarına göz atın:

* [Raporların, veri kümelerinin, panoların ve kutucukların nasıl bir uyum içinde çalıştığı hakkında bilgi edinin](service-basic-concepts.md)
* [Power BI videoları](videos.md)
* [Kullanımınıza sunulan örnek verilere bakın](sample-datasets.md)

### <a name="stay-in-touch-with-power-bi"></a>Power BI ile bağlantıda kalın
* [Twitter'da @MSPowerBI hesabını takip edin](https://twitter.com/mspowerbi)
* [YouTube video kanalımıza](https://www.youtube.com/channel/UCy--PYvwBwAeuYaR8JLmrfg) abone olun
* İsteğe bağlı olarak sunulan, [Power BI ile Çalışmaya Başlama web seminerlerimizi](webinars.md) izleyin
* Yardım için nereye başvuracağınızdan emin değil misiniz? [Yardım almaya yönelik 10 ipucu ](service-tips-for-finding-help.md) sayfamıza başvurun

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

