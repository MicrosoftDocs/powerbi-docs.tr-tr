---
title: Power BI için dosyalardan veri alma
description: Excel, Power BI Desktop ve CSV dosyalarından Power BI'a veri almayı öğrenin
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 05/08/2019
LocalizationGroup: Data from files
ms.openlocfilehash: 2ed532986dd31e97e535f27d70c9f5cfd8c66fd5
ms.sourcegitcommit: 24887643bd3e1b3749ce325dc0ae407432d7fee4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100489889"
---
# <a name="get-data-from-files-for-power-bi"></a>Power BI için dosyalardan veri alma
![Excel, Power BI Desktop, ve CSV simgesi](media/service-get-data-from-files/file_icons.png)

Power BI'da bağlanabileceğiniz ve verilerini içeri aktarabileceğiniz üç dosya türü vardır.

* Microsoft Excel (.xlsx veya .xlsm)
* Power BI Desktop (.pbix)
* Virgülle Ayrılmış Değer (.csv)

## <a name="what-does-get-data-from-a-file-really-mean"></a>Bir dosyadan veri alma tam olarak nedir?
Power BI'da araştırdığınız veriler bir veri kümesinden gelir. Ancak, bir veri kümesine sahip olmak için öncelikle bazı veriler almanız gerekir. Bu makalede dosyalardan veri alma işlemine odaklanılacaktır.

Veri kümelerinin önemini ve veri kümelerinden nasıl veri alınacağını daha iyi anlamak için bir otomobili inceleyelim. Otomobilinizin koltuğuna oturun ve gösterge panosuna bakın. Bu tıpkı bilgisayarınızın başına oturup Power BI'da bir panoya bakmaya benzer. Otomobildeki gösterge panosu; otomobilin ne yaptığını, motorun hangi devirde çalıştığını, sıcaklığı, kaçıncı viteste olduğunuzu, hızınızı ve buna benzer bilgileri gösterir.

Power BI'daki veri kümesi de otomobilinizin motoru gibidir. Veri kümesi; Power BI panonuzda görüntülenen bilgileri, ölçümleri ve verileri sağlar. Elbette motorunuzun yakıta ihtiyacı vardır. Power BI'daki yakıt ise verilerdir. Otomobilinizde, motora gaz veren bir yakıt deposu bulunur. Benzer şekilde Power BI'da da veri kümenizi besleyebileceğiniz verileri içeren bir yakıt deposuna ihtiyaç duyarsınız. Bu durumda yakıt depomuz bir Power BI Desktop dosyası, Excel çalışma kitabı dosyası veya .CSV dosyasıdır.

Hatta bunu bir adım daha ileri taşıyabiliriz. Otomobilin yakıt deposu yakıtla doldurulmalıdır. Power BI Desktop, Excel veya .CSV dosyasının yakıtı da başka bir veri kaynağından alınan verilerdir. Başka bir veri kaynağından aldığımız verileri bir Excel, Power BI Desktop veya .CSV dosyasına yerleştiririz. Bu bir Excel çalışma kitabı veya .CSV dosyasıysa veri satırlarını el ile girebiliriz. Alternatif olarak, verileri sorgulamak ve dosyanıza yüklemek için bir dış veri kaynağına bağlanabiliriz. Veri içeren bir dosyamız varsa bu dosyayı Power BI'a bir veri kümesi olarak alabiliriz.

> [!NOTE]
> Excel çalışma kitaplarında bulunan verilerin Power BI'a aktarılabilmesi için bir tablo veya veri modeli biçiminde olması gerekir.
> 
> 

## <a name="where-your-file-is-saved-makes-a-difference"></a>Dosyanızı nereye kaydettiğiniz önemlidir
**Yerel**: Yerel dosyanızı bilgisayarınızdaki bir yerel sürücüye veya kuruluşunuzdaki bir konuma kaydederseniz Power BI'ı kullanarak dosyanızı Power BI'a *aktarabilirsiniz*. Dosyanız gerçekte yerel sürücünüzde kalır. Böylece, dosyanın tamamı Power BI'a aktarılmamış olur. Burada gerçekleştirilen asıl işlem, Power BI sitenizde yeni bir veri kümesinin oluşturulması ve verilerin (bazı durumlarda ise veri modelinin) bu veri kümesine yüklenmesidir. Dosyanız rapor içeriyorsa bu raporlar, Power BI sitenizdeki Raporlar bölümü altında görünür.

**OneDrive-iş** : OneDrive iş 'e sahipseniz ve Power BI oturum açmak için kullandığınız hesapla oturum açarsanız, bu, işinizi Excel, Power BI Desktop veya a 'da tutmanın en etkili yoludur. CSV dosyası ve veri kümeniz, raporlarınız ve panolarınız Power BI eşitleme sırasında. Hem Power BI hem de OneDrive bulutta olduğundan, Power BI OneDrive 'daki dosyanıza her saatte bağlanır. Herhangi bir değişiklik bulunması durumunda veri kümeniz, raporlarınız ve panolarınız Power BI'da da otomatik olarak güncelleştirilir.

**OneDrive - Bireysel**: Dosyalarınızı kendi OneDrive hesabınıza kaydederseniz OneDrive İş ile ilgili olarak elde ettiğiniz avantajların pek çoğundan yararlanırsınız. En büyük fark şudur: Dosyanıza ilk kez bağlanırken (Veri Al > Dosyalar > OneDrive – Bireysel adımlarını kullanarak) OneDrive oturumunuzu Microsoft hesabınızla açmanız gerekir. Bu hesap genellikle, Power BI'da oturum açarken kullandığınızdan farklı bir hesaptır. OneDrive'da Microsoft hesabınız ile oturum açarken Oturumumu açık bırak seçeneğini belirlediğinizden emin olun. Bu şekilde Power BI, yaklaşık olarak her saatte bir dosyanıza bağlanabilir ve Power BI'daki veri kümenizin eşitlenmiş durumda kalmasını sağlayabilir.

**SharePoint - Ekip Siteleri**: Power BI Desktop dosyalarınızı SharePoint - Ekip Siteleri'ne kaydetmek, OneDrive İş'e kaydetmeye çok benzer. En büyük fark, Power BI'dan dosyaya bağlanma şeklinizdir. Bir URL belirtebilir veya kök klasöre bağlanabilirsiniz.

## <a name="ready-to-get-started"></a>Başlamaya hazır mısınız?
Dosyanızı Power BI'a aktarmaya ilişkin daha fazla bilgi edinmek için aşağıdaki makalelere başvurun.

* [Excel çalışma kitabı dosyalarından veri alma](service-excel-workbook-files.md)
* [Power BI Desktop dosyalarından veri alma](service-desktop-files.md)
* [Virgülle Ayrılmış Değer dosyalarından veri alma](service-comma-separated-value-files.md)

