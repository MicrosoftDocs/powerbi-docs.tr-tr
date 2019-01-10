---
title: Raporu güvenli bir portala veya web sitesine ekleme
description: Power BI güvenli ekleme özelliğiyle, kullanıcılarınızın raporları kolayca ve güvenle dahili web portallarına eklemesini sağlayabilirsiniz.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/08/2019
LocalizationGroup: Share your work
ms.openlocfilehash: 81f6d77543ec53ac790f5c5183da32bde80fd6b9
ms.sourcegitcommit: b3af4f7ef486c95cea173caea5a31d0472816ddd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54136856"
---
# <a name="embed-a-report-in-a-secure-portal-or-website"></a>Raporu güvenli bir portala veya web sitesine ekleme

Power BI'da raporlara yönelik yeni güvenli **Ekle** seçeneği, kullanıcıların **web tabanlı** veya **barındırılan şirket içi** (SharePoint 2019 gibi) olması fark etmeksizin dahili web portallarına kolayca ve güvenle rapor ekleyebilmesine olanak tanır. Bu yolla eklenen raporlarda satır düzeyi güvenlik (RLS) aracılığıyla tüm öğe izinlerine ve veri güvenliğine uyulur. Özellik, URL veya iFrame eklemeyi kabul eden hiçbir portala kod eklenmesine izin vermeyecek şekilde tasarlanmıştır.

**Ekle** seçeneği [URL Filtrelerini](service-url-filters.md) ve URL ayarlarını da destekler. **Ekle** seçeneği, temel düzeyde HTML ve JavaScript bilgisi gerektiren alt düzey kod yaklaşımını kullanarak portallarla tümleştirmenize olanak tanır.

## <a name="how-to-embed-power-bi-reports-into-portals"></a>Power BI raporlarını portallara **ekleme**

1. Power BI hizmetinde raporlara yönelik yeni **Ekle** seçeneği **Dosya** menüsünde sağlanır.

    ![Güvenli Ekle seçeneği açılan menüsü](media/service-embed-secure/secure-embed-drop-down-menu.png)

2. Raporu güvenle eklemek için kullanılacak bir bağlantı ve iFrame sağlayan iletişim kutusunu açmak için Ekle seçeneğini belirtin.

    ![Ekle seçeneği iletişim kutusu](media/service-embed-secure/secure-embed-code-dialog.png)

3. URL'nizi web portalınıza ekledikten sonra veya URL'yi doğrudan açmanız durumunda, rapora erişim verilmeden önce kullanıcının kimliği doğrulanır. Aşağıda, kullanıcı tarayıcı oturumunda Power BI'da oturum açmamıştır. **Oturum Aç**'a bastığında, yeni bir tarayıcı penceresinin veya sekmesinin açılması gerekebilir. Oturum açmanız istenmezse açılır pencere engelleyicilerini denetleyin.

    ![Bu raporu görüntülemek için oturum açın](media/service-embed-secure/secure-embed-sign-in.png)

4. Kullanıcı oturum açtıktan sonra rapor açılır. Burada veriler gösterilir ve kullanıcıların sayfalar arasında gezinmesine ve filtreler ayarlamasına olanak sağlanır. Rapor yalnızca Power BI'da raporu görüntüleme izni olan kullanıcılara gösterilir. Tüm satır düzeyi güvenlik (RLS) kuralları da uygulanır. Son olarak, kullanıcının doğru bir biçimde lisanslanmış olması gerekir. Power BI Pro lisansı gereklidir veya rapor bir Power BI Premium kapasitesinde yer alan bir çalışma alanında olmalıdır. Kullanıcı açtığı her yeni tarayıcı penceresinde oturum açmalıdır ama bir kez oturum açtıktan sonra diğer raporlar otomatik olarak yüklenir.

    ![Raporu ekleme](media/service-embed-secure/secure-embed-report.png)

5. iFrame seçeneği kullanılırken, sağlanan HTML'yi düzenleyerek portalınızın web sayfasına sığabilmesi için gereken yüksekliği ve genişliği belirtmeniz faydalı olacaktır.

    ![Yüksekliği ve genişliği ayarlama](media/service-embed-secure/secure-embed-size.png)

## <a name="granting-access-to-reports"></a>Raporlara yönelik erişim izni verme

Ekle seçeneği kullanıcıların raporu görüntülemesine otomatik olarak izin vermez. Raporu görüntüleme izinleri Power BI hizmetinde ayarlanır.

Power BI hizmetinin içinde rapora erişim sağlamak için, eklenen raporu buna erişmesi gereken kullanıcılarla paylaşabilirsiniz. Office 365 Grubu kullanıyorsanız, kullanıcıyı Power BI hizmetindeki uygulama çalışma alanının bir üyesi olarak listeleyebilirsiniz. Daha fazla bilgi için bkz. [Bir uygulama çalışma alanını yönetme](service-manage-app-workspace-in-power-bi-and-office-365.md).

## <a name="licensing"></a>Lisanslama

Eklenen raporu görüntüleyen kullanıcıların Power BI Pro lisansına sahip olması veya içeriğin bir [Power BI Premium kapasitesinde (EM veya P SKU)](service-admin-premium-purchase.md) bulunması gerekir.

