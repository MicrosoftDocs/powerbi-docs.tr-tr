---
title: 'Öğretici: Power BI hizmetinde veri uyarısı oluşturma'
description: Bu öğreticide, panolarınızdaki veriler Microsoft Power BI hizmetinde belirlediğiniz sınırları aşacak şekilde değiştiğinde bunu size bildirecek uyarılar koymayı öğreneceksiniz.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: JbL2-HJ8clE
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: tutorial
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 64da077e079ca3df11ce2a89da546e24865eaf0e
ms.sourcegitcommit: f05ba39a0e46cb9cb43454772fbc5397089d58b4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68522898"
---
# <a name="tutorial-set-data-alerts-in-power-bi-service"></a>Öğretici: Power BI hizmetinde veri uyarısı oluşturma
Panolarınızdaki veriler belirlediğiniz sınırları aşacak şekilde değiştiğinde bunu size bildirecek uyarılar ayarlayın.  

Power BI Pro lisansınız varsa veya bir [Premium kapasiteden](../service-premium-what-is.md) sizinle pano paylaşıldıysa kutucuklar için uyarılar ayarlayabilirsiniz. Uyarılar yalnızca rapor görsellerinden sabitlenmiş olan kutucuklarda ve yalnızca ölçekler, KPI'ler ve kartlar için ayarlanabilir. Uyarılar rapordan panoya sabitlenmiş olan akış veri kümelerinden oluşturulan görseller için de ayarlanabilir ancak **Kutucuk ekle** > **Özel akış verileri** menüsü kullanılarak doğrudan panoda oluşturulmuş olan akış kutucukları için ayarlanamaz. 

Panonuzu paylaşsanız dahi ayarladığınız uyarıları yalnızca siz görebilirsiniz. Veri uyarıları platformlar arasında tamamen eşitlenir. Veri uyarılarını [Power BI mobil uygulamalarında](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) ve Power BI hizmetinde ayarlayıp görüntüleyebilirsiniz. 

![kutucuklar](../media/service-set-data-alerts/powerbi-alert-types-new.png)

> [!WARNING]
> Veri tabanlı uyarı bildirimleri, verileriniz hakkında bilgi verir. Power BI verilerini bir mobil cihazda görüntülüyorsanız ve cihazınız çalınırsa, Power BI hizmetini kullanarak veri tabanlı uyarı kurallarının tümünü devre dışı bırakmanızı öneririz.
> 

Bu öğretici aşağıdakileri ele almaktadır.
> [!div class="checklist"]
> * Kimler uyarı koyabilir
> * Hangi görseller uyarıları destekler
> * Uyarılarımı kimler görebilir
> * Uyarılar Power BI Desktop'ta ve mobilde çalışır mı
> * Nasıl uyarı oluştururum
> * Uyarılarımı nereden alacağım

Power BI’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="set-data-alerts-in-power-bi-service"></a>Power BI hizmetinde veri uyarısı oluşturma
Amanda'nın, panodaki kutucuklara uyarı eklemesini izleyin. Ardından, videonun altında yer alan adım adım yönergeleri izleyerek bu işlemi kendiniz deneyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

