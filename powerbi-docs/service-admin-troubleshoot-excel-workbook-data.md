---
title: 'Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık'
description: 'Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık'
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: ea5312178d33986ebc3f4b9e8610012c87d54216
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026043"
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık

>[!NOTE]
>Bu makale Excel 2007 ve sonraki sürümleri için geçerlidir.

Power BI'a Excel çalışma kitabı aktarırken şu hatayla karşılaşabilirsiniz:

*Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık. Verileriniz uygun şekilde biçimlendirilmemiş olabilir. Çalışma kitabınızı Excel'de düzenlemeniz ve ardından tekrar içeri aktarmanız gerekir.*

![Çalışma kitabında veri bulunamadı](media/service-admin-troubleshoot-excel-workbook-data/pbi_wecouldntfindanydata.png)

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
    
    ![Çalışma kitabını aç](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht1.png)
2. Verilerinizin bulunduğu hücre aralığını seçin. İlk satırda sütun üstbilgilerinizin (sütun adları) bulunması gerekir:
   
    ![Hücre aralığını seçin](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht2.png)
3. **EKLE** sekmesindeki şeritte bulunan **Tablo**'ya tıklayın. (Alternatif olarak **Ctrl + T** kısayolunu da kullanabilirsiniz.)
   
    ![Tablo ekle](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht3.png)
4. Aşağıdaki iletişim kutusunu görürsünüz. **Tablom üstbilgi satırı içeriyor** onay kutusunun işaretlendiğinden emin olun ve **Tamam**'ı seçin:
   
    ![Tablo oluştur](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlcreatetbl.png)
5. Artık verileriniz tablo biçimindedir:
   
    ![Tablo olarak biçimlendirilmiş veriler](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xltbl.png)
6. Çalışma kitabınızı kaydedin.
7. Power BI'a geri dönün. Sol gezinti bölmesinin alt kısmındaki Veri Al seçeneğini belirleyin.
   
    ![Veri al](media/service-admin-troubleshoot-excel-workbook-data/pbi_getdata.png)
8. **Dosyalar** kutusunda **Al**'ı seçin.
   
    ![Dosya alma](media/service-admin-troubleshoot-excel-workbook-data/pbi_getfiles.png)
9. Excel çalışma kitabınızı yeniden içeri aktarın. Bu kez içeri aktarma işlemiyle tablonun bulunması ve işlemin başarılı olması gerekir.
   
    İçeri aktarma işlemi yine de başarısız olursa yardım menüsündeki **Topluluk **seçeneğine tıklayarak bizi haberdar edin:
   
    ![Topluluk bağlantısı](media/service-admin-troubleshoot-excel-workbook-data/pbi_questionmenucommunity.png)
