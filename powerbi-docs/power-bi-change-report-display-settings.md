---
title: "Bir rapor sayfasının boyutunu değiştirme (Eğitim)"
description: "Eğitim: Power BI raporlarındaki sayfaların görüntüleme ayarlarını değiştirme"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/25/2017
ms.author: mihart
ms.openlocfilehash: a5cc05e26012f88e889612788d4479a370063d4f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="change-the-size-of-a-report-page-tutorial"></a>Bir rapor sayfasının boyutunu değiştirme (Eğitim)
[Önceki makalede ve videoda](power-bi-report-display-settings.md), Power BI raporlarındaki sayfaların nasıl görüntüleneceğini denetlemeye ilişkin iki farklı yöntem öğrendiniz: **Görünüm** ve **Sayfa Boyutu**. Şimdi kendimiz deneyelim.

## <a name="first-lets-change-the-page-view-setting"></a>İlk olarak, sayfa görünümü ayarını değiştirelim
1. Bir raporu Okuma Görünümü'nde veya Düzenleme Görünümü'nde açın. Aşağıdaki örnekte, [Perakende Analizi örneğinin](sample-retail-analysis.md) "New Stores" sayfası kullanılmıştır.  Bu sayfa, **Sayfaya Sığdır** ayarı kullanılarak görüntülenir.  Bu örnekte Sayfaya Sığdır seçeneği kullanılmıştır ve rapor sayfası, kaydırma çubukları olmadan görüntülenmektedir ancak bazı ayrıntılar ve başlıklar okunamayacak kadar küçüktür.
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_page.png)
2. Tuvalde herhangi bir görselleştirmenin seçili olmadığından emin olun. **Görünüm**'ü seçin ve görüntüleme seçeneklerini gözden geçirin.

* Okuma görünümünde, aşağıdaki seçenekleri görürsünüz.
  
     ![](media/power-bi-change-report-display-settings/power-bi-page-view-menu-new.png)
* Düzenleme görünümü'nde ise aşağıdaki gibi bir menüyle karşılaşırsınız.
  
    ![](media/power-bi-change-report-display-settings/power-bi-view-editing-view.png)

1. **Gerçek boyut** ayarını kullanarak sayfanın nasıl göründüğüne bakalım.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)
   
   Pek iyi göründüğü söylenemez. Panoda artık iki kaydırma çubuğu bulunmaktadır.
2. **Genişliğe uydur**'u seçin.
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_width.png)
   
   Artık daha iyi görünüyor. Kaydırma çubukları hâlâ var ancak ayrıntılar daha kolay bir şekilde okunabiliyor.

## <a name="change-the-default-view-for-a-report-page"></a>Bir rapor sayfasının varsayılan görünümünü değiştirme
Tüm Power BI raporlarında varsayılan olarak **Sayfaya sığdır** görünümü kullanılmaktadır. Bu rapor sayfasının her zaman **Gerçek boyut** görünümünde açılmasını istiyorsanız ne yapmanız gerekir?

1. Raporun **New Stores** sayfasında **Gerçek boyut** görünümüne geri dönün.
   
   ![](media/power-bi-change-report-display-settings/power-bi-actual-size.png)
2. **Dosya > Farklı kaydet**'i seçerek dosyayı farklı bir adla kaydedin. Artık bu raporun 2 kopyasına sahipsiniz; özgün raporda **New Stores** sayfası varsayılan görünümde açılmaya devam eder ancak yeni raporda **Gerçek boyut** görünümünde açılır. Hemen deneyelim.
   
   ![](media/power-bi-change-report-display-settings/power-bi-save-as.png)
3. Üstteki gezinti çubuğunda, geçerli çalışma alanının adını seçerek bu çalışma alanına dönün.  
   
   ![](media/power-bi-change-report-display-settings/power-bi-my-workspace.png)
4. **Raporlar** sekmesini ve yeni oluşturduğunuz raporu (yanında sarı bir yıldız olan) seçin.
   
    ![](media/power-bi-change-report-display-settings/power-bi-new-report2.png)
5. Rapor, **Gerçek boyut** görünümünde açılıyor!
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)

