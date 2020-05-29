---
title: Power BI ile Power Automate tümleştirmesi
description: Power BI veri uyarıları ile tetiklenen Power Automate akışları oluşturmayı öğrenin.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: YhmNstC39Mw
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/25/2020
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 9e8f90465ab7b5b9545460de8d763061bf9bcf94
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83275030"
---
# <a name="power-automate-and-power-bi"></a>Power Automate ve Power BI

[Power Automate](https://docs.microsoft.com/power-automate/getting-started), işletme kullanıcılarının kullandığı, sayısı sürekli olarak artan uygulamalarda ve SaaS hizmetlerinde iş akışlarının otomatikleştirilmesine yönelik bir SaaS teklifidir. Power Automate ile; bildirimler almak, dosyaları eşitlemek, veri toplamak ve daha fazlasını gerçekleştirmek için, sık kullandığınız uygulamaları ve hizmetleri (Power BI dahil) tümleştirerek görevleri otomatikleştirebilirsiniz. Yinelenen görevler, iş akışı otomasyonuyla kolay hale gelir.

[Power Automate’i kullanmaya hemen başlayın.](https://docs.microsoft.com/power-automate/getting-started)

Sirui, bir Power BI uyarısı tetiklendiğinde iş arkadaşlarına ayrıntılı bir e-posta gönderilmesini sağlayan bir Power Automate akışı oluştururken ona izleyin. Ardından, videonun altında yer alan adım adım yönergeleri izleyerek bu işlemi kendiniz deneyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Power BI veri uyarısıyla tetiklenen bir akış oluşturma

### <a name="prerequisites"></a>Önkoşullar
Bu eğitimde, biri şablondan ve diğeri sıfırdan olmak üzere iki farklı akışı nasıl oluşturacağınız gösterilmektedir. Örneği takip edebilmek için, [Power BI'da bir veri uyarısı oluşturun](../create-reports/service-set-data-alerts.md), ücretsiz bir Slack hesabı oluşturun ve [Power Automate’e kaydolun](https://flow.microsoft.com/#home-signup) (ücretsiz!).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Power BI'ı kullanan bir akış oluşturma (şablondan)
Bu görevde bir Power BI veri uyarısı (bildirim) tarafından tetiklenen basit bir akış oluşturmak için şablon kullanıyoruz.

1. Power Automate’te oturum açın (flow.microsoft.com).
2. **Akışlarım**'ı seçin.
   
   ![Power Automate menü çubuğu](media/service-flow-integration/power-bi-my-flows.png)
3. **Şablondan oluştur** seçeneğini belirleyin.
   
    ![Akışlarım menü çubuğu](media/service-flow-integration/power-bi-template.png)
4. Power BI şablonlarını bulmak için Arama kutusunu kullanın ve **Power BI veri uyarısı tetiklendiğinde her izleyiciye e-posta gönder > Devam** seçeneğini işaretleyin.
   
    ![arama sonuçları](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>Akışı oluşturma
Bu şablonda bir tetikleyici (İrlanda'nın kazandığı her yeni Olimpiyat madalyasına yönelik Power BI veri uyarısı) ve bir eylem (e-posta gönderme) bulunur. Bir alan seçtiğinizde Power Automate ekleyebileceğiniz dinamik içerikleri görüntüler.  Bu örnekte, kutucuk değerini ve kutucuk URL'sini ileti gövdesine ekledik.

![akış şablonu](media/service-flow-integration/power-bi-template1.png)

1. Tetikleyici açılan menüsünden bir Power BI veri uyarısı seçin. **New medal for Ireland** seçeneğini belirleyin. Uyarı oluşturma hakkında bilgi edinmek için bkz. [Power BI'daki veri uyarıları](../create-reports/service-set-data-alerts.md).
   
   ![uyarı açılan menüsü](media/service-flow-integration/power-bi-trigger-flow.png)
2. Bir veya daha fazla geçerli e-posta adresi girin ve sonra **Düzenle** (aşağıda gösterilmiştir) ya da **Dinamik içerik ekle**’yi seçin. 
   
   ![E-posta gönderme ekranı](media/service-flow-integration/power-bi-flow-email.png)

3. Power Automate, tutabileceğiniz veya değiştirebileceğiniz bir başlık ve ileti oluşturur. Power BI'da uyarı oluştururken ayarladığınız tüm değerleri kullanabilirsiniz; imleci yerleştirmeniz ve gri ile vurgulanan alanı seçmeniz yeterlidir. 

   ![E-posta gönderme ekranı](media/service-flow-integration/power-bi-flow-email-default.png)

1.  Örneğin, Power BI'de **Bir madalya daha kazandık** şeklinde bir uyarı başlığı oluşturduysanız, **Uyarı başlığı**’nı seçerek bu metni e-postanızın Konu alanına ekleyebilirsiniz.

    ![e-posta metnini oluşturma](media/service-flow-integration/power-bi-flow-message.png)

    Ayrıca, varsayılan e-posta gövdesini kabul edebilir veya kendinizinkini oluşturabilirsiniz. Yukarıdaki örnekte iletinin birkaç değişikliği gösterilmiştir.

1. Bu işlemi tamamladığınızda, **Akış oluştur** veya **Akışı kaydet** seçeneğini belirleyin.  Akış oluşturulur ve değerlendirilir.  Power Automate herhangi bir hata bulması durumunda sizi bilgilendirir.
2. Hata bulunması halinde bunları düzeltmek için **Akışı düzenle**'yi, aksi halde, yeni akışı çalıştırmak için **Bitti**'yi seçin.
   
   ![başarılı iletisi](media/service-flow-integration/power-bi-flow-running.png)
5. Veri uyarısı tetiklendiğinde belirttiğiniz adreslere bir e-posta gönderilir.  
   
   ![uyarı e-postası](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-power-automate-that-uses-power-bi---from-scratch-blank"></a>Power BI'ı kullanan bir Power Automate akışı oluşturma - sıfırdan (boş)
Bu görevde, bir Power BI veri uyarısı (bildirim) ile tetiklenen basit bir akışı sıfırdan oluşturuyoruz.

1. Power Automate’te oturum açın.
2. **Akışlarım** > **Boş akış oluştur** seçeneğini belirleyin.
   
   ![Power Automate üst menü çubuğu](media/service-flow-integration/power-bi-my-flows.png)
3. Bir Power BI tetikleyicisi bulmak için Arama kutusunu kullanın ve **Power BI - veri temelli bir uyarı tetiklendiğinde** seçeneğini belirleyin.

### <a name="build-your-flow"></a>Akışınızı oluşturma
1. Açılan menüden uyarınızın adını seçin.  Uyarı oluşturma hakkında bilgi edinmek için bkz. [Power BI'daki veri uyarıları](../create-reports/service-set-data-alerts.md).
   
    ![Uyarının adını seçme](media/service-flow-integration/power-bi-totalstores2.png)
2. **Yeni adım** > **Eylem ekle**'yi seçin.
   
   ![yeni adım ekleme](media/service-flow-integration/power-bi-new-step.png)
3. **Outlook**'u bulun ve **Create event** seçeneğini belirleyin.
   
   ![akışı oluşturma](media/service-flow-integration/power-bi-create-event.png)
4. Etkinlik alanlarını doldurun. Bir alan seçtiğinizde Power Automate ekleyebileceğiniz dinamik içerikleri görüntüler.
   
   ![akışı oluşturmaya devam etme](media/service-flow-integration/power-bi-flow-event.png)
5. Gerekli alanları doldurduktan sonra, **Akış oluştur**'u seçin.  Power Automate akışı kaydeder ve değerlendirir. Herhangi bir hatayla karşılaşılmazsa **Bitti**'yi seçerek bu akışı çalıştırın.  Yeni akış **Akışlarım** sayfanıza eklenir.
   
   ![Akışı tamamlama](media/service-flow-integration/power-bi-flow-running.png)
6. Akış Power BI veri uyarınız ile tetiklendiğinde aşağıdakine benzer bir Outlook etkinlik bildirimi alırsınız.
   
    ![Power Automate Outlook bildirimini tetikler](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Power Automate’i kullanmaya başlama](https://docs.microsoft.com/power-automate/getting-started/)
* [Set data alerts in Power BI service (Power BI hizmetinde veri uyarısı oluşturma)](../create-reports/service-set-data-alerts.md)
* [iPhone'unuzda veri uyarısı oluşturma](../consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* [Windows 10 için Power BI mobil uygulamasında veri uyarısı oluşturma](../consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)