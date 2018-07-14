---
title: Power BI hizmetinde veri uyarısı oluşturma
description: Panolarınızdaki veriler Microsoft Power BI hizmetinde belirlediğiniz sınırları aşacak şekilde değiştiğinde bunu size bildirecek uyarılar ayarlamayı öğrenin.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: JbL2-HJ8clE
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: ffbad48df6665d5dff6c4eca97e86e6f2850565f
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37137650"
---
# <a name="data-alerts-in-power-bi-service"></a>Power BI hizmetindeki veri uyarıları
Panolarınızdaki veriler belirlediğiniz sınırları aşacak şekilde değiştiğinde bunu size bildirecek uyarılar ayarlayın. 

Power BI Pro lisansınız varsa veya bir [Premium kapasiteden](service-premium.md) sizinle pano paylaşıldıysa kutucuklar için uyarılar ayarlayabilirsiniz. Uyarılar yalnızca rapor görsellerinden sabitlenmiş olan kutucuklarda ve yalnızca ölçekler, KPI'ler ve kartlar için ayarlanabilir. Uyarılar rapordan panoya sabitlenmiş olan akış veri kümelerinden oluşturulan görseller için de ayarlanabilir ancak **Kutucuk ekle** > **Özel akış verileri** menüsü kullanılarak doğrudan panoda oluşturulmuş olan akış kutucukları için ayarlanamaz. 

