---
title: "Özel görselleri Office Mağazası'nda yayımlama"
description: "Özel görselinizi diğer kullanıcıların keşfetmesi ve kullanması amacıyla Office Mağazası'nda nasıl yayımlayacağınızı öğrenin."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/20/2017
ms.author: asaxton
ms.openlocfilehash: 13456711e6c3bdce4554df7b7fbc0e4e9943987a
ms.sourcegitcommit: 12236d08c27c7ee3fabb7ef9d767e9dee693f8aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="publish-custom-visuals-to-the-office-store"></a>Özel görselleri Office Mağazası'nda yayımlama
Özel görselinizi diğer kullanıcıların keşfetmesi ve kullanması amacıyla Office Mağazası'nda nasıl yayımlayacağınızı öğrenin.

Özel görselinizi oluşturduktan sonra diğer kullanıcıların keşfetmesi ve kullanması amacıyla Office Mağazası'nda yayımlamak isteyebilirsiniz. Bu işlemi gerçekleştirmeden önce yapmanız gereken hazırlıklar vardır. Özel görsel oluşturma hakkında daha fazla bilgi için bkz. [Özel görseller oluşturmak için geliştirici araçları kullanma](../service-custom-visuals-getting-started-with-developer-tools.md).

![](media/office-store/powerbi-custom-visual-store.png)

Office Mağazası nedir? Kısaca, Office 365 yazılımınız için uygulamalar (eklenti) bulabileceğiniz yerdir. [Office Mağazası](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) milyonlarca Office 365 kullanıcısını, işlerini hiç olmadığı kadar verimli, bilinçli veya iyi bir şekilde gerçekleştirmelerine yardımcı olacak çözümlere bağlar.

## <a name="preparing-to-submit-your-custom-visual"></a>Özel görselinizi göndermek için hazırlanma
Özel görselinizi kodlamayı ve test etmeyi tamamlayıp pbiviz dosyası şeklinde paketledikten sonra aşağıdaki gönderim için gerekli bilgilere sahip olmanız gerekir.

