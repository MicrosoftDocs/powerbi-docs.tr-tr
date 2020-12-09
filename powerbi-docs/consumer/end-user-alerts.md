---
title: 'Öğretici: Power BI hizmeti panolarında veri uyarısı oluşturma'
description: Bu öğreticide, panolarınızdaki veriler Microsoft Power BI hizmetinde belirlediğiniz sınırları aşacak şekilde değiştiğinde bunu size bildirecek uyarılar ayarlamayı öğreneceksiniz.
author: mihart
ms.author: mihart
ms.reviewer: mihart
featuredvideoid: removed
ms.service: powerbi
ms.subservice: pbi-explore
ms.topic: how-to
ms.date: 12/03/2020
LocalizationGroup: Dashboards
ms.openlocfilehash: 369eb05795262ad628b9dd89c23ac59269e6f6c3
ms.sourcegitcommit: cb6e0202de27f29dd622e47b305c15f952c5769b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96577613"
---
# <a name="tutorial-set-alerts-on-power-bi-dashboards"></a>Öğretici: Power BI panolarında uyarı ayarlama

[!INCLUDE[consumer-appliesto-yynn](../includes/consumer-appliesto-yynn.md)]


Power BI hizmetinde, panonuzdaki veriler belirlediğiniz sınırları aşacak veya sınırların altında kalacak şekilde değiştiğinde bunu size bildirecek uyarılar ayarlayın. Uyarılar yalnızca rapor görsellerinden sabitlenmiş olan kutucuklarda ve yalnızca ölçekler, KPI'ler ve kartlar için ayarlanabilir. 

![kutucuk, kart, KPI](media/end-user-alerts/card-gauge-kpi.png)

Şu panolar üzerinde uyarılar oluşturulabilir:
- **Çalışma alanımda** oluşturup kaydettiğiniz
- [Premium kapasitede](end-user-license.md) sizinle paylaşılmış olan. 
- Power BI Pro lisansınız varsa, erişebileceğiniz herhangi bir çalışma alanında.    

Uyarılar yalnızca yenilenen verilerde çalışır. Veriler yenilendiğinde Power BI bu veriler için bir uyarı ayarlanıp ayarlanmadığını kontrol eder. Veriler bir uyarı eşiğine ulaştığında bir uyarı tetiklenir. 

