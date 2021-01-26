---
title: Destek için tanılama bilgilerini yakala
description: Power BI hizmeti Tanılama bilgilerinin el ile toplanması için yönergeler. Bu bilgileri, sorun gidermeye yardımcı olmak için desteğe gönderin.
author: kfollis
ms.author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/21/2021
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 59e434d571c5b8d10c944bc385fb4e18ed89963c
ms.sourcegitcommit: 84f0e7f31e62cae3bea2dcf2d62c2f023cc2d404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98781390"
---
# <a name="capture-diagnostic-information-from-the-power-bi-service"></a>Power BI hizmeti Tanılama bilgilerini yakala

Power BI hizmeti sahip olduğunuz bir sorunla ilgili yardım almak için Microsoft Desteği iletişime geçmeden önce, sorununuzu çözmenize yardımcı olacak dosyaları toplayabilirsiniz. Tarayıcı oturumunuzla bir tarayıcı izleme almanızı öneririz. Tarayıcı izlemesi, sorun oluştuğunda Power BI hizmeti neler olduğunu öğrenmek için önemli ayrıntılar sağlayabilen bir tanılama dosyasıdır.

Power BI yöneticileri, [Power Platform Yönetim merkezinde](https://admin.powerplatform.microsoft.com/) **Yardım + Destek** deneyimini kullanarak kendi kendine yardım çözümleri alabilir ve desteğe başvurabilirsiniz. Aşağıdaki adımları kullanarak topladığınız tanılama dosyaları, sorun gidermenize yardımcı olmak için destek isteğinize eklenebilir. Daha fazla destek seçeneği için [Power BI destek seçeneklerine](service-support-options.md)bakın.

Bir tarayıcı izlemesi ve diğer oturum bilgilerini toplamak için, kullandığınız tarayıcı için aşağıdaki adımları izleyin.

## <a name="collect-a-browser-trace"></a>Bir tarayıcı izlemesi toplayın

> [!IMPORTANT]
>Kullandığınız tarayıcıyı bağımsız olarak, tarayıcı izleme bilgilerini toplamaya *başlamadan önce* [Power BI hizmeti](https://app.powerbi.com) oturum açın. Bu adım, izleme bilgisinin oturum açma ile ilgili hassas bilgileri içermediğinden emin olmak için önemlidir.

#### <a name="google-chrome-or-microsoft-edge"></a>[Google Chrome veya Microsoft Edge](#tab/google-chrome-or-microsoft-edge)

Google Chrome ve Microsoft Edge (Kmıum), her ikisi de [kmıum açık kaynak projesine](https://www.chromium.org/Home)dayalıdır. Aşağıdaki adımlarda, iki tarayıcıda benzer olan Geliştirici araçlarının nasıl kullanılacağı gösterilmektedir. Daha fazla bilgi için bkz. [Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools) ve [Microsoft Edge (kmıum) geliştirici araçları](/microsoft-edge/devtools-guide-chromium).

1. Oturum açtıktan sonra klavyenizdeki F12 tuşuna basın. Ya da Microsoft Edge 'de **Ayarlar ' ı ve daha fazlasını (...)**  >  seçin. **Diğer araçlar**  >  **Geliştirici Araçları**. Google Chrome 'da **Özelleştir ve Google Chrome** :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/chromium-icon-settings.png" alt-text="Google Chrome ayarları menüsünü" border="false"::: denetle ' yi seçin. > **Diğer araçlar**  >  **Geliştirici Araçları**.
1. İzleme seçeneklerini ayarlayarak tarayıcı izlemesini toplamaya hazırlanın. Ayrıca, sorunu yeniden oluşturmaya başlamadan önce toplanan tüm bilgileri de durdurup temizleyemezsiniz. Varsayılan olarak tarayıcı, izleme bilgilerini yalnızca şu anda yüklü olan sayfa için tutar. Yeniden oluşturma işlemleri birden fazla sayfaya gitse bile, tarayıcıyı tüm izleme bilgilerini tutacak şekilde ayarlamak için şu adımları izleyin:
    1. **Geliştirici Araçları** penceresinde **ağ** sekmesini seçin. Ardından, **günlüğü** tut ' u seçin.
    
       :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/browser-trace-preserve-log.png" alt-text="Ağ sekmesi olan geliştirici araçları ve günlüğü koru seçili." :::

     2. **Konsol** sekmesini seçin ve ardından **Ayarlar**  >  **günlüğü tut**' u seçin. 
   
           :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/browser-trace-console-settings.png" alt-text="Konsol sekmesi olan geliştirici araçları ve günlüğü koru seçili." :::

        **Konsol ayarlarını** kapatmak için **ayarları** yeniden seçin.

3. Sonra, devam eden tüm kayıtları durdurun ve temizleyin. **Ağ** sekmesini seçin, **ağ günlüğü kaydını durdur**' u ve ardından **Temizle**' yi seçin.
   
   :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/browser-trace-stop-recording.png" alt-text="Ağ sekmesine sahip geliştirici araçları ve kayıt seçeneklerini durdurur ve temizler." :::
     
2. Artık Power BI hizmeti yaşadığınız sorunu yeniden oluşturacaksınız. Başlamak için, **Geliştirici Araçları** ' nda **ağ** sekmesini seçin. **Ağ günlüğünü kaydet**' i seçin.

    > [!IMPORTANT]
    >İzlemelerin doğru yakalanabilmesi için sorunu yeniden oluşturmaya başlamadan önce Power BI hizmeti tarayıcı sayfasını yenileyin.

   Yardım almanız gereken sorun ile sonuçlanan adımları yeniden üretin.

     :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/browser-trace-record-network-log.png" alt-text="Ağ sekmesine sahip geliştirici araçları ve kayıt ağı günlüğü seçilidir." :::

    Sorunu yeniden oluştururken, **Geliştirici Araçları** penceresinde aşağıdaki görüntüye benzer bir çıktı görürsünüz.

    :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/browser-trace-output.png" alt-text="Oturum çıkışını görüntüleyen ağ sekmesi olan geliştirici araçları." :::
    
3. Sorun davranışını yeniden oluşturduktan sonra, günlük dosyalarını kaydetmeniz ve bunları destek isteğinize bağlamanız gerekir.
    1. Ağ günlüğünü dışarı aktarmak için, **Geliştirici Araçları** ' nda **ağ** sekmesini seçin. **Ağ günlüğü kaydını durdur**' u seçin. Ardından, **har... dışa aktar** ' ı seçin ve dosyayı kaydedin.

         :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/browser-trace-export-har.png" alt-text="Ağ sekmesi olan geliştirici araçları, Kaydı Durdur ve HAR seçeneklerini dışarı aktar seçili." :::

    2. Konsol çıkışını dışarı aktarmak için, **Geliştirici Araçları** ' nda **konsol** sekmesini seçin. Görüntülenmiş bir iletiye sağ tıklayın, ardından **Farklı Kaydet...** öğesini seçin ve konsol çıkışını bir metin dosyasına kaydedin.
    
         :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/browser-trace-save-as.png" alt-text="Konsol sekmesi seçiliyken ve farklı Kaydet seçeneği gösterilen geliştirici araçları." :::

   Kaydedilmiş HAR dosyasını, konsol çıkışını ve ekran kaydını. zip gibi sıkıştırılmış bir biçimde paketleyin ve dosyayı destek isteğinize ekleyin.

#### <a name="apple-safari"></a>[Apple Safari](#tab/apple-safari)

Aşağıdaki adımlarda, Apple Safari 'de Geliştirici araçlarının nasıl kullanılacağı gösterilmektedir. Daha fazla bilgi için bkz. [Safari geliştirici araçları genel bakış](https://support.apple.com/guide/safari-developer/safari-developer-tools-overview-dev073038698/11.0/mac).

1. Oturum açtıktan sonra, Apple Safari 'de geliştirici araçları 'nı etkinleştirin:
    1. Sayfa başlığından **Safari**  >  **tercihleri**' ni seçin.
    
       :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/safari-preferences.png" alt-text="Tercihler seçiliyken Apple Safari menüsü." :::

    2. **Gelişmiş**' i seçin ve ardından geliştirici araçlarını etkinleştirmek için **menü çubuğunda geliştir menüsünü göster** ' i seçin.
    
       :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/safari-show-develop-menu.png" alt-text="Menü çubuğunda geliştir menüsünü göster seçiliyken Safari Gelişmiş menüsü." :::

2. Daha sonra, **Web denetçisinde** , tarayıcınızın tüm izleme bilgilerini tutmasını sağlamak için seçenekler ayarlayacaksınız. Varsayılan olarak tarayıcı, izleme bilgilerini yalnızca şu anda yüklü olan sayfa için tutar. Bu ayarlar, yeniden oluşturma işlemi birden fazla sayfaya gitse bile izleme bilgilerinin toplanmasını sağlar.

    1. **Geliştirme**  >  **Web denetçisini göster**' i seçin.
    
        :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/safari-web-inspector.png" alt-text="Web 'i göster denetçisi seçiliyken menüyü geliştir." :::

    2. **Ağ**  >  **koruma günlüğünü** seçin
       
         :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/safari-network-preserve-log.png" alt-text="Ağ ve günlüğü koru seçiliyken Web denetçisi menüsü." :::

    1. **Konsol**  >  **koruma günlüğünü** seçin
   
       :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/safari-console-preserve-log.png" alt-text="Konsol ve günlüğü koru seçiliyken Web denetçisi menüsü." :::

3. Seçenekler ayarlandıktan sonra,   >  günlüklerinizin yalnızca yeniden üretme ile ilgili ayrıntıları içerdiğinden emin olmak için ağ **Temizleme ağ öğeleri** ' ni seçin.

    :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/safari-clear-network-items.png" alt-text="Ağ ve açık ağ öğeleri seçiliyken Web denetçisi menüsü." :::


4. Artık sorunu yeniden oluşturmaya hazır olursunuz. 
    > [!IMPORTANT]
    >İzlemelerin doğru yakalanabilmesi için sorunu yeniden oluşturmaya başlamadan önce Power BI hizmeti tarayıcı sayfasını yenileyin.

    Sahip olduğunuz sorunu yeniden oluşturmak için adımları izleyin. Sorunu yeniden oluştururken, **ağ** penceresinde aşağıdaki görüntüye benzer bir çıktı görürsünüz.

    :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/safari-session-output.png" alt-text="Örnek çıktıyı görüntüleyen Ağ penceresi." :::

5. Sorun davranışını yeniden oluşturduktan sonra, günlük dosyalarını kaydetmeniz ve bunları destek isteğinize bağlamanız gerekir.

    1. Ağ günlüğünü dışarı aktarmak için, **ağ** sekmesinden **dışarı aktar** ' ı seçin ve dosyayı har biçiminde kaydedin.

         :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/safari-export.png" alt-text="Dışa aktarma seçeneği belirlenmiş ağ sekmesi." :::

    2. Konsol çıkışını dışarı aktarmak için, araç **geliştirme** bölmesinde **konsol** sekmesini seçin ve pencereyi genişletin. İmlecinizi konsol çıkışının başlangıcına yerleştirin ve ardından çıktının tüm içeriğini sürükleyin ve seçin. Çıktıyı kopyalamak ve bir metin dosyasına kaydetmek için Command-C komutunu kullanın.

   Kaydedilmiş HAR dosyasını, konsol çıkışını ve ekran kaydını. zip gibi sıkıştırılmış bir biçimde paketleyin ve dosyayı destek isteğinize ekleyin.

#### <a name="firefox"></a>[Firefox](#tab/firefox)

Aşağıdaki adımlarda, Firefox 'ta Geliştirici araçlarının nasıl kullanılacağı gösterilmektedir. Daha fazla bilgi için bkz. [Firefox geliştirici araçları](https://developer.mozilla.org/docs/Tools).

1. Oturum açtıktan sonra klavyenizdeki F12 tuşuna basın. Veya Firefox 'ta **Open Menu** :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/firefox-menu.png" alt-text="Firefox menü simgesini seçin." border="false"::: > **Web geliştiricisi**  >  **Iki durumlu araçlar**. Araçlar ekranınızın en altında görünür.

1. Daha sonra, tarayıcınızda tüm izleme bilgilerini tutabilmeniz için **Inspector** seçeneklerini ayarlayacaksınız. Varsayılan olarak tarayıcı, izleme bilgilerini yalnızca şu anda yüklü olan sayfa için tutar. Bu ayarlar, yeniden oluşturma işlemi birden fazla sayfaya gitse bile izleme bilgilerinin toplanmasını sağlar.

    1. **Inspector** penceresinde **ağ** sekmesini seçin. Ardından, **günlükleri kalıcı** yap ' ı seçin.
    
       :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/firefox-network-persist-logs.png" alt-text="Ağ sekmesi olan Inspector araçları ve günlükleri kalıcı olarak seçildi." :::

     2. **Konsol** sekmesini seçin ve ardından **Konsol ayarları**  >  **kalıcı Günlükler**' i seçin. 
   
           :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/firefox-console-persist-logs.png" alt-text="Konsol sekmesi olan Inspector araçları ve günlükleri kalıcı olarak seçildi." :::

3. Seçenekler ayarlandıktan sonra, devam eden tüm kayıtları temizleyin. **Ağ** sekmesini seçin ve ardından **işaretini kaldırın**.
   
   :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/browser-trace-stop-recording.png" alt-text="Ağ sekmesine sahip geliştirici araçları ve kayıt seçeneklerini durdurur ve temizler." :::
     
2. Artık sorunu yeniden oluşturmaya hazır olursunuz. 
    > [!IMPORTANT]
    >İzlemelerin doğru yakalanabilmesi için sorunu yeniden oluşturmaya başlamadan önce Power BI hizmeti tarayıcı sayfasını yenileyin.
 
    Sahip olduğunuz sorunu yeniden oluşturmak için adımları izleyin.
    
3. Sorun davranışını yeniden oluşturduktan sonra, günlük dosyalarını kaydetmeniz ve bunları destek isteğinize bağlamanız gerekir.
    1. Ağ günlüğünü dışarı aktarmak için **ağ**  >  **har dışarı/içeri** Aktar ' ı seçin ve ardından **Tümünü har olarak kaydedin**.

         :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/firefox-save-har.png" alt-text="HAR dışa/içe aktarma menüsündeki Ağ sekmesine ve tüm seçenekleri Kaydet seçili." :::

    2. Konsol çıkışını dışarı aktarmak için **konsol** sekmesini seçin. Görüntülenmiş bir iletiye sağ tıklayın, ardından **görünür Iletileri dışarı aktar**' ı seçin ve konsol çıkışını bir metin dosyasına kaydedin.
    
         :::image type="content" source="media/service-admin-capturing-additional-diagnostic-information-for-power-bi/firefox-export-visible-messages.png" alt-text="Konsol sekmesi seçili ve görünür iletileri dışarı aktar seçeneği gösteriliyor." :::

   Kaydedilmiş HAR dosyasını, konsol çıkışını ve ekran kaydını. zip gibi sıkıştırılmış bir biçimde paketleyin ve dosyayı destek isteğinize ekleyin.

---

Tanılama dosyalarını topladıktan sonra destek mühendisinin sorununuzu çözmesine yardımcı olmak için bunları destek isteğinize ekleyin. HAR dosyası tarayıcı penceresi ve Power BI hizmeti arasındaki ağ istekleriyle ilgili tüm bilgileri içerir, örneğin:

* Her istek için etkinlik kimlikleri.

* Her istek için kesin zaman damgası.

* İstemciye döndürülen tüm hata bilgileri.

Bu izlemede, ekranda gösterilen görselleri doldurmak için kullanılan veriler de yer alır.

## <a name="next-steps"></a>Sonraki adımlar

* [Microsoft 365'te Power BI hizmet durumunu izleme](service-admin-health.md)
* [Hizmet kesintisi bildirimlerini etkinleştirme](service-interruption-notifications.md)
* [Power BI Topluluğu birleştirin](https://community.powerbi.com/)
