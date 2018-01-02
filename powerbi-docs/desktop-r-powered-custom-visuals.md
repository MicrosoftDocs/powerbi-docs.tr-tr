---
title: "Power BI'da R tarafından sağlanan özel görselleri kullanma"
description: "Power BI'da R tarafından sağlanan özel görselleri kullanma"
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: f2887b5d93a6f88c00f8ab8d21676ed53776b9f2
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2017
---
# <a name="use-r-powered-custom-visuals-in-power-bi"></a>Power BI'da R tarafından sağlanan özel görselleri kullanma
**Power BI Desktop**'ta ve **Power BI hizmetinde** herhangi bir R bilgisine sahip olmanıza ve R betiği oluşturmanıza gerek kalmadan R tarafından sağlanan özel görselleri kullanabilirsiniz. Bu sayede, R hakkında bilgi sahibi olmadan veya kendiniz herhangi bir programlama yapmadan R görselleri ve R betiklerinin analitik ve görsel özelliklerinden yararlanabilirsiniz.

R tabanlı özel görselleri kullanmak için önce Power BI'a yönelik [**AppSource**](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals&page=1) **özel görsel** galerisinden işinize yarayacak R özel görselini seçip indirmeniz gerekir.

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_1a.png)

**Power BI Desktop**'ta R tabanlı görselleri seçme, yükleme ve kullanma işlemleri aşağıdaki bölümlerde açıklanmıştır.

## <a name="use-r-custom-visuals"></a>R özel görsellerini kullanma
R tabanlı özel görselleri kullanmak için her bir görseli **özel görsel** kitaplığından indirmeniz gerekir. Böylece, ilgili görseli **Power BI Desktop**'taki tüm diğer görsel türleri gibi kullanabilirsiniz. Özel görselleri almak için izlenebilecek iki yol vardır: Çevrimiçi **AppSource** sitesinden indirebilir veya **Power BI Desktop**'tayken göz atıp edinebilirsiniz. 

### <a name="get-custom-visuals-from-appsource"></a>Özel görselleri AppSource'tan alma

Görselleri **AppSource** sitesinde bulup seçmeye yönelik adımlar aşağıda verilmiştir:

1. [https://appsource.microsoft.com](https://appsource.microsoft.com/) adresindeki [Power BI visuals](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals&page=1) kitaplığına gidin. *Ürüne göre daralt* bölümündeki *Power BI apps* onay kutusunu işaretleyin ve ardından **Tümünü gör** bağlantısını seçin.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_2a.png)

2. Sol bölmedeki Eklentiler listesinden **Power BI visuals**'ı seçin. 


   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_2b.png)

3. Galeriden işinize yarayacak **görseli** seçin, seçiminizin ardından görsel açıklamasının sunulduğu bir sayfaya yönlendirilirsiniz. İndirmek için **Şimdi edinin** seçeneğini belirleyin.
   
   > [!NOTE]
> **Power BI Desktop**'ta yazmak için yerel makinenizde R yüklü olmalıdır. Ancak, kullanıcılar R tabanlı bir görseli **Power BI hizmetinde** görüntülemek isterse R'nin yerel makinede yüklü olmasına gerek *yoktur*.
   > 
   > 
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_3a.png)
   
   R tabanlı görselleri **Power BI hizmetinde** kullanmak için R'yi yüklemeniz gerekmez ancak R tabanlı görselleri **Power BI Desktop**'ta kullanmak isterseniz yerel makinenize R'yi yüklemeniz *gerekir*. R'yi aşağıdaki konumlardan indirebilirsiniz:
   
   * [CRAN](https://cran.r-project.org/)
   * [MRO](https://mran.microsoft.com/)

4. Görseli indirdikten sonra (indirme işlemi tarayıcınızdan herhangi bir dosya indirmeye benzer) **Power BI Desktop**'a giderek **Görsel Öğeler** bölmesindeki üç nokta (...) simgesine sağ tıklayın ve **Dosyadan içeri aktar**'ı seçin.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_4a.png)
5. Aşağıdaki görüntüde gösterildiği gibi özel görselleri içeri aktarırken dikkatli olmanız konusunda bir uyarı alırsınız:
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_5.png)
6. Görsel dosyasının kaydedildiği konuma gidin ve dosyayı seçin. **Power BI Desktop** özel görselleştirmeleri .pbiviz uzantılıdır.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_6.png)
7. Power BI Desktop'a döndüğünüzde yeni görsel türünü **Görsel Öğeler** bölmesinde bulabilirsiniz.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_7.png)
8. Yeni görseli içeri aktardığınızda (veya R tabanlı özel görseli içeren bir raporu açtığınızda) **Power BI Desktop** gerekli R paketlerini yükler.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_8.png)