Bu örnekte [Perakende Analizi örneği](http://go.microsoft.com/fwlink/?LinkId=529778) panosu kullanılmıştır.

1. Panodaki bir ölçek, KPI veya kart kutucuğunda üç nokta simgesini seçin.
   
   ![Toplam Mağaza Sayısı kutucuğu](media/end-user-alerts/powerbi-card.png)
2. Zil simgesini ![Uyarı simgesi](media/end-user-alerts/power-bi-bell-icon.png) veya **Uyarıları yönet**'i seçerek **Toplam mağaza sayısı** için bir veya daha fazla uyarı ekleyin.
   
1. **Uyarıları yönet** bölmesinde **+ Uyarı kuralı ekle**'yi seçin.  Kaydırıcının **Açık** konumda olduğundan emin olun ve uyarınıza bir ad verin. Başlıklar, uyarılarınızı kolayca ayırt etmenizi sağlar.
   
   ![Uyarıları yönetme penceresi](media/end-user-alerts/powerbi-alert-title.png)
4. Sayfayı aşağı kaydırıp uyarıyla ilgili ayrıntıları girin.  Bu örnekte toplam mağaza sayısı 100'ün üzerine çıktığında bizi günde bir kez bilgilendiren bir uyarı oluşturacağız. Uyarılar, Bildirim merkezinde görüntülenecek. Ayrıca Power BI bize bir e-posta da gönderecek.
   
   ![Uyarıları yönetme penceresi, Eşiği ayarlama](media/end-user-alerts/power-bi-set-alert-details.png)
5. **Kaydet ve kapat**’ı seçin.

## <a name="receiving-alerts"></a>Uyarı alma
Takip edilen veriler belirlediğiniz eşiklerden birine ulaşırsa birkaç şey gerçekleşir. Öncelikle Power BI (belirlediğiniz seçeneğe bağlı olarak) son uyarının gönderilmesinin üzerinden bir saat veya 24 saat geçip geçmediğini kontrol eder. Veriler eşiği geçtiği sürece uyarı gönderilir.

Ardından, Power BI, bildirim merkezinize ve isteğe bağlı olarak gelen kutunuza uyarı gönderir. Uyarılarda doğrudan verilerinize ulaşabileceğiniz bir bağlantı da bulunur. İlgili kutucuğu görmek için bağlantıyı seçin.  

1. Uyarının e-posta gönderme ayarını etkinleştirdiyseniz, Gelen Kutunuzda aşağıdakine benzer bir ileti görürsünüz.
   
   ![Uyarı e-postası](media/end-user-alerts/powerbi-alerts-email.png)
2. Power BI, **Bildirim merkezinize** bir ileti ekler ve ilgili kutucukta yeni uyarı simgesi görüntüler.
   
   ![Power BI hizmetinde bildirim simgesi](media/end-user-alerts/powerbi-alert-notifications.png)
3. Uyarıyla ilgili ayrıntılı bilgileri görmek için Bildirim merkezinizi açın.
   
    ![Uyarıyı okuma](media/end-user-alerts/powerbi-alert-notification.png)
   
   > [!NOTE]
   > Uyarılar yalnızca yenilenen verilerde çalışır. Veriler yenilendiğinde Power BI bu veriler için bir uyarı ayarlanıp ayarlanmadığını kontrol eder. Veriler bir uyarı eşiğine ulaştığında bir uyarı tetiklenir.
   > 
   > 

## <a name="managing-alerts"></a>Uyarıları yönetme
Uyarılarınızı yönetmenin birçok yolu vardır: Pano kutucuğunun kendisinden, Power BI Ayarlar menüsünden, [iPhone'daki Power BI mobil uygulaması](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) veya [Windows 10 için Power BI mobil uygulamasında](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) yer alan kutucuktan.

### <a name="from-the-tile-itself"></a>Kutucuğun kendisinden
1. Kutucuklara ilişkin uyarıları değiştirmek veya kaldırmak için zil simgesini ![Uyarı simgesi](media/end-user-alerts/power-bi-bell-icon.png) seçerek **Uyarıları yönet** penceresini yeniden açın. İlgili kutucuk için ayarladığınız tüm uyarılar görüntülenir.
   
    ![Uyarıları yönetme penceresi](media/end-user-alerts/powerbi-see-alerts.png)geçin.
2. Bir uyarıyı değiştirmek için adının sol tarafındaki oku seçin.
   
    ![Uyarı adının yanındaki ok](media/end-user-alerts/powerbi-see-alerts-arrow.png)geçin.
3. Bir uyarıyı silmek için adının sağ tarafındaki çöp kutusunu seçin.
   
      ![seçili çöp kutusu simgesi](media/end-user-alerts/powerbi-see-alerts-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Power BI Ayarlar menüsünden
1. Power BI menü çubuğundaki dişli simgesini seçin.
   
    ![dişli simgesi](media/end-user-alerts/powerbi-gear-icon.png)geçin.
2. **Ayarlar** bölümünden **Uyarılar**'ı seçin.
   
    ![Ayarlar penceresinin Uyarılar sekmesi](media/end-user-alerts/powerbi-alert-settings.png)
3. Bu sayfadan uyarıları etkinleştirebilir ve devre dışı bırakabilir, **Uyarıları yönet** penceresini açarak değişiklik yapabilir veya uyarıları silebilirsiniz.

## <a name="tips-and-troubleshooting"></a>İpuçları ve sorun giderme
* Şu an için Bing kutucukları veya tarih/saat ölçülerine sahip kart kutucuklarında uyarılar desteklenmemektedir.
* Uyarılar yalnızca sayısal veri türleriyle çalışır.
* Uyarılar yalnızca yenilenen verilerde çalışır. Sabit veriler üzerinde çalışmazlar.
* Uyarılar, akış veri kümelerinde yalnızca KPI/kart/ölçek rapor görseli oluşturup bunu panoya sabitlemeniz durumunda çalışır.

## <a name="clean-up-resources"></a>Kaynakları temizleme
Uyarıları silmek yönergeleri yukarıda açıklanmıştır. Kısaca, Power BI menü çubuğundaki dişli simgesini seçin. **Ayarlar**'ın altından **Uyarılar**'ı seçin ve uyarıyı silin.

> [!div class="nextstepaction"]
> [Mobil cihazınızda veri uyarısı oluşturma](mobile/mobile-set-data-alerts-in-the-mobile-apps.md)


