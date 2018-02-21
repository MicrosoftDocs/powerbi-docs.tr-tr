---
title: "Power BI Desktop'taki Rapor Görünümü"
description: "Power BI Desktop'taki Rapor Görünümü"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 02/05/2018
ms.author: davidi
ms.openlocfilehash: 5ae0ef1ec5b13699f3ae5c502d29529841a7a726
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="report-view-in-power-bi-desktop"></a>Power BI Desktop'taki Rapor Görünümü
Power BI'a aşinaysanız, verilerinize dinamik bakış açıları ve öngörüler kazandıran raporlar oluşturmanın ne kadar kolay olduğunu biliyorsunuz demektir. Power BI, Power BI Desktop'ta daha gelişmiş özelliklere de sahiptir. Power BI Desktop ile gelişmiş sorgular oluşturabilir, birden fazla kaynaktaki verileri birleştirebilir, tablolar arasında ilişkiler oluşturabilir ve daha fazlasını yapabilirsiniz.

Power BI Desktop, görselleştirmeler içeren istediğiniz sayıda rapor sayfası oluşturabildiğiniz **Rapor Görünümü**'nü içerir. Rapor Görünümü, Power BI hizmetindeki Düzenleme Görünümü ile neredeyse aynı tasarım deneyimini sunar. Görselleştirmeleri taşıma, kopyalayıp yapıştırma ve birleştirme gibi işlemler gerçekleştirebilirsiniz.

Aralarındaki fark şudur: Power BI Desktop'ı kullanırken sorgularla çalışabilir ve verilerinizin raporlarınızdaki en etkileyici öngörüleri desteklediğinden emin olmak için verilerinizi modelleyebilirsiniz. Ardından, Power BI Desktop dosyanızı dilediğiniz yere (ister yerel sürücünüze ister buluta) kaydedebilirsiniz.

## <a name="lets-take-a-look"></a>Şimdi bir göz atalım!
Power BI Desktop'a veri yüklediğinizde ilk olarak boş bir tuval içeren **Rapor Görünümü** ile karşılaşırsınız.

![](media/desktop-report-view/pbi_reportviewinpbidesigner_reportview.png)

Sol taraftaki gezinti çubuğunda bulunan simgeleri seçerek **Rapor Görünümü**, **Veri Görünümü** ve **İlişki Görünümü** arasında geçiş yapabilirsiniz:

![](media/desktop-report-view/pbi_reportviewinpbidesigner_changeview.png)

Veri ekledikten sonra tuvaldeki yeni bir görselleştirmeye alanlar ekleyebilirsiniz.

![](media/desktop-report-view/pbid_reportview_addvis.gif)

Görselleştirmenin türünü değiştirmek için şeritteki **Görsel Öğeler** grubundan seçim yapabilir veya görselleştirmeye sağ tıklayıp farklı bir **görselleştirme** türü seçebilirsiniz.

![](media/desktop-report-view/pbid_reportview_changevis.gif)

> [!TIP]
> Farklı görselleştirme türleriyle deneme yapmayı ihmal etmeyin. Görselleştirmenizin verilerinizdeki bilgileri açık bir şekilde ifade etmesi önemlidir.
> 
> 

Bir rapor başlangıç olarak en az bir boş sayfa içerir. Sayfalar, tuvalin solundaki gezinti bölmesinde görünür. Bir sayfaya istediğiniz türden görselleştirmeler ekleyebilirsiniz ancak aşırıya kaçmamakta yarar vardır. Bir sayfada çok fazla görselleştirmenin bulunması sayfanın karmaşık görünmesine ve aranan bilgilerin bulunmasının zorlaşmasına neden olur. Raporunuza yeni sayfalar eklemek için şeritteki **Yeni Sayfa**'ya tıklamanız yeterlidir.

![](media/desktop-report-view/pbidesignerreportviewnewpage.png)

Bir sayfayı silmek için, Rapor Görünümü'nde altta sayfanın sekmesinde bulunan **X** işaretini tıklayın.

![](media/desktop-report-view/pbi_reportviewinpbidesigner_deletepage.png)

> [!NOTE]
> Raporlar ve görselleştirmeler Power BI Desktop'tan bir panoya sabitlenemez. Bunu gerçekleştirmek için, kutucuğu Power BI sitenizde [Power BI Desktop'tan yayımlamanız](desktop-upload-desktop-files.md) gerekir.

## <a name="hide-report-pages"></a>Rapor sayfalarını gizleme

Bir rapor oluştururken raporda belirli sayfaları gizleme imkanınız da vardır. Bu özellik, raporun diğer sayfalarında kullanılan tablolar veya destekleyici görseller oluştururken olduğu gibi bir raporda temel veriler veya görseller oluşturmanızın gerektiği, ancak bu sayfaların başkaları tarafından görülmesini istemediğiniz durumlarda kullanışlı olabilir. Bir rapor sayfası oluşturup yayımlamak istediğiniz rapordan gizli tutmak isteyebileceğiniz durumlar için başka birçok yaratıcı neden bulunabilir. 

Bir rapor sayfasını gizlemek kolaydır. Basitçe rapor sayfasının sekmesine sağ tıklayın ve açılan menüden **Gizle**’yi seçin.

![](media/desktop-report-view/report-view_05.png)

Rapor sayfası gizleme konusunda dikkat etmeniz gereken bazı noktalar vardır:

* Gizlenen bir rapor görünümünü başlığı gri olmasına rağmen **Power BI Desktop**’ta görmeye devam edersiniz. Aşağıdaki resimde, 4. sayfa gizlidir.

    ![](media/desktop-report-view/report-view_06.png)

* Raporu **Power BI hizmetinde** görüntülerken gizli rapor sayfalarını *göremezsiniz*.

* Rapor sayfalarının gizlenmesi bir güvenlik önlemi *değildir*. Kullanıcıların sayfaya erişimi devam eder ve detaylandırma gibi yöntemler kullanılarak içeriğe erişilebilir.

* Bir sayfa gizliyse, Görünüm Modu’nda görünüm modu gezinti okları gösterilmez.

