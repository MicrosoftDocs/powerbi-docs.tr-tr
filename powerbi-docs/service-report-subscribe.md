---
title: Kendinizi ve başkalarını Power BI hizmetinde raporlara ve panolara abone yapma
description: Kendinizi ve başkalarını bir Power BI raporunun veya panosunun anlık görüntüsüne abone yapmayı öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2019
ms.author: maggies
LocalizationGroup: Common tasks
ms.openlocfilehash: 639fbd58236debc2c71a87a9e9cfd551ad4b433d
ms.sourcegitcommit: 89e9875e87b8114abecff6ae6cdc0146df40c82a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58306539"
---
# <a name="subscribe-yourself-and-others-to-a-report-or-dashboard-in-the-power-bi-service"></a>Kendinizi ve başkalarını Power BI hizmetinde bir rapora veya panoya abone yapma

Kendinizi ve iş arkadaşlarınızı en fazla önem verdiğiniz rapor sayfalarına ve panolara abone yapabilirsiniz. Bunu yaptığınızda Power BI gelen kutunuza e-postayla bir anlık görüntü gönderir. Power BI'da e-postaları hangi sıklıkla almak istediğinizi seçebilirsiniz: günlük, haftalık veya günde bir kez ilk veri yenilemesinden sonra.  Günlük veya haftalığı seçerseniz aboneliğin çalıştırılmasını istediğiniz saatleri seçebilirsiniz.  Her rapor sayfası veya pano için günde en fazla 24 farklı abonelik ayarlayabilirsiniz.

![panonun anlık görüntüsünü e-posta ile gönderme](media/service-report-subscribe/power-bi-dashboard-email-new.jpg) 

Abonelikleri yalnızca Power BI hizmetinde oluşturabilirsiniz. Anlık görüntüyü içeren ve rapor sayfasını veya panoyu açabileceğiniz bağlantının da bulunduğu bir e-posta alırsınız. Power BI uygulamalarının yüklü olduğu mobil cihazlarda bu bağlantı seçildiğinde rapor veya pano Power BI web sitesinde açılmaz. Bunun yerine Power BI uygulaması başlatılır.

## <a name="requirements"></a>Gereksinimler
- Abonelik **oluşturma** bir Power BI Pro özelliğidir.
- Kendinize abonelik oluşturmak için içeriği (pano veya rapor) düzenleme izinleriniz olması gerekmez, ancak başkası için abonelik oluşturacaksanız düzenleme izinleriniz olmalıdır. 
- Ocak 2019’dan itibaren, aboneliği çalıştırmak için veri kümesi yenilemesinin ayarlanması gerekmez.  Ayarlamış olduğunuz tüm zamanlanmış yenilemelerden bağımsız olarak çalışır.  

## <a name="subscribe-to-a-dashboard-or-a-report-page"></a>Bir panoya veya rapor sayfasına abone olma
Panoya ve rapora abone olma süreçleri birbirine benzerdir. Aynı düğmeyi kullanarak Power BI hizmet panolarına ve raporlarına abone olabilirsiniz.
 
![Abone ol simgesini seçme](media/service-report-subscribe/power-bi-subscribe-orientation.png)geçin.

1. Panoyu veya raporu açın.
2. Üstteki menü çubuğundan **Abone ol** seçeneğini belirleyin veya zarf simgesini ![Abone ol simgesi](media/service-report-subscribe/power-bi-icon-envelope.png) seçin.
   
   ![Abone ol simgesi](media/service-report-subscribe/power-bi-subscribe-icon.png)

3. Aboneliği açıp kapatmak için sarı kaydırıcıyı kullanın.  Kaydırıcı **Kapalı** olarak ayarlandığında abonelik silinmez. Aboneliği silmek için çöp kutusu simgesini seçin.

