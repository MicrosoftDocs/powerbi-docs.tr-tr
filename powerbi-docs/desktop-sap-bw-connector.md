---
title: Power BI Desktop'ta SAP BW Bağlayıcısı'nı kullanma
description: Power BI Desktop'ta SAP BW Bağlayıcısı'nı kullanma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/05/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: d0cc0ce18a187280c48be0c84bf9adf680ea3ea4
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34813446"
---
# <a name="use-the-sap-bw-connector-in-power-bi-desktop"></a>Power BI Desktop'ta SAP BW Bağlayıcısı'nı kullanma
Power BI Desktop ile **SAP Business Warehouse (BW)** verilerine erişebilirsiniz.

SAP müşterilerinin Power BI’ı mevcut SAP Business Warehouse (BW) sistemlerine bağlayarak nasıl avantaj elde edebileceği hakkında bilgi için bkz. [Power BI ve SAP BW teknik incelemesi](https://aka.ms/powerbiandsapbw).

**Power BI Desktop**’ın Haziran 2018 sürümünden itibaren, SAP BW bağlayıcısını performans ve özellikler bakımından önemli iyileştirmeler içeren bir uygulama ile birlikte kullanabilirsiniz. SAP BW bağlayıcısının bu güncelleştirilmiş sürümü Microsoft tarafından geliştirilmiştir ve **Uygulama 2.0** olarak adlandırılır. Standart **SAP BW Bağlayıcısı**’nı veya **Uygulama 2.0 SAP Bağlayıcısı**’nı seçebilirsiniz. Aşağıdaki bölümlerde, her bir sürümün yüklenmesi sırayla açıklanmaktadır. Power BI Desktop’tan SAP BW’ye bağlanırken bağlayıcılardan birini seçebilirsiniz.

Mümkün olduğunda **Uygulama 2.0 SAP Bağlayıcısı**’nı seçmeniz önerilir.

## <a name="installation-of-the-standard-sap-bw-connector"></a>Standart SAP BW Bağlayıcısı'nı yükleme
Mümkün olduğunda Uygulama 2.0 SAP Bağlayıcısı’nın kullanılması önerilir (aşağıdaki bölümde verilen yönergelere bakın). Bu bölümde, aşağıdaki yükleme adımları uygulanarak gerçekleştirebileceğiniz standart **SAP BW Bağlayıcısı**’nı yükleme işlemi açıklanmaktadır:

1. Yerel makinenize **SAP NetWeaver** kitaplığını yükleyin. **SAP Netweaver** kitaplığını SAP yöneticinizden veya doğrudan [SAP Software Download Center](https://support.sap.com/swdc) sayfasından edinebilirsiniz. **SAP Software Download Center** sayfasının yapısı sıklıkla değiştiğinden sitede gezinmeyle ilgili ayrıntılı bilgi veremiyoruz. **SAP NetWeaver** kitaplığı genelde SAP Client Tools yüklemesine de dahil edilir.
   
   Son sürümü bulmak için *SAP Note #1025361* terimini de aratabilirsiniz. **SAP NetWeaver** kitaplığı mimarisinin (32 bit veya 64 bit) **Power BI Desktop** yüklemenizle aynı olduğundan emin olduktan sonra **SAP NetWeaver RFC SDK** içindeki tüm dosyaları SAP Note talimatlarına uygun şekilde yükleyin.
2. **Veri Al** iletişim kutusunun **Veritabanı** kategorisinde **SAP Business Warehouse Uygulama Sunucusu** ve **SAP Business Warehouse İleti Sunucusu** için bir giriş bulunur.
   
   ![SAP için Veri Alma seçenekleri](media/desktop-sap-bw-connector/sap_bw_2a.png)

## <a name="installation-of-implementation-20-sap-connector"></a>Uygulama 2.0 SAP Bağlayıcısı’nı yükleme

SAP Bağlayıcısı **Uygulama 2.0**, SAP .NET Bağlayıcısı 3.0 gerektirir. Aşağıdaki bağlantıyı kullanarak [SAP .NET Bağlayıcısı 3.0](https://go.microsoft.com/fwlink/?linkid=872300)’ı SAP’nin web sitesinden indirebilirsiniz:

* [SAP .NET Bağlayıcısı 3.0](https://go.microsoft.com/fwlink/?linkid=872300)

İndirme bağlantısına erişmek için geçerli bir S kullanıcı gerekir. Müşterilerin SAP .NET Bağlayıcısı 3.0’ı edinmek için SAP Basis ekibi ile iletişim kurması önerilir. 

Bağlayıcının 32 bit ve 64 bit sürümleri mevcuttur ve kullanıcılar Power BI Desktop yüklemeleri ile eşleşen sürümü *seçmelidir*. Bu makalenin yazıldığı sırada, web sitesinde iki sürüm (.NET 4.0 framework için) listelenmektedir:

* Windows 32 bit (x86) için Microsoft .NET 3.0.20.0 SAP Bağlayıcısı zip dosyası (6,896 KB), 16 Ocak 2018
* Windows 64 bit (x64) için Microsoft .NET 3.0.20.0 SAP Bağlayıcısı zip dosyası (7,180 KB), 16 Ocak 2018

Yükleme sırasında, **İsteğe bağlı kurulum adımları** penceresinde aşağıdaki resimde gösterildiği gibi *Bütünleştirilmiş kodları GAC’ye yükle* seçeneğini işaretlediğinizden emin olun.

![SAP isteğe bağlı kurulum adımları](media/desktop-sap-bw-connector/sap_bw_2b.png)

> [!NOTE]
> Standart SAP BW uygulaması için Netweaver DLL’leri gerekiyordu. SAP Bağlayıcısı Uygulama 2.0 kullanıyorsanız ve standart sürümü kullanmıyorsanız, Netweaver DLL’leri gerekli değildir.


## <a name="standard-sap-bw-connector-features"></a>Standart SAP BW Bağlayıcısı'nın özellikleri
Power BI Desktop’taki standart **SAP BW Bağlayıcısı**, **SAP Business Warehouse Sunucusu** küplerinden verileri içeri aktarmanıza veya DirectQuery’yi kullanmanıza olanak tanır. 

**SAP BW bağlayıcısı** ve bunun DirectQuery ile kullanımı hakkında daha fazla bilgi edinmek için [DirectQuery ve SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md) makalesine göz atın.

Bağlantıyı kurmak için bir *Sunucu*, *Sistem Numarası* ve *İstemci Kimliği* belirtmeniz gerekir.

![SAP sunucusu bağlantı ayarları](media/desktop-sap-bw-connector/sap_bw_3a.png)

Ayrıca belirtebileceğiniz iki ek **Gelişmiş seçenek** de vardır: Dil kodu ve belirtilen sunucuda çalıştırılacak özel MDX deyimi.

![ek bağlantı bilgileri](media/desktop-sap-bw-connector/sap_bw_4a.png)

Herhangi bir MDX deyimi belirtilmezse **Gezgin** penceresi açılır ve burada sunucudaki kullanılabilir küplerin listesinin yanı sıra kullanılabilir küplerden boyutlar ve ölçüler dahil olmak üzere detaya gitme ve öğe belirleme seçenekleri görüntülenir. Power BI, [BW Open Analysis Interface OLAP BAPI'leri](https://help.sap.com/saphelp_nw70/helpdata/en/d9/ed8c3c59021315e10000000a114084/content.htm) tarafından gösterilen sorguları ve küpleri gösterir.

Sunucudan bir veya daha fazla öğe seçtiğinizde yaptığınız seçime bağlı olarak çıkış tablosu önizlemesi oluşturulur.

![SAP tablo önizlemesi](media/desktop-sap-bw-connector/sap_bw_5.png)

**Gezgin** penceresinde ayrıca aşağıdakileri yapmanızı sağlayan birkaç **Görüntüleme Seçeneği** de bulunur:

* ***Yalnızca Seçilen Öğeler* veya *Tüm Öğeler* (varsayılan görünüm) arasında seçim yapma:** Bu seçenek, seçilen son öğe kümesini doğrulama açısından yararlıdır. Bu görünüme alternatif olarak *Önizleme* alanında *Sütun Adları*'nı seçerek de ulaşabilirsiniz.
* **Veri Önizlemelerini Etkinleştir (varsayılan davranış):** Veri önizlemelerinin bu iletişim kutusunda görüntülenip görüntülenmeyeceğini de denetleyebilirsiniz. Veri önizlemelerini devre dışı bıraktığınızda, önizleme için veri isteği gönderilmediğinden sunucu çağrısı sayısı da azalır.
* **Teknik Adlar:** SAP BW, bir küp içindeki nesneler için *teknik adlar* kavramının kullanılmasını destekler. Teknik adlar, küp sahibinin küp içindeki nesnelerin yalnızca *fiziksel adlarını* değil, küp nesnelerinin *kolay adlarını* da görüntülemesini sağlar.

![Gezgin penceresi](media/desktop-sap-bw-connector/sap_bw_6.png)

**Gezgin**'de gerekli tüm nesneleri seçtikten sonra **Gezgin** penceresinin en altında bulunan aşağıdaki düğmelerden birini seçerek bir sonraki adımı belirleyebilirsiniz:

* **Yükle**'yi seçtiğinizde satır kümesinin tamamı çıkış tablosunu oluşturmak üzere Power BI Desktop veri modeline yüklenir. Ardından açılan **Rapor** görünümünde verileri görselleştirmeye başlayabilir ya da **Veri** veya **İlişkiler** görünümlerini kullanarak ek değişiklikler yapabilirsiniz.
* **Düzenle**'yi seçtiğinizde açılan **Sorgu Düzenleyicisi**'nde satır kümesinin tamamı Power BI Desktop veri modeline alınmadan önce ek veri dönüştürme ve filtreleme adımları uygulayabilirsiniz.

**SAP BW** küplerindeki verileri içeri aktarmanın yanı sıra Power BI Desktop'a birçok farklı veri kaynağından da veri aktararak bunları tek bir raporda birleştirebileceğinizi unutmayın. Bu sayede **SAP BW** verilerine ek olarak çok çeşitli raporlama ve analiz senaryoları oluşturabilirsiniz.

## <a name="using-implementation-20-sap-bw-connector"></a>Uygulama 2.0 SAP BW Bağlayıcısı'nı kullanma

SAP BW Bağlayıcısı Uygulama 2.0’ı kullanmak için yeni bir bağlantı oluşturmanız gerekir. Yeni bir bağlantı oluşturmak için aşağıdaki adımları uygulayın.

1. **Veri Al** penceresinden **SAP Business Warehouse Uygulama Sunucusu** veya **SAP Business Warehouse İleti Sunucusu**’nu seçin.

2. Uygulamanın seçilmesine olanak tanıyan yeni bağlantı iletişim kutusu açılır. Aşağıdaki görüntüde gösterildiği gibi **Uygulama 2.0** seçildiğinde Yürütme modu, Toplu iş boyutu ve Özellik yapılarını etkinleştir seçenekleri etkin hale gelir.

    ![SAP bağlantısı iletişim kutusu](media/desktop-sap-bw-connector/sap_bw_7.png)

3. **Tamam**’ı seçtikten sonra **Gezgin** deneyimi, standart SAP BW Bağlayıcısına ilişkin önceki bölümde açıklanan deneyimle aynıdır. 

### <a name="new-options-for-implementation-20"></a>Uygulama 2.0 için yeni seçenekler 

Uygulama 2.0 aşağıdaki seçenekleri destekler:

1. **ExecutionMode** - Sunucu üzerinde sorgu yürütmek için kullanılan MDX arabirimini belirtir. Geçerli seçenekler aşağıdaki gibidir:

        a. SapBusinessWarehouseExecutionMode.BasXml
        b. SapBusinessWarehouseExecutionMode.BasXmlGzip
        c. SapBusinessWarehouseExecutionMode.DataStream

    Bu seçenek için varsayılan değer SapBusinessWarehouseExecutionMode.BasXmlGzip şeklindedir.

    *SapBusinessWarehouseExecutionMode.BasXmlGzip* değerinin kullanılması, büyük veri kümeleri için yüksek gecikme süresi yaşandığında performansı artırabilir.

2. **BatchSize** - Bir MDX deyimi yürütülürken aynı anda alınacak en fazla satır sayısını belirtir. Az sayıda satır, büyük bir veri kümesi alınırken sunucuya daha fazla çağrı gönderilmesine neden olur. Çok sayıda satır, performansını artırabilir ancak SAP BW sunucusunda bellek sorunlarına neden olabilir. Varsayılan değer 50000 satırdır.

3. **EnableStructures** - Özellik yapılarının tanınıp tanınmadığını belirten mantıksal değer. Bu seçenek için varsayılan değer false şeklindedir. Seçime uygun olan nesnelerin listesini etkiler. Yerel sorgu modunda desteklenmez.

**ScaleMeasures** seçeneği bu uygulamada kullanım dışı bırakılmıştır. Şu anda davranış, her zaman ölçeklendirilmemiş değerleri gösteren *ScaleMeasures = false* ayarı ile aynıdır.

### <a name="additional-improvements-for-implementation-20"></a>Uygulama 2.0 için diğer iyileştirmeler 

Aşağıdaki madde işaretli listede yeni uygulama ile birlikte gelen ek iyileştirmelerden bazıları açıklanmaktadır:

* Performans iyileştirmesi
* Birkaç milyon veri satırı alma ve toplu iş boyutu parametresi ile ince ayar yapma olanağı.
* Yürütme modları arasında geçiş yapma olanağı.
* Sıkıştırılmış mod desteği. Özellikle yüksek gecikme süreli bağlantılar veya büyük veri kümeleri için yararlıdır.
* Tarih değişkenlerinin daha iyi algılanması
* [Deneysel] Metin değerleri yerine, sırasıyla tarih ve saat olarak Kullanıma Sunma Tarihi (ABAP türü DATS) ve Saat (ABAP türü TIMS) boyutları.
* Daha iyi özel durum işleme. BAPI çağrılarında oluşan hatalar şimdi yüzeye çıkarılmıştır.
* BasXml ve BasXmlGzip modlarında sütun katlama. Örneğin, oluşturulan MDX sorgusu 40 sütun alırken geçerli seçim için yalnızca 10 sütun gerekliyse, bu istek daha küçük bir veri kümesi almak üzere sunucuya geçirilir.


### <a name="changing-existing-reports-to-use-implementation-20"></a>Var olan raporları Uygulama 2.0 kullanacak şekilde değiştirme 

Var olan raporların **Uygulama 2.0** kullanacak şekilde değiştirilmesi yalnızca İçeri Aktarma modunda mümkündür ve aşağıdaki adımların el ile uygulanmasını gerektirir.

1. Var olan bir raporu açın, şeritten **Sorguları Düzenle**’yi seçin ve sonra güncelleştirmek istediğiniz SAP Business Warehouse sorgusunu belirleyin.

2. Sorguya sağ tıklayın ve **Gelişmiş Düzenleyici**’yi seçin.

3. **Gelişmiş Düzenleyici**’de SapBusinessWarehouse.Cubes çağrısını aşağıdaki gibi değiştirin: 

    a. Sorgunun halihazırda aşağıdaki örnekte gösterildiği gibi bir seçenek kaydı içerip içermediğini belirleyin:

    ![sorgu kod parçacığı](media/desktop-sap-bw-connector/sap_bw_9.png)

    b. Bu durum geçerliyse, Uygulama 2.0 seçeneğini ekleyin ve mevcutsa, aşağıda gösterildiği gibi ScaleMeasures seçeneğini kaldırın:

    ![sorgu kod parçacığı](media/desktop-sap-bw-connector/sap_bw_10.png)

    c. Sorgu halihazırda bir seçenekler kaydı içermiyorsa eklemeniz yeterlidir. Örneğin, aşağıdakileri içeriyorsa:

    ![sorgu kod parçacığı](media/desktop-sap-bw-connector/sap_bw_11.png)

    d. Yalnızca şu şekilde değiştirin:

    ![sorgu kod parçacığı](media/desktop-sap-bw-connector/sap_bw_12.png)

4. SAP BW Bağlayıcısı Uygulama 2.0’ı standart SAP BW Bağlayıcısı ile uyumlu hale getirmek için her türlü çaba gösterilmiştir. Ancak, kullanılmakta olan farklı SAP BW MDX yürütme modları nedeniyle bazı farklılıklar olabilir. Tutarsızlıkları gidermek için yürütme modları arasında geçiş yapmayı deneyin.

## <a name="troubleshooting"></a>Sorun giderme
Bu bölümde **SAP BW** bağlayıcısıyla çalışırken karşılaşabileceğiniz sorunlara (ve çözümlerine) yer verilmiştir.

1. **SAP BW** sayısal verilerinde ondalık ayırıcı olarak virgül yerine nokta dönüyor. Örneğin 1,000,000 sayısı 1.000.000 olarak döndürülüyor.
   
   **SAP BW**, ondalık verileri *,* (virgül) veya *.* (nokta) ondalık ayırıcısıyla döndürür. **SAP BW**'nin hangi ondalık ayırıcıyı kullanacağını belirtmek için **Power BI Desktop** tarafından kullanılan sürücü, *BAPI_USER_GET_DETAIL* için bir çağrıda bulunur. Bu çağrı tarafından döndürülen **DEFAULTS** adlı yapının *DCPFM* alanında *Decimal Format Notation* (Ondalık Ayırıcı Biçimi) bulunur. Bu parametre aşağıdaki üç değerden birini alır:
   
       ‘ ‘ (space) = Decimal point is comma: N.NNN,NN
       'X' = Decimal point is period: N,NNN.NN
       'Y' = Decimal point is N NNN NNN,NN
   
   Bu sorunu bildiren müşteriler *BAPI_USER_GET_DETAIL* çağrısının belirli bir kullanıcı (verilerin hatalı gösterildiği kullanıcı) için başarısız olduğunu ve aşağıdakine benzer bir hata iletisiyle karşılaşıldığını belirlemiştir:
   
       You are not authorized to display users in group TI:
           <item>
               <TYPE>E</TYPE>
               <ID>01</ID>
               <NUMBER>512</NUMBER>
               <MESSAGE>You are not authorized to display users in group TI</MESSAGE>
               <LOG_NO/>
               <LOG_MSG_NO>000000</LOG_MSG_NO>
               <MESSAGE_V1>TI</MESSAGE_V1>
               <MESSAGE_V2/>
               <MESSAGE_V3/>
               <MESSAGE_V4/>
               <PARAMETER/>
               <ROW>0</ROW>
               <FIELD>BNAME</FIELD>
               <SYSTEM>CLNTPW1400</SYSTEM>
           </item>
   
   Bu hatayı çözmek için kullanıcıların SAP yöneticilerinden Power BI'da kullanılan SAPBW kullanıcısına *BAPI_USER_GET_DETAIL* yürütme iznini vermelerini istemesi gerekmektedir. Ayrıca bu sorun giderme adımının önceki bölümlerinde anlatıldığı üzere kullanıcının gerekli *DCPFM* değerini alıp almadığının doğrulanmasında da fayda vardır.
2. **SAP BEx sorguları için bağlantı**
   
   Aşağıdaki görüntüde gösterildiği üzere belirli bir özelliği etkinleştirerek Power BI Desktop'ta **BEx** sorguları gerçekleştirebilirsiniz:
   
   ![](media/desktop-sap-bw-connector/sap_bw_8.png)

## <a name="next-steps"></a>Sonraki adımlar
SAP ve DirectQuery hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen Veri Kaynakları](desktop-directquery-data-sources.md)
* [Power BI ve SAP BW teknik incelemesi](https://aka.ms/powerbiandsapbw)