## <a name="now-lets-explore-the-page-size-setting"></a>Şimdi *sayfa boyutu* ayarını inceleyelim
Sayfa boyutu ayarları yalnızca [Düzenleme görünümü](service-interact-with-a-report-in-editing-view.md)'nde kullanılabilir. Bir raporu Düzenleme görünümü'nde açmak için rapora ilişkin sahip izinleriniz olmalıdır. [Örneklerimizden](sample-datasets.md) herhangi birine bağlandıysanız mevcut raporlara ilişkin sahip izinleriniz olur.

1. [Perakende Analizi örneğinin](sample-retail-analysis.md) "District monthly sales" sayfasını, Düzenleme Görünümü'nde açın.
2. Tuvalde herhangi bir görselleştirmenin seçili olmadığından emin olun.  **Görsel Öğeler** bölmesinde boya rulosu simgesini ![](media/power-bi-change-report-display-settings/power-bi-paintroller.png) seçin.
3. Sayfa boyutu seçeneklerini görüntülemek için **Sayfa Boyutu** &gt; **Tür**'ü seçin.
   
   ![](media/power-bi-change-report-display-settings/power-bi-page-size-menu-new.png)
4. **Letter**'ı seçin.  Tuvalde, yalnızca 816 x 1056 piksele (Letter boyutu) sığan içerikler tuvalin beyaz kısmında kalır.
   
   ![](media/power-bi-change-report-display-settings/power-bi-letter-new.png)
5. **Görünüm**'ü "Genişliğe uydur" olarak değiştirirsek tuvalimizde artık yalnızca Letter boyutuna uyan sayfa içeriği görüntülenir.
   
   ![](media/power-bi-change-report-display-settings/power-bi-fit-to-width-new.png)
6. **Sayfa boyutu** **16:9** oranını seçin.
   
   ![](media/power-bi-change-report-display-settings/power-bi-16-to-9-new.png)
   
   Rapor sayfası 16:9 oranı kullanılarak görüntülenir. Kullanılan gerçek piksel boyutunu görmek için, gri renkli Genişlik ve Yükseklik alanlarına (1280 x 720) bakın. Rapor tuvalinin etrafında çok fazla boşluk bulunmaktadır. Bunun nedeni, **Görünüm**'ü "Genişliğe uydur" olarak ayarlamış olmamızdır.
7. **Sayfa Boyutu** seçeneklerini incelemeye devam edin.

## <a name="using-page-view-and-page-size-together"></a>Sayfa Görünümü ve Sayfa Boyutu'nu birlikte kullanma
Başka bir uygulamaya eklendiğinde en iyi şekilde görüntülenecek olan bir rapor oluşturmak için Sayfa Görünümü ve Sayfa Boyutu seçeneklerini birlikte kullanın.

Bu alıştırmada, 500 piksel genişliğinde ve 750 piksel yüksekliğinde alana sahip bir uygulamada görüntülenecek bir rapor oluşturacaksınız.

Önceki adımda, rapor sayfamızın 1280 piksel genişliğinde ve 720 piksel yüksekliğinde görüntülendiğini görmüştük. Bu nedenle, tüm görsellerimizin sığmasını istiyorsak birçok yeniden boyutlandırma ve yeniden düzenleme işlemi yapmamız gerektiğini biliyoruz.

1. Görselleri, geçerli tuval alanının yarısından daha küçük bir alana sığacak şekilde yeniden boyutlandırın ve taşıyın.
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-view.gif)
2. **Sayfa Boyutu** &gt; **Özel**'i seçin.
3. Genişlik değerini 500, Yükseklik değerini ise 750 olarak ayarlayın.
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-new.png)
4. En iyi şekilde görünmesi için rapor sayfası üzerinde ince ayarlar yapın. Ayarlamalar yapmak için **Görünüm > Gerçek boyut** ve **Görünüm > Sayfaya sığdır** seçenekleri arasında geçiş yapın.
   
    ![](media/power-bi-change-report-display-settings/power-bi-final-new.png)

## <a name="next-steps"></a>Sonraki adımlar
[Cortana için rapor oluşturma](service-cortana-answer-cards.md)

[Power BI raporlarında sayfa görüntüleme ayarları](power-bi-report-display-settings.md) konusuna tekrar göz atın

[Power BI'daki raporlar](service-reports.md) hakkında daha fazla bilgi edinin

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

