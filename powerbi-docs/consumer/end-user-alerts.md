---
title: 'Öğretici: Power BI hizmeti panolarında veri uyarısı oluşturma'
description: Bu öğreticide, panolarınızdaki veriler Microsoft Power BI hizmetinde belirlediğiniz sınırları aşacak şekilde değiştiğinde bunu size bildirecek uyarılar koymayı öğreneceksiniz.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: removed
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: tutorial
ms.date: 08/26/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 16639f6e9bf005d04c64fc3ae6a331338efdd5d4
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2019
ms.locfileid: "70064349"
---
# <a name="tutorial-set-dashboard-alerts-on-power-bi-dashboards"></a>Öğretici: Power BI panolarında pano uyarıları ayarlama
Panolarınızdaki veriler belirlediğiniz sınırları aşacak veya sınırların altında kalacak şekilde değiştiğinde bunu size bildirecek uyarılar ayarlayın. Uyarılar, ölçerlerde, KPI’lerde ve kartlarda çalışır. Bu özellik hala geliştirilmektedir. Bu nedenle, [aşağıdaki İpuçları ve sorun giderme](#tips-and-troubleshooting) bölümüne bakın.

![kutucuk, kart, KPI](media/end-user-alerts/card-gauge-kpi.png)

Panonuzu paylaşsanız dahi ayarladığınız uyarıları yalnızca siz görebilirsiniz. Veri uyarıları platformlar arasında tamamen eşitlenir. Veri uyarılarını [Power BI mobil uygulamalarında](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) ve Power BI hizmetinde ayarlayıp görüntüleyebilirsiniz. 

> [!WARNING]
> Bu uyarılar verileriniz hakkında bilgi sağlar. Power BI verilerini bir mobil cihazda görüntülüyorsanız ve cihazınız çalınırsa, Power BI hizmetini kullanarak tüm uyarıları devre dışı bırakmanızı öneririz.
> 

Bu öğretici aşağıdakileri ele almaktadır.
> [!div class="checklist"]
> * Kimler uyarı koyabilir
> * Hangi görseller uyarıları destekler
> * Uyarılarımı kimler görebilir
> * Uyarılar Power BI Desktop'ta ve mobilde çalışır mı
> * Uyarı nasıl oluşturulur?
> * Uyarılarımı nereden alacağım

Power BI’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

Bu örnek, Satış ve Pazarlama örnek uygulamasındaki bir pano kartı kutucuğunu kullanır. Bu uygulama [Microsoft AppSource](https://appsource.microsoft.com)’ta kullanılabilir. Uygulamayı edinme hakkında yardım almak için bkz. [Power BI ile uygulamaları yükleyip kullanma](end-user-app-view.md).

1. Panodaki bir ölçek, KPI veya kart kutucuğunda üç nokta simgesini seçin.
   
   ![kart kutucuğu](media/end-user-alerts/power-bi-cards.png)
2. Zil simgesini ![Uyarı simgesi](media/end-user-alerts/power-bi-bell-icon.png) veya **Uyarıları yönet**'i seçerek **Toplam mağaza sayısı** için bir veya daha fazla uyarı ekleyin.

   ![üç noktaların seçili olduğu kart kutucuğu](media/end-user-alerts/power-bi-ellipses.png)

   
1. **Uyarıları yönet** bölmesinde **+ Uyarı kuralı ekle**'yi seçin.  Kaydırıcının **Açık** konumda olduğundan emin olun ve uyarınıza bir ad verin. Başlıklar, uyarılarınızı kolayca ayırt etmenizi sağlar.
   
   ![Uyarıları yönetme penceresi](media/end-user-alerts/power-bi-manage-alert.png)
4. Sayfayı aşağı kaydırıp uyarıyla ilgili ayrıntıları girin.  Bu örnekte, pazar payımız 35’e veya daha üzerine çıktığında bizi günde bir kez bilgilendiren bir uyarı oluşturacağız. Uyarılar, Bildirim merkezinde görüntülenecek. Ayrıca Power BI bize bir e-posta da gönderecek.
   
   ![Uyarıları yönetme penceresi, Eşiği ayarlama](media/end-user-alerts/power-bi-manage-alert-details.png)
5. **Kaydet ve kapat**’ı seçin.
 
   > [!NOTE]
   > Uyarılar yalnızca yenilenen verilerde çalışır. Veriler yenilendiğinde Power BI bu veriler için bir uyarı ayarlanıp ayarlanmadığını kontrol eder. Veriler bir uyarı eşiğine ulaştığında bir uyarı tetiklenir. 
   > 

## <a name="receiving-alerts"></a>Uyarı alma
Takip edilen veriler belirlediğiniz eşiklerden birine ulaşırsa birkaç şey gerçekleşir. Öncelikle Power BI (belirlediğiniz seçeneğe bağlı olarak) son uyarının gönderilmesinin üzerinden bir saat veya 24 saat geçip geçmediğini kontrol eder. Veriler eşiği geçtiği sürece uyarı gönderilir.

Ardından, Power BI, Bildirim merkezinize ve isteğe bağlı olarak gelen kutunuza uyarı gönderir. Uyarılarda doğrudan verilerinize ulaşabileceğiniz bir bağlantı da bulunur. İlgili kutucuğu görmek için bağlantıyı seçin.  

1. Uyarının e-posta gönderme ayarını etkinleştirdiyseniz, Gelen Kutunuzda aşağıdakine benzer bir ileti görürsünüz. Bu, farklı bir panoda ayarladığımız bir uyarıdır. Bu pano, Kullanılabilirlik ekibi tarafından tamamlanan görevleri izler.
   
   ![Uyarı e-postası](media/end-user-alerts/power-bi-alert-email.png)
2. Power BI, **Bildirim merkezinize** bir ileti ekler ve ilgili kutucukta yeni uyarı simgesi görüntüler.
   
   ![Power BI hizmetinde bildirim simgesi](media/end-user-alerts/power-bi-task-alert.png)
3. Uyarıyla ilgili ayrıntılı bilgileri görmek için Bildirim merkezinizi açın.
   
    ![Uyarıyı okuma](media/end-user-alerts/power-bi-notification.png)
   
  

## <a name="managing-alerts"></a>Uyarıları yönetme

Uyarılarınızı yönetmenin birçok yolu vardır: Pano kutucuğunun kendisinden, Power BI Ayarlar menüsünden, [iPhone'daki Power BI mobil uygulaması](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) veya [Windows 10 için Power BI mobil uygulamasında](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) yer alan kutucuktan.

### <a name="from-the-tile-itself"></a>Kutucuğun kendisinden

1. Kutucuklara ilişkin uyarıları değiştirmek veya kaldırmak için zil simgesini ![Uyarı simgesi](media/end-user-alerts/power-bi-bell-icon.png) seçerek **Uyarıları yönet** penceresini yeniden açın. İlgili kutucuk için ayarladığınız tüm uyarılar görüntülenir.
   
    ![Uyarıları yönetme penceresi](media/end-user-alerts/power-bi-manage-alerts.png)geçin.
2. Bir uyarıyı değiştirmek için adının sol tarafındaki oku seçin.
   
    ![Uyarı adının yanındaki ok](media/end-user-alerts/power-bi-modify-alert.png)geçin.
3. Bir uyarıyı silmek için adının sağ tarafındaki çöp kutusunu seçin.
   
      ![seçili çöp kutusu simgesi](media/end-user-alerts/power-bi-alert-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Power BI Ayarlar menüsünden

1. Power BI menü çubuğundaki dişli simgesini seçin.
   
    ![dişli simgesi](media/end-user-alerts/powerbi-gear-icon.png)geçin.
2. **Ayarlar** bölümünden **Uyarılar**'ı seçin.
   
    ![Ayarlar penceresinin Uyarılar sekmesi](media/end-user-alerts/power-bi-alert-settings.png)
3. Bu sayfadan uyarıları etkinleştirebilir ve devre dışı bırakabilir, **Uyarıları yönet** penceresini açarak değişiklik yapabilir veya uyarıları silebilirsiniz.

## <a name="tips-and-troubleshooting"></a>İpuçları ve sorun giderme 

* Uyarılar yalnızca ölçerlerde, KPI’lerde ve kartlarda ayarlanabilir.
* Bir ölçer, KPI veya kart için uyarı ayarlayamıyorsanız, yardım için sistem yöneticinize başvurun. Uyarılar, bazen panolarınız veya belirli türden pano kutucukları için kapatılır veya kullanılamaz.
* Uyarılar yalnızca yenilenen verilerde çalışır. Sabit veriler üzerinde çalışmazlar. Microsoft tarafından sağlanan örneklerin çoğu statiktir. 


## <a name="clean-up-resources"></a>Kaynakları temizleme
Uyarıları silmek yönergeleri yukarıda açıklanmıştır. Kısaca, Power BI menü çubuğundaki dişli simgesini seçin. **Ayarlar**'ın altından **Uyarılar**'ı seçin ve uyarıyı silin.

> [!div class="nextstepaction"]
> [Mobil cihazınızda veri uyarısı oluşturma](mobile/mobile-set-data-alerts-in-the-mobile-apps.md)


