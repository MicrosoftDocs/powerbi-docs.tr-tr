---
title: SharePoint Online'da rapor web bölümüyle ekleme
description: Power BI'ın SharePoint Online'a yönelik yeni rapor web bölümü ile etkileşimli Power BI raporlarını SharePoint Online sayfalarına kolayca ekleyebilirsiniz.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 10/20/2018
ms.openlocfilehash: e336323863dfacc8c74f2dc1f721231d58d03834
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50100784"
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>SharePoint Online'da rapor web bölümüyle ekleme

Power BI'ın SharePoint Online'a yönelik yeni rapor web bölümü ile etkileşimli Power BI raporlarını SharePoint Online sayfalarına kolayca ekleyebilirsiniz.

Yeni **SharePoint Online'a ekle** seçeneğini kullandığınızda, eklenen raporlar tamamen güvenli olduğu için kolayca güvenli iç portal oluşturabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**SharePoint Online'a ekle** seçeneği kullanılarak eklenen raporlarının çalışması için birkaç gereksinim vardır.

* Power BI Pro lisansına veya Power BI lisansı ile [Power BI Premium kapasitesine (EM veya P SKU)](service-premium.md#premium-capacity-nodes) sahip olmanız gerekir.
* SharePoint Online'a yönelik Power BI web bölümü için [Modern Sayfalar](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b) gereklidir.

## <a name="embed-your-report"></a>Raporunuzu ekleme

Raporunuzu SharePoint Online'a eklemek için öncelikle raporun URL'sini alıp bu URL'yi SharePoint Online'daki yeni Power BI web bölümünde kullanmanız gerekir.

### <a name="get-a-url-to-your-report"></a>Raporunuzun URL'sini alma

1. Raporu Power BI hizmetinde görüntüleyin.

2. **Dosya** menü öğesini seçin.

3. **SharePoint Online'a ekle**'yi seçin.

    ![Dosya menüsü](media/service-embed-report-spo/powerbi-file-menu.png)

4. İletişim kutusundaki URL'yi kopyalayın.

    ![Ekleme bağlantısı](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Power BI raporunu bir SharePoint Online sayfasına ekleme

1. SharePoint Online'da raporu eklemek istediğiniz sayfayı açıp **Düzenle**'yi seçin.

    ![SP düzenleme sayfası](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    Alternatif olarak, SharePoint Online'da **+ Yeni**'yi seçerek yeni bir modern site oluşturabilirsiniz.

    ![SP yeni sayfa](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. **+** öğesini ve **Power BI** web bölümünü seçin.

    ![SP yeni web bölümü](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. **Rapor ekle**'yi seçin.

    ![SP yeni rapor](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)

4. Rapor URL'sini özellik bölmesine yapıştırın. Bu rapor URL’si, yukarıdaki adımlarda kopyaladığınız URL’dir. Rapor otomatik olarak yüklenir.

    ![SP yeni web bölümü özellikleri](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. SharePoint Online kullanıcılarınızın bu değişikliği görebilmesi için **Yayımla**'yı seçin.

    ![SP rapor yüklendi](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="granting-access-to-reports"></a>Raporlara yönelik erişim izni verme

Bir raporu SharePoint Online'a eklediğinizde kullanıcılara raporu görüntüleme izni otomatik olarak verilmez. Raporu görüntüleme izinleri Power BI hizmetinde ayarlanır.

> [!IMPORTANT]
> Power BI hizmetinde, raporu görebilecek olan kullanıcıları belirleyip listede olmayanlara erişim izni vermeyi unutmayın.

Power BI hizmetinde rapora yönelik erişim izni vermek için kullanabileceğiniz iki yöntem vardır. SharePoint Online ekip sitenizi oluşturmak için bir Office 365 Grubu kullanıyorsanız kullanıcıyı, **Power BI hizmetindeki ve uygulama çalışma alanının** ve **SharePoint sayfasının** bir üyesi olarak eklersiniz. Bu sayede kullanıcılar söz konusu grubun içeriğini görüntüleyebilir. Daha fazla bilgi için bkz. [Power BI'da uygulama oluşturma ve dağıtma](service-create-distribute-apps.md).

Alternatif olarak raporu bir uygulamaya ekleyerek kullanıcılarla doğrudan paylaşabilirsiniz. Raporun eklenmesi için uygulamanın önceden yüklenmiş olması gerekir. **Uygulamayı otomatik olarak yükleme** özelliğini kullanarak önceden yüklenecek uygulamayı belirleyebilirsiniz.

   ![Uygulamayı otomatik olarak yükle](media/service-embed-report-spo/install-app-automatically.png)

> [!NOTE]
> **Kullanıcının SharePoint sayfasındaki raporu görebilmesi için hem SharePoint sayfasına hem de rapora erişim sahibi olması gerekir.**

## <a name="multi-factor-authentication"></a>Çok faktörlü kimlik doğrulaması

Power BI ortamınızda oturum açmak için çok faktörlü kimlik doğrulaması kullanmanız gerekiyorsa kimliğinizi doğrulamak için bir güvenlik cihazıyla oturum açmanız istenebilir. Bu durum SharePoint Online oturumunuzu çok faktörlü kimlik doğrulaması kullanmadan açmış olmanız ancak Power BI ortamınızın, güvenlik cihazıyla doğrulanmış bir hesap istemesi durumunda ortaya çıkar.

> [!NOTE]
> Çok faktörlü kimlik doğrulaması henüz Azure Active Directory 2.0 sürümünde desteklenmemektedir. Kullanıcılar *hata* ifadesini içeren bir iletiyle karşılaşır. Kullanıcı, güvenlik cihazını kullanarak SharePoint Online oturumu açması halinde raporu görüntüleyebilir.

## <a name="web-part-settings"></a>Web bölümü ayarları

Aşağıda, SharePoint Online'a yönelik Power BI web bölümü için yapılabilecek ayarların açıklamalarına yer verilmiştir.

![SP web bölümü özellikleri](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| Özellik | Açıklama |
| --- | --- |
| Sayfa adı |Web bölümü tarafından gösterilen varsayılan sayfayı ayarlar. Açılan listeden bir değer seçin. Herhangi bir sayfa görüntülenmiyorsa raporunuzda tek sayfa vardır veya yapıştırdığınız URL bir sayfa adı içeriyordur. Belirli bir sayfayı seçmek için URL'deki rapor bölümünü kaldırın. |
| Görüntüle |Bu seçenek, raporun SharePoint Online sayfasına nasıl yerleştirileceğini ayarlamanızı sağlar. |
| Gezinti Bölmesini Göster |Gezinti bölmesini gösterir veya gizler. |
| Filtre Bölmesini Göster |Filtre bölmesini gösterir veya gizler. |

## <a name="reports-that-do-not-load"></a>Yüklenmeyen raporlar

Raporunuz, Power BI web bölümünde yüklenmeyebilir ve aşağıdaki ileti görüntülenebilir.

*Bu içerik kullanılamıyor.*

![Rapor bulunamadı iletisi](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

Bu iletinin iki olası nedeni vardır.

1. Rapora erişiminiz yoktur.
2. Rapor silinmiştir.

Sorunu çözmenize yardımcı olması için SharePoint Online sayfasının sahibiyle iletişime geçin.

## <a name="licensing"></a>Lisanslama

SharePoint’te rapor görüntüleyen kullanıcıların bir **Power BI Pro lisansına** sahip olması veya içeriğin bir **[Power BI Premium kapasitesinde (EM veya P SKU)](service-admin-premium-purchase.md)** bulunması gerekir.

## <a name="known-issues-and-limitations"></a>Bilinen sorunlar ve sınırlamalar

* Error: "An error occurred, please try logging out and back in and then revisiting this page. Bağıntı kimliği: tanımsız, http yanıtı durumu: 400, sunucu hata kodu 10001, ileti: Yenileme belirteci eksik"
  
  Bu hatayı almaya devam ederseniz aşağıdaki sorun giderme adımlarından birini deneyin.
  
  1. SharePoint oturumunuzu kapatıp tekrar açın. Tekrar oturum açmadan önce tüm tarayıcı pencerelerini kapattığınızdan emin olun.

  2. Kullanıcı hesabınız için çok faktörlü kimlik doğrulaması (MFA) kullanmanız gerekiyorsa SharePoint oturumunuzu, çok faktörlü kimlik doğrulaması cihazınızı (telefon uygulaması, akıllı kart vb.) kullanarak açtığınızdan emin olun.
  
  3. Azure B2B Konuk kullanıcı hesapları desteklenmez. Kullanıcılar bölümün yüklendiğini gösteren Power BI logosunu görür, ancak rapor gösterilmez.

* Power BI, SharePoint Online ile aynı yerelleştirilmiş dilleri desteklemez. Bu nedenle, eklenen rapordaki yerelleştirme doğru olmayabilir.

* Internet Explorer 10 kullanıyorsanız sorunlarla karşılaşabilirsiniz. [Office 365](https://products.office.com/office-system-requirements#Browsers-section) ve [Power BI için tarayıcı desteği](consumer/end-user-browsers.md) sayfalarına bakabilirsiniz.

* Power BI web bölümü [bağımsız bulutlar](https://powerbi.microsoft.com/en-us/clouds/) için kullanılamaz.

* Klasik SharePoint Sunucusu bu web bölümü ile desteklenmez.

* [URL filtreleri](service-url-filters.md), SPO web bölümü ile desteklenmez.

## <a name="next-steps"></a>Sonraki adımlar

[Son kullanıcıların modern site oluşturmasına izin verme veya bunu engelleme](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
[Power BI'da uygulama oluşturma ve dağıtma](service-create-distribute-apps.md)  
[Panoları iş arkadaşlarınızla ve diğer kişilerle paylaşma](service-share-dashboards.md)  
[Power BI Premium nedir?](service-premium.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)