---
title: Power BI Desktop'taki Rapor Görünümü
description: Power BI Desktop'taki Rapor Görünümü
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/19/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 06b8c9d0be2ec8bc5b350767263bfc5e0ab4ec81
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73877860"
---
# <a name="report-view-in-power-bi-desktop"></a>Power BI Desktop'taki Rapor Görünümü
Power BI'a aşinaysanız, verilerinize dinamik bakış açıları ve öngörüler kazandıran raporlar oluşturmanın ne kadar kolay olduğunu biliyorsunuz demektir. Power BI, Power BI Desktop'ta daha gelişmiş özelliklere de sahiptir. Power BI Desktop ile gelişmiş sorgular oluşturabilir, birden fazla kaynaktaki verileri birleştirebilir, tablolar arasında ilişkiler oluşturabilir ve daha fazlasını yapabilirsiniz.

Power BI Desktop, görselleştirmeler içeren istediğiniz sayıda rapor sayfası oluşturabildiğiniz **Rapor Görünümü**'nü içerir. Rapor Görünümü, Power BI hizmetindeki Düzenleme Görünümü ile neredeyse aynı tasarım deneyimini sunar. Görselleştirmeleri taşıma, kopyalayıp yapıştırma ve birleştirme gibi işlemler gerçekleştirebilirsiniz.

Aralarındaki fark şudur: Power BI Desktop'ı kullanırken sorgularla çalışabilir ve verilerinizin raporlarınızdaki en etkileyici öngörüleri desteklediğinden emin olmak için verilerinizi modelleyebilirsiniz. Ardından, Power BI Desktop dosyanızı dilediğiniz yere (ister yerel sürücünüze ister buluta) kaydedebilirsiniz.

## <a name="lets-take-a-look"></a>Şimdi bir göz atalım!
Power BI Desktop'a veri yüklediğinizde ilk olarak boş bir tuval içeren **Rapor Görünümü** ile karşılaşırsınız.

![Power BI Desktop](media/desktop-report-view/pbi_reportviewinpbidesigner_reportview.png)

Sol taraftaki gezinti bölmesinde bulunan simgeleri seçerek **Rapor Görünümü**, **Veri Görünümü** ve **İlişki Görünümü** arasında geçiş yapabilirsiniz:

![Rapor görünümü simgesi](media/desktop-report-view/pbi_reportviewinpbidesigner_changeview.png)

Veri ekledikten sonra tuvaldeki yeni bir görselleştirmeye alanlar ekleyebilirsiniz.

![Alanlar bölmesinden sürükleyerek görsel ekleme](media/desktop-report-view/pbid_reportview_addvis.gif)

Görselleştirmenin türünü değiştirmek için şeritteki **Görselleştirme** grubundan seçim yapabilir veya görselleştirmeye sağ tıklayıp **Görselleştirme türünü değiştir** simgesinden farklı bir tür seçebilirsiniz.

![Yeni bir görsel seçerek görseli değiştirme](media/desktop-report-view/pbid_reportview_changevis.gif)

> [!TIP]
> Farklı görselleştirme türleriyle deneme yapmayı ihmal etmeyin. Görselleştirmenizin verilerinizdeki bilgileri açık bir şekilde ifade etmesi önemlidir.

Bir rapor başlangıç olarak en az bir boş sayfa içerir. Sayfalar, tuvalin solundaki gezinti bölmesinde görünür. Bir sayfaya istediğiniz türden görselleştirmeler ekleyebilirsiniz ancak aşırıya kaçmamakta yarar vardır. Bir sayfada çok fazla görselleştirmenin bulunması sayfanın karmaşık görünmesine ve aranan bilgilerin bulunmasının zorlaşmasına neden olur. Raporunuza yeni sayfalar ekleyebilirsiniz. Şeritteki **Yeni Sayfa**’ya tıklayın.

![Yeni sayfa simgesi](media/desktop-report-view/pbidesignerreportviewnewpage.png)

Bir sayfayı silmek için, Rapor Görünümü'nde altta sayfanın sekmesinde bulunan **X** işaretini tıklayın.

![Rapora sayfa ekleme](media/desktop-report-view/pbi_reportviewinpbidesigner_deletepage.png)