Panonuzu paylaşsanız dahi ayarladığınız uyarıları yalnızca siz görebilirsiniz. Veri uyarıları platformlar arasında tamamen eşitlenir. Veri uyarılarını [Power BI mobil uygulamalarında](mobile-set-data-alerts-in-the-mobile-apps.md) ve Power BI hizmetinde ayarlayıp görüntüleyebilirsiniz. Uyarılar Power BI Desktop'ta kullanılamaz. İsterseniz uyarıları [Microsoft Flow'u kullanarak otomatikleştirilmiş ve tümleşik hale getirebilirsiniz](https://flow.microsoft.com) - [kendiniz deneyin](service-flow-integration.md).

![kutucuklar](media/service-set-data-alerts/powerbi-alert-types-new.png)

> [!WARNING]
> Veri tabanlı uyarı bildirimleri, verileriniz hakkında bilgi verir. Power BI verilerini bir mobil cihazda görüntülüyorsanız ve cihazınız çalınırsa, Power BI hizmetini kullanarak veri tabanlı uyarı kurallarının tümünü devre dışı bırakmanızı öneririz.
> 
> 

## <a name="set-data-alerts-in-power-bi-service"></a>Power BI hizmetinde veri uyarısı oluşturma
Amanda'nın, panosundaki kutucuklara uyarı eklemesini izleyin. Ardından, videonun altında yer alan adım adım yönergeleri izleyerek bu işlemi kendiniz deneyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

Bu örnekte Perakende Analizi örneği panosu kullanılmıştır.

1. İşleme bir panodan başlayın. Panodaki bir ölçek, KPI veya kart kutucuğundaki üç nokta simgesini seçin.
   
   ![Toplam Mağaza Sayısı kutucuğu](media/service-set-data-alerts/powerbi-card.png)
2. Zil simgesini ![Uyarı simgesi](media/service-set-data-alerts/power-bi-bell-icon.png) seçerek **Toplam mağaza sayısı** için bir veya daha fazla uyarı ekleyin.
   
1. Başlamak için **+ Uyarı kuralı ekle**'yi seçin kaydırıcının **Açık** konumda olduğundan emin olun ve uyarınıza bir ad verin. Başlıklar, uyarılarınızı kolayca ayırt etmenizi sağlar.
   
   ![Uyarıları yönetme penceresi](media/service-set-data-alerts/powerbi-alert-title.png)
4. Sayfayı aşağı kaydırıp uyarıyla ilgili ayrıntıları girin.  Bu örnekte toplam mağaza sayısı 100'ün üzerine çıktığında bizi günde bir kez bilgilendiren bir uyarı oluşturacağız. Uyarılar, Bildirim merkezinde görüntülenecek. Ayrıca Power BI bize bir e-posta da gönderecek.
   
   ![Uyarıları yönetme penceresi, Eşiği ayarlama](media/service-set-data-alerts/power-bi-set-alert-details.png)
5. **Kaydet**'i seçin.

## <a name="receiving-alerts"></a>Uyarı alma
Takip edilen veriler belirlediğiniz eşiklerden birine ulaşırsa birden fazla işlem gerçekleşir. Öncelikle Power BI son uyarının gönderilmesinin üzerinden bir saat veya 24 saat (belirlediğiniz seçeneğe bağlı olarak) geçip geçmediğini kontrol eder. Veriler eşiği geçtiği sürece uyarı gönderilir.

Ardından, Power BI, bildirim merkezinize ve isteğe bağlı olarak gelen kutunuza uyarı gönderir. Uyarılarda doğrudan verilerinize ulaşabileceğiniz bir bağlantı da bulunur. Bağlantıya tıklayarak ilgili kutucuğa gidebilir; araştırma, paylaşma ve daha fazla bilgi edinme işlevlerini kullanabilirsiniz.  

1. Uyarının e-posta gönderme ayarını etkinleştirdiyseniz, Gelen Kutunuzda aşağıdakine benzer bir ileti görürsünüz.
   
   ![Uyarı e-postası](media/service-set-data-alerts/powerbi-alerts-email.png)
2. Power BI, **Bildirim merkezinize** bir ileti ekler ve ilgili kutucukta yeni uyarı simgesi görüntüler.
   
   ![Power BI hizmetinde bildirim simgesi](media/service-set-data-alerts/powerbi-alert-notifications.png)
3. Uyarıyla ilgili ayrıntılı bilgileri görmek için Bildirim merkezinizi açın.
   
    ![Uyarıyı okuma](media/service-set-data-alerts/powerbi-alert-notfication.png)
   
   > [!NOTE]
   > Uyarılar yalnızca yenilenen verilerde çalışır. Veriler yenilendiğinde Power BI bu veriler için bir uyarı ayarlanıp ayarlanmadığını kontrol eder. Veriler bir uyarı eşiğine ulaştığında bir uyarı tetiklenir.
   > 
   > 

## <a name="managing-alerts"></a>Uyarıları yönetme
Uyarıları yönetmek için kullanabileceğiniz birçok farklı yöntem vardır: Pano kutucuğunun kendisinden, Power BI Ayarlar menüsünden, [iPhone'daki Power BI mobil uygulaması](mobile-set-data-alerts-in-the-mobile-apps.md) veya [Windows 10 için Power BI mobil uygulamasında](mobile-set-data-alerts-in-the-mobile-apps.md) yer alan kutucuktan.

### <a name="from-the-tile-itself"></a>Kutucuğun kendisinden
1. Kutucuklara ilişkin uyarıları değiştirmek veya kaldırmak için zil simgesini ![Uyarı simgesi](media/service-set-data-alerts/power-bi-bell-icon.png) seçerek **Uyarıları yönet** penceresini yeniden açın. İlgili kutucuk için ayarladığınız tüm uyarılar görüntülenir.
   
    ![Uyarıları yönetme penceresi](media/service-set-data-alerts/powerbi-see-alerts.png)geçin.
2. Bir uyarıyı değiştirmek için adının sol tarafındaki oku seçin.
   
    ![Uyarı adının yanındaki ok](media/service-set-data-alerts/powerbi-see-alerts-arrow.png)geçin.
3. Bir uyarıyı silmek için adının sağ tarafındaki çöp kutusunu seçin.
   
      ![seçili çöp kutusu simgesi](media/service-set-data-alerts/powerbi-see-alerts-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Power BI Ayarlar menüsünden
1. Power BI menü çubuğundaki dişli simgesini seçin.
   
    ![dişli simgesi](media/service-set-data-alerts/powerbi-gear-icon.png)geçin.
2. **Ayarlar** bölümünden **Uyarılar**'ı seçin.
   
    ![Ayarlar penceresinin Uyarılar sekmesi](media/service-set-data-alerts/powerbi-alert-settings.png)
3. Bu sayfadan uyarıları etkinleştirebilir ve devre dışı bırakabilir, **Uyarıları yönet** penceresini açarak değişiklik yapabilir veya uyarıları silebilirsiniz.

## <a name="tips-and-troubleshooting"></a>İpuçları ve sorun giderme
* Şu an için Bing kutucukları veya tarih/saat ölçülerine sahip kart kutucuklarında uyarılar desteklenmemektedir.
* Uyarılar yalnızca sayısal veri türleriyle çalışır.
* Uyarılar yalnızca yenilenen verilerde çalışır. Sabit veriler üzerinde çalışmazlar.
* Uyarılar, akış veri kümelerinde yalnızca KPI/kart/ölçek rapor görseli oluşturup bunu panoya sabitlemeniz durumunda çalışır.

## <a name="next-steps"></a>Sonraki adımlar
[Veri uyarısı içeren bir Microsoft Flow akışı oluşturma](service-flow-integration.md)    
[Mobil cihazınızda veri uyarısı oluşturma](mobile-set-data-alerts-in-the-mobile-apps.md)    
[Power BI nedir?](power-bi-overview.md)    
Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

