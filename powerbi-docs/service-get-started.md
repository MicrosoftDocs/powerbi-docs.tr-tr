---
title: Power BI hizmeti ile çalışmaya başlama
description: Power BI çevrimiçi hizmeti (app.powerbi.com) ile çalışmaya başlama
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2019
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 007819ead82f558efa8179a49dfba9454558dfbb
ms.sourcegitcommit: d12bc6df16be1f1993232898f52eb80d0c9fb04e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68995198"
---
# <a name="tutorial-get-started-with-the-power-bi-service-apppowerbicom"></a>Öğretici: Power BI hizmeti (app.powerbi.com) ile çalışmaya başlama
Bu eğitim, *Power BI hizmeti* ile çalışmaya başlamanıza yardımcı olur. Power BI hizmetinin, diğer Power BI teklifleriyle nasıl bir uyum içinde çalıştığını anlamanız için ilk olarak [Power BI nedir?](power-bi-overview.md) makalesini okumanızı öneririz.

![Power BI Desktop, hizmet ve mobil arasındaki ilişki](media/service-get-started/power-bi-components.png)

Bu öğreticide aşağıdaki adımları tamamlarsınız:

> [!div class="checklist"]
> * Power BI hizmetine yönelik başlangıç içeriğini bulun.
> * Power BI çevrimiçi hesabınızda oturum açın veya Power BI hesabınız yoksa Power BI hesabına kaydolun.
> * Power BI hizmetini açın.
> * Bazı verileri alın ve rapor görünümünde açın.
> * Bu verileri kullanarak görselleştirmeler oluşturun ve rapor olarak kaydedin.
> * Rapordan kutucukları sabitleyerek bir pano oluşturun.
> * Soru-Cevap doğal dil aracını kullanarak panonuza başka görselleştirmeler ekleyin.
> * Veri kümesini, raporu ve panoyu silerek kaynakları temizleyin.