> [!NOTE]
> Raporlar ve görselleştirmeler Power BI Desktop'tan bir panoya sabitlenemez. Bunu gerçekleştirmek için, kutucuğu Power BI sitenizde [Power BI Desktop'tan yayımlamanız](desktop-upload-desktop-files.md) gerekir.

## <a name="copy-and-paste-between-reports"></a>Raporlar arasında kopyalama ve yapıştırma

Bir Power BI Desktop raporundaki görseli kolayca alabilir ve başka bir rapora yapıştırabilirsiniz. Rapor görselinizi **CTRL+C** klavye kısayolunu kullanarak kopyalamanız ve ardından diğer Power BI Desktop raporunda görseli yapıştırmak için **CTRL+V** kısayolunu kullanmanız yeterlidir. Görselleri birer birer veya toplu olarak seçip kopyalayabilir ve hedef Power BI Desktop raporuna yapıştırabilirsiniz. 

Görselleri kopyalayıp yapıştırabilme olanağı birden çok raporu sık sık derleyen ve güncelleştiren kişiler için kullanışlıdır. Dosyalar arasında kopyalarken; biçimlendirme bölmesinde açıkça ayarlanan ayarlar ve biçimlendirme iletilir. Öte yandan bir temayı veya varsayılan ayarları temel alan görsel öğeler, hedef raporun temasına uyacak şekilde otomatik olarak güncelleştirilir. Dolayısıyla görselin tam istediğiniz gibi biçimlendirilmesini ve görünmesini sağladığınızda, o görseli kopyalayıp yeni rapora yapıştırabilir ve tüm biçimlendirme çalışmasını koruyabilirsiniz.

Modelinizdeki alanlar farklıysa, görselde hata gösterilir ve hangi alanların mevcut olmadığına ilişkin bir uyarı görürsünüz. Hata, modelde görselin kullandığı bir alanı sildiğinizde karşılaştığınız deneyime benzer. 

![Görsel kopyalama/yapıştırma hatası - veri alanı yok](media/desktop-report-view/report-view_07.png)

Hatayı düzeltmek için, bozuk alanları görseli yapıştırdığınız rapordaki modelin kullanmak istediğiniz alanlarıyla değiştirin. Özel bir görsel kullanıyorsanız bu özel görseli de hedef raporun içine aktarmalısınız.




## <a name="hide-report-pages"></a>Rapor sayfalarını gizleme

Bir rapor oluştururken raporda belirli sayfaları gizleme imkanınız da vardır. Bu özellik, raporun diğer sayfalarında kullanılan tablolar veya destekleyici görseller oluştururken olduğu gibi bir raporda temel veriler veya görseller oluşturmanızın gerektiği, ancak bu sayfaların başkaları tarafından görülmesini istemediğiniz durumlarda kullanışlı olabilir. Bir rapor sayfası oluşturup yayımlamak istediğiniz rapordan gizli tutmak isteyebileceğiniz durumlar için başka birçok yaratıcı neden bulunabilir. 

Bir rapor sayfasını gizlemek kolaydır. Basitçe rapor sayfasının sekmesine sağ tıklayın ve açılan menüden **Gizle**’yi seçin.

![Sayfayı gizle seçeneği](media/desktop-report-view/report-view_05.png)

Rapor sayfası gizleme konusunda dikkat etmeniz gereken bazı noktalar vardır:

* Gizlenen bir rapor görünümünü başlığı gri olmasına rağmen **Power BI Desktop**’ta görmeye devam edersiniz. Aşağıdaki resimde, 4. sayfa gizlidir.

    ![gri gösterilen gizli sayfa](media/desktop-report-view/report-view_06.png)

* Raporu **Power BI hizmetinde** görüntülerken gizli rapor sayfalarını *göremezsiniz*.

* Rapor sayfalarının gizlenmesi bir güvenlik önlemi *değildir*. Kullanıcıların sayfaya erişimi devam eder ve detaylandırma gibi yöntemler kullanılarak içeriğe erişilebilir.

* Bir sayfa gizliyse, Görünüm Modu’nda görünüm modu gezinti okları gösterilmez.

