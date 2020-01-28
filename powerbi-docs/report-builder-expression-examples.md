---
title: Power BI Rapor Oluşturucusu’nda İfade örnekleri
description: İçerik ve rapor görünümünü denetlemek için Power BI Report Builder’da ifadeler sıklıkla kullanılır.
ms.date: 10/21/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 87ddb651-a1d0-4a42-8ea9-04dea3f6afa4
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 48e81c91a4555b4c8ea847ddffb1413058bbb152
ms.sourcegitcommit: df8bcc65f0df69bf1fc1d47eb06575742eac1622
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75953972"
---
# <a name="expression-examples-in-power-bi-report-builder"></a>Power BI Rapor Oluşturucusu’nda İfade örnekleri
İçerik ve rapor görünümünü denetlemek için Power BI Report Builder’da ifadeler sıklıkla kullanılır. Microsoft Visual Basic’te yazılan ifadeler yerleşik işlevleri, özel kodu, rapor ve grup değişkenlerini, kullanıcı tanımlı değişkenleri kullanabilir. İfadeler eşittir işaretiyle (=) başlar.   

Bu konu, bir raporda sıkça gerçekleştirilen görevler için kullanılabilen ifadelerin örneklerini sunar.  
  
-   Tarih, dize, dönüştürme ve koşullu Visual Basic işlevlerine yönelik [Visual Basic İşlevi](#VisualBasicFunctions) Örnekleri.  
  
-   Toplamalar ve diğer yerleşik rapor işlevlerine yönelik [Rapor İşlevi](#ReportFunctions) Örnekleri.  
  
-   Raporun görünümünü değiştirmeye yönelik [Rapor Verileri Görünümü](#AppearanceofReportData) Örnekleri.  
  
-   Biçimi veya görünürlüğü denetlemek için rapor öğesi özelliklerini ayarlamaya yönelik [Özellik](#Properties) Örnekleri.  
  
-   Bir ifadede parametreleri kullanmaya yönelik [Parametre](#Parameters) Örnekleri.  
  
-   Ekli özel kodlardan oluşan [Özel Kod](#CustomCode) Örnekleri.  
  
Basit ve karmaşık ifadeler, ifadelerin kullanım yerleri ve bir ifadeye ekleyebileceğiniz başvuru türleri hakkında daha fazla bilgi edinmek için [Power BI Rapor Oluşturucusu’nda İfadeler](report-builder-expressions.md) bölümünde yer alan konu başlıklarına göz atın. 
  
## <a name="functions"></a>İşlevler  
 Bir raporda bulunan ifadelerin çoğu işlev içerir. Bu işlevleri kullanarak verileri biçimlendirebilir, mantık uygulayabilir ve raporun meta verilerine erişebilirsiniz. Microsoft Visual Basic çalışma zamanı kitaplığındaki işlevlerin yanı sıra `xref:System.Convert` ve `xref:System.Math` ad alanlarındaki işlevleri de kullanan ifadeler yazabilirsiniz. Özel kodda işlevlere başvurular ekleyebilirsiniz. `xref:System.Text.RegularExpressions` dahil olmak üzere Microsoft .NET Framework sınıflarını da kullanabilirsiniz.  
  
##  <a name="VisualBasicFunctions"></a> Visual Basic işlevleri  
 Metin kutularında görüntülenen veya parametreler, özellikler veya raporun diğer alanları için kullanılan verileri denetlemek için Visual Basic işlevlerini kullanabilirsiniz. Bu bölüm, bu işlevlerin bazılarını gösteren örnekleri sunar. Daha fazla bilgi için MSDN’de bulunan [Visual Basic Çalışma Zamanı Kitaplığı Üyeleri](https://go.microsoft.com/fwlink/?LinkId=198941) bölümüne göz atın.  
  
 .NET Framework birçok özel biçim seçeneği sunar (örneğin, belirli tarih biçimlerine yönelik seçenekler). Daha fazla bilgi için bkz. [Biçimlendirme Türleri](/dotnet/standard/base-types/formatting-types).  
  
### <a name="math-functions"></a>Matematik İşlevleri  
  
-   **Round** işlevi, sayıları en yakın tamsayıya yuvarlamak için kullanışlıdır. Aşağıdaki ifade 1,3 değerini 1’e yuvarlar:  
  
    ```  
    = Round(1.3)  
    ```  
  
     Excel’deki **MRound** işlevine benzer şekilde, bir değeri belirttiğiniz bir katsayıya yuvarlamak için bir ifade de yazabilirsiniz. Tamsayı oluşturan bir faktörle değeri çarpın, sayıyı yuvarlayın ve bunu aynı faktöre bölün. Örneğin, 1,3 değerini 0,2’nin en yakın katına (1,4) yuvarlamak için aşağıdaki ifadeyi kullanın:  
  
    ```  
    = Round(1.3*5)/5  
    ```  
  
###  <a name="DateFunctions"></a> Tarih işlevleri  
  
-   **Today** işlevi geçerli tarihi sağlar. Bu ifade, tarihin raporda gösterilmesini sağlamak için bir metin kutusunda veya verileri, geçerli tarihi temel alarak filtrelemek için bir parametrede kullanılabilir.  
  
    ```  
    =Today()  
    ```  
  
-   Tarihin belirli bir kısmını çekmek için **DateInterval** işlevini kullanın. Bazı geçerli **DateInterval** parametrelerini aşağıda bulabilirsiniz:

    -   DateInterval.Second
    -   DateInterval.Minute
    -   DateInterval.Hour
    -   DateInterval.Weekday
    -   DateInterval.Day
    -   DateInterval.DayOfYear
    -   DateInterval.WeekOfYear
    -   DateInterval.Month
    -   DateInterval.Quarter
    -   DateInterval.Year

    Örneğin, bu ifade bugünün tarihinin mevcut yılın kaçıncı haftasında olduğunu gösterir:
  
    ```  
    =DatePart(DateInterval.WeekOfYear, today()) 
    ```  
  
-   **DateAdd** işlevi, tek bir parametreyi temel alarak bir tarih aralığı sağlamak için kullanışlıdır. Aşağıdaki ifade, *StartDate* adlı parametrenin altı ay sonrasına denk gelen bir ifade sağlar.  
  
    ```  
    =DateAdd(DateInterval.Month, 6, Parameters!StartDate.Value)  
    ```  
  
-   **Year** işlevi, belirli bir tarih için yılı görüntüler. Tarihleri birlikte gruplandırmak veya bir tarih kümesinin etiketi olarak yıl değerini görüntülemek için bunu kullanabilirsiniz. Bu ifade, belirli bir satış siparişi tarih grubu için yıl değerini sağlar. Tarihleri denetlemek için **Month** işlevi ve diğer işlevler de kullanılabilir. Daha fazla bilgi için Visual Basic belgelerine bakın.  
  
    ```  
    =Year(Fields!OrderDate.Value)  
    ```  
  
-   Biçimi özelleştirmek için bir ifadedeki işlevleri birleştirebilirsiniz. Aşağıdaki ifade, ay, gün, yıl biçiminde yazılmış bir tarihin biçimini ay, hafta, hafta numarası olacak şekilde değiştirir. Örneğin, 12/23/2009 tarihi Aralık 3. Hafta olarak değiştirilir:  
  
    ```  
    =Format(Fields!MyDate.Value, "MMMM") & " Week " &   
    (Int(DateDiff("d", DateSerial(Year(Fields!MyDate.Value),   
    Month(Fields!MyDate.Value),1), Fields!FullDateAlternateKey.Value)/7)+1).ToString  
    ```  
  
     Hesaplanan alan olarak bir veri kümesinde kullanıldığında, değerleri her ayın haftalarına göre toplamak için bu ifadeyi bir grafikte kullanabilirsiniz.  
  
-   Aşağıdaki ifade SellStartDate değerini AAA-YY olarak biçimlendirir. SellStartDate alanı bir DateTime veri türüdür.  
  
    ```  
    =FORMAT(Fields!SellStartDate.Value, "MMM-yy")  
    ```  
  
-   Aşağıdaki ifade SellStartDate değerini gg/AA/yyyy olarak biçimlendirir. SellStartDate alanı bir DateTime veri türüdür.  
  
    ```  
    =FORMAT(Fields!SellStartDate.Value, "dd/MM/yyyy")  
    ```  
  
-   **CDate** işlevi değeri bir tarihe dönüştürür. **Now** işlevi, sisteminize göre geçerli tarih ve saati içeren değeri döndürür. **DateDiff**, iki Tarih değerinin arasındaki zaman aralıklarının sayısını belirten bir Long değeri döndürür.  
  
     Aşağıdaki örnek, geçerli yılın başlangıç tarihini görüntüler  
  
    ```  
    =DateAdd(DateInterval.Year,DateDiff(DateInterval.Year,CDate("01/01/1900"),Now()),CDate("01/01/1900"))  
    ```  
  
-   Aşağıdaki örnek, geçerli ayı temel alarak önceki ayın başlangıç tarihini görüntüler.  
  
    ```  
    =DateAdd(DateInterval.Month,DateDiff(DateInterval.Month,CDate("01/01/1900"),Now())-1,CDate("01/01/1900"))  
    ```  
  
-   Aşağıdaki ifade, SellStartDate ve LastReceiptDate arasındaki aralık yıllarını oluşturur. Bu alanlar iki farklı veri kümesinde (DataSet1 ve DataSet2) bulunur.  
  
    ```  
    =DATEDIFF("yyyy", First(Fields!SellStartDate.Value, "DataSet1"), First(Fields!LastReceiptDate.Value, "DataSet2"))  
    ```  
  
-   **DatePart** işlevi, belirli bir Tarih değerinin belirtilen bileşenini içeren bir Tamsayı değerini döndürür. Aşağıdaki ifade, DataSet1’deki SellStartDate’in ilk değeri için yıl değerini döndürür. Raporda birden çok veri kümesi bulunduğu için veri kümesi kapsamı belirtilir.  
  
    ```  
    =Datepart("yyyy", First(Fields!SellStartDate.Value, "DataSet1"))  
  
    ```  
  
-   **DateSerial** işlevi, zaman bilgisi gece yarısına ayarlı olacak şekilde, belirtilen yıl, ay ve günü temsil eden bir Tarih değerini döndürür. Aşağıdaki örnek, bu ayı temel alarak önceki ayın bitiş tarihini görüntüler.  
  
    ```  
    =DateSerial(Year(Now()), Month(Now()), "1").AddDays(-1)  
    ```  
  
-   Aşağıdaki ifadeler, kullanıcı tarafından seçilen tarih parametresi değerini temel alarak çeşitli tarihleri görüntüler.  
  
|Örnek Açıklaması|Örnek|  
|-------------------------|-------------|  
|Dün|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-1)`|  
|İki Gün Önce|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-2)`|  
|Bir Ay Önce|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-1,Day(Parameters!TodaysDate.Value))`|  
|İki Ay Önce|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-2,Day(Parameters!TodaysDate.Value))`|  
|Bir Yıl Önce|`=DateSerial(Year(Parameters!TodaysDate.Value)-1,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
|İki Yıl Önce|`=DateSerial(Year(Parameters!TodaysDate.Value)-2,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
  
###  <a name="StringFunctions"></a> Dize işlevleri  
  
-   Birleştirme işleçlerini ve Visual Basic sabitlerini kullanarak birden çok alanı birleştirin. Aşağıdaki ifade, aynı metin kutusunda bulunan fakat farklı satırlarda olan iki alanı döndürür:  
  
    ```  
    =Fields!FirstName.Value & vbCrLf & Fields!LastName.Value   
    ```  
  
-   **Format** işlevini kullanarak bir dizedeki tarih ve sayıları biçimlendirin. Aşağıdaki ifade, *StartDate* ve *EndDate* parametrelerinin değerlerini uzun tarih biçiminde görüntüler:  
  
    ```  
    =Format(Parameters!StartDate.Value, "D") & " through " &  Format(Parameters!EndDate.Value, "D")    
    ```  
  
     Metin kutusu sadece bir tarih veya sayı içeriyorsa, biçimlendirmeyi uygulamak için metin kutusunun içinde **Format** işlevinin yerine metin kutusunun Format özelliğini kullanmanız gerekir.  
  
-   **Right**, **Len** ve **InStr** işlevleri bir alt dizeyi döndürmek için kullanışlıdır. Örneğin, *ETKİALANI*\\*kullanıcıadı*’nı yalnızca kullanıcı adından oluşacak şekilde kırpabilirsiniz. Aşağıdaki ifade *User* adlı bir parametreden, dizenin ters eğik çizgi karakterinin (\\) sağında yer alan kısmını döndürür:  
  
    ```  
    =Right(Parameters!User.Value, Len(Parameters!User.Value) - InStr(Parameters!User.Value, "\"))  
    ```  
  
     Aşağıdaki ifade, Visual Basic işlevlerinin yerine .NET Framework’ün `xref:System.String` sınıfını kullanarak önceki değerin aynısını sonuç olarak verir:  
  
    ```  
    =Parameters!User.Value.Substring(Parameters!User.Value.IndexOf("\")+1, Parameters!User.Value.Length-Parameters!User.Value.IndexOf("\")-1)  
    ```  
  
-   Çok değerli bir parametrenin seçilen değerlerini görüntüleyin. Aşağıdaki örnek, *MySelection* parametresinin seçilen değerlerini bir rapor öğesindeki metin kutusunun değeri için ifade olarak ayarlanabilen tek bir dizede birleştirmek amacıyla **Join** işlevini kullanır:  
  
    ```  
    = Join(Parameters!MySelection.Value)  
    ```  
  
     Aşağıdaki örnek, yukarıdaki örneğin yaptıklarını yapar ve seçilen değerlerin listesinden önce bir metin dizesini gösterir.  
  
    ```  
    ="Report for " & JOIN(Parameters!MySelection.Value, " & ")  
  
    ```  
  
-   .NET Framework `xref:System.Text.RegularExpressions` içindeki **Regex** işlevleri, mevcut dizelerin biçimini değiştirmek için kullanışlıdır (örneğin, bir telefon numarasını biçimlendirme). Aşağıdaki ifade, bir alanda yer alan on haneli telefon numarasını “*nnn*-*nnn*-*nnnn*” biçiminden “(*nnn*) *nnn*-*nnnn*” biçimine çevirmek için **Replace** işlevini kullanır:  
  
    ```  
    =System.Text.RegularExpressions.Regex.Replace(Fields!Phone.Value, "(\d{3})[ -.]*(\d{3})[ -.]*(\d{4})", "($1) $2-$3")  
    ```  
  
    > [!NOTE]  
    >  Fields!Phone.Value değerinin ek boşluk içermediğini ve türünün `xref:System.String` olduğunu doğrulayın.  
  
### <a name="lookup"></a>Arama  
  
-   Anahtar alanı belirterek, veri kümesinden bire bir ilişkiye yönelik değeri (örneğin, bir anahtar-değer çifti) almak için **Lookup** işlevini kullanabilirsiniz. Aşağıdaki ifade, eşleştirilecek ürün tanımlayıcısı sağlandıysa, bir veri kümesindeki ürün adını gösterir (“Product”):  
  
    ```  
    =Lookup(Fields!PID.Value, Fields!ProductID.Value, Fields.ProductName.Value, "Product")  
    ```  
  
### <a name="lookupset"></a>LookupSet  
  
-   Anahtar alanı belirterek, veri kümesinden bire çok ilişkiye yönelik değer kümesini almak için **LookupSet** işlevini kullanabilirsiniz. Örneğin, bir kişinin birden çok telefon numarası olabilir. Aşağıdaki örnekte, PhoneList veri kümesinin her satırda kişi tanımlayıcısı ve telefon numarası içerdiğini varsayın. **LookupSet** bir değer dizisi döndürür. Aşağıdaki ifade, döndürülen değerleri tek bir dizede birleştirir ve ContactID tarafından belirtilen kişi için telefon numaralarının listesini gösterir:  
  
    ```  
    =Join(LookupSet(Fields!ContactID.Value, Fields!PersonID.Value, Fields!PhoneNumber.Value, "PhoneList"),",")  
    ```  
  
###  <a name="ConversionFunctions"></a> Dönüştürme işlevleri  
 Bir alanı bir veri türünden farklı bir veri türüne dönüştürmek için Visual Basic işlevlerini kullanabilirsiniz. Bir alanın varsayılan veri türünü, hesaplamalar veya metin birleştirmesi için gerekli veri türüne dönüştürmek için dönüştürme işlevleri kullanılabilir.  
  
-   Aşağıdaki ifade, bir filtre ifadesi için Değer alanındaki bir Transact-SQL para veri türüyle karşılaştırılması amacıyla 500 sabitini Ondalık türüne dönüştürür.  
  
    ```  
    =CDec(500)  
    ```  
  
-   Aşağıdaki ifade, çok değerli *MySelection* parametresi için seçilen değerlerin sayısını gösterir.  
  
    ```  
    =CStr(Parameters!MySelection.Count)  
    ```  
  
###  <a name="DecisionFunctions"></a> Karar işlevleri  
  
-   **Iif** işlevi, ifadenin doğru olup olmadığına bağlı olarak iki değerden birini döndürür. Aşağıdaki ifade, `LineTotal` değeri 100’ü aşarsa **True** Boole değerini döndürmek için **Iif** işlevini kullanır. Aksi halde **False** döndürülür:  
  
    ```  
    =IIF(Fields!LineTotal.Value > 100, True, False)  
    ```  
  
-   `PctComplete` değerine bağlı olarak üç değerden birini döndürmek için çoklu **IIF** işlevlerini (“iç içe geçmiş IIF’ler” olarak da bilinir) kullanın. Aşağıdaki ifade, metin kutusundaki değere bağlı olarak arka plan rengini değiştirmek için bir metin kutusunun dolgu rengi yerine yerleştirilebilir.  
  
    ```  
    =IIF(Fields!PctComplete.Value >= 10, "Green", IIF(Fields!PctComplete.Value >= 1, "Blue", "Red"))  
    ```  
  
     10’dan büyük veya 10’a eşit değerler yeşil, 1 ve 9 arasındaki değerler mavi, 1’den küçük değerler de kırmızı bir arka planla görüntülenir.  
  
-   Aynı işlevi elde etmeye yarayan farklı bir yöntemde **Switch** işlevini kullanılır. Test edeceğiniz üç veya daha fazla koşul varsa **Switch** işlevi kullanışlıdır. **Switch** işlevi, bir serideki true olarak değerlendirilen ilk ifade ile ilişkili değeri döndürür:  
  
    ```  
    =Switch(Fields!PctComplete.Value >= 10, "Green", Fields!PctComplete.Value >= 1, "Blue", Fields!PctComplete.Value = 1, "Yellow", Fields!PctComplete.Value <= 0, "Red")  
    ```  
  
     10’dan büyük veya 10’a eşit değerler yeşil, 1 ve 9 arasındaki değerler mavi, 1’e eşit değerler sarı ve 0 veya daha küçük değerler kırmızı bir arka plan ile görüntülenir.  
  
-   `ImportantDate` alanının değerini test edin ve bir haftadan daha eski ise “Kırmızı”, aksi takdirde “Mavi” döndürün. Bu ifade, bir rapor öğesindeki metin kutusunun Color özelliğini denetlemek için kullanılabilir:  
  
    ```  
    =IIF(DateDiff("d",Fields!ImportantDate.Value, Now())>7,"Red","Blue")  
    ```  
  
-   `PhoneNumber` alanının değerini test edin ve **null** ise “Değer Yok” (Visual Basic’te **Nothing**) döndürün. Aksi takdirde, telefon numarası değerini döndürün. Bu ifade, bir rapor öğesindeki metin kutusunun değerini denetlemek için kullanılabilir.  
  
    ```  
    =IIF(Fields!PhoneNumber.Value Is Nothing,"No Value",Fields!PhoneNumber.Value)  
    ```  
  
-   `Department` alanının değerini test edin ve bir alt rapor adını veya **null** değerini döndürün (Visual Basic’te **Nothing**). Bu ifade, koşullu detaylandırma alt raporları için kullanılabilir.  
  
    ```  
    =IIF(Fields!Department.Value = "Development", "EmployeeReport", Nothing)  
    ```  
  
-   Bir alanın değerinin null olup olmadığını test edin. Bu ifade, bir resim raporu öğesinin **Hidden** özelliğini denetlemek için kullanılabilir. Aşağıdaki örnekte, [LargePhoto] alanı tarafından belirtilen resim, yalnızca alanın değeri ‘null’ olmadığında görüntülenir.  
  
    ```  
    =IIF(IsNothing(Fields!LargePhoto.Value),True,False)  
    ```  
  
-   **MonthName** işlevi, belirtilen ayın adını içeren bir dize değerini döndürür. Aşağıdaki örnek, alan 0 değerini içerdiğinde Ay alanında YOK değerini görüntüler.  
  
    ```  
    IIF(Fields!Month.Value=0,"NA",MonthName(IIF(Fields!Month.Value=0,1,Fields!Month.Value)))  
  
    ```  
  
##  <a name="ReportFunctions"></a> Rapor işlevleri  
 Bir ifadede, rapordaki verileri denetleyen ek rapor işlevlerine yönelik başvuru ekleyebilirsiniz. Bu bölüm, bu işlevlerin ikisine yönelik örnekleri sunar. 
  
###  <a name="Sum"></a> Sum  
  
-   **Sum** işlevi, bir grup veya veri bölgesindeki değerlerin toplamını alabilir. Bu işlev bir grubun üst bilgisinde veya alt bilgisinde kullanışlı olabilir. Aşağıdaki ifade, Order grubundaki veya veri bölgesindeki verilerin toplamını gösterir:  
  
    ```  
    =Sum(Fields!LineTotal.Value, "Order")  
    ```  
  
-   **Sum** işlevini koşullu toplu hesaplamalar için de kullanabilirsiniz. Örneğin, bir veri kümesinde olası değerleri Not Started (Başlatılmadı), Started (Başlatıldı) ve Finished (Tamamlandı) olan State (Durum) adlı bir alan bulunuyorsa, aşağıdaki ifade bir grup üst bilgisine yerleştirildiğinde, sadece Finished değeri için toplamı hesaplar:  
  
    ```  
    =Sum(IIF(Fields!State.Value = "Finished", 1, 0))  
    ```  
  
###  <a name="RowNumber"></a> RowNumber  
  
-   **RowNumber** işlevi, veri bölgesindeki bir metin kutusunda kullanıldığında ifadenin göründüğü her metin kutusu örneği için satır numarasını görüntüler. Bu işlev, bir tablodaki satırları numaralandırmak için kullanışlı olabilir. Bu, satır numaralarını temel alarak sayfa sonu sağlama gibi daha karmaşık görevler için de kullanışlı olabilir. Daha fazla bilgi için bu konu başlığındaki [Sayfa Sonları](#PageBreaks) bölümüne göz atın.  
  
     **RowNumber** için belirttiğiniz kapsam, yeniden numaralandırmanın ne zaman başlayacağını denetler. **Nothing** anahtar sözcüğü, işlevin sayıma en dışta yer alan veri bölgesinin ilk satırından başlayacağını gösterir. İç içe geçmiş veri bölgelerinde sayıma başlamak için veri bölgesinin adını kullanın. Bir grupta sayıma başlamak için grubun adını kullanın.  
  
    ```  
    =RowNumber(Nothing)  
    ```  
  
##  <a name="AppearanceofReportData"></a> Rapor verilerinin görünümü  
 Verilerin raporda nasıl göründüğünü denetlemek için ifadeleri kullanabilirsiniz. Örneğin, iki alanın değerlerini tek bir metin kutusunda görüntüleyebilirsiniz. Bunun yanı sıra, rapor hakkında verileri görüntüleyip sayfa sonlarının rapora eklenme şeklini de değiştirebilirsiniz.  
  
###  <a name="PageHeadersandFooters"></a> Sayfa üst bilgileri ve alt bilgileri  
 Rapor tasarlarken, raporun adını ve sayfa numarasını raporun alt bilgisinde görüntülemek isteyebilirsiniz. Bunu yapmak için aşağıdaki ifadeleri kullanabilirsiniz:  
  
-   Aşağıdaki ifade, raporun adını ve çalıştırılma zamanını sağlar. Bu, raporun alt bilgisindeki veya raporun gövdesindeki bir metin kutusuna yerleştirilebilir. Zaman, .NET Framework kısa tarih biçimlendirme dizesi ile biçimlendirilir:  
  
    ```  
    =Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")  
    ```  
  
-   Bir raporun alt bilgisindeki metin kutusuna yerleştirilen aşağıdaki ifade, sayfa numarasını ve rapordaki toplam sayfa sayısını sağlar:  
  
    ```  
    =Globals.PageNumber & " of " & Globals.TotalPages  
    ```  
  
 Aşağıdaki örnekler, bir dizin listelemesinde bulabileceklerinize benzer olarak sayfa üst bilgisindeki ilk ve son değerlerin nasıl görüntülendiğini açıklamaktadır. Örnek, `LastName` adlı metin kutusunu içeren bir veri bölgesinin olduğunu varsayar.  
  
-   Sayfa üst bilgisinin sol tarafında bulunan bir metin kutusuna yerleştirilen aşağıdaki ifade, sayfada bulunan `LastName` metin kutusunun ilk değerini sağlar:  
  
    ```  
    =First(ReportItems("LastName").Value)  
    ```  
  
-   Sayfa üst bilgisinin sağ tarafında bulunan bir metin kutusuna yerleştirilen aşağıdaki ifade, sayfada bulunan `LastName` metin kutusunun son değerini sağlar:  
  
    ```  
    =Last(ReportItems("LastName").Value)  
    ```  
  
 Aşağıdaki örnek, sayfa toplamının nasıl görüntülendiğini açıklamaktadır. Örnek, veri bölgesinin `Cost` adlı bir metin kutusu içerdiğini varsayar.  
  
-   Sayfa üst bilgisine veya alt bilgisine yerleştirilen aşağıdaki ifade, `Cost` metin kutusunda sayfanın değerlerinin toplamını sağlar:  
  
    ```  
    =Sum(ReportItems("Cost").Value)  
    ```  
  
> [!NOTE]  
>  Sayfa üst bilgisindeki veya alt bilgisindeki her ifade başına yalnızca bir rapor öğesine başvurabilirsiniz. Ayrıca, sayfa üst bilgi veya alt bilgi ifadelerinde metin kutusu adına başvurabilirsiniz ancak metin kutusundaki gerçek veri ifadelerine başvuramazsınız.  
  
###  <a name="PageBreaks"></a> Sayfa sonları  
 Bazı raporlarda, grup veya rapor öğelerinin yerine veya bunlara ek olarak, belirtilen sayıda satırın sonuna bir sayfa sonu eklemek isteyebilirsiniz. Bunu yapmak için, istediğiniz grupları veya ayrıntı kayıtlarını içeren grubu oluşturun, gruba bir sayfa sonu ekleyin ve belirtilen satır sayısı kadar grup ifadesi ekleyin.  
  
-   Aşağıdaki ifade bir grup ifadesine eklendiğinde 25 satırlık her kümeye bir sayı atar. Grup için bir sayfa sonu tanımlandığında, bu ifade her 25 satırda bir sayfa sonu oluşturulmasını sağlar.  
  
    ```  
    =Ceiling(RowNumber(Nothing)/25)  
    ```  
  
     Kullanıcının sayfa başına satır sayısı için bir değer ayarlamasını sağlamak için, `RowsPerPage` adlı bir parametre oluşturun ve aşağıdaki ifadede gösterildiği gibi grup ifadesini, parametreyi temel alacak şekilde ayarlayın:  
  
    ```  
    =Ceiling(RowNumber(Nothing)/Parameters!RowsPerPage.Value)  
    ```  
  
##  <a name="Properties"></a> Özellikler  
 İfadeler, yalnızca metin kutularında verileri görüntülemek için kullanılmaz. Özelliklerin rapor öğelerine nasıl uygulandığını değiştirmek için de kullanılabilirler. Bir rapor öğesi için stil bilgisini veya bunun görünürlüğünü değiştirebilirsiniz.  
  
###  <a name="Formatting"></a> Biçimlendirme  
  
-   Aşağıdaki ifade bir metin kutusunun Color özelliğinde kullanıldığında, `Profit` alanının değerine bağlı olarak metnin rengini değiştirir:  
  
    ```  
    =Iif(Fields!Profit.Value < 0, "Red", "Black")  
    ```  
  
     `Me` Visual Basic nesne değişkenini de kullanabilirsiniz. Bu değişken, bir metin kutusunun değerine başvurmanın farklı yollarından biridir.  
  
     `=Iif(Me.Value < 0, "Red", "Black")`  
  
-   Aşağıdaki ifade, bir veri bölgesindeki rapor öğesinin BackgroundColor özelliğinde kullanıldığında her satırın arka plan rengini soluk yeşil ve beyaz renkleri arasında değiştirir:  
  
    ```  
    =Iif(RowNumber(Nothing) Mod 2, "PaleGreen", "White")  
    ```  
  
     Belirtilen bir kapsama yönelik ifade kullanıyorsanız, toplama işlevi için veri kümesini göstermeniz gerekebilir:  
  
    ```  
    =Iif(RowNumber("Employees") Mod 2, "PaleGreen", "White")  
    ```  
  
> [!NOTE]  
>  Kullanılabilen renkler, .NET Framework KnownColor sabit listesinden gelmektedir.  
  
### <a name="chart-colors"></a>Grafik renkleri  
 Bir Şekil grafiğinin renklerini belirtmek için, renklerin veri noktası değerlerine eşlenme sırasını denetlemek amacıyla özel kod kullanabilirsiniz. Bu, aynı kategori grubuna sahip olan birden çok grafik için tutarlı renkleri kullanmanıza yardımcı olur. 
  
###  <a name="Visibility"></a> Görünürlük  
 Rapor öğesinin görünürlük özelliklerini kullanarak bir rapordaki öğeleri gösterebilir veya gizleyebilirsiniz. Tablo gibi bir veri bölgesinde, ifadedeki değeri temel alarak başlangıçta ayrıntı satırlarını gizleyebilirsiniz.  
  
-   Aşağıdaki ifade bir gruptaki ayrıntı satırlarının başlangıç görünürlüğü için kullanıldığında `PctQuota` alanında yüzde 90’ı geçen tüm satışlar için ayrıntı satırlarını gösterir:  
  
    ```  
    =Iif(Fields!PctQuota.Value>.9, False, True)  
    ```  
  
-   Aşağıdaki ifade bir tablonun Hidden özelliğinde ayarlandığında, tabloyu sadece 12’den fazla satır varsa gösterir:  
  
    ```  
    =IIF(CountRows()>12,false,true)  
    ```  
  
-   Aşağıdaki ifade, bir sütunun **Hidden** özelliğinde ayarlandığında, veriler veri kaynağından alındıktan sonra, sütunu yalnızca, raporun veri kümesinde alanın mevcut olması durumunda gösterir:  
  
    ```  
    =IIF(Fields!Column_1.IsMissing, true, false)  
    ```  
  
###  <a name="Hyperlinks"></a> URL'ler  
 Rapor verilerini kullanarak URL’leri özelleştirebilir ve URL’lerin bir metin kutusu için bir eylem olarak eklenip eklenmediğini koşullu olarak denetleyebilirsiniz.  
  
-   Aşağıdaki ifade, bir metin kutusunda eylem olarak kullanıldığında, bir URL parametresi olarak `EmployeeID` veri kümesi alanını belirten özelleştirilmiş bir URL oluşturur.  
  
    ```  
    ="https://adventure-works/MyInfo?ID=" & Fields!EmployeeID.Value  
    ```  
  
-   Aşağıdaki ifade, bir metin kutusuna URL eklenip eklenmeyeceğini koşullu olarak denetler. Bu ifade, `IncludeURLs` adlı parametreye bağımlıdır ve kullanıcıya, etkin URL’leri rapora dahil edip etmeyeceğine karar verme olanağı tanır. Bu ifade, bir metin kutusunda eylem olarak ayarlanır. Parametreyi False olarak ayarlayıp raporu görüntüleyerek, köprüler olmadan Microsoft Excel’e aktarabilirsiniz.  
  
    ```  
    =IIF(Parameters!IncludeURLs.Value,"https://adventure-works.com/productcatalog",Nothing)  
    ```  
  
##  <a name="ReportData"></a> Rapor verileri  
 Raporda kullanılan verileri denetlemek için ifadeler kullanılabilir. Parametrelere ve diğer rapor bilgilerine başvurabilirsiniz. Rapora yönelik verileri almak için kullanılan sorguyu bile değiştirebilirsiniz.  
  
###  <a name="Parameters"></a> Parametreler  
 Parametre için varsayılan değeri değiştirmek amacıyla ifadeleri bir parametrede kullanabilirsiniz. Örneğin, raporu çalıştırmak için kullanılan kullanıcı kimliğini temel alarak verileri belirli bir kullanıcının erişebileceği şekilde filtrelemek için bir parametre kullanabilirsiniz.  
  
-   Aşağıdaki ifade, bir parametre için varsayılan değer olarak kullanıldığında raporu çalıştıran kişinin kullanıcı kimliğini toplar:  
  
    ```  
    =User!UserID  
    ```  
  
-   Sorgu parametresinde, filtre ifadesinde, metin kutusunda veya raporun diğer alanlarında bir parametreye başvurmak için **Parameters** genel koleksiyonunu kullanın. Bu örnekte, parametre adının *Department* olduğu varsayılır:  
  
    ```  
    =Parameters!Department.Value  
    ```  
  
-   Parametreler raporda oluşturulabilir ancak bunlar gizli olarak ayarlanabilir. Rapor, rapor sunucusunda çalıştığında parametre araç çubuğunda görünmez ve rapor okuyucusu varsayılan değeri değiştiremez. Varsayılan değere ayarlı gizli bir parametreyi özel sabit olarak kullanabilirsiniz. Bu değeri, alan ifadeleri de dahil olmak üzere tüm ifadelerde kullanabilirsiniz. Aşağıdaki ifade, *ParameterField* adlı parametre için varsayılan parametre değeri tarafından belirtilen alanı tanımlamaktadır:  
  
    ```  
    =Fields(Parameters!ParameterField.Value).Value  
    ```  
  
##  <a name="CustomCode"></a> Özel kod  
 Bir raporda katıştırılmış özel kod kullanabilirsiniz. 
  
### <a name="using-group-variables-for-custom-aggregation"></a>Özel toplama için grup değişkenlerini kullanma  
 Belirli bir grup kapsamında yerel olan bir grup değişkeninin değerini başlatıp ifadelere bu değişken için bir başvuru ekleyebilirsiniz. Özel toplama uygulama, özel kod ile grup değişkeni kullanmanıza olanak tanıyan yöntemlerden biridir. 
  
## <a name="suppressing-null-or-zero-values-at-run-time"></a>Çalışma zamanında null veya sıfır değerlerini gizleme  
 Bir ifadede yer alan bazı değerler, raporun işlenme zamanında null veya tanımsız olarak değerlendirilebilir. Bu, değerlendirilen ifade yerine **#Hata** öğesinin metin kutusunda görüntülenmesiyle sonuçlanan çalışma zamanı hataları oluşturabilir. Bir If-Then-Else deyiminin aksine, **true** mu **false** mu olduğunu test eden yordama gönderilmeden önce **IIF** deyiminin her parçası değerlendirildiği için (işlev çağrıları da dahil), **IIF** işlevi bu davranışa özellikle hassastır. `Fields!Sales.Value` değeri NOTHING ise, `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` deyimi işlenmiş raporda **#Hata** oluşturur.  
  
 Bu durumu önlemek için aşağıdaki stratejilerden birini kullanın:  
  
-   B alanının değeri 0 veya tanımlanmamış ise payı 0, paydayı da 1 olarak ayarlayın. Aksi takdirde, payı A alanının, paydayı da B alanının değerine ayarlayın.  
  
    ```  
    =IIF(Field!B.Value=0, 0, Field!A.Value / IIF(Field!B.Value =0, 1, Field!B.Value))  
    ```  
  
-   İfadenin değerini döndürmek için bir özel kod işlevi kullanın. Aşağıdaki örnek, bir mevcut değer ve önceki değer arasındaki yüzdelik farkını döndürür. Bu, iki ardışık değer arasındaki farkı hesaplamak için kullanılabilir, (önceki değer olmadığında) ilk karşılaştırmanın eşik durumunu ve önceki değer veya mevcut değerden herhangi birinin **null** (Visual Basic’te **Nothing**) olduğu durumları işler.  
  
    ```  
    Public Function GetDeltaPercentage(ByVal PreviousValue, ByVal CurrentValue) As Object  
        If IsNothing(PreviousValue) OR IsNothing(CurrentValue) Then  
            Return Nothing  
        Else if PreviousValue = 0 OR CurrentValue = 0 Then  
            Return Nothing  
        Else   
            Return (CurrentValue - PreviousValue) / CurrentValue  
        End If  
    End Function  
    ```  
  
     Aşağıdaki ifade, “ColumnGroupByYear” kapsayıcısı için (grup veya veri bölgesi) bu özel koda bir metin kutusundan nasıl çağrı yapıldığını gösterir.  
  
    ```  
    =Code.GetDeltaPercentage(Previous(Sum(Fields!Sales.Value),"ColumnGroupByYear"), Sum(Fields!Sales.Value))  
    ```  
  
     Bu, çalışma zamanı özel durumlarından kaçınmaya yardımcı olur. Değerlerin 0’dan büyük olup olmadığını temel alarak koşullu bir şekilde metin görüntülemek için artık metin kutusunun **Color** özelliğindeki `=IIF(Me.Value < 0, "red", "black")` ifadesi gibi bir ifade kullanabilirsiniz.  
  
## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
  