| Öğe | Gerekli | Açıklama |
| --- | --- | --- |
| Pbiviz paketi gerekli tüm meta verileri içeriyor |Evet |Görsel adı<br>Görünen ad<br>GUID<br>Sürüm<br>Açıklama<br>Yazarın adı ve e-posta adresi |
| Örnek .pbix rapor dosyası |Evet |Görselinizi sergilemek için kullanıcıların görselle tanışmasına yardımcı olmanız gerekir. Görselin kullanıcıya kattığı değere odaklanmanız ve kullanım, biçimlendirme seçenekleri gibi alanlarda örnekler vermeniz gerekir. En sona ekleyeceğiniz *"ipuçları"* sayfasına püf noktalarını, dikkat edilmesi gerekenleri ve benzer bilgileri girebilirsiniz. |
| Simge |Evet |Mağazada görünecek özel görsel logosunu eklemeniz gerekir. Bu logo .png, .jpg, .jpeg veya .gif biçiminde olabilir. Boyutu tam olarak 300 piksel (genişlik) x 300 piksel (yükseklik) olmalıdır. Dosya boyutu 512 KB'tan büyük olamaz. |
| Ekran görüntüleri |Evet |En az bir ekran görüntüsü eklemeniz gerekir. Bu logo .png, .jpg, .jpeg veya .gif biçiminde olabilir. Boyutu tam olarak 1366 piksel (genişlik) x 768 piksel (yükseklik) olmalıdır. Dosya boyutu 1024 KB'tan büyük olamaz. *Kullanım kolaylığı sağlamak için ekran görüntülerinde gösterilen önemli özellikleri vurgulayan metin kutuları ekleyin.* |
| Destek indirme bağlantısı |Evet |Görselinizle sorun yaşayan müşterilerin destek için ulaşabileceği URL'yi girin. URL'niz https:// veya http:// ile başlamalıdır. |
| Gizlilik belgesi bağlantısı |Evet |Görselinizi kullanmak isteyen müşterilerin inceleyebileceği gizlilik ilkesinin bağlantısını girin. Bağlantınız http:// veya https:// ile başlamalıdır. |
| Son kullanıcı lisans sözleşmesi (EULA) |Evet |EULA dosyası yüklemeniz gerekir. Kendi EULA dosyanızı veya Office Mağazası'ndaki Power BI özel görsellerine yönelik varsayılan EULA dosyasını kullanabilirsiniz. Varsayılan EULA dosyasını kullanmak için aşağıdaki URL'yi satıcı panosunun "Son Kullanıcı Lisans Sözleşmesi" dosyası yükleme iletişim kutusuna yapıştırın: [https://visuals.azureedge.net/app-store/Power BI - Default Custom Visual EULA.pdf](https://visuals.azureedge.net/app-store/Power BI - Default Custom Visual EULA.pdf). |
| Video bağlantısı |Hayır |Kullanıcıların dikkatini özel görselinize çekmek için görselinizle ilgili bir videonun bağlantısını eklemeniz önerilir. URL'niz https:// veya http:// ile başlamalıdır. |
| GitHub deposu |Hayır |Geliştiricilerin kodunuzla ilgili geri bildirim sağlamasını ve geliştirme önermesini sağlamak için görselinizin kaynağının ve örnek verilerin bulunduğu geçerli ve herkese açık [GitHub](https://www.github.com) deposu bağlantısına sahip olmanız önerilir. |

## <a name="submitting-to-power-bi"></a>Power BI'a gönderme
Gönderme süreci Power BI özel görseller gönderim ekibine gönderilen bir e-posta ile başlar. E-postayı [pbivizsubmit@microsoft.com](mailto:pbivizsubmit@microsoft.com) adresine gönderebilirsiniz.

E-postanıza .pbiviz dosyasını ve örnek rapor .pbix dosyanızı ekleyin. Power BI ekibi yanıt olarak talimatları ve yüklenecek uygulama paketi XML dosyasını gönderecektir. Görselinizi Office Geliştirici Merkezi'nden göndermek için bu XML uygulama paketini kullanmanız gerekir.

> [!NOTE]
> Kaliteyi yükseltmek ve var olan raporların hata vermemesini sağlamak için var olan görsellerde yapılan güncelleştirmelerin mağaza onayından geçtikten sonra üretim ortamına ulaşması fazladan 2 hafta sürecektir.
> 
> 

## <a name="submitting-to-the-office-store"></a>Office Mağazası'na gönderme
Power BI ekibinin gönderdiği uygulama paketi XML dosyasını aldıktan sonra [Office Geliştirici Merkezi](https://sellerdashboard.microsoft.com/Application/Summary)'ne giderek görselinizi Office Mağazası'na gönderebilirsiniz.

> [!NOTE]
> [Office Geliştirici Merkezi](https://dev.office.com/)'nde oturum açmak için geçerli bir Office geliştirici hesabına sahip olmanız gerekir. Office geliştirici hesabının Microsoft Hesabı (hotmail.com veya outlook.com gibi Live ID) olması gerekir.
> 
> [!IMPORTANT]
> Görselinizi Office Mağazası'na göndermeden önce .pbiviz ve .pbix dosyasını e-posta ile Power BI ekibine göndermeniz gerekir. Power BI ekibi dosyaları herkese açık paylaşım sunucusuna yükleyecektir. Aksi halde Office Mağazası dosyaları alamayacaktır. Yeni bir görsel gönderirken, var olan görseli güncelleştirirken veya Office Mağazası tarafından reddedilen görselleri düzeltirken dosyaları göndermeniz gerekir.
> 
> 

### <a name="process-to-submit-visual"></a>Görsel gönderme işlemi
Gönderim işlemini tamamlamak için aşağıdaki adımları uygulayın.

1. **Add a new app** (Yeni uygulama ekle) seçeneğini belirleyin.
   
    ![](media/office-store/powerbi-custom-visual-add-an-app.png)
2. **Power BI custom visual** (Power BI özel görsel) ve ardından **Next** (İleri) seçeneklerini belirleyin.
3. **App package** (Uygulama paketi) bölümündeki **+** öğesini seçin ve dosya aç iletişim kutusunda Power BI ekibinden gelen uygulama paketi XML dosyasını seçin.
   
    ![](media/office-store/powerbi-custom-visual-apppackage.png)
4. Geçerli bir Power BI uygulama paketi olduğunu belirten bir onay iletisi görmeniz gerekir.
   
    ![](media/office-store/powerbi-custom-visual-manifest-approved.png)
5. **General info** (Genel bilgiler) bölümünü doldurun.
   
   * *Submission title* (Gönderim başlığı): Gönderdiğiniz dosyaya geliştirici merkezinde verilecek ad
   * *Version* (Sürüm): Sürüm numaranız, eklenti uygulama paketinden otomatik olarak alınır.
   * *Release Date (UTC)* (Sürüm Tarihi (UTC)): Uygulamanızın mağazada yayımlanacağı tarihi seçin. Gelecekteki bir tarihi seçerseniz bu tarihe kadar uygulamanız mağazada yer almaz.
   * *Category* (Kategori): İlk kategori otomatik olarak "Data Visualization + BI" şeklinde belirlenecektir. Tüm Power BI özel görselleri bu şekilde etiketlenir. Kullanıcılarınızın görselinizi kolayca bulmasına yardımcı olmak için 2 ek kategori ekleyebilirsiniz
   * *Test notes* (Test notları): İsteğe bağlıdır, Microsoft'taki test uzmanlarına vermek istediğiniz talimatları buraya yazabilirsiniz
   * *My app calls, supports, contains, or uses cryptography or encryption* (Uygulamam şifreleme çağrısı yapıyor, şifrelemeyi destekliyor, içeriyor veya kullanıyor): İşaretlemeyin
   * *Make this add-in available in the Office add-in catalog on iPad* (Bu eklentiyi iPad üzerindeki Office eklenti kataloğuna ekle): İşaretlemeyin
6. **App logo** (Uygulama logosu) bölümündeki **+** öğesini seçerek görselinizin logosunu yükleyin. Ardından dosya aç iletişim kutusundan simge dosyasını seçin. Dosya .png, .jpg, .jpeg veya .gif biçiminde olmalıdır. Tam olarak 300 piksel (genişlik) x 300 piksel (yükseklik) olmalı ve 512 KB'tan büyük olmamalıdır.
   
    ![](media/office-store/powerbi-custom-visual-app-logo.png)
7. **Support documents** (Destek belgeleri) ayrıntılarını girin.
   
   * Destek belgesi bağlantısı
   * Gizlilik belgesi bağlantısı
   * Video bağlantısı
   * Son Kullanıcı Lisans Sözleşmesi (EULA)
     
       EULA dosyası yüklemeniz gerekir. Kendi EULA dosyanızı veya Office Mağazası'ndaki Power BI özel görsellerine yönelik varsayılan EULA dosyasını kullanabilirsiniz. Varsayılan EULA dosyasını kullanmak için aşağıdaki URL'yi satıcı panosunun "Son Kullanıcı Lisans Sözleşmesi" dosyası yükleme iletişim kutusuna yapıştırın: [https://visuals.azureedge.net/app-store/Power BI - Default Custom Visual EULA.pdf](https://visuals.azureedge.net/app-store/Power BI - Default Custom Visual EULA.pdf).
8. **Next**'i (İleri) seçerek **Details** (Ayrıntılar) sayfasına gidin.
9. **Language**'ı (Dil) seçip listeden bir dil belirleyin.
   
    ![](media/office-store/powerbi-custom-visual-language.png)
10. "Description" (Açıklama) ayrıntılarını girin.
    
    * *App name (for this language)* (Uygulama adı (bu dil için)): Uygulamanızın adını mağazada görünmesini istediğiniz şekilde girin.
    * *Short description* (Kısa açıklama): Mağazada görüntülenmek üzere en fazla 100 karakterlik uygulama açıklaması girin. Bu açıklama üst düzey sayfalarda logoyla birlikte gösterilir. Pbiviz paketindeki açıklamayı kullanabilirsiniz.
    * *Long description* (Uzun açıklama): Müşterilerin uygulama ayrıntıları sayfasında göreceği ayrıntılı uygulama açıklamasını girin. Görselinizi açık kaynak yaparak topluluğun geliştirmesine izin vermek için GitHub gibi herkese açık depo bağlantısını buraya girin.
11. En az bir ekran görüntüsü yükleyin. Bu logo .png, .jpg, .jpeg veya .gif biçiminde olabilir. Boyutu tam olarak 1366 piksel (genişlik) x 768 piksel (yükseklik) olmalıdır. Dosya boyutu 1024 KB'tan büyük olamaz. *Kullanım kolaylığı sağlamak için ekran görüntülerinde gösterilen önemli özellikleri vurgulayan metin kutuları ekleyin.*
12. Daha fazla dil eklemek istiyorsanız **Add a language** (Dil ekle) seçeneğini belirleyin ve 10-11 arası adımları tekrarlayın. Daha fazla dil eklemek kullanıcılarınızın özel görsel ayrıntılarını kendi dillerinde görüntülemesine yardımcı olur. Listede bulunmayan diller için varsayılan olarak seçilen ilk dil kullanılacaktır.
13. Dil eklemeyi tamamladığınızda **Next**'i (İleri) seçerek **Block access** (Erişimi engelle) sayfasına geçin.
14. Belirli ülke veya bölgelerdeki müşterilerin uygulamanızı kullanmanızı veya satın almasını önlemek istiyorsanız kutuyu işaretleyip listeden seçim yapın.
15. **Next**'i (İleri) seçerek **Pricing** (Fiyatlandırma) sayfasına gidin.
16. Şu anda yalnızca *ücretsiz* görseller desteklenmektedir ve görsel içinde ek satın alma işlemlerine (Uygulama içi satın alma) izin verilmez. **This app is free** (Bu uygulama ücretsizdir) seçeneğini blirleyin. 
    
    > [!NOTE]
    > Ücretsiz dışında bir seçenek belirlerseniz veya gönderilen görselde Uygulama içi satın alma varsa gönderim reddedilir.
    > 
    > 
17. Bu adımda "Save as draft"ı (Taslak olarak kaydet) seçip daha sonra gönderebilir veya **Submit for approval**'ı (Onay için gönder) seçerek özel görselinizi Office Mağazası'na gönderebilirsiniz.

## <a name="tracking-submission-status-and-usage"></a>Gönderme ve kullanma durumu takibi
[Doğrulama ilkelerini](https://dev.office.com/officestore/docs/validation-policies#13-power-bi-custom-visuals) inceleyebilirsiniz.

Uygulamayı gönderdikten sonra durumunu [uygulama panosu](https://sellerdashboard.microsoft.com/Application/Summary/) sayfasından görüntüleyebilirsiniz.

## <a name="certify-your-visual"></a>Görselinizi onaylatma
Görselinizi oluşturduktan sonra isterseniz sertifikalatabilirsiniz. Sertifikalatmanız durumunda görseliniz Power BI hizmetinde çalışabilir ve PowerPoint'e aktarma gibi diğer özelliklerle birlikte kullanılabilir. Daha fazla bilgi için bkz. [Özel görselleri *sertifikalatma*](../power-bi-custom-visuals-certified.md).

## <a name="next-steps"></a>Sonraki adımlar
[Özel görseller oluşturmak için geliştirici araçları kullanma](../service-custom-visuals-getting-started-with-developer-tools.md)  
[Power BI'daki görselleştirmeler](../power-bi-report-visualizations.md)  
[Power BI'daki Özel Görselleştirmeler](../power-bi-custom-visuals.md)  
[Özel görselleri *sertifikalatma*](../power-bi-custom-visuals-certified.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

