---
title: Satıcı Panosu'nu kullanarak Power BI görselini AppSource'a gönderme
description: Satıcı Panosu'nu kullanarak Power BI görselini AppSource'a gönderme
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/03/2019
ms.openlocfilehash: 73a6a3d16ae2515af41a3232a37579e18876f38b
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2020
ms.locfileid: "75223659"
---
# <a name="submit-a-power-bi-visual-to-appsource-using-seller-dashboard"></a>Satıcı Panosu'nu kullanarak Power BI görselini AppSource'a gönderme

Görselinizi AppSource'a göndermeden önce **pbiviz** dosyasını ve **pbix** dosyasını e-posta ile Power BI ekibine göndermeniz gerekir. Böylece Power BI ekibi, dosyaları herkese açık paylaşım sunucusuna yükleyebilir. Aksi halde mağaza, dosyaları alamaz. Yeni Power BI görsel gönderimlerini, mevcut Power BI görsellerinin güncelleştirmelerini ve reddedilen gönderimlerin düzeltmelerini içeren dosyaları göndermeniz gerekir.

>[!NOTE]
>[Satıcı Panosu](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store) kullanımdan kaldırılıyor. Bunun yerini [İş Ortağı Merkezi](https://docs.microsoft.com/partner-center/) alıyor. Satıcı Panosu'nu ancak Power BI görselini gönderme işleminin ortasındaysanız kullanın. AppSource'a yeni bir Power BI görseli gönderiyorsanız [İş Ortağı Merkezi yöntemini](office-store.md#submitting-to-appsource) kullanın.

### <a name="seller-dashboard-submission-process"></a>Satıcı Panosu gönderme işlemi

[Office geliştirici merkezinde](https://dev.office.com/) oturum açmak için geçerli bir Office geliştirici hesabına sahip olmanız gerekir. Office geliştirici hesabının Microsoft Hesabı (hotmail.com veya outlook.com gibi) olması gerekir.

1. [Geliştirici merkezine](https://sellerdashboard.microsoft.com/Application/Summary) gidin.

2. **Add a new app** (Yeni uygulama ekle) seçeneğini belirleyin.

    ![Uygulama ekleme](media/office-store/powerbi-custom-visual-add-an-app.png)

3. **Power BI custom visual** (Power BI özel görsel) ve ardından **Next** (İleri) seçeneklerini belirleyin.

4. **App package** (Uygulama paketi) bölümündeki **+** öğesini seçin ve dosya aç iletişim kutusunda Power BI ekibinden gelen uygulama paketi XML dosyasını seçin.

    ![Uygulama paketi](media/office-store/powerbi-custom-visual-apppackage.png)

5. Geçerli bir Power BI uygulama paketi olduğunu belirten bir onay iletisi görmeniz gerekir.

    ![Bildirim onaylandı](media/office-store/powerbi-custom-visual-manifest-approved.png)

6. **General info** (Genel bilgiler) bölümünü doldurun.

   * *Submission title* (Gönderim başlığı): Gönderdiğiniz dosyaya geliştirici merkezinde verilecek ad.
   * *Version* (Sürüm): Sürüm numaranız, eklenti uygulama paketinden otomatik olarak alınır.
   * *Release Date (UTC)* (Sürüm Tarihi (UTC)): Uygulamanızın mağazada yayımlanacağı tarihi seçin. Gelecekteki bir tarihi seçerseniz bu tarihe kadar uygulamanız mağazada yer almaz.
   * *Category* (Kategori): İlk kategori otomatik olarak "Data Visualization + BI" şeklinde belirlenecektir. Tüm Power BI görselleri bu şekilde etiketlenir. Kullanıcılarınızın görselinizi kolayca arayabilmesine yardımcı olmak için iki kategori daha ekleyebilirsiniz.
   * *Test notes* (Test notları): İsteğe bağlıdır, Microsoft'taki test uzmanlarına vermek istediğiniz talimatları buraya yazabilirsiniz
   * *My app calls, supports, contains, or uses cryptography or encryption* (Uygulamam şifreleme çağrısı yapıyor, şifrelemeyi destekliyor, içeriyor veya kullanıyor): İşaretlemeyin
   * *Make this add-in available in the Office add-in catalog on iPad* (Bu eklentiyi iPad üzerindeki Office eklenti kataloğuna ekle): İşaretlemeyin
7. **App logo** (Uygulama logosu) bölümündeki **+** öğesini seçerek görselinizin logosunu yükleyin. Ardından dosya aç iletişim kutusundan simge dosyasını seçin. Dosya .png, .jpg, .jpeg veya .gif biçiminde olmalıdır. Tam olarak 300 piksel (genişlik) x 300 piksel (yükseklik) olmalı ve 512 KB’tan büyük olmamalıdır.

    ![Uygulama logosu](media/office-store/powerbi-custom-visual-app-logo.png)

8. **Support documents** (Destek belgeleri) ayrıntılarını girin.

   * Destek belgesi bağlantısı
   * Gizlilik belgesi bağlantısı
   * Video bağlantısı
   * Son Kullanıcı Lisans Sözleşmesi (EULA)

       EULA dosyası yüklemeniz gerekir. Kendi EULA dosyanızı veya Office Mağazası'ndaki Power BI görsellerine yönelik varsayılan EULA dosyasını kullanabilirsiniz. Varsayılan EULA dosyasını kullanmak için aşağıdaki URL’yi satıcı panosunun "Son Kullanıcı Lisans Sözleşmesi" dosyasını karşıya yükleme iletişim kutusuna yapıştırın: [https://visuals.azureedge.net/app-store/Power BI - Default Custom Visual EULA.pdf](https://visuals.azureedge.net/app-store/Power%20BI%20-%20Default%20Custom%20Visual%20EULA.pdf).

9. **Next**'i (İleri) seçerek **Details** (Ayrıntılar) sayfasına gidin.

10. **Language**'ı (Dil) seçip listeden bir dil belirleyin.

    ![Dil](media/office-store/powerbi-custom-visual-language.png)

11. "Description" (Açıklama) ayrıntılarını girin.

    * *App name (for this language)* (Uygulama adı (bu dil için)): Uygulamanızın başlığını mağazada görünmesini istediğiniz şekilde girin.
    * *Short description* (Kısa açıklama): Mağazada görüntülenmek üzere en fazla 100 karakterlik uygulama açıklaması girin. Bu açıklama üst düzey sayfalarda logoyla birlikte gösterilir. Pbiviz paketindeki açıklamayı kullanabilirsiniz.
    * *Long description* (Uzun açıklama): Müşterilerin uygulama ayrıntıları sayfasında göreceği ayrıntılı uygulama açıklamasını girin. Görselinizi açık kaynak yaparak topluluğun geliştirmesine izin vermek için GitHub gibi herkese açık depo bağlantısını buraya girin.

12. En az bir ekran görüntüsü yükleyin. Bu logo .png, .jpg, .jpeg veya .gif biçiminde olabilir. Tam olarak 1366 piksel (genişlik) x 768 piksel (yükseklik) boyutunda olmalıdır. Dosya boyutu 1024 KB’tan büyük olamaz. *Kullanım kolaylığı sağlamak için ekran görüntülerinde gösterilen önemli özellikleri vurgulayan metin kutuları ekleyin.*

12. Daha fazla dil eklemek istiyorsanız **Add a language** (Dil ekle) seçeneğini belirleyin ve 10-11 arası adımları tekrarlayın. Daha fazla dil eklemek kullanıcılarınızın özel görsel ayrıntılarını kendi dillerinde görüntülemesine yardımcı olur. Listede bulunmayan diller için varsayılan olarak seçilen ilk dil kullanılacaktır.

13. Dil eklemeyi tamamladığınızda **Next**'i (İleri) seçerek **Block access** (Erişimi engelle) sayfasına geçin.

14. Belirli ülke veya bölgelerdeki müşterilerin uygulamanızı kullanmanızı veya satın almasını önlemek istiyorsanız kutuyu işaretleyip listeden seçim yapın.

15. **Next**'i (İleri) seçerek **Pricing** (Fiyatlandırma) sayfasına gidin.

16. Şu anda yalnızca *ücretsiz* görseller desteklenmektedir ve görsel içinde ek satın alma işlemlerine (Uygulama içi satın alma) izin verilmez. **This app is free** (Bu uygulama ücretsizdir) seçeneğini blirleyin.

    > [!NOTE]
    > Ücretsiz dışında bir seçenek belirlerseniz veya gönderilen görselde Uygulama içi satın alma varsa gönderim reddedilir.

17. Bu adımda **Save as draft** (Taslak olarak kaydet) seçeneğini belirleyip daha sonra gönderebilir veya **Submit for approval** (Onay için gönder) seçeneğini belirleyerek özel görselinizi Office Mağazası’na gönderebilirsiniz.

## <a name="seller-dashboard-certification-submission-process"></a>Satıcı Panosu sertifikasyon gönderme işlemi

Satıcı Panosu'nda Power BI görselinizi sertifikasyon amacıyla göndermek için bu bölümdeki yönergeleri izleyin. Daha önce Power BI görselini Satıcı Panosu'nu kullanarak AppSource'a gönderirken, bu yöntemi kullanın.

1. Power BI görselleri destek ekibine (pbicvsupport@microsoft.com) bir e-posta gönderin. E-postada aşağıdaki bilgileri verin:
    * Başlık: Görsel Sertifikasyon Talebi
    * İnsanlar tarafından okunabilir kaynak kodunun bulunduğu GitHub deposu bağlantısı
    * [Gereksinimlere uygunluk](power-bi-custom-visuals-certified.md#certification-requirements)
    * Kod incelemesini geçme

2. Microsoft Power BI görselleri ekibi, Power BI görseliniz sertifikalandığında ve [sertifikalı Power BI görselleri](power-bi-custom-visuals-certified.md#certified-power-bi-visuals) listesine eklendiğinde ya da reddedilmesi durumunda düzeltilmesi gereken sorunların yer aldığı bir raporla sizi bilgilendirir. Microsoft ile açık bir iletişim hattı kurmak ve sertifikalı görsellerini gerektiği şekilde güncelleştirmek geliştiricinin sorumluluğundadır.

## <a name="tracking-submission-status-and-usage"></a>Gönderme ve kullanma durumu takibi

[Doğrulama ilkelerini](https://dev.office.com/officestore/docs/validation-policies#13-power-bi-custom-visuals) inceleyebilirsiniz.

Uygulamayı gönderdikten sonra durumunu [uygulama panosu](https://sellerdashboard.microsoft.com/Application/Summary/) sayfasından görüntüleyebilirsiniz.

## <a name="certify-your-visual"></a>Görselinizi onaylatma

Görseliniz oluşturulduktan sonra isterseniz görselinizi [sertifikalayabilirsiniz](../developer/power-bi-custom-visuals-certified.md).

## <a name="next-steps"></a>Sonraki adımlar

[Power BI özel görseli geliştirme](visuals/custom-visual-develop-tutorial.md)  
[Power BI'daki Görselleştirmeler](../visuals/power-bi-report-visualizations.md)  
[Power BI'daki Özel Görselleştirmeler](../developer/power-bi-custom-visuals.md)  
[Power BI görselini sertifikalama](../developer/power-bi-custom-visuals-certified.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
