---
title: Rapordan Power BI panosu oluşturma
description: Rapordan Power BI panosu oluşturma
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/17/2019
ms.author: maggies
ms.openlocfilehash: 108882dd0f3b61d6cb19fd18290b44316231f3cb
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020316"
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Rapordan Power BI panosu oluşturma
[Power BI'da panolara giriş](service-dashboards.md) makalesini okuduğunuza göre artık kendi panolarınızı oluşturabilirsiniz. Pano oluşturmanın birçok farklı yolu vardır. Örneğin bir rapordan, sıfırdan, bir veri kümesinden veya mevcut panoyu yinelenerek oluşturulabilirler.  

Daha önce oluşturulmuş bir raporun görselleştirmelerini sabitleyen bir panoyu hızla ve kolayca oluşturarak başlayacağız. 

Bu makaleyi tamamladıktan sonra şu konular hakkında fikir sahibi olacaksınız:
- Panolarla raporlar arasındaki ilişki
- Rapor düzenleyicisinde Düzenleme görünümünü açma
- Kutucukları sabitleme 
- Panoyla rapor arasında gezinme 
 
![Pano](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

> [!NOTE] 
> Panolar Power BI Desktop'ın değil Power BI hizmetinin sunduğu bir özelliktir. Power BI mobil uygulamalarında pano oluştaramasanız da bu cihazlarda onları [görüntüleyebilir ve paylaşabilirsiniz](consumer/mobile/mobile-apps-view-dashboard.md).
>
> 

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Video: Rapordaki görselleri ve resimleri sabitleyerek pano oluşturma
Amanda'nın bir rapordaki görselleştirmeleri sabitleyerek yeni bir pano oluşturmasını izleyin. Ardından, Tedarik Analizi örneğini kullanarak bunu denemek için bir sonraki bölüm olan [Rapor içeren bir veri kümesini içeri aktarma](#import-a-dataset-with-a-report) başlığı altında verilen adımları izleyin.
    

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>Rapor içeren bir veri kümesini içeri aktarma
Adım adım ilerleyen bu kılavuzda, Power BI örnek veri kümelerinden birini içeri aktarıp yeni panomuzu oluşturmak için kullanacağız. Kullandığımız örnek iki PowerView sayfası bulunan bir Excel çalışma kitabıdır. Çalışma kitabı Power BI tarafından içeri aktarıldığında, çalışma alanınıza bir veri kümesi ve bir rapor eklenir. Rapor otomatik olarak PowerView sayfalarından oluşturulur.

1. [Tedarik Analizi örneğinin](http://go.microsoft.com/fwlink/?LinkId=529784) Excel dosyasını indirin. Dosyayı OneDrive İş hesabınıza kaydetmenizi öneririz.
2. Tarayıcınızda Power BI hizmetine (app.powerbi.com) gidin ve oturum açın.
3. Sol gezinti bölmesinde **Çalışma Alanım**'ı ve ardından **Veri Al**'ı seçin.

    ![Sol gezinti bölmesi](media/service-dashboard-create/power-bi-get-data-new-look.png)
5. **Dosyalar**’ı seçip **Al** seçeneğini belirleyin.

   ![Dosya alma](media/service-dashboard-create/power-bi-select-files.png)
6. Tedarik Analizi örnek Excel dosyasını kaydettiğiniz konuma gidin. Dosyayı seçin ve **Bağlan** seçeneğini belirleyin.

   ![Dosyalara bağlanma](media/service-dashboard-create/power-bi-connectnew.png)
7. Bu alıştırma için **İçeri aktar** seçeneğini belirleyin.

    ![OneDrive İş penceresi](media/service-dashboard-create/power-bi-import.png)
8. Başarılı iletisi gösterildiğinde kapatmak için **x** işaretini seçin.

   ![Başarılı iletisi](media/service-dashboard-create/power-bi-view-datasetnew.png)

> [!TIP]
> Biliyor muydunuz? Yukarıda yer alan üç çizgili simgeyi (![Gezinti bölmesini göster veya gizle simgesi](media/service-dashboard-create/power-bi-new-look-hide-nav-pane.png)) seçerek sol gezinti çubuğunu daraltabilirsiniz. Böylelikle rapor için daha fazla alan elde edersiniz.

### <a name="open-the-report-and-pin-tiles-to-your-dashboard"></a>Raporu açma ve panonuza kutucukları sabitleme
1. Aynı çalışma alanında **Raporlar** sekmesini seçin ve ardından **Tedarik Analizi Örneği**'ni seçerek raporu açın.

    ![Raporlar sekmesi](media/service-dashboard-create/power-bi-reports.png) Rapor Okuma görünümünde açılır. Alt kısımda iki sekmesi olduğuna dikkat edin: **Discount Analysis** ve **Spend Overview**. Her sekme raporun bir sayfasını temsil eder.

2. **Raporu düzenle**'yi seçerek raporu Düzenleme görünümünde açın.

    ![Okuma görünümünde rapor](media/service-dashboard-create/power-bi-reading-view.png)
3. Kullanılabilir seçenekleri görüntülemek için bir görselleştirmenin üzerine gelin. Panoya görselleştirme eklemek için raptiye simgesini seçin ![Raptiye simgesi](media/service-dashboard-create/power-bi-pin-icon.png)geçin.

    ![Kutucuğun üzerine gelin](media/service-dashboard-create/power-bi-hover.png)
4. Yeni bir pano oluşturduğumuz için **Yeni pano** seçeneğini belirtin ve buna bir ad verin.

    ![Panoya sabitle iletişim kutusu](media/service-dashboard-create/power-bi-pin-tile.png)
5. **Sabitle**'yi seçtiğinizde, Power BI geçerli çalışma alanında yeni bir pano oluşturur. **Panoya sabitlendi** iletisi görüntülendiğinde **Panoya git**'i seçin. Raporu kaydetmeniz istenirse **Kaydet**'i seçin.

    ![Başarılı iletisi](media/service-dashboard-create/power-bi-pin-success.png)

    Power BI yeni panoyu açar. Tek kutucuğu vardır: yeni sabitlediğiniz görselleştirme.

   ![bir kutucuk içeren pano](media/service-dashboard-create/power-bi-pinned.png)
7. Rapora dönmek için kutucuğu seçin. Yeni panoya birkaç kutucuk daha sabitleyin. **Panoya sabitle** penceresi görüntülendiğinde, **Var olan pano**'yu seçin.  

   ![Panoya sabitle iletişim kutusu](media/service-dashboard-create/power-bi-existing-dashboard.png)

## <a name="pin-an-entire-report-page-to-the-dashboard"></a>Rapor sayfasının tamamını panoya sabitleme
Görselleri tek tek sabitlemek yerine, [bir rapor sayfasının tamamını *canlı kutucuk* olarak sabitleyebilirsiniz](service-dashboard-pin-live-tile-from-report.md). Şimdi bu işlemi yapalım.

1. Rapor düzenleyicisinde **Spend Overview** sekmesini seçerek raporun ikinci sayfasını açın.

   ![Rapor sekmesi](media/service-dashboard-create/power-bi-page-tab.png)

2. Rapordaki tüm görsellerin panonuzda olmasını istiyoruz. Menü çubuğunun sağ üst köşesindeki **Canlı sabitleme sayfası**’nı seçin. Sayfa her yenilendiğinde bir panodaki canlı sayfa kutucukları güncelleştirilir.

   ![Rapor düzenleyicisinin sağ üst kısmı](media/service-dashboard-create/power-bi-pin-live.png)

3. **Panoya sabitle** penceresi görüntülendiğinde **Var olan pano**'yu seçin.

   ![Panoya sabitle iletişim kutusu](media/service-dashboard-create/power-bi-pin-live2.png)

4. Başarılı iletisi görüntülendikten sonra **Panoya git**'i seçin. Burada, rapordan sabitlediğiniz kutucukları görürsünüz. Aşağıdaki örnekte biri raporun ilk sayfasından ve diğeri de canlı kutucuk olan (raporun ikinci sayfası) iki kutucuk sabitledik.

   ![Pano](media/service-dashboard-create/power-bi-dashboard.png)

## <a name="next-steps"></a>Sonraki adımlar
Tebrikler, ilk panonuzu oluşturdunuz! Artık panonuz olduğuna göre bununla birçok şey yapabilirsiniz. Aşağıdaki önerilen makalelerden birini izleyin veya kendi başınıza keşfetmeye başlayın: 

* [Kutucukları yeniden boyutlandırma ve taşıma](service-dashboard-edit-tile.md)
* [Pano kutucukları hakkında tüm bilmeniz gerekenler](service-dashboard-tiles.md)
* [Uygulama oluşturarak panonuzu paylaşma](service-create-workspaces.md)
* [Power BI - Temel Kavramlar](service-basic-concepts.md)
* [Harika bir pano oluşturmaya yönelik ipuçları](service-dashboards-design-tips.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/).