## <a name="customize-your-embed-experience-using-url-settings"></a>URL ayarlarını kullanarak ekleme deneyiminizi özelleştirme

Ekleme URL'si, kullanıcı deneyiminizi özelleştirmenize yardımcı olacak çeşitli giriş ayarlarını destekler. Sağlanan iFrame'i kullanıyorsanız, iFrame'in src ayarlarında URL'yi güncelleştirdiğinizden emin olun.

| Özellik  | Açıklama  |  |  |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| pageName  | **pageName** sorgu dizesi parametresini, raporun hangi sayfasının açılacağını ayarlamak için kullanabilirsiniz. Aşağıda gösterildiği gibi, rapor Power BI hizmetinde görüntülenirken **pageName** değeri rapor URL'sinin son bölümüne karşılık gelir. |  |  |  |
| URL Filtreleri  | Eklemenin içeriğini filtrelemek için Power BI kullanıcı arabirimden aldığınız ekleme URL'sinde [URL Filtreleri](service-url-filters.md) kullanabilirsiniz. Bu şekilde, yalnızca temel düzeyde bir HTML ve JavaScript deneyimiyle alt düzey kod tümleştirmeleri oluşturabilirsiniz.  |  |  |  |

## <a name="set-which-page-opens-when-the-report-is-embedded"></a>Rapor eklendiğinde hangi sayfanın açılacağını ayarlama

*pageName* ayarında sağlanan değer, rapor Power BI hizmetinde görüntülenirken rapor URL'sinin son bölümüne karşılık gelir.

1. Raporu web tarayıcınızda Power BI hizmetinde açın ve adres çubuğundan URL'yi kopyalayın.

    ![Rapor bölümü](media/service-embed-secure/secure-embed-report-section.png)

2. *pageName* ayarını URL'nin sonuna ekleyin.

    ![PageName ayarını ekleme](media/service-embed-secure/secure-embed-append-page-name.png)

## <a name="filter-report-content-using-url-filters"></a>URL filtrelerini kullanarak rapor içeriğini filtreleme

Bazı gelişmiş özellikler için, [URL Filtreleri](service-url-filters.md) kullanarak raporun kullanımında başka deneyimler de oluşturabilirsiniz. Örneğin aşağıdaki URL, Enerji sektörüne ilişkin verileri gösterecek şekilde raporu filtreler.

**pageName** ile [URL Filtreleri](service-url-filters.md)'nin birlikte kullanılması güçlü bir sonuç verebilir. Temel HTML ve JavaScript kullanarak deneyimler oluşturabilirsiniz.

Örneğin, aşağıda gösterildiği gibi HTML sayfasına bir düğme ekleyebilirsiniz:

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

Düğmeye basıldığında, iFrame'i Enerji sektörü filtresini içeren güncelleştirilmiş bir URL ile güncelleştiren bir işlev çağrılır.

```javascript
function show(pageName, filterValue)

{

var newUrl = baseUrl + "&pageName=" + pageName;

if(null != filterValue && "" != filterValue)

{

newUrl += "&$filter=Industries/Industry eq '" + filterValue + "'";

}

//Assumes there’s an iFrame on the page with id=”iFrame”

var report = document.getElementById("iFrame")

report.src = newUrl;

}
```

![Filtrele](media/service-embed-secure/secure-embed-filter.png)

Alt düzey kodlu özel bir deneyim oluşturmak için istediğiniz kadar çok düğme ekleyebilirsiniz. 

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Azure işletmeler arası (B2B) ile dışarıdan konuk kullanıcıları desteklemez.

* Güvenli ekleme özelliği Power BI hizmetinde yayımlanmış olan raporlarda çalışır.

* Kullanıcı her yeni tarayıcı penceresini açtığında raporu görüntülemek için oturum açmalıdır.

* Bazı tarayıcılarda, özellikle de InPrivate veya Incognito modları kullanıldığında oturum açtıktan sonra sayfayı yenilemeniz gerekir.

* Çoklu oturum açma deneyiminden yararlanabilmek için, SharePoint Online'da Ekle seçeneğini kullanın veya [verilerin kullanıcıya ait olması](developer/embed-sample-for-your-organization.md) yaklaşımını kullanarak özel tümleştirme oluşturun. [Verilerin kullanıcıya ait olması](developer/embed-sample-for-your-organization.md) hakkında daha fazla bilgi edinin.

* **Ekle** seçeneğiyle birlikte sağlanan otomatik kimlik doğrulama özelliği Power BI JavaScript API’si ile çalışmaz. Power BI JavaScript API'sinde, ekleme için [verilerin kullanıcıya ait olması](developer/embed-sample-for-your-organization.md) yaklaşımını kullanın. [Verilerin kullanıcıya ait olması](developer/embed-sample-for-your-organization.md) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar

* [Çalışmanızı paylaşmanın yolları](service-how-to-collaborate-distribute-dashboards-reports.md)

* [URL filtreleri](service-url-filters.md)

* [SharePoint Online rapor web bölümü](service-embed-report-spo.md)

* [Web'de yayımlama](service-publish-to-web.md)