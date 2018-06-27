---
title: Microsoft Flow ile Power BI tümleştirmesi
description: Power BI veri uyarıları ile tetiklenen Akışlar oluşturmayı öğrenin.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: YhmNstC39Mw
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: dc79282a5c221e85fae7838009f6cecf91cbfdb8
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34246839"
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow ve Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started), işletme kullanıcılarının kullandığı, sayısı sürekli olarak artan uygulamalarda ve SaaS hizmetlerinde iş akışlarının otomatikleştirilmesine yönelik bir SaaS teklifidir. Flow ile; bildirimler almak, dosyaları eşitlemek, veri toplamak ve daha fazlasını gerçekleştirmek için, sık kullandığınız uygulamaları ve hizmetleri (Power BI dahil) tümleştirerek görevleri otomatikleştirebilirsiniz. Yinelenen görevler, iş akışı otomasyonuyla kolay hale gelir.

[Flow'u kullanmaya hemen başlayın.](https://flow.microsoft.com/documentation/getting-started)

Sirui, bir Power BI uyarısı tetiklendiğinde iş arkadaşlarına ayrıntılı bir e-posta gönderilmesini sağlayan bir Akış oluştururken ona eşlik edin. Ardından, videonun altında yer alan adım adım yönergeleri izleyerek bu işlemi kendiniz deneyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Power BI veri uyarısıyla tetiklenen bir akış oluşturma

### <a name="prerequisites"></a>Önkoşullar
Bu eğitimde, biri şablondan ve diğeri sıfırdan olmak üzere iki farklı akışı nasıl oluşturacağınız gösterilmektedir. Örneği takip edebilmek için, [Power BI'da bir veri uyarısı oluşturun](service-set-data-alerts.md), ücretsiz bir Slack hesabı oluşturun ve [Microsoft Flow'a kaydolun](https://flow.microsoft.com/en-us/#home-signup) (ücretsiz!).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Power BI'ı kullanan bir akış oluşturma (şablondan)
Bu görevde bir Power BI veri uyarısı (bildirim) tarafından tetiklenen basit bir akış oluşturmak için şablon kullanacağız.

1. Microsoft Flow'da (flow.microsoft.com) oturum açın.
2. **Akışlarım**'ı seçin.
   
   ![Akış menü çubuğu](media/service-flow-integration/power-bi-my-flows.png)
3. **Şablondan oluştur** seçeneğini belirleyin.
   
    ![Akışlarım menü çubuğu](media/service-flow-integration/power-bi-template.png)
4. Power BI şablonlarını bulmak için Arama kutusunu kullanın ve **Power BI veri uyarısı tetiklendiğinde her izleyiciye e-posta gönder > Devam** seçeneğini işaretleyin.
   
    ![arama sonuçları](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>Akışı oluşturma
Bu şablonda bir tetikleyici (İrlanda'nın kazandığı her yeni Olimpiyat madalyasına yönelik Power BI veri uyarısı) ve bir eylem (e-posta gönderme) bulunur. Bir alan seçtiğinizde Flow, ekleyebileceğiniz dinamik içerikleri görüntüler.  Bu örnekte, kutucuk değerini ve ileti gövdesindeki kutucuk URL'sini ekledik.

![akış şablonu](media/service-flow-integration/power-bi-template1.png)

1. Tetikleyici açılan menüsünden bir Power BI veri uyarısı seçin. **New medal for Ireland** seçeneğini belirleyin. Uyarı oluşturma hakkında bilgi edinmek için bkz. [Power BI'daki veri uyarıları](service-set-data-alerts.md).
   
   ![uyarı açılan menüsü](media/service-flow-integration/power-bi-trigger-flow.png)
2. Bir veya daha fazla geçerli e-posta adresi girin ve sonra **Düzenle** (aşağıda gösterilmiştir) ya da **Dinamik içerik ekle**’yi seçin. 
   
   ![E-posta gönderme ekranı](media/service-flow-integration/power-bi-flow-email.png)

3. Akış, tutabileceğiniz veya değiştirebileceğiniz bir başlık ve ileti oluşturur. Power BI'de uyarı oluştururken ayarladığınız tüm değerleri kullanabilirsiniz; imleci yerleştirmeniz ve gri ile vurgulanan alanı seçmeniz yeterlidir. 

   ![E-posta gönderme ekranı](media/service-flow-integration/power-bi-flow-email-default.png)

1.  Örneğin, Power BI'de **Bir madalya daha kazandık** şeklinde bir uyarı başlığı oluşturduysanız, **Uyarı başlığı**’nı seçerek bu metni e-postanızın Konu alanına ekleyebilirsiniz.

    ![e-posta metnini oluşturma](media/service-flow-integration/power-bi-flow-message.png)

    Ayrıca, varsayılan e-posta gövdesini kabul edebilir veya kendinizinkini oluşturabilirsiniz. Yukarıdaki örnekte iletinin birkaç değişikliği gösterilmiştir.

1. Bu işlemi tamamladığınızda, **Akış oluştur** veya **Akışı kaydet** seçeneğini belirleyin.  Akış oluşturulur ve değerlendirilir.  Flow, herhangi bir hata bulması durumunda sizi bilgilendirir.
2. Hata bulunması halinde bunları düzeltmek için **Akışı düzenle**'yi, aksi halde, yeni akışı çalıştırmak için **Bitti**'yi seçin.
   
   ![başarılı iletisi](media/service-flow-integration/power-bi-flow-running.png)
5. Veri uyarısı tetiklendiğinde belirttiğiniz adreslere bir e-posta gönderilir.  
   
   ![uyarı e-postası](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Power BI'ı kullanan bir Akış oluşturma (sıfırdan)
Bu görevde, bir Power BI veri uyarısı (bildirim) ile tetiklenen basit bir akışı sıfırdan oluşturacağız.

1. Microsoft Flow'da oturum açın.
2. **Akışlarım** > **Boş akış oluştur** seçeneğini belirleyin.
   
   ![Akış üst menü çubuğu](media/service-flow-integration/power-bi-my-flows.png)
3. Bir Power BI tetikleyicisi bulmak için Arama kutusunu kullanın ve **Power BI - veri temelli bir uyarı tetiklendiğinde** seçeneğini belirleyin.

### <a name="build-your-flow"></a>Akışınızı oluşturma
1. Açılan menüden uyarınızın adını seçin.  Uyarı oluşturma hakkında bilgi edinmek için bkz. [Power BI'daki veri uyarıları](service-set-data-alerts.md).
   
    ![Uyarının adını seçme](media/service-flow-integration/power-bi-totalstores2.png)
2. **Yeni adım** > **Eylem ekle**'yi seçin.
   
   ![yeni adım ekleme](media/service-flow-integration/power-bi-new-step.png)
3. **Outlook**'u bulun ve **Create event** seçeneğini belirleyin.
   
   ![akışı oluşturma](media/service-flow-integration/power-bi-create-event.png)
4. Etkinlik alanlarını doldurun. Bir alan seçtiğinizde Flow, ekleyebileceğiniz dinamik içerikleri görüntüler.
   
   ![akışı oluşturmaya devam etme](media/service-flow-integration/power-bi-flow-event.png)
5. Gerekli alanları doldurduktan sonra, **Akış oluştur**'u seçin.  Flow, akışı kaydeder ve değerlendirir. Herhangi bir hatayla karşılaşılmazsa **Bitti**'yi seçerek bu akışı çalıştırın.  Yeni akış **Akışlarım** sayfanıza eklenir.
   
   ![Akışı tamamlama](media/service-flow-integration/power-bi-flow-running.png)
6. Akış Power BI veri uyarınız ile tetiklendiğinde aşağıdakine benzer bir Outlook etkinlik bildirimi alırsınız.
   
    ![Outlook bildirimini tetikleyen akış](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Get started with Microsoft Flow (Microsoft Flow ile çalışmaya başlama)](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Set data alerts in Power BI service (Power BI hizmetinde veri uyarısı oluşturma)](service-set-data-alerts.md)
* [iPhone'unuzda veri uyarısı oluşturma](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Windows 10 için Power BI mobil uygulamasında veri uyarısı oluşturma](mobile-set-data-alerts-in-the-mobile-apps.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

