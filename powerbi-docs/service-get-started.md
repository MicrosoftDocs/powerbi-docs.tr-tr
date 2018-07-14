---
title: Power BI hizmeti (Power BI çevrimiçi) ile çalışmaya başlama
description: Power BI çevrimiçi (app.powerbi.com) ile çalışmaya başlama
author: adamw
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/22/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: 1c4f710cd048fc2c2828f0386d23328c164bb3fb
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37598679"
---
# <a name="tutorial-get-started-with-power-bi-service-apppowerbicom"></a>Öğretici: Power BI hizmeti (app.powerbi.com) ile çalışmaya başlama
Bu eğitim, ***Power BI hizmeti*** ile çalışmaya başlamanıza yardımcı olur. Power BI hizmetinin, diğer Power BI teklifleri ile nasıl bir uyum içinde çalıştığını anlamanız için ilk olarak [Power BI nedir?](power-bi-overview.md) makalesini okumanızı öneririz.

![Desktop, hizmet, mobil arasındaki ilişkiyi gösteren resim](media/service-get-started/power-bi-components.png)

Bu öğreticide aşağıdaki adımları tamamlarsınız:

> [!div class="checklist"]
> * Power BI hizmetine yönelik diğer başlangıç içeriğini bulun
> * Power BI çevrimiçi hesabınızda oturum açma veya Power BI hesabınız yoksa, Power BI hesabına kaydolma
> * Power BI hizmetini açma
> * Bazı verileri alma ve rapor görünümünde açma
> * Bu verileri kullanarak görselleştirmeler oluşturma ve bunları rapor olarak kaydetme
> * Rapordan kutucukları sabitleyerek bir pano oluşturma
> * Soru-Cevap doğal dil aracını kullanarak panonuza başka görselleştirmeler ekleme
> * Veri kümesini, raporu ve panoyu silerek kaynakları temizleme

## <a name="sign-up-for-power-bi-service"></a>Power BI hizmetine kaydolma
Power BI'a kaydolmadıysanız başlamadan önce [ücretsiz Power BI Pro denemesine](https://app.powerbi.com/signupredirect?pbi_source=web) kaydolun.

Zaten hesabınız varsa, tarayıcı penceresi açıp app.powerbi.com adresini girerek Power BI hizmetini açın. 

![Oturum açma veya ücretsiz kaydolma](media/service-get-started/power-bi-sign-up.png)

Power BI Desktop ile ilgili yardım almak isterseniz bkz. [Desktop ile çalışmaya başlama](desktop-getting-started.md). Power BI Mobil ile ilgili yardım almak isterseniz bkz. [Mobil cihazlar için Power BI uygulamaları](mobile-apps-for-mobile-devices.md).

