---
title: 'Öğretici: Bir VM’de Power BI Rapor Sunucusunu keşfetme'
description: Bu öğreticide, Power BI Rapor Sunucusu zaten yüklüyken bir sanal makine oluşturacak ve web portalını keşfedeceksiniz.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: tutorial
ms.date: 05/18/2018
ms.author: maggies
ms.openlocfilehash: 32bf2d3cedbeeb2430620855a2ac95bf349af9a2
ms.sourcegitcommit: 695c65629d6d1faba61db2e1570324f65f235dde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37092058"
---
# <a name="tutorial-explore-the-power-bi-report-server-web-portal-in-a-vm"></a>Öğretici: Bir VM’de Power BI Rapor Sunucusu web portalını keşfetme
Bu öğreticide, örnek Power BI ve sayfalandırılmış raporları görüntüleme, düzenleme ve yönetme işlemlerini yapabilmek için Power BI Rapor Sunucusu zaten yüklüyken bir Azure sanal makinesi oluşturacaksınız.

![Rapor Sunucusu web portalı](media/tutorial-explore-report-server-web-portal/power-bi-report-server-browser-in-vm-no-numbers.png)

Bu öğreticide gerçekleştireceğiniz görevler şunlardır:

> [!div class="checklist"]
> * VM oluşturma ve bağlanma
> * Power BI Rapor Sunucusu web portalını başlatma ve keşfetme
> * Sık kullanılan öğeyi etiketleme
> * Power BI raporunu görüntüleme ve düzenleme
> * Sayfalandırılmış bir raporu görüntüleme, yönetme ve düzenleme
> * Excel Online’da bir Excel çalışma kitabını görüntüleme

Bu öğreticide, bir Azure aboneliği gerekir. Aboneliğiniz yoksa, başlamadan önce [ücretsiz bir hesap](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) oluşturun.

## <a name="create-a-power-bi-report-server-vm"></a>Power BI Rapor Sunucusu sanal makinesi oluşturma

Neyse ki, Power BI ekibi Power BI Rapor Sunucusunun zaten yüklü olduğu bir VM oluşturmuştur.