4. E-postanız zaten **Abone ol** kutusundadır. Aboneliğe başka e-posta adresleri de ekleyebilirsiniz ama bu adreslerin aynı etki alanında olmaları gerekir. Rapor veya pano [Premium kapasitede](service-premium.md) barındırılıyorsa tek tek e-posta adreslerini ve grup diğer adlarını abone yapabilirsiniz. Rapor veya pano Premium kapasitede barındırılmıyorsa, başkalarını yine abone yapabilirsiniz ama o kişilerin de Power BI Pro lisansları olmalıdır. Ayrıntılar için aşağıdaki [Önemli noktalar ve sorun giderme](#considerations-and-troubleshooting) bölümüne bakın. 

5. E-posta iletisinin **Konu** ve **İleti** ayrıntılarını doldurun. 

5. Aboneliğiniz için **Sıklık** seçin: **Günlük**, **Haftalık** veya **Veri Yenilemesinden Sonra (Günlük)**.  Abonelik e-postasını yalnızca belirli günlerde almak için **Haftalık** seçin ve hangi günler almak istediğinizi belirtin.  Örneğin abonelik e-postasını yalnızca iş günleri almak istiyorsanız **Haftalık** seçeneğini belirtin ve **Cts** ile **Paz** kutularının işaretini kaldırın.  

6. **Günlük** veya **Haftalık** seçerseniz, abonelik için **Zamanlanan Saat**'i de seçebilirsiniz.  Bir saat ya da 15, 30 veya 45 dakika geçince çalıştırabilirsiniz.  Sabah (AM) veya öğleden sonra/akşam (PM) ayarını seçin. Saat dilimini de belirtebilirsiniz.

7. Varsayılan olarak, aboneliğinizin başlangıç tarihi aboneliği oluşturduğunuz tarihtir. İsterseniz bir bitiş tarihi belirleyebilirsiniz. Siz bir bitiş tarihi ayarlamazsanız, otomatik olarak başlangıç tarihinden bir yıl sonrası olarak belirlenir. Bu tarihi, aboneliğiniz bitmeden önce gelecekte istediğiniz herhangi bir tarihle değiştirebilirsiniz (en fazla 9999 yıl). Abonelik bitiş tarihine ulaşıldığında, siz yeniden etkinleştirene kadar abonelik durdurulur. Zamanlanan bitiş tarihinden önce, süreyi uzatmayı isteyip istemediğinizi soran bildirimler alırsınız.    

    Aşağıdaki ekran görüntüsünde, bir rapora abone olduğunuzda aslında bir rapor *sayfasına* abone olduğunuzu görebilirsiniz.  Bir rapordaki birden çok sayfaya abone olmak için **Başka bir abonelik ekle**’yi seçip farklı bir sayfa seçin. 
      
   ![Abone ol bölmesi](media/service-report-subscribe/power-bi-subscribe-pane.png)  

7. **Kaydet ve kapat**’ı seçin. Abone olan kişiler seçtiğiniz sıklıkta ve saatlerde e-postayla pano veya rapor sayfasının anlık görüntüsünü alır. Toplamda rapor veya pano başına en fazla 24 abonelik oluşturabilirsiniz ve her abonelik için benzersiz alıcılar, saatler ve sıklıklar sağlayabilirsiniz.  Panonuz veya raporunuz için **Veri Yenilemesinden Sonra** olarak ayarlanan tüm abonelikler, yine de yalnızca zamanlanmış ilk yenilemeden sonra e-posta gönderir.   
      
   > [!TIP]
   > Abonelikten e-postayı hemen mi yoksa isteğe bağlı olarak herhangi bir zamanda mı göndermek istiyorsunuz? Göndermek istediğiniz panonun veya raporun abonelikleri için **Şimdi Çalıştır**’ı seçin. Bu abonelik için herkese e-posta gönderildiğine ilişkin bir bildirim görürsünüz.  Bunu istediğiniz sıklıkta yapabilirsiniz. Rapor veya pano başına günde 24 zamanlanmış abonelik çalıştırması sınırınızda bu hesaba katılmaz. Bunun, temel veri kümesinde bir veri yenilemesi tetiklemediğini unutmayın. 
   > 
   > 
   
## <a name="email-languages"></a>E-posta dilleri

E-posta ve anlık görüntü, Power BI ayarlarında belirtilen dil ayarını kullanır (bkz. [Power BI için desteklenen diller ve ülkeler/bölgeler](supported-languages-countries-regions.md)). Dil tanımlanmazsa, Power BI geçerli tarayıcınızın yerel ayarına göre seçilen dili kullanır. Dil tercihinizi görmek veya belirlemek için sırasıyla dişli simgesini ![dişli simgesi](media/service-report-subscribe/power-bi-settings-icon.png) > **Ayarlar > Genel > Dil** seçeneklerini belirleyin. 

![Dil açılan menüsü](media/service-report-subscribe/power-bi-language.png)

## <a name="manage-your-subscriptions"></a>Aboneliklerinizi yönetme
Aboneliği yalnızca oluşturan kişi yönetebilir.  Aboneliklerinizi yönetmeye yönelik ekrana iki farklı şekilde ulaşabilirsiniz.  İlki **E-postalara abone olun** iletişim kutusundan **Tüm abonelikleri yönet** seçeneğini belirlemektir. (Yukarıdaki 4. adımın altında yer alan ekran görüntülerine bakın.) İkincisi ise üstteki menü çubuğundan Power BI dişli simgesini ![dişli simgesi](media/service-report-subscribe/power-bi-settings-icon.png) seçip **Ayarlar** seçeneğini belirlemektir.

![Ayarlar seçeneğini belirleme](media/service-report-subscribe/power-bi-subscribe-settings.png)

Görüntülenen abonelikler o sırada etkin olan çalışma alanına bağlıdır.  Tüm çalışma alanları için aboneliklerinizi aynı anda görmek için **Çalışma Alanım**'ın etkin olduğundan emin olun. Çalışma alanlarının anlaşılması konusunda yardım almak için bkz. [Power BI'daki Çalışma Alanları](service-create-workspaces.md).

![Çalışma Alanım içinde tüm abonelikleri görüntüleme](media/service-report-subscribe/power-bi-subscriptions.png)