Bu özellik hala geliştirilmektedir. Bu nedenle, [aşağıdaki İpuçları ve sorun giderme](#tips-and-troubleshooting) bölümüne bakın.



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

## <a name="prerequisites"></a>Ön koşullar

Power BI’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

1. Bu örnek, Satış ve Pazarlama örneğindeki bir pano kartı kutucuğunu kullanır. Power BI hizmetini (app.powerbi.com) açın, oturum açın ve **Çalışma Alanım** bölümünüzü açın.    
    ![Çalışma Alanım’ı açma](media//end-user-alerts/power-bi-my-workspace.png)

2. Sol alt köşedeki **Veri Al** seçeneğini belirleyin.

    ![Veri Al’ı seçme](media//end-user-alerts/power-bi-get-data.png)

3. Görüntülenen Veri Al sayfasında **Örnekler**’i seçin.

4. Satış ve Pazarlama Örneği’ni ve ardından **Bağlan**’ı seçin.

    ![Satış ve Pazarlama örneğini indirme](media//end-user-alerts/power-bi-sample.png)

5. Power BI örneğe bağlandıktan sonra görüntülenen iletişim kutusundan **Panoya git**’i seçin.     
    ![Satış ve Pazarlama örneğini açma](media//end-user-alerts/power-bi-go-to-dashboard.png)

## <a name="add-an-alert-to-a-dashboard-tile"></a>Bir pano kutucuğuna uyarı ekleme

1. Panodaki bir ölçek, KPI veya kart kutucuğunda üç nokta simgesini seçin.
   
   ![kart kutucuğu](media/end-user-alerts/power-bi-card.png)

2. Uyarı simgesini ![Uyarı simgesi](media/end-user-alerts/power-bi-alert-icon.png) veya **Uyarıları yönet**’i seçerek **Pazar payı** kartı için bir veya daha fazla uyarı ekleyin.

   ![üç noktaların seçili olduğu kart kutucuğu](media/end-user-alerts/power-bi-manage.png)

   
1. **Uyarıları yönet** bölmesinde **+ Uyarı kuralı ekle**'yi seçin.  Kaydırıcının **Açık** konumda olduğundan emin olun ve uyarınıza bir ad verin. Başlıklar, uyarılarınızı kolayca ayırt etmenizi sağlar.
   
   ![Uyarı kuralı ekleme penceresi](media/end-user-alerts/power-bi-alert-manage.png)
4. Sayfayı aşağı kaydırıp uyarıyla ilgili ayrıntıları girin.  Bu örnekte, pazar payımız 40’a veya daha üzerine çıktığında bizi günde bir kez bilgilendiren bir uyarı oluşturacağız. Uyarılar, [Bildirim merkezimizde](end-user-notification-center.md) görüntülenecek. Ayrıca Power BI bize bir e-posta da gönderecek.
   
   ![Uyarıları yönetme penceresi, Eşiği ayarlama](media/end-user-alerts/power-bi-manage-alert-detail.png)

5. **Kaydet ve kapat**’ı seçin.
 


   > 

## <a name="receiving-alerts"></a>Uyarı alma
Takip edilen veriler belirlediğiniz eşiklerden birine ulaşırsa birkaç şey gerçekleşir. Öncelikle Power BI (belirlediğiniz seçeneğe bağlı olarak) son uyarının gönderilmesinin üzerinden bir saat veya 24 saat geçip geçmediğini kontrol eder. Veriler eşiği geçtiği sürece uyarı gönderilir.

Ardından, Power BI, Bildirim merkezinize ve isteğe bağlı olarak gelen kutunuza uyarı gönderir. Uyarılarda doğrudan verilerinize ulaşabileceğiniz bir bağlantı da bulunur. İlgili kutucuğu görmek için bağlantıyı seçin.  

1. Uyarının e-posta gönderme ayarını etkinleştirdiyseniz, Gelen Kutunuzda aşağıdakine benzer bir ileti görürsünüz. Bu, **Yaklaşım** kartı için ayarladığımız bir uyarıdır.
   
   ![Uyarı e-postası](media/end-user-alerts/power-bi-email.png)
2. Power BI, **Bildirim merkezinize** de bir ileti ekler.
   
   ![Power BI hizmetinde bildirim simgesi](media/end-user-alerts/power-bi-task.png)
3. Uyarıyla ilgili ayrıntılı bilgileri görmek için Bildirim merkezinizi açın.
   
    ![Uyarıyı okuma](media/end-user-alerts/power-bi-notifications.png)
   
  

## <a name="managing-alerts"></a>Uyarıları yönetme

Uyarılarınızı yönetmek için kullanabileceğiniz birçok farklı yöntem vardır: Pano kutucuğunun kendisinden, Power BI Ayarlar menüsünden, [iPhone’daki Power BI mobil uygulaması](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) veya [Windows 10 için Power BI mobil uygulamasında](mobile/mobile-set-data-alerts-in-the-mobile-apps.md) yer alan kutucuktan.

### <a name="from-the-tile-itself"></a>Kutucuğun kendisinden

1. Kutucuklara ilişkin uyarıları değiştirmek veya kaldırmak için uyarı simgesini ![Uyarı simgesi](media/end-user-alerts/power-bi-alert-icon.png) seçerek **Uyarıları yönet** penceresini yeniden açın. İlgili kutucuk için ayarladığınız tüm uyarılar görüntülenir.
   
    ![Uyarıları yönetme penceresi](media/end-user-alerts/power-bi-manage-alert.png).
2. Bir uyarıyı değiştirmek için adının sol tarafındaki oku seçin.
   
    ![Uyarı adının yanındaki ok](media/end-user-alerts/power-bi-alert-modify.png).
3. Bir uyarıyı silmek için adının sağ tarafındaki çöp kutusunu seçin.
   
      ![seçili çöp kutusu simgesi](media/end-user-alerts/power-bi-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Power BI Ayarlar menüsünden

1. Power BI menü çubuğundaki dişli simgesini seçin.
   
    ![dişli simgesi](media/end-user-alerts/power-bi-gear-icon.png).
2. **Ayarlar** bölümünden **Uyarılar**'ı seçin.
   
    ![Ayarlar penceresinin Uyarılar sekmesi](media/end-user-alerts/power-bi-settings.png)
3. Bu sayfadan uyarıları etkinleştirebilir ve devre dışı bırakabilir, **Uyarıları yönet** penceresini açarak değişiklik yapabilir veya uyarıları silebilirsiniz.

## <a name="tips-and-troubleshooting"></a>İpuçları ve sorun giderme 

* Bir ölçer, KPI veya kart için uyarı ayarlayamıyorsanız yardım için Power BI yöneticinize veya BT yardım masanıza başvurun. Uyarılar, bazen panolarınız veya belirli türden pano kutucukları için kapatılır veya kullanılamaz.
* Uyarılar yalnızca yenilenen verilerde çalışır. Sabit veriler üzerinde çalışmazlar. Microsoft tarafından sağlanan örneklerin çoğu statiktir. 
* Paylaşılan içeriği almak ve görüntülemek için Power BI Pro veya Premium lisansı gerekir. Daha fazla bilgi için bkz. [Hangi lisansa sahibim?](end-user-license.md)
* Bir rapordan panoya sabitlenmiş olan akış veri kümelerinden oluşturulan görseller üzerinde uyarılar ayarlanabilir. **Kutucuk ekle** > **Özel akış verileri** kullanılarak doğrudan pano üzerinde oluşturulan akış kutucukları üzerinde uyarılar ayarlanamaz.


## <a name="clean-up-resources"></a>Kaynakları temizleme
Uyarıları silmek yönergeleri yukarıda açıklanmıştır. Kısaca, Power BI menü çubuğundaki dişli simgesini seçin. **Ayarlar**'ın altından **Uyarılar**'ı seçin ve uyarıyı silin.

> [!div class="nextstepaction"]
> [Mobil cihazınızda veri uyarısı oluşturma](mobile/mobile-set-data-alerts-in-the-mobile-apps.md)


