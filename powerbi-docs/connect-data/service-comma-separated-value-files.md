---
title: Virgülle Ayrılmış Değer (.CSV) dosyalarından veri alma
description: CSV dosyalarından Power BI'a veri almayı öğrenin
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 05/08/2019
LocalizationGroup: Data from files
ms.openlocfilehash: 01bef505d48f28df869bf2be705dcda963b3d0f9
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96403341"
---
# <a name="get-data-from-comma-separated-value-csv-files"></a>Virgülle Ayrılmış Değer (.CSV) dosyalarından veri alma
![CSV simgesi](media/service-comma-separated-value-files/csv_icon.png)

Genellikle .CSV olarak bilinen virgülle ayrılmış değer dosyaları, her değerin virgülle ayrıldığı veri satırları içeren basit metin dosyalarıdır. Bu tür dosyaların çok büyük miktarda veriyi görece küçük boyutlu bir dosya içinde barındırması, bu dosyaları Power BI için ideal bir veri kaynağı haline getirir. Bir .CSV dosyası örneğini [buradan](https://go.microsoft.com/fwlink/?LinkID=619356) indirebilirsiniz.

Bir .CSV dosyanız varsa bu dosyayı bir veri kümesi olarak Power BI sitenize almanın şimdi tam zamanı! Burada verilerinizi araştırmaya başlayabilir, bazı panolar oluşturabilir ve öngörülerinizi başkalarıyla paylaşabilirsiniz.

>[!TIP]
>Birçok kuruluş her gün güncelleştirilen verilerle bir .CSV dosyası oluşturur. Power BI'daki veri kümenizin güncelleştirilen dosyanızla eşitlenmiş durumda kaldığından emin olmak için dosyanın aynı adla OneDrive'a kaydedildiğinden emin olun.

## <a name="where-your-file-is-saved-makes-a-difference"></a>Dosyanızı nereye kaydettiğiniz önemlidir
**Yerel**: .CSV dosyanızı bilgisayarınızdaki bir yerel sürücüye veya kuruluşunuzdaki diğer bir konuma kaydederseniz Power BI'ı kullanarak dosyanızı Power BI'a *aktarabilirsiniz*. Dosyanız gerçekte yerel sürücünüzde kalır. Böylece, dosyanın tamamı Power BI'a aktarılmamış olur. Burada asıl olan, Power BI'da yeni bir veri kümesinin oluşturulması ve .CSV dosyasındaki verilerin veri kümesine yüklenmesidir.

**OneDrive - İş**: OneDrive İş kullanıyorsanız .CVS dosyanız ile Power BI'daki veri kümenizi, raporlarınızı ve panolarınızı eşitlenmiş durumda tutmanın en etkili yolu, Power BI'da oturum açarken kullandığınız hesap ile OneDrive İş'te oturum açmaktır. Hem Power BI hem de OneDrive bulutta olduğundan Power BI, OneDrive'daki dosyanıza hemen hemen her saatte bir *bağlanır*. Herhangi bir değişiklik bulunması durumunda veri kümeniz, raporlarınız ve panolarınız Power BI'da da otomatik olarak güncelleştirilir.

**OneDrive - Bireysel**: Dosyalarınızı kendi OneDrive hesabınıza kaydederseniz OneDrive İş ile ilgili olarak elde ettiğiniz avantajların pek çoğundan yararlanırsınız. En büyük fark şudur: Dosyanıza ilk kez bağlanırken (Veri Al > Dosyalar > OneDrive – Bireysel yolunu izleyerek) OneDrive'da Microsoft hesabınızla oturum açmanız gerekir. Bu genellikle, Power BI'da oturum açarken kullandığınız hesaptan farklıdır. OneDrive hesabınızda Microsoft hesabınız ile oturum açtığınızda, Oturumu açık bırak'ı seçtiğinizden emin olun. Bu şekilde Power BI, yaklaşık olarak her saatte bir dosyanıza bağlanabilir ve Power BI'daki veri kümenizin eşitlenmiş durumda kalmasını sağlayabilir.

**SharePoint - Ekip Siteleri**: Power BI Desktop dosyalarınızı SharePoint - Ekip Siteleri'ne kaydetmek, OneDrive İş'e kaydetmeye çok benzer. En büyük fark, Power BI'dan dosyaya bağlanma şeklinizdir. Bir URL belirtebilir veya kök klasöre bağlanabilirsiniz.

## <a name="import-or-connect-to-a-csv-file"></a>.CSV dosyalarını içeri aktarma veya .CSV dosyalarına bağlanma
>[!IMPORTANT]
>Power BI'a aktarabileceğiniz en büyük dosya boyutu 1 gigabayttır.

1. Power BI'daki gezinti bölmesinden **Veri Al**'ı seçin.
   
   ![Gezgin bölmesindeki düğmeyi gösteren Power BI Desktop’taki Veri Al’ın ekran görüntüsü.](media/service-comma-separated-value-files/csv_get_data_button.png)
2. **Dosyalar**'da, **Al**'a tıklayın.
   
   ![Al düğmesini gösteren, Dosyalar iletişim kutusunun ekran görüntüsü.](media/service-comma-separated-value-files/csv_files_get.png)
3. Dosyanızı bulun.
   
   ![Yerel dosya, OneDrive İş, OneDrive Bireysel ve SharePoint seçimlerini gösteren, dosyanızı bulmaya yönelik dört kutucuğun ekran görüntüsü.](media/service-comma-separated-value-files/csv_find_your_file.png)

## <a name="next-steps"></a>Sonraki adımlar
**Verilerinizi araştırma**: Verileri dosyanızdan Power BI'a aktardığınızda artık araştırmaya başlayabilirsiniz. Yeni veri kümesine sağ tıklayıp **Araştır** seçeneğini belirlemeniz yeterlidir.

**Yenilemeyi zamanlama**: Dosyanız bir yerel sürücüye kaydedilmişse zamanlanmış yenileme ayarlayarak Power BI'daki veri kümenizin ve raporlarınızın güncel tutulmasını sağlayabilirsiniz. Daha fazla bilgi için bkz. [Power BI'da veri yenileme](refresh-data.md). Dosyanız OneDrive'a kaydedildiyse Power BI yaklaşık saatte bir otomatik olarak dosyanızla eşitlenir.

