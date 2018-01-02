---
title: "Power BI hizmetinde veri uyarısı oluşturma"
description: "Panolarınızdaki veriler Microsoft Power BI hizmetinde belirlediğiniz sınırları aşacak şekilde değiştiğinde bunu size bildirecek uyarılar ayarlamayı öğrenin."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: JbL2-HJ8clE
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/06/2017
ms.author: mihart
ms.openlocfilehash: cfbd7d124784b15b432921554c8ac5bbe321846c
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="data-alerts-in-power-bi-service"></a>Power BI hizmetindeki veri uyarıları
Panolarınızdaki veriler belirlediğiniz sınırları aşacak şekilde değiştiğinde bunu size bildirecek uyarılar ayarlayın. Uyarılar yalnızca rapor görsellerinden sabitlenmiş olan kutucuklarda ve yalnızca ölçekler, KPI'ler ve kartlar için ayarlanabilir. Uyarılar rapordan panoya sabitlenmiş olan akış veri kümelerinden oluşturulan görseller için de ayarlanabilir ancak **Kutucuk ekle** > **Özel akış verileri** menüsü kullanılarak doğrudan panoda oluşturulmuş olan akış kutucukları için ayarlanamaz. Panonuzu paylaşsanız dahi ayarladığınız uyarıları yalnızca siz görebilirsiniz. Veri uyarıları platformlar arasında tamamen eşitlenir. Veri uyarılarını [Power BI mobil uygulamalarında](mobile-set-data-alerts-in-the-mobile-apps.md) ve Power BI hizmetinde ayarlayıp görüntüleyebilirsiniz. Uyarılar Power BI Desktop'ta kullanılamaz. İsterseniz uyarıları [Microsoft Flow'u kullanarak otomatikleştirilmiş ve tümleşik hale getirebilirsiniz](https://flow.microsoft.com) - [kendiniz deneyin](service-flow-integration.md).

![](media/service-set-data-alerts/powerbi-alert-types-new.png)

> [!WARNING]
> Veri tabanlı uyarı bildirimleri, verileriniz hakkında bilgi verir. Power BI verilerini bir mobil cihazda görüntülüyorsanız ve cihazınız çalınırsa, Power BI hizmetini kullanarak veri tabanlı uyarı kurallarının tümünü devre dışı bırakmanızı öneririz.
> 
> 

## <a name="set-data-alerts-in-power-bi-service"></a>Power BI hizmetinde veri uyarısı oluşturma
Amanda'nın, panosundaki kutucuklara uyarı eklemesini izleyin. Ardından, videonun altında yer alan adım adım yönergeleri izleyerek bu işlemi kendiniz deneyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

Bu örnekte Perakende Analizi örneği panosu kullanılmıştır.

1. İşleme bir panodan başlayın. Panodaki bir ölçek, KPI veya kart kutucuğundaki üç nokta simgesini seçin.
   
   ![](media/service-set-data-alerts/powerbi-card.png)
2. Zil simgesini ![](media/service-set-data-alerts/power-bi-bell-icon.png) seçerek **Total stores** için bir veya daha fazla uyarı ekleyin.
   
   ![](media/service-set-data-alerts/powerbi-set-alert.png)
3. Başlamak için kaydırıcının **Açık** konumda olduğundan emin olun ve uyarınıza bir ad verin. Başlıklar, uyarılarınızı kolayca ayırt etmenizi sağlar.
   
   ![](media/service-set-data-alerts/powerbi-alert-title.png)
4. Sayfayı aşağı kaydırıp uyarıyla ilgili ayrıntıları girin.  Bu örnekte toplam mağaza sayısı 100'ün üzerine çıktığında bizi günde bir kez bilgilendiren bir uyarı oluşturacağız. Uyarılar, Bildirim merkezinde görüntülenecek. Ayrıca Power BI bize bir e-posta da gönderecek.
   
   ![](media/service-set-data-alerts/powerbi-set-alert-details.png)
5. **Kaydet**'i seçin.

## <a name="receiving-alerts"></a>Uyarı alma
Takip edilen veriler belirlediğiniz eşiklerden birine ulaşırsa birden fazla işlem gerçekleşir. Öncelikle Power BI son uyarının gönderilmesinin üzerinden bir saat veya 24 saat (belirlediğiniz seçeneğe bağlı olarak) geçip geçmediğini kontrol eder. Veriler eşiği geçtiği sürece uyarı gönderilir.

Ardından, Power BI, bildirim merkezinize ve isteğe bağlı olarak gelen kutunuza uyarı gönderir. Uyarılarda doğrudan verilerinize ulaşabileceğiniz bir bağlantı da bulunur. Bağlantıya tıklayarak ilgili kutucuğa gidebilir; araştırma, paylaşma ve daha fazla bilgi edinme işlevlerini kullanabilirsiniz.  

1. Uyarının e-posta gönderme ayarını etkinleştirdiyseniz, Gelen Kutunuzda aşağıdakine benzer bir ileti görürsünüz.
   
   ![](media/service-set-data-alerts/powerbi-alerts-email.png)
2. Power BI, **Bildirim merkezinize** bir ileti ekler ve ilgili kutucukta yeni uyarı simgesi görüntüler.
   
   ![](media/service-set-data-alerts/powerbi-alert-notifications.png)
3. Uyarıyla ilgili ayrıntılı bilgileri görmek için Bildirim merkezinizi açın.
   
    ![](media/service-set-data-alerts/powerbi-alert-notfication.png)
   
   > [!NOTE]
   > Uyarılar yalnızca yenilenen verilerde çalışır. Veriler yenilendiğinde Power BI bu veriler için bir uyarı ayarlanıp ayarlanmadığını kontrol eder. Veriler bir uyarı eşiğine ulaştığında bir uyarı tetiklenir.
   > 
   > 

## <a name="managing-alerts"></a>Uyarıları yönetme
Uyarıları yönetmek için kullanabileceğiniz üç farklı yöntem vardır: Pano kutucuğunun kendisinden, Power BI Ayarlar menüsünden ve [iPhone'daki Power BI mobil uygulaması](mobile-set-data-alerts-in-the-mobile-apps.md) veya [Windows 10 için Power BI mobil uygulamasında](mobile-set-data-alerts-in-the-mobile-apps.md) yer alan kutucuktan.

### <a name="from-the-tile-itself"></a>Kutucuğun kendisinden
1. Kutucuklara ilişkin uyarıları değiştirmek veya kaldırmak için zil simgesini ![](media/service-set-data-alerts/power-bi-bell-icon.png) seçerek **Uyarıları yönet** penceresini yeniden açın. İlgili kutucuk için ayarladığınız tüm uyarılar görüntülenir.
   
    ![](media/service-set-data-alerts/powerbi-see-alerts.png).
2. Bir uyarıyı değiştirmek için adının sol tarafındaki oku seçin.
   
    ![](media/service-set-data-alerts/powerbi-see-alerts-arrow.png).
3. Bir uyarıyı silmek için adının sağ tarafındaki çöp kutusunu seçin.
   
      ![](media/service-set-data-alerts/powerbi-see-alerts-delete.png)

### <a name="from-the-power-bi-settings-menu"></a>Power BI Ayarlar menüsünden
1. Power BI menü çubuğundaki dişli simgesini seçin.
   
    ![](media/service-set-data-alerts/powerbi-gear-icon.png).
2. **Ayarlar** bölümünden **Uyarılar**'ı seçin.
   
    ![](media/service-set-data-alerts/powerbi-alert-settings.png)
3. Bu sayfadan uyarıları etkinleştirebilir ve devre dışı bırakabilir, **Uyarıları yönet** penceresini açarak değişiklik yapabilir veya uyarıları silebilirsiniz.

## <a name="tips-and-troubleshooting"></a>İpuçları ve sorun giderme
* Şu an için Bing kutucukları veya tarih/saat ölçülerine sahip kart kutucuklarında uyarılar desteklenmemektedir.
* Uyarılar yalnızca sayısal veri türleriyle çalışır.
* Uyarılar yalnızca yenilenen verilerde çalışır. Sabit veriler üzerinde çalışmazlar.
* Uyarılar, akış veri kümelerinde yalnızca KPI/kart/ölçek rapor görseli oluşturup bunu panoya sabitlemeniz durumunda çalışır.

## <a name="next-steps"></a>Sonraki adımlar
[Veri uyarısı içeren bir Microsoft Flow akışı oluşturma](service-flow-integration.md)    
[Mobil cihazınızda veri uyarısı oluşturma](mobile-set-data-alerts-in-the-mobile-apps.md)    
[Power BI ile çalışmaya başlama](service-get-started.md)    
Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

