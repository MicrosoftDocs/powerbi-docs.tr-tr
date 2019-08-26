---
title: Power BI hizmetinde Excel çalışma kitabından muhteşem raporlar elde etme
description: Bu makalede bir Excel çalışma kitabından hızlıca etkileyici bir rapor oluşturma işlemi gösterilmektedir.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/12/2019
ms.author: maggies
LocalizationGroup: Data from files
ms.openlocfilehash: ed4bc9d10e3e1512aba559d77ba8729a39cb8a84
ms.sourcegitcommit: d12bc6df16be1f1993232898f52eb80d0c9fb04e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68995021"
---
# <a name="from-excel-workbook-to-stunning-report-in-the-power-bi-service"></a>Power BI hizmetinde Excel çalışma kitabından muhteşem raporlar elde etme
Yöneticiniz gün bitimine kadar, son kampanyaya ilişkin izlenimlerinizle birlikte güncel satış rakamlarınızın yer aldığı bir rapor sunmanızı istiyor. Ancak, güncel verileriniz çeşitli üçüncü taraf sistemlerde ve dizüstü bilgisayarınızdaki dosyalarda bulunur. Daha önce, görseller oluşturmak ve bir raporu biçimlendirmek saatler sürüyor ve sonunda endişelenmeye başlıyordunuz.

Endişelenmeyin. Power BI ile çok kısa sürede harika raporlar oluşturabilirsiniz.

Bu örnekte, yerel sistemde bulunan bir dosyayı karşıya yükleyecek, yeni bir rapor oluşturacak ve bu raporu iş arkadaşlarımızla paylaşacağız. Üstelik bu işlemlerin tümünü Power BI'da gerçekleştireceğiz.

## <a name="prepare-your-data"></a>Verilerinizi hazırlama
Örnek olarak basit bir Excel dosyasını ele alalım. 

