---
title: "Eğitim: Microsoft Flow ile Power BI tümleştirmesi"
description: "Power BI veri uyarıları ile tetiklenen Akışlar oluşturmayı öğrenin."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: YhmNstC39Mw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart
ms.openlocfilehash: efab2e6be1d376a0da70c13bb66144ba34afa58c
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/17/2017
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow ve Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started), işletme kullanıcılarının kullandığı, sayısı sürekli olarak artan uygulamalarda ve SaaS hizmetlerinde iş akışlarının otomatikleştirilmesine yönelik bir SaaS teklifidir. Flow ile; bildirimler almak, dosyaları eşitlemek, veri toplamak ve daha fazlasını gerçekleştirmek için, sık kullandığınız uygulamaları ve hizmetleri (Power BI dahil) tümleştirerek görevleri otomatikleştirebilirsiniz. Yinelenen görevler, iş akışı otomasyonuyla kolay hale gelir.

[Flow'u kullanmaya hemen başlayın.](https://flow.microsoft.com/documentation/getting-started)

Sirui, bir Power BI uyarısı tetiklendiğinde iş arkadaşlarına ayrıntılı bir e-posta gönderilmesini sağlayan bir Akış oluştururken ona eşlik edin. Ardından, videonun altında yer alan adım adım yönergeleri izleyerek bu işlemi kendiniz deneyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Power BI veri uyarısıyla tetiklenen bir akış oluşturma
Bu eğitimde, biri şablondan ve diğeri sıfırdan olmak üzere iki farklı akışı nasıl oluşturacağınız gösterilmektedir. Eğitimi takip edebilmek için, [Power BI'da bir veri uyarısı oluşturun](service-set-data-alerts.md) ve [Microsoft Flow'a kaydolun](https://flow.microsoft.com/en-us/#home-signup) (Ücretsiz!).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Power BI'ı kullanan bir akış oluşturma (şablondan)
Bu görevde bir Power BI veri uyarısı (bildirim) tarafından tetiklenen basit bir akış oluşturmak için şablon kullanacağız.

1. Microsoft Flow'da (flow.microsoft.com) oturum açın.
2. **Akışlarım**'ı seçin.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. **Şablondan oluştur** seçeneğini belirleyin.
   
    ![](media/service-flow-integration/power-bi-template.png)
4. Power BI şablonlarını bulmak için Arama kutusunu kullanın ve **Power BI veri uyarısı tetiklendiğinde Slack kanalında bir ileti paylaşın** adlı şablonu seçin.
   
    ![](media/service-flow-integration/power-bi-template2.png)
5. **Bu şablonu kullan** seçeneğini belirleyin.
   
   ![](media/service-flow-integration/power-bi-use-template.png)
6. İstenirse, **Oturum aç**'ı seçip görüntülenen istemleri izleyerek Slack'e ve Power BI'a bağlanın. Yeşil onay işareti oturum açmış olduğunuzu gösterir.  Bağlantılarınızı doğruladıktan sonra, **Devam**'ı seçin.
   
   ![](media/service-flow-integration/power-bi-flow-signin.png)

### <a name="build-the-flow"></a>Akışı oluşturma
Bu şablonda bir tetikleyici (İrlanda'nın kazandığı her yeni Olimpiyat madalyasına yönelik Power BI veri uyarısı) ve bir eylem (Slack'te bir ileti paylaşma) bulunur. Bir alan seçtiğinizde Flow, ekleyebileceğiniz dinamik içerikleri görüntüler.  Bu örnekte, kutucuk değerini ve ileti gövdesindeki kutucuk URL'sini ekledik.

![](media/service-flow-integration/power-bi-flow-template.png)

1. Tetikleyici açılan menüsünden bir Power BI veri uyarısı seçin. **New medal for Ireland** seçeneğini belirleyin. Uyarı oluşturma hakkında bilgi edinmek için bkz. [Power BI'daki veri uyarıları](service-set-data-alerts.md).
   
   ![](media/service-flow-integration/power-bi-trigger-flow.png)
2. Slack'te paylaşımda bulunmak için bir kanal adı ve ileti metni girin (Flow'un oluşturduğu varsayılan iletiyi de seçebilirsiniz). İleti metni alanına eklediğimiz dinamik içeriği inceleyin.
   
   > [!NOTE]
   > Kanal adınızın başına "@" ekleyin.  Örneğin, Slack kanalı "channelA" olarak adlandırılmışsa Flow'da "@channelA" girin.
   > 
   > 
   
   ![](media/service-flow-integration/power-bi-flow-slacker.png)
3. Bu işlemi tamamladığınızda, **Akış oluştur** veya **Akışı kaydet** seçeneğini belirleyin.  Akış oluşturulur ve değerlendirilir.  Flow, herhangi bir hata bulması durumunda sizi bilgilendirir.
4. Hata bulunması halinde bunları düzeltmek için **Akışı düzenle**'yi, aksi halde, yeni akışı çalıştırmak için **Bitti**'yi seçin.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
5. İletiyi görmek için Slack hesabınızı açın.  
   
   ![](media/service-flow-integration/power-bi-slack-message.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Power BI'ı kullanan bir Akış oluşturma (sıfırdan)
Bu görevde, bir Power BI veri uyarısı (bildirim) ile tetiklenen basit bir akışı sıfırdan oluşturacağız.

1. Microsoft Flow'da oturum açın.
2. **Akışlarım** > **Boş akış oluştur** seçeneğini belirleyin.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Bir Power BI tetikleyicisi bulmak için Arama kutusunu kullanın ve **Veri temelli bir Power BI uyarısı tetiklendiğinde bir Akış tetikleyin** seçeneğini belirleyin.

### <a name="build-your-flow"></a>Akışınızı oluşturma
1. Açılan menüden uyarınızın adını seçin.  Uyarı oluşturma hakkında bilgi edinmek için bkz. [Power BI'daki veri uyarıları](service-set-data-alerts.md).
   
    ![](media/service-flow-integration/power-bi-totalstores.png)
2. **Yeni adım** > **Eylem ekle**'yi seçin.
   
   ![](media/service-flow-integration/power-bi-new-step.png)
3. **Outlook**'u bulun ve **Create event** seçeneğini belirleyin.
   
   ![](media/service-flow-integration/power-bi-create-event.png)
4. Etkinlik alanlarını doldurun. Bir alan seçtiğinizde Flow, ekleyebileceğiniz dinamik içerikleri görüntüler.
   
   ![](media/service-flow-integration/power-bi-flow-event.png)
5. Gerekli alanları doldurduktan sonra, **Akış oluştur**'u seçin.  Flow, akışı kaydeder ve değerlendirir. Herhangi bir hatayla karşılaşılmazsa **Bitti**'yi seçerek bu akışı çalıştırın.  Yeni akış **Akışlarım** sayfanıza eklenir.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
6. Akış Power BI veri uyarınız ile tetiklendiğinde aşağıdakine benzer bir Outlook etkinlik bildirimi alırsınız.
   
    ![](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Get started with Microsoft Flow (Microsoft Flow ile çalışmaya başlama)](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Set data alerts in Power BI service (Power BI hizmetinde veri uyarısı oluşturma)](service-set-data-alerts.md)
* [iPhone'unuzda veri uyarısı oluşturma](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Windows 10 için Power BI mobil uygulamasında veri uyarısı oluşturma](mobile-set-data-alerts-in-the-mobile-apps.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