## <a name="sign-up-for-the-power-bi-service"></a>Power BI hizmetine kaydolma
Bir Power BI hesabınız yoksa, başlamadan önce [ücretsiz Power BI Pro deneme sürümüne kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

Bir hesap oluşturduktan sonra, Power BI hizmetini açmak için tarayıcınızda *app.powerbi.com* adresini girin. 

Power BI Desktop ile ilgili yardım almak isterseniz bkz. [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md). Power BI Mobil ile ilgili yardım almak isterseniz bkz. [Mobil cihazlar için Power BI uygulamaları](consumer/mobile/mobile-apps-for-mobile-devices.md).

> [!TIP]
> Bunun yerine kendi kendinize ilerleyebileceğiniz ücretsiz bir eğitim almayı mı tercih edersiniz? [EdX'teki Analyzing and Visualizing Data (Verileri Çözümleme ve Görselleştirme) kursumuza kaydolun](http://aka.ms/edxpbi).

[YouTube'daki oynatma listemizi](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP) ziyaret edin. *Introduction to Power BI service* (Power BI hizmetine giriş) başlangıç için uygun bir videodur:
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 

## <a name="what-is-the-power-bi-service"></a>Power BI hizmeti nedir?
Microsoft Power BI hizmeti bazen Power BI çevrimiçi veya app.powerbi.com olarak da adlandırılır. Power BI, önem verdiğiniz bilgileri edinmenize ve her zaman en güncel bilgilere sahip olmanıza yardımcı olur. Power BI hizmetindeki *panolar*, işletmenizin nabzını tutmanıza yardımcı olur. Panolarınızda görüntülenen *kutucukları* seçtiğinizde *raporlar* açılır ve böylece daha fazla araştırma yapabilirsiniz. Birden çok *veri kümesine* bağlanarak tüm ilgili verileri bir yerde toplayın. Power BI'ın yapı taşlarını anlamak için yardıma mı ihtiyacınız var? Bkz. [Power BI hizmetinde tasarımcılar için temel kavramlar](service-basic-concepts.md).

Excel veya CSV dosyalarında önemli verileriniz varsa, bilgilere her yerden erişmek ve öngörülerinizi başkalarıyla paylaşmak için bir Power BI panosu oluşturabilirsiniz.  Salesforce gibi bir SaaS uygulaması aboneliğiniz var mı?  Salesforce'a bağlanıp ilgili verilerden otomatik olarak bir pano oluşturarak başlayın veya bağlanabileceğiniz [diğer tüm SaaS uygulamalarına göz atın](service-get-data.md). Bir kuruluşa bağlıysanız sizin için yayımlanan herhangi bir [uygulama](service-create-distribute-apps.md) olup olmadığına bakın.

[Power BI'a veri almak](service-get-data.md) için kullanabileceğiniz diğer tüm yöntemlerle ilgili bilgi edinin.

## <a name="step-1-get-data"></a>1\. Adım: Veri al
Aşağıda, CSV dosyasından veri almaya ilişkin bir örnek verilmiştir. Bu eğitimle birlikte ilerlemek ister misiniz? [Financial Sample CSV dosyasını indirin](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Power BI'da oturum açın](http://www.powerbi.com/). Hesabınız yok mu? Endişelenmeyin, ücretsiz denemeye kaydolabilirsiniz.
2. Power BI, tarayıcınızda açılır. Sol gezinti çubuğunun alt kısmında bulunan **Veri al**'ı seçin.

    **Veri Al** sayfası açılır.   

3. **Yeni içerik oluştur** bölümünde **Dosyalar**'ı seçin. 
   
   ![Dosya alma](media/service-get-started/gs1.png)
4.  **Yerel dosya**’yı seçin.
   
     ![Veri Al > Dosyalar ekranı](media/service-get-started/gs2.png)

5. Bilgisayarınızda dosyanın bulunduğu konuma gidin ve **Aç** düğmesini seçin.

5. Bu eğitimde; Excel dosyasını, raporlar ve panolar oluşturmak için kullanabileceğimiz bir veri kümesi olarak eklemek için **İçeri aktar** seçeneğini belirleyeceğiz. **Karşıya yükle** seçeneğini belirlerseniz Excel çalışma kitabının tamamı Power BI'a yüklenir. Daha sonra çalışma kitabını Excel Online'da açıp düzenleyebilirsiniz.
   
   ![İçeri Aktar seçeneğini belirleme](media/service-get-started/power-bi-import.png)
6. Veri kümeniz hazır olduğunda, **Veri kümesini görüntüle**'yi seçerek veri kümesini rapor düzenleyicisinde açın. 

    ![Veri kümeniz hazır iletişim kutusu](media/service-get-started/power-bi-gs.png)

    Henüz görselleştirme oluşturmadığımız için tuval boştur.

    ![Boş rapor tuvali](media/service-get-started/power-bi-report-editor.png)

7. Üst gezinti çubuğunda **Okuma görünümü** için bir seçenek olduğuna dikkat edin. Bu seçeneğe sahip olmanız şu anda Düzenleme görünümünde olduğunuz anlamına gelir. 

    ![Okuma görünümü seçeneği](media/service-get-started/power-bi-editing-view.png)

    Raporun *sahibi* olduğunuz için Düzenleme görünümünde rapor oluşturabilir ve değiştirebilirsiniz. Yani, bir *oluşturucu* olursunuz. Raporunuzu paylaştığınızda iş arkadaşlarınız *tüketici* olarak raporla yalnızca Okuma görünümü'nde etkileşim kurabilir. [Okuma görünümü ve Düzenleme görünümü](consumer/end-user-reading-view.md) hakkında daha fazla bilgi edinin.
    
    Rapor düzenleyicisi ile ilgili bilgi edinmenin en iyi yollarından biri de [tura katılmaktır](service-the-report-editor-take-a-tour.md).
 

## <a name="step-2-start-exploring-your-dataset"></a>2\. Adım: Veri kümenizi araştırmaya başlama
Verilere bağlandığınıza göre keşfetmeye başlayabilirsiniz.  İlginizi çeken bir öğe bulduğunuzda izlemek ve zaman içindeki değişimini görmek için pano oluşturabilirsiniz. Şimdi bunun nasıl çalıştığına bakalım.
    
1. Rapor düzenleyicisinde sayfanın sağ tarafındaki **Alanlar** bölmesini kullanarak bir görselleştirme oluşturacağız. **Gross Sales** ve **Date** onay kutularını işaretleyin.
   
   ![Alanlar listesi](media/service-get-started/fields.png)

    Power BI, verileri çözümler ve bir görselleştirme oluşturur. İlk olarak **Date**'i seçtiyseniz bir tablo görürsünüz. İlk olarak **Gross Sale**'i seçtiyseniz bir grafik görürsünüz. 

2. Verilerinizi farklı şekillerde görüntüleyin. Şimdi bu verilere çizgi grafik üzerine göz atalım. **Görselleştirmeler** bölmesinden çizgi grafiği simgesini seçin.
   
   ![Çizgi grafik seçiliyken rapor düzenleyicisi](media/service-get-started/gettingstart5new.png)

3. Bu grafik ilginç görünüyor, bunu bir panoya *sabitleyelim*. Görselleştirmenin üzerine gelin ve raptiye simgesini seçin. Görselleştirme sabitlendiğinde panonuzda depolanır ve güncelleştirilir. Böylece, en güncel değerleri bir bakışta izleyebilirsiniz.
   
   ![Raptiye simgesi](media/service-get-started/pinnew.png)

4. Bu rapor yeni olduğundan, görselleştirmeyi panoya sabitleyebilmeniz için öncelikle raporu kaydetmeniz istenir. Raporunuza bir ad verin (örn. *Sales over time*), ardından **Kaydet ve devam et**'i seçin. 
   
   ![Raporu kaydet iletişim kutusu](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
5. Şimdi çizgi grafiği yeni panoya sabitleyip *Financial sample for tutorial* adını verin. 
   
   ![Raporu adlandırma](media/service-get-started/power-bi-pin.png)
   
6. **Sabitle**'yi seçin.
   
    Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.
   
    ![Panoya sabitlendi iletişim kutusu](media/service-get-started/power-bi-pin-success.png)

7. **Panoya git**'i seçtiğinizde çizgi grafiğin yeni panonuza kutucuk olarak sabitlendiğini görebilirsiniz. Daha fazla görselleştirme kutucuğu ekleyip [kutucuklarınızı yeniden adlandırma, yeniden boyutlandırma, bağlantılı hale getirme ve yeniden konumlandırma](service-dashboard-edit-tile.md) yoluyla panonuzu iyileştirin.
   
   ![Görselleştirmenin sabitlendiği pano](media/service-get-started/power-bi-new-dashboard.png)
   
8. Rapora geri dönmek için panonuzdaki yeni kutucuğu seçin. Power BI rapor düzenleyicisi Okuma görünümü'nde açılır. Düzenleme görünümü'ne geçmek için üst gezinti çubuğundan **Raporu düzenle**'yi seçin. Düzen görünümü'ne geçtikten sonra kutucukları keşfetmeye ve sabitlemeye devam edebilirsiniz. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>3\. Adım:  Soru-Cevap ile araştırmaya devam etme (doğal dil sorgusu)
1. Verilerinizi hızla araştırmak için Soru-Cevap kutusunda soru sorun. Soru-Cevap soru kutusu panonuzun en üstünde (**Verileriniz hakkında soru sorun** ) ve raporunuzun üstündeki gezinti çubuğunda (**Bir soru sorun**) yer alır. Örneğin, Soru-Cevap kutusuna *what segment had the most revenue* (en çok gelir elde eden segment) yazın.
   
   ![Soru-Cevap tuvali](media/service-get-started/powerbi-qna.png)

2. Soru-Cevap yanıt arar ve görselleştirme biçiminde sunar. Bu görselleştirmenin panonuzda da gösterilmesi için raptiye simgesini ![Raptiye simgesi](media/service-get-started/pbi_pinicon.png) seçin.
3. Görselleştirmeyi **Financial Sample for tutorial** panosuna sabitleyin.
   
    ![Panoya sabitle iletişim kutusu](media/service-get-started/power-bi-pin2.png)

4. Panonuza döndüğünüzde yeni kutucuğu görebilirsiniz.

   ![Grafiğin sabitlendiği pano](media/service-get-started/power-bi-final-dashboard.png)

## <a name="clean-up-resources"></a>Kaynakları temizleme
Öğreticiyi bitirdiğinize göre şimdi veri kümesini, raporu ve panoyu silebilirsiniz. 

1. Sol gezinti çubuğundan **Çalışma Alanım**’ı seçin.
2. **Veri Kümeleri** sekmesini seçin ve bu öğretici için içeri aktardığınız veri kümesini bulun.  
3. Üç nokta (...) > **Sil**'i seçin.

    ![Veri kümesini silme](media/service-get-started/power-bi-delete.jpg)

    Veri kümesini sildiğinizde Power BI, raporu ve panoyu da siler. 


## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Power BI ile kullandığınız çevrimiçi hizmetlere bağlanma](service-connect-to-services.md)