1. Excel dosyanızı Power BI'a yükleyebilmeniz için verilerinizi düz bir tabloda düzenlemeniz gerekir. Düz bir tabloda, her sütun aynı veri türünü (örn. metin, tarih, sayı veya para birimi) içerir. Tablonuzun bir başlık satırı olması gerekir, ancak toplamları görüntüleyen herhangi bir sütun veya satır olmamalıdır.

   ![Excel'de düzenlenmiş veriler](media/service-from-excel-to-stunning-report/pbi_excel_file.png)

2. Şimdi, verilerinizi bir tablo olarak biçimlendirin. Excel'in **Giriş** sekmesindeki **Stiller** grubunda **Tablo Olarak Biçimlendir** seçeneğini belirleyin. 

3. Çalışma sayfanızda uygulanacak bir tablo stili seçin. 

   Excel çalışma sayfanız artık Power BI'a yüklenmek için hazır.

   ![Tablo olarak biçimlendirilmiş veriler](media/service-from-excel-to-stunning-report/pbi_excel_table.png)

## <a name="upload-your-excel-file-to-the-power-bi-service"></a>Excel dosyanızı Power BI hizmetine yükleme
Power BI hizmeti, bilgisayarınızda bulunan Excel dosyaları da dahil olmak üzere birçok veri kaynağına bağlanır. 

 > [!NOTE] 
 > Bu öğreticinin kalan kısmında birlikte ilerleyebilmemiz için [Finansal Örnek çalışma kitabını](sample-financial-download.md) kullanın.

1. Çalışmaya başlamak için Power BI hizmetinde oturum açın. Henüz kaydınız yoksa [ücretsiz kaydolabilirsiniz](https://powerbi.com).

2. Yeni bir pano oluşturmak istediğinizi varsayalım. **Çalışma Alanım**'ı açın ve **Oluştur** simgesini seçin.

   ![Oluştur simgesi](media/service-from-excel-to-stunning-report/power-bi-new-dash.png)

3. **Pano**'yu seçin, bir ad girin ve sonra **Oluştur**’u seçin. 

   Yeni pano hiç veri olmadan görüntülenir.

   ![Oluştur açılan menüsü](media/service-from-excel-to-stunning-report/power-bi-create-dash.png)

4. Sol gezinti bölmesinin alt kısmında bulunan **Veri al** seçeneğini belirleyin. 

5. **Veri Al** sayfasındaki **Yeni içerik oluştur**’un altında bulunan **Dosyalar** kutusunda **Al**’ı seçin.

   ![Dosyalardan veri alma](media/service-from-excel-to-stunning-report/pbi_get_files.png)

6. **Dosyalar** sayfasında **Yerel Dosya**'yı seçin. Bilgisayarınızdaki Excel çalışma kitabına gidin ve Power BI hizmetine yüklemek için **Aç**'ı seçin. 

   ![Veri al > Dosyalar penceresi](media/service-from-excel-to-stunning-report/pbi_local_file.png)

7. **Yerel Dosya** sayfasından **İçeri Aktar**’ı seçin.


## <a name="build-your-report"></a>Raporunuzu oluşturma
Power BI hizmeti Excel dosyanızı içeri aktardıktan sonra raporunuzu oluşturmaya başlayın. 

1. **Veri kümeniz hazır** iletisi göründüğünde **Veri kümesini görüntüle**'yi seçin.  

   Power BI, Düzenleme görünümü'nde açılır ve rapor tuvali görüntülenir. Sağ tarafta **Görsel Öğeler**, **Filtreler** ve **Alanlar** bölmeleri bulunur. Excel çalışma kitabınızdaki tablo verilerinin, **Alanlar** bölümünde göründüğüne dikkat edin. Power BI, sütun başlıklarını tablo adının altında ayrı alanlar olarak listeler.

   ![Alanlar bölmesinde Excel verilerinin görünümü](media/service-from-excel-to-stunning-report/pbi_report_fields.png)

2. Artık görselleştirme oluşturmaya başlayabilirsiniz. Yöneticinizin zaman içinde elde edilen kârı görmek istediğini varsayalım. **Alanlar** bölmesinde **Kar**’ı rapor tuvaline sürükleyin. 

   Varsayılan olarak, Power BI bir çubuk grafik gösterir. 

3. **Tarih** alanını da rapor tuvaline sürükleyin. 

   Power BI, çubuk grafiği, tarihe göre kâr görüntülenecek şekilde güncelleştirir.

   ![Rapor düzenleyicisindeki sütun grafik](media/service-from-excel-to-stunning-report/pbi_report_pin-new.png)

   > [!TIP]
   > Grafiğiniz beklediğiniz gibi görünmüyorsa toplama işlemlerinizi kontrol edin. Örneğin, **Değer** kutusunda, yeni eklediğiniz değere sağ tıklayın ve verilerin istediğiniz şekilde toplandığından emin olun. Biz bu örnekte **Toplam** seçeneğini kullanıyoruz.
   > 

Yöneticiniz, en fazla kâr sağlayan ülkeleri görmek istiyor. Bir harita görselleştirmesi hazırlayarak yöneticinizi etkileyebilirsiniz. 

1. Rapor tuvalinizde boş bir alan seçin. 

2. **Alanlar** bölmesinde **Ülke** ve **Kar** alanlarını rapor tuvalinize sürükleyin.

   Power BI her bir konumun göreceli kârını temsil eden balonlar içeren bir harita görseli oluşturur.

   ![Rapor düzenleyicisindeki harita görseli](media/service-from-excel-to-stunning-report/pbi_report_map-new.png)

Ürüne ve pazar segmentine göre satışları görüntüleyen bir görsel oluşturmaya ne dersiniz? Çok basit. 

1. **Alanlar** bölmesinde **Satışlar**, **Ürün** ve **Segment** alanlarını seçin. 
   
   Power BI anında bir çubuk grafik oluşturur. 

2. **Görsel Öğeler** menüsündeki simgelerden birini seçerek grafiğin türünü değiştirin. Örneğin, görseli bir **Yığılmış sütun grafik** olarak değiştirin. 

3. Grafiği sıralamak için üç nokta (...) > **Sıralama Ölçütü** seçeneğini belirleyin.

   ![Rapor düzenleyicisinde yığılmış sütun grafik](media/service-from-excel-to-stunning-report/pbi_barchart-new.png)

Tüm görsellerinizi panonuza sabitleyin. Artık, panonuzu iş arkadaşlarınızla paylaşabilirsiniz.

   ![Sabitlenmiş üç görselin bulunduğu pano](media/service-from-excel-to-stunning-report/pbi_report.png)

## <a name="share-your-dashboard"></a>Panonuzu paylaşma
Panonuzu yöneticinizle paylaşmak istediğinizi varsayalım. Panonuzu ve bağlantılı raporu, Power BI hesabı olan tüm iş arkadaşlarınızla paylaşabilirsiniz. Bu kişi raporunuzla etkileşim kurabilir ancak değişiklikleri kaydedemez.

1. Raporunuzu paylaşmak için panonun üst kısmında bulunan **Paylaş** seçeneğini belirleyin.

   ![Paylaş simgesi](media/service-from-excel-to-stunning-report/power-bi-share.png)

   Power BI, **Panoyu paylaş** sayfasını görüntüler. 

2. **E-posta adreslerini girin** kutusuna alıcıların e-posta adreslerini girin ve altındaki kutuya bir mesaj ekleyin. 

3. Alıcıların panonuzu diğer kullanıcılarla paylaşmasına izin vermek için **Alıcıların panonuzu paylaşmasına izin verin** seçeneğini belirleyin. **Paylaş**'ı seçin.

   ![Panoyu paylaşma penceresi](media/service-from-excel-to-stunning-report/power-bi-share-dash-new.png)

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI hizmeti ile çalışmaya başlama](service-get-started.md)
* [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md)
* [Power BI hizmetinde tasarımcılar için temel kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/).