Tüm diğer **Power BI Desktop** görsellerinde yaptığınız gibi buradan görsele veri ekleyebilirsiniz. İşlemlerinizi tamamladığınızda, görselinizin son halini tuvalde görebilirsiniz. Aşağıdaki görselde, Birleşmiş Milletler (BM) doğum oranı tahminlerini (soldaki görsel) sunmak üzere R tabanlı **Forecasting** görseli kullanılmıştır.

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_10.png)

Tüm diğer **Power BI Desktop** görsellerinde olduğu gibi R tabanlı görselleriyle birlikte bu raporu da **Power BI hizmetinde** yayımlayabilir ve başkalarıyla paylaşabilirsiniz.

Her zaman yeni görseller eklendiği için kitaplığı sık sık ziyaret etmeyi unutmayın.

### <a name="get-custom-visuals-from-within-power-bi-desktop"></a>Özel görselleri **Power BI Desktop**'tan edinme

Özel görselleri **Power BI Desktop**'tan da edinebilirsiniz. **Power BI Desktop**'ta **Görsel Öğeler** bölmesindeki üç nokta (...) simgesine sağ tıklayın ve **Mağazadan al**'ı seçin.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_4a.png)

Bu işlemin ardından, kullanılabilir özel görsellere göz atarak aralarından seçim yapabileceğiniz **Power BI Özel Görselleri** iletişim kutusu açılır. Ada göre arama yapabilir, kategori belirleyebilir veya kullanılabilir görsellere göz atabilirsiniz. Hazır olduğunuzda özel görseli **Power BI Desktop**'a eklemek için **Ekle** seçeneğini belirlemeniz yeterlidir.

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_12.png)

## <a name="contribute-r-powered-custom-visuals"></a>R tabanlı özel görsellere katkıda bulunma
Raporlarınızda kullanmak için kendi R görsellerinizi oluşturursanız bunları **özel görseller galerisine** ekleyerek tüm dünyayla paylaşabilirsiniz. Katkılar, GitHub aracılığıyla yapılır ve katkıda bulunma işlemi, aşağıdaki konumda ana hatlarıyla açıklanmıştır:

* [R tabanlı özel görseller galerisine katkıda bulunma](https://github.com/Microsoft/PowerBI-visuals#building-r-powered-custom-visual-corrplot)

## <a name="troubleshoot-r-powered-custom-visuals"></a>R tabanlı özel görseller ile ilgili sorunları giderme
R tabanlı özel görseller, görsellerin düzgün şekilde çalışması için karşılanması gereken belirli bağımlılıklar içerir. R tabanlı özel görseller düzgün şekilde çalıştırılamıyor veya yüklenemiyorsa sorun genellikle aşağıdakilerden biridir:

* R altyapısının eksik olması
* R betiğindeki görsel temelli hatalar
* R paketlerinin eksik olması veya güncel olmaması

Aşağıdaki bölümde, karşılaştığınız sorunları çözmenize yardımcı olacak sorun giderme adımları açıklanmaktadır.

### <a name="missing-or-outdated-r-packages"></a>Güncel olmayan veya eksik R paketleri
R tabanlı bir özel görseli yüklerken güncel olmayan veya eksik R paketlerine bağlı sorunlarla karşılaşabilirsiniz; bunun nedeni genellikle aşağıdakilerden biridir:

* R yüklemesinin R paketi ile uyumlu olmaması,
* Bir güvenlik duvarının, virüsten koruma yazılımının veya ara sunucu ayarlarının, R'nin İnternet'e bağlanmasına engel olması
* İnternet bağlantısının yavaş olması veya bir İnternet bağlantısı sorununun bulunması

Power BI ekibi, siz henüz karşılaşmadan bu tür sorunları azaltmak için etkin bir şekilde çalışır ve sonraki Power BI Desktop sürümüne bu sorunları gidermeye yönelik güncelleştirmeler eklenir. Şimdilik bu sorunları gidermek için aşağıdaki adımlardan birini veya birkaçını uygulayabilirsiniz:

1. Özel görseli kaldırın ve tekrar yükleyin. Bu işlem, R paketlerini yeniden yükleme işlemini başlatır.
2. R yüklemeniz güncel değilse R yüklemenizi yükseltin, ardından önceki adımda açıklandığı gibi özel görseli kaldırın/yeniden yükleyin.
   
   * Desteklenen R sürümleri, aşağıdaki görüntüde gösterildiği gibi R tabanlı her bir özel görselin açıklamasında belirtilmiştir.
     ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_11.png)
     > [!NOTE]
> Özgün R yüklemesini koruyabilir ve Power BI Desktop'ı yalnızca yüklediğiniz güncel sürümle ilişkilendirebilirsiniz. **Dosya > Seçenekler ve ayarlar > Seçenekler > R betiği oluşturma** seçeneğine gidin.
3. R konsolunu kullanarak R paketlerini el ile yükleyin. Bu yaklaşıma ilişkin adımlar aşağıda açıklanmıştır:
   
   a.  R tabanlı görselin yükleme betiğini indirin ve bu dosyayı yerel bir sürücüye kaydedin.
   
   b.  R konsolunda aşağıdaki komutu çalıştırın:
   
       > source(“C:/Users/david/Downloads/ScriptInstallPackagesForForecastWithWorkarounds.R”)    
   
   Genellikle, varsayılan yükleme konumları şunlardır:
   
       c:\Program Files\R\R-3.3.x\bin\x64\Rterm.exe (for CRAN-R)
       c:\Program Files\R\R-3.3.x\bin\x64\Rgui.exe (for CRAN-R)
       c:\Program Files\R\R-3.3.x\bin\R.exe (for CRAN-R)
       c:\Program Files\Microsoft\MRO-3.3.x\bin\R.exe (for MRO)
       c:\Program Files\Microsoft\MRO-3.3.x\bin\x64\Rgui.exe (for MRO)
       c:\Program Files\RStudio\bin\rstudio.exe (for RStudio)
4. Önceki adımlar işe yaramazsa şunları deneyin:
   
   a. **R Studio**'yu kullanın ve yukarıdaki 3.b. maddesinde açıklanan adımı uygulayın. (Betik satırını R konsolunda çalıştırın.)
   
   b. Önceki adım işe yaramazsa **R Studio**'daki **Tools > Global Options > Packages** (Araçlar > Genel Seçenekler > Paketler) seçeneğini değiştirin ve **Use Internet Explorer library/proxy for HTTP** (HTTP için Internet Explorer kitaplığını/ara sunucuyu kullan) onay kutusunu etkinleştirip yukarıdaki adımlardan 3.b. adımını tekrarlayın.

## <a name="next-steps"></a>Sonraki adımlar
Power BI'da R programlama dili hakkında sunulan aşağıdaki ek bilgilere göz atın.

* [Power BI özel görselleri galerisi](https://app.powerbi.com/visuals/)
* [Power BI Desktop'ta R betikleri çalıştırma](desktop-r-scripts.md)
* [Power BI Desktop'ta R görselleri oluşturma](desktop-r-visuals.md)
* [Power BI ile harici bir R IDE kullanma](desktop-r-ide.md)