> [!TIP]
> Bunun yerine kendi kendinize ilerleyebileceğiniz ücretsiz bir eğitim almayı mı tercih edersiniz? [EdX'teki Analyzing and Visualizing Data (Verileri Çözümleme ve Görselleştirme) kursumuza kaydolun](http://aka.ms/edxpbi).

[YouTube'daki oynatma listemizi](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP) ziyaret edin. Introduction to Power BI service (Power BI hizmetine giriş) başlangıç için uygun bir videodur:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 

## <a name="what-is-power-bi-service"></a>Power BI hizmeti nedir?
Microsoft Power BI hizmeti bazen Power BI çevrimiçi veya app.powerbi.com olarak da adlandırılır. Power BI, önem verdiğiniz bilgileri edinmenize ve her zaman en güncel bilgilere sahip olmanıza yardımcı olur.  Power BI hizmetindeki ***panolar***, işletmenizin nabzını tutmanıza yardımcı olur.  Panolarınızda görüntülenen ***kutucuklara*** tıkladığınızda ***raporlar*** açılır ve böylece daha fazla araştırma yapabilirsiniz.  Birden çok ***veri kümesine*** bağlanarak tüm ilgili verileri bir yerde toplayın. Power BI'ı oluşturan yapı taşlarını anlamak için yardıma mı ihtiyacınız var?  Bkz. [Power BI - Temel Kavramlar](service-basic-concepts.md).

Excel veya CSV dosyalarında önemli verileriniz varsa, bilgilere her yerden erişmek ve öngörülerinizi başkalarıyla paylaşmak için bir Power BI panosu oluşturabilirsiniz.  Salesforce gibi bir SaaS uygulaması aboneliğiniz var mı?  Salesforce'a bağlanıp ilgili verilerden otomatik olarak bir pano oluşturarak başlayın veya bağlanabileceğiniz [diğer tüm SaaS uygulamalarına göz atın](service-get-data.md). Bir kuruluşa bağlıysanız sizin için yayımlanan herhangi bir [uygulama](service-create-distribute-apps.md) olup olmadığına bakın.

[Power BI'a veri almak](service-get-data.md) için kullanabileceğiniz diğer tüm yöntemlerle ilgili bilgi edinin.

## <a name="step-1-get-data"></a>1. Adım: Veri alma
Aşağıda, CSV dosyasından veri almaya ilişkin bir örnek verilmiştir. Bu eğitimle birlikte ilerlemek ister misiniz? [Bu örnek CSV dosyasını indirin](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Power BI'da oturum açın](http://www.powerbi.com/). Hesabınız yok mu? Endişelenmeyin, ücretsiz denemeye kaydolabilirsiniz.
2. Power BI, tarayıcınızda açılır. Sol gezinti çubuğunun alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![veri al](media/service-get-started/getdata3.png)
3. **Dosyalar**'ı seçin. 
   
   ![dosya alma](media/service-get-started/gs1.png)
4. Bilgisayarınızda dosyanın bulunduğu konuma gidin ve **Aç** düğmesini seçin. Dosyayı OneDrive İş'e kaydettiyseniz bu seçeneği belirleyin. Yerel ortama kaydettiyseniz **Yerel dosya**'yı seçin. 
   
   ![Veri Al > Dosyalar ekranı](media/service-get-started/gs2.png)
5. Bu eğitimde; Excel dosyasını, raporlar ve panolar oluşturmak için kullanabileceğimiz bir veri kümesi olarak eklemek için **İçeri aktar** seçeneğini belirleyeceğiz. **Karşıya yükle** seçeneğini belirlerseniz Excel çalışma kitabının tamamı Power BI'a yüklenir. Daha sonra çalışma kitabını Excel Online'da açıp düzenleyebilirsiniz.
   
   ![içe aktar seçeneğini belirleme](media/service-get-started/power-bi-import.png)
6. Veri kümeniz hazır olduğunda, **Veri kümesini görüntüle**'yi seçerek veri kümesini rapor düzenleyicisinde açın. 

    ![Veri kümeniz hazır iletişim kutusu](media/service-get-started/power-bi-gs.png)

    Henüz görselleştirme oluşturmadığımız için tuval boş olacaktır.

    ![boş rapor tuvali](media/service-get-started/power-bi-report-editor.png)

6. Üstteki menü çubuğuna baktığınızda **Okuma görünümü** seçeneğini göreceksiniz. Okuma görünümü seçeneğinin görünmesi, **Düzenleme görünümü**'nün etkin olduğunu gösterir. 

    ![Okuma görünümü seçeneği](media/service-get-started/power-bi-editing-view.png)

    Düzenleme görünümü'nde raporun *sahibi*, içerik *oluşturan* olduğunuz için rapor oluşturabilir ve değiştirebilirsiniz. Raporunuzu paylaştığınızda iş arkadaşlarınız *tüketici* olarak raporla yalnızca Okuma görünümü'nde etkileşim kurabilir. [Okuma görünümü ve Düzenleme görünümü](service-reading-view-and-editing-view.md) hakkında daha fazla bilgi edinin.
    
    Rapor düzenleyicisi ile ilgili bilgi edinmenin en iyi yollarından biri de [tura katılmaktır](service-the-report-editor-take-a-tour.md)
   > 
 

## <a name="step-2-start-exploring-your-dataset"></a>2. Adım: Veri kümenizi araştırmaya başlama
Verilere bağlandığınıza göre keşfetmeye başlayabilirsiniz.  İlginizi çeken bir öğe bulduğunuzda izlemek ve zaman içindeki değişimini görmek için pano oluşturabilirsiniz. Şimdi bunun nasıl çalıştığına bakalım.
    
1. Rapor düzenleyicisinde sayfanın sağ tarafındaki **Alanlar** bölmesini kullanarak bir görselleştirme oluşturacağız.  **Gross Sales** ve **Date** alanlarının yanındaki onay kutusunu işaretleyin.
   
   ![Alanlar listesi](media/service-get-started/fields.png)

2. Power BI, verileri çözümler ve bir görselleştirme oluşturur.  İlk olarak **Date**'i seçtiyseniz bir tablo görürsünüz.  **Gross Sale**'i daha önce seçtiyseniz bir grafik görüntülenir. Verilerinizi farklı şekillerde görüntüleyin. Şimdi bu verilere çizgi grafik üzerine göz atalım. **Görsel öğeler bölmesinden** çizgi grafik simgesini (şablon olarak da bilinir) seçin.
   
   ![simgenin seçili olduğu rapor düzenleyicisi](media/service-get-started/gettingstart5new.png)

3. Veriler ilginç görünüyor, bunu bir panoya *sabitleyelim*. Görselleştirmenin üzerine gelin ve **Raptiye** simgesini seçin.  Görselleştirme sabitlendiğinde panonuzda depolanır ve güncelleştirilir. Böylece, en güncel değerleri bir bakışta izleyebilirsiniz.
   
   ![raptiye simgesi](media/service-get-started/pinnew.png)

4. Bu yeni bir rapor olduğundan, görselleştirmeyi panoya sabitleyebilmeniz için öncelikle raporu kaydetmeniz istenir. Raporunuza bir ad verin (ör. *Sales over time*), ardından **Kaydet ve Devam Et**'i seçin. 
   
   ![Raporu kaydet iletişim kutusu](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
5. Şimdi çizgi grafiği yeni panoya sabitleyip "Financial sample for tutorial" adını verelim. 
   
   ![raporu adlandırma](media/service-get-started/power-bi-pin.png)
   
1. **Sabitle**'yi seçin.
   
    Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.
   
    ![Panoya sabitlendi iletişim kutusu](media/service-get-started/power-bi-pin-success.png)

6. **Panoya git**'i seçtiğinizde çizgi grafiğin yeni panonuza kutucuk olarak sabitlendiğini görebilirsiniz. Daha fazla görselleştirme kutucuğu ekleyip [kutucukları yeniden adlandırma, yeniden boyutlandırma, bağlantılı hale getirme ve yeniden konumlandırma](service-dashboard-edit-tile.md) yoluyla panonuzu iyileştirin.
   
   ![Görselleştirmenin sabitlendiği pano](media/service-get-started/power-bi-new-dashboard.png)
   
   İstediğiniz zaman rapora geri dönmek için panonuzdaki yeni kutucuğu seçin. Power BI rapor düzenleyicisi Okuma görünümü'nde açılır. Düzenleme görünümü'ne geçmek için üst menü çubuğundan **Raporu düzenle**'yi seçin. Düzenleme görünümü'ne geçtikten sonra kutucukları keşfetmeye ve sabitlemeye devam edin. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>3. Adım: Soru-Cevap ile araştırmaya devam etme (doğal dil sorgusu)
1. Verilerinizi hızla araştırmak için Soru-Cevap kutusunda soru sormayı deneyin. Soru-Cevap soru kutusu panonuzun en üstünde (**Verileriniz hakkında soru sorun** ) ve raporunuzun üstündeki menü çubuğunda (**Bir soru sorun**) yer alır. Örneğin, "what segment had the most revenue" (en çok gelir elde eden segment) yazın.
   
   ![Soru-Cevap tuvali](media/service-get-started/powerbi-qna.png)

2. Soru-Cevap yanıt arar ve görselleştirme biçiminde sunar. Bu görselleştirmenin panonuzda da gösterilmesi için raptiye simgesini ![raptiye simgesi](media/service-get-started/pbi_pinicon.png) seçin.
3. Görselleştirmeyi "Financial Sample for tutorial" panosuna sabitleyin.
   
    ![Panoya sabitle iletişim kutusu](media/service-get-started/power-bi-pin2.png)

4. Panonuza döndüğünüzde yeni kutucuğu görebilirsiniz.

   ![grafiğin sabitlendiği pano](media/service-get-started/power-bi-final-dashboard.png)

## <a name="clean-up-resources"></a>Kaynakları temizleme
Öğreticiyi bitirdiğinize göre şimdi veri kümesini, raporu ve panoyu silebilirsiniz. 

1. Sol gezinti çubuğundan **Çalışma Alanım**’ı seçin.
2. **Veri Kümeleri** sekmesini seçin ve bu öğretici için içeri aktardığınız veri kümesini bulun.  
3. Üç noktayı (...) > **Sil**'i seçin.

    ![Veri kümesini silme](media/service-get-started/power-bi-delete.jpg)

    Veri kümesinin silinmesiyle, rapor ve pano da silinir. 


## <a name="next-steps"></a>Sonraki adımlar
Daha fazlasını denemeye hazır mısınız?  Power BI ile ilgili keşif yapmak için uygulayabileceğiniz bazı harika yöntemler.

> [!div class="nextstepaction"]
> [Kullandığınız çevrimiçi hizmetlere bağlanma](./service-connect-to-services.md)

