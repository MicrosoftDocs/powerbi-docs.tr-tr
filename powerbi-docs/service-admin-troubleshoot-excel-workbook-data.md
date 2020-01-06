---
title: 'Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık'
description: 'Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık'
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 04/30/2019
ms.author: kfollis
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 1976567029454445f625ff400fb1d87ae6c01219
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "74698429"
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık

>[!NOTE]  
>Bu makale Excel 2007 ve sonraki sürümleri için geçerlidir.

Power BI'a Excel çalışma kitabı aktarırken şu hatayla karşılaşabilirsiniz:

*Hata: Tablo olarak biçimlendirilmiş bir veri bulamadık. Excel'den Power BI hizmetine aktarmak için verileri tablo olarak biçimlendirmeniz gerekir. Tabloda istediğiniz tüm verileri seçin ve Ctrl+T tuşlarına basın.*

![Çalışma kitabında veri bulunamadı](media/service-admin-troubleshoot-excel-workbook-data/power-bi-we-couldnt-find-any-data.png)

## <a name="quick-solution"></a>Hızlı çözüm
1. Çalışma kitabınızı Excel'de düzenleyin.
2. Verilerinizin bulunduğu hücre aralığını seçin. İlk satırda sütun üstbilgilerinizin (sütun adları) bulunması gerekir.
3. **Ctrl + T** tuşlarına basarak bir tablo oluşturun.
4. Çalışma kitabınızı kaydedin.
5. Power BI'a geri dönün ve çalışma kitabınızı yeniden içeri aktarın veya Excel 2016'da çalışıyorsanız ve çalışma kitabınızı OneDrive İş'e kaydettiyseniz, Excel'de Dosya > Yayımla seçeneklerini belirleyin.

## <a name="details"></a>Ayrıntılar
### <a name="cause"></a>Neden
Excel'de, bir dizi hücreden **tablo** oluşturabilir, böylece verilerinizi kolayca sıralayabilir, filtreleyebilir ve biçimlendirebilirsiniz.

Bir Excel çalışma kitabını içeri aktardığınızda, Power BI bu tabloları bulur ve bir veri kümesine aktarır. Tablo bulunamaması halinde ise bu hata iletisiyle karşılaşırsınız.

### <a name="solution"></a>Çözüm
1. Çalışma kitabınızı Excel'de açın. 
    >[!NOTE]
    >Buradaki görüntüler Excel 2013'ten alınmıştır. Farklı bir sürüm kullanıyorsanız görüntüler küçük farklılıklar gösterebilir ancak adımlar aynıdır.
    
    ![Çalışma kitabını aç](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-worksheet-1.png)
2. Verilerinizin bulunduğu hücre aralığını seçin. İlk satırda sütun üstbilgilerinizin (sütun adları) bulunması gerekir:
   
    ![Hücre aralığını seçin](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-worksheet-2.png)
3. **EKLE** sekmesindeki şeritte bulunan **Tablo**'ya tıklayın. (Alternatif olarak **Ctrl + T** kısayolunu da kullanabilirsiniz.)
   
    ![Tablo ekle](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-worksheet-3.png)
4. Aşağıdaki iletişim kutusunu görürsünüz. **Tablom üstbilgi satırı içeriyor** onay kutusunun işaretlendiğinden emin olun ve **Tamam**'ı seçin:
   
    ![Tablo oluştur](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-create-table.png)
5. Artık verileriniz tablo biçimindedir:
   
    ![Tablo olarak biçimlendirilmiş veriler](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-table.png)
6. Çalışma kitabınızı kaydedin.
7. Power BI'a geri dönün. Gezinti bölmesinin alt kısmında bulunan Veri Al'ı seçin.
   
    ![Veri al](media/service-admin-troubleshoot-excel-workbook-data/power-bi-get-data.png)
8. **Dosyalar** kutusunda **Al**'ı seçin.
   
    ![Dosya alma](media/service-admin-troubleshoot-excel-workbook-data/power-bi-get-files.png)
9. Excel çalışma kitabınızı yeniden içeri aktarın. Bu kez içeri aktarma işlemiyle tablonun bulunması ve işlemin başarılı olması gerekir.
   
    İçeri aktarma işlemi yine de başarısız olursa yardım menüsündeki **Topluluk **seçeneğine tıklayarak bizi haberdar edin:
   
    ![Topluluk bağlantısı](media/service-admin-troubleshoot-excel-workbook-data/power-bi-question-menu-community.png)