1. Azure Market’te [Power BI Rapor Sunucusu](https://azuremarketplace.microsoft.com/marketplace/apps/reportingservices.technical-preview?tab=Overview)’nu açın.  

2. **Şimdi al**’ı seçin.
3. Sağlayıcının kullanım koşulları ve gizlilik ilkesini kabul etmek için **Devam**’ı seçin.

    ![Power BI Rapor Sunucusu sanal makinesi oluşturma](media/tutorial-explore-report-server-web-portal/power-bi-report-server-virtual-machine-create.png)

4. **1. Adım Temel Bilgiler**, **VM Adı** için **reportservervm** girin.

5. Bir kullanıcı adı ve parola oluşturun.

6. **Kaynak grubu** için **Yeni oluştur**’u seçin **reportserverresourcegroup** olarak adlandırın.

    Öğreticiyi bir kereden fazla uygularsanız, kaynak grubuna ilk denemenizde kullandığınız addan farklı bir ad vermeniz gerekir. Bir kaynak grubu adını aynı abonelik içinde ikinci kez kullanamazsınız. 

7. Diğer varsayılanları tutun > **Tamam**’ı seçin.

    ![VM ve kaynak grubunu adlandırma](media/tutorial-explore-report-server-web-portal/power-bi-report-server-create-resource-group.png)

8. **2. Adım Ayarlar**, varsayılanları tutun > **Tamam**’ı seçin.

9. **3. Adım Özet** > **Tamam**.

10. **4. Adım**, Kullanım koşullarını ve gizlilik ilkesini gözden geçirin > **Oluştur**’u seçin.

    **Power BI Rapor Sunucusu için dağıtım gönderiliyor** işlemi birkaç dakika sürer.

## <a name="connect-to-your-virtual-machine"></a>Sanal makinenize bağlanma

1. Azure sol gezinti bölmesinde **Sanal makineler**’i seçin. 

2. **Ada göre filtrele** kutusuna "report" yazın. 

3. **REPORTSERVERVM** adlı VM’yi seçin.

    ![Sanal makineyi görüntüleme](media/tutorial-explore-report-server-web-portal/power-bi-report-server-view-virtual-machine.png)

4. REPORTSERVERVM sanal makinesi altında **Bağlan**’ı seçin.

    ![Sanal makineye bağlanma](media/tutorial-explore-report-server-web-portal/power-bi-report-server-connect-to-virtual-machine.png)

5. Uzak Masaüstü Bağlantısı iletişim kutusunda **Bağlan**’ı seçin.

6. VM için oluşturduğunuz parola ve adı girin > **Tamam**’ı seçin.

7. Sonraki iletişim kutusunda, uzak bilgisayar kimliğinin tanımlanamadığı söylenir. **Evet**’i seçin.

   Yeni sanal makineniz açılır.

## <a name="power-bi-report-server-on-the-vm"></a>VM üzerinde Power BI Rapor Sunucusu

Sanal makineniz açıldığında masaüstünde aşağıdaki öğeleri görürsünüz.

![Power BI Rapor Sunucusu sanal makinesi başlatılır](media/tutorial-explore-report-server-web-portal/power-bi-report-server-start-vm-numbered.png)

|Sayı  |Nedir  |
|---------|---------|
|![1 Numara](media/tutorial-explore-report-server-web-portal/number-1.png) | Sayfalandırılmış (.RDL) raporlar oluşturmak için SQL Server Veri Araçları’nı başlatır |
|![2 Numara](media/tutorial-explore-report-server-web-portal/number-2.png) | Örnek Power BI (.PBIX) raporları  |
|![3 Numara](media/tutorial-explore-report-server-web-portal/number-3.png) | Power BI Rapor Sunucusu belgelerinin bağlantıları   |
|![4 Numara](media/tutorial-explore-report-server-web-portal/number-4.png) | Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını başlatır (Mart 2018)  |
|![5 Numara](media/tutorial-explore-report-server-web-portal/number-5.png) | Power BI Rapor Sunucusu web portalını tarayıcıda açar   |

**Rapor Sunucusu Web Portalı** simgesine çift tıklayın. Tarayıcıda `http://localhost/reports/browse` sayfası açılır. Web portalında türe göre gruplandırılmış çeşitli dosyalar görürsünüz. 

![Power BI Rapor Sunucusu web portalı](media/tutorial-explore-report-server-web-portal/power-bi-report-server-browser-in-vm.png)

|Sayı  |Nedir  |
|---------|---------|
|![1 Numara](media/tutorial-explore-report-server-web-portal/number-1.png) | Web portalında oluşturulan KPI’ler |
|![2 Numara](media/tutorial-explore-report-server-web-portal/number-2.png) |  Power BI (.PBIX) raporları  |
|![3 Numara](media/tutorial-explore-report-server-web-portal/number-3.png) | SQL Server Mobil Rapor Yayımcısında oluşturulan mobil raporlar  |
|![4 Numara](media/tutorial-explore-report-server-web-portal/number-4.png) |  Rapor Oluşturucusu veya SQL Server Veri Araçları’nda oluşturulan sayfalandırılmış raporlar  |
|![5 Numara](media/tutorial-explore-report-server-web-portal/number-5.png) | Excel çalışma kitapları   | 
|![6 Numara](media/tutorial-explore-report-server-web-portal/number-6.png) | Sayfalandırılmış raporlar için veri kaynakları | 


## <a name="tag-your-favorites"></a>Sık kullanılanları etiketleme
Sık kullanılan olmasını istediğiniz raporları ve KPI'leri etiketleyebilirsiniz. Hem web portalında hem de Power BI mobil uygulamalarında tek bir Sık Kullanılanlar klasöründe toplandıklarından bulunmaları daha kolaydır. 

1. **Kar Marjı** KPI > **Sık Kullanılanlara Ekle** öğesinin sağ üst köşesindeki üç nokta (**…**) simgesini seçin.
   
    ![Sık kullanılanlara ekleme](media/tutorial-explore-report-server-web-portal/power-bi-report-server-add-to-favorites.png)
2. Söz konusu öğeyi web portalındaki Favorites (Sık Kullanılanlar) sayfasında diğer öğelerle birlikte görmek için web portalı şeridindeki **Favorites** (Sık Kullanılanlar) seçeneğini belirleyin.
   
    ![Sık kullanılanları görüntüleme](media/tutorial-explore-report-server-web-portal/power-bi-report-server-favorites.png)

3. Web portalına geri dönmek için **Göz at**’ı seçin.
   
## <a name="view-items-in-list-view"></a>Liste görünümünde öğeleri görüntüleme
Varsayılan olarak web portalı, içeriklerini Kutucuk görünümünde görüntüler.

Aynı anda birden fazla öğenin kolayca taşınabildiği veya silinebildiği Liste görünümüne geçiş yapabilirsiniz. 

1. **Tiles** > **List** (Kutucuklar > Liste) seçeneğini belirleyin.
   
    ![Görünümleri değiştirme](media/tutorial-explore-report-server-web-portal/report-server-web-portal-list-view.png)

2. Kutucuklar görünümüne geri dönün: **Liste** > **Kutucuklar**.

## <a name="power-bi-reports"></a>Power BI raporları

Web portalında Power BI raporlarını görüntüleyip etkileşimde bulunabilir ve Power BI Desktop’ı doğrudan web portalından başlatabilirsiniz.

### <a name="view-power-bi-reports"></a>Power BI raporlarını görüntüleme

1. Web portalındaki **Power BI raporları** altında **Örnek Müşteriye Genel Bakış Raporları**’nı seçin. Rapor, tarayıcıda açılır.

1. Diğer görsellerdeki ilgili değerleri nasıl vurguladığını görmek için, ağaç haritasında Amerika Birleşik Devletleri bloğunu seçin.

    ![Vurgulanmış Power BI raporu](media/tutorial-explore-report-server-web-portal/power-bi-report-server-power-bi.png)

### <a name="edit-in-power-bi-desktop"></a>Power BI Desktop'ta düzenleme

1. **Power BI Desktop'ta düzenle**’yi seçin.

1. Bu web sitesinin bilgisayarınızda bir programı açmasına izin vermek için **İzin Ver**’i seçin. 

     Rapor Power BI Desktop’ta açılır. Üst çubuktaki "Power BI Desktop (Mart 2018)" adını not edin. Bu sürüm, Power BI Rapor Sunucusu için en iyi duruma getirilmiştir.

    ![Power BI Desktop](media/tutorial-explore-report-server-web-portal/power-bi-report-server-power-bi-desktop.png)

     VM’de yüklü olan Power BI Desktop sürümünü kullanın. Bir raporu karşıya yüklemek için etki alanları arasında geçiş yapamazsınız.

3. Alanlar bölmesinde, Müşteriler tablosunu genişletin ve Meslek alanını Rapor düzeyi filtrelerine sürükleyin.

    ![Bir alanı Filtreler bölmesine sürükleme](media/tutorial-explore-report-server-web-portal/power-bi-report-server-desktop-filter.png)

1. Raporu kaydedin.

1. Tarayıcıda rapora geri dönün ve tarayıcının **Yenile** simgesini seçin.

    ![Tarayıcı Yenile simgesi](media/tutorial-explore-report-server-web-portal/power-bi-report-server-browser-refresh.png)

8. Eklediğiniz **Meslek** filtresini görmek için sağ taraftaki **Filtreler** bölmesini genişletin. **Profesyonel**’i seçin.

    ![Filtre uygulanmış Power BI raporu](media/tutorial-explore-report-server-web-portal/power-bi-report-server-power-bi-filtered.png)

3. Web portalına geri dönmek için **Göz at**’ı seçin.

## <a name="paginated-rdl-reports"></a>Sayfalandırılmış (.RDL) raporlar

Sayfalandırılmış raporları görüntüleyip yönetebilir ve web portalından Rapor Oluşturucu’yu başlatabilirsiniz.

### <a name="manage-a-paginated-report"></a>Sayfalandırılmış rapor yönetme

1. Web portalındaki **Sayfalandırılmış raporlar** altında, **Satış Siparişi** > **Yönet** öğesinin yanında bulunan üç noktayı (...) seçin.

1. **Parametreler**’i seçin, **SalesOrderNumber** varsayılan değerini değiştirin: **SO50689** > **Uygula**’yı seçin.

   ![Rapor parametrelerini ayarlama](media/tutorial-explore-report-server-web-portal/power-bi-report-server-set-parameters.png)

3. Web portalına geri dönmek için **Göz at**’ı seçin.

### <a name="view-a-paginated-report"></a>Sayfalandırılmış rapor görüntüleme

1. Web portalında **Satış Siparişi**’ni seçin.
 
3.  Ayarladığınız **Sipariş** parametresi **SO50689** ile açıldığını görürsünüz. 

    ![Sayfalandırılmış rapor parametresi](media/tutorial-explore-report-server-web-portal/power-bi-report-server-paginated.png)

    Burada, varsayılan ayarları değiştirmeden diğer parametrelerle birlikte söz konusu parametreyi değiştirebilirsiniz.

1. **Sipariş** **SO48339** > **Raporu Görüntüle**’yi seçin.

4. Bunun 1/2 numaralı sayfa olduğunu görürsünüz. İkinci sayfayı görmek için sağ oku seçin. Tablo bu sayfadan devam eder.

    ![Sayfalandırılmış rapor sayfası 2/2](media/tutorial-explore-report-server-web-portal/power-bi-report-server-paginated-2-of-2.png)

5. Web portalına geri dönmek için **Göz at**’ı seçin.

### <a name="edit-a-paginated-report"></a>Sayfalandırılmış raporu düzenleme

Rapor Oluşturucusu’nda sayfalandırılmış raporları düzenleyebilir ve Rapor Oluşturucusu’nu doğrudan tarayıcıdan başlatabilirsiniz.

1. Web portalında, **Satış Siparişi** > **Rapor Oluşturucusu’nda Düzenle** öğesinin yanında bulunan üç nokta (...) simgesini seçin.

1. Bu web sitesinin bilgisayarınızda bir programı açmasına izin vermek için **İzin Ver**’i seçin.

1. Satış Siparişi raporu, Rapor Oluşturucusu’nun Tasarım Görünümünde açılır.

    ![Tasarım görünümü, sayfalandırılmış rapor](media/tutorial-explore-report-server-web-portal/power-bi-report-server-paginated-design-view.png)

1. Raporun önizlemesini görmek için **Çalıştır**’ı seçin.

    ![Sayfalandırılmış raporun önizlemesini görme](media/tutorial-explore-report-server-web-portal/power-bi-report-server-paginated-preview.png)

5. Rapor Oluşturucu'yu kapatın ve tarayıcıya geri dönün.

## <a name="view-excel-workbooks"></a>Excel çalışma kitaplarını görüntüleme

Excel çalışma kitaplarını Power BI Rapor Sunucusu’ndaki Excel Online'da görüntüleyip etkileşimde bulunabilirsiniz. 

1. **Office Liquidation Sale.xlsx** adlı Excel çalışma kitabını seçin. Kimlik bilgileri istenebilir. **İptal**’i seçin. 
    Web portalında açılır.
1. Dilimleyicide **Alet**’i seçin.

    ![Web portalında Excel Online](media/tutorial-explore-report-server-web-portal/power-bi-report-server-excel-online.png)

1. Web portalına geri dönmek için **Göz at**’ı seçin.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Bu öğreticiyi bitirdikten sonra kaynak grubunu, sanal makineyi ve tüm ilişkili kaynakları silin. 

- Bunu yapmak için VM kaynak grubunu ve **Sil** öğesini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, Power BI Rapor Sunucusu ile bir VM oluşturdunuz. Web portalının bazı işlevlerini denediniz ve bir Power BI raporu ile sayfalandırılmış bir raporu ilgili düzenleyicilerde açtınız. Bu VM’de SQL Server Analysis Services veri kaynakları yüklü olduğundan, bu veri kaynaklarını kullanarak kendi Power BI raporlarınızı ve sayfalandırılmış raporlarınızı oluşturmayı deneyebilirsiniz. 

Power BI Rapor Sunucusuna yönelik raporlar oluşturma hakkında daha fazla bilgi için devam edin.

> [!div class="nextstepaction"]
> [Power BI Rapor Sunucusu için Power BI raporu oluşturma](./quickstart-create-powerbi-report.md)