Pro lisansının süresi dolarsa, pano veya rapor sahibi tarafından silinirse veya aboneliğin oluşturulması için kullanılan kullanıcı hesabı silinirse abonelik sona erer.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Üzerinde 25’ten fazla sabitlenmiş kutucuk veya 4 sabitlenmiş canlı rapor sayfası olan panolar, kullanıcılara gönderilen abonelik e-postalarında tam olarak işlenemeyebilir.  Bu sayıdan fazla kutucuk içeren panoların abonelikleri engellenmez ama sorunlarla karşılaşırsanız desteklenmiyor olarak kabul edilir ve desteklenen aralıkta olacak şekilde değiştirilmeleri gerekir.
* E-posta aboneliklerinizi ayarlarken, lütfen abonelik işinin başlatılması ile e-postanın gönderildiği tam zaman arasında bir gecikme olduğunu unutmayın.  İşin başlatılması ile e-postanın gönderilmesi arasındaki gecikmeyi en aza indirmek için, zamanlanan veri yenilemeniz için e-posta aboneliğinizin çalışmak için zamanlandığı saatten farklı bir zaman seçmeniz önerilir.
* Pano e-posta abonelikleri için, satır düzeyi güvenlik (RLS) uygulanan kutucuklar varsa bunlar görüntülenmez.  Rapor e-posta abonelikleri için, veri kümesi RLS kullanıyorsa bir abonelik oluşturamazsınız.
* Rapor sayfası abonelikleri rapor sayfasının adıyla ilişkilidir. Rapor sayfasına abone olduktan sonra sayfayı yeniden adlandırırsanız aboneliğinizi yeniden oluşturmanız gerekir.
* Kuruluşunuz, Power BI’da e-posta aboneliği kullanımını sınırlayan Azure Active Directory’deki belirli ayarları yapılandırabilir.  Bu sınırlamaların bazıları kaynak erişimi sırasında çok faktörlü kimlik doğrulaması gereksinimi veya IP aralığı kısıtlamaları olabilir.
* Kendiniz dışındaki kullanıcıları abone yaparken canlı bağlantı veri kümeleri kullanan raporlara/panolara yönelik e-posta abonelikleri şu anda desteklenmiyor.
* E-posta abonelikleri çoğu [özel görselleri](power-bi-custom-visuals.md) desteklemez.  Bu konudaki tek istisna, [sertifikalı](power-bi-custom-visuals-certified.md) özel görsellerdir.  
* E-posta abonelikleri şu anda R tarafından desteklenen özel görselleri desteklemiyor.  
* Pano kutucuklarına satır düzeyi güvenlik (RLS) uygulandıysa, söz konusu kutucuklar görüntülenmez.
* Diğer kullanıcıları satır düzeyi güvenlik (RLS) uygulanmış olan bir rapora abone yapamazsınız.
* E-posta abonelikleri raporun varsayılan filtresi ve dilimleyici durumları ile gönderilir. Abone olduktan sonra varsayılanlarda yaptığınız hiçbir değişiklik e-postada gösterilmez.    
* Özellikle pano abonelikleri için belirli kutucuk türleri henüz desteklenmemektedir.  Bu kutucuk türleri şunlardır: akış kutucukları, video kutucukları ve özel web içeriği kutucukları.     
* Bir panoyu kiracınız dışındaki bir iş arkadaşıyla paylaşıyorsanız bu iş arkadaşı için bir de abonelik oluşturamazsınız. Bu nedenle, siz aaron@xyz.com kişisiyseniz anyone@ABC.com kişisiyle paylaşım yapabilirsiniz, ancak henüz anyone@ABC.com kişisini abone yapamazsınız ve bu kişi paylaşılan içeriğe abone olamaz.      
* Power BI, 2 aydan daha uzun bir süredir ziyaret edilmemiş panolar ve raporlar ile ilişkili veri kümelerinde yenilemeyi otomatik olarak duraklatır.  Ancak bir panoya veya rapora abonelik eklerseniz bu abonelik ziyaret edilmese bile duraklatılmaz.    
* Abonelik e-postalarını almıyorsanız Kullanıcı Asıl Adınızın (UPN) e-posta alabildiğinden emin olun. [Power BI ekibi şu anda bu gereksinimi esnetmek için çalışıyor](https://community.powerbi.com/t5/Issues/No-Mail-from-Cloud-Service/idc-p/205918#M10163), bu nedenle takipte kalın. 
* Panonuz veya raporunuz Premium kapasitedeyse iş arkadaşlarını her seferinde bir e-posta adresi girerek abone yapmak yerine abonelikler için grup e-postası diğer adını kullanabilirsiniz. Diğer adlar için geçerli Active Directory temel alınır. 

## <a name="next-steps"></a>Sonraki adımlar
* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)    
* [Blog gönderisini okuyun](https://powerbi.microsoft.com/blog/introducing-dashboard-email-subscriptions-a-360-degree-view-of-your-business-in-your-inbox-every-day/)

