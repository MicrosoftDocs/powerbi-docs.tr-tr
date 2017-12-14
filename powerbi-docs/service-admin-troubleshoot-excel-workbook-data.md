---
title: "Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık"
description: "Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 77bd53a5bb54ff5bd982ba8e912c81ca520c5b8f
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık

>[!NOTE]
>Bu makale Excel 2007 ve sonraki sürümleri için geçerlidir.

Power BI'a Excel çalışma kitabı aktarırken şu hatayla karşılaşabilirsiniz:

*Hata: Excel çalışma kitabınızda herhangi bir veri bulamadık. Verileriniz uygun şekilde biçimlendirilmemiş olabilir. Çalışma kitabınızı Excel'de düzenlemeniz ve ardından tekrar içeri aktarmanız gerekir.*

![](media/service-admin-troubleshoot-excel-workbook-data/pbi_wecouldntfindanydata.png)

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
    
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht1.png)
2. Verilerinizin bulunduğu hücre aralığını seçin. İlk satırda sütun üstbilgilerinizin (sütun adları) bulunması gerekir:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht2.png)
3. **EKLE** sekmesindeki şeritte bulunan **Tablo**'ya tıklayın. (Alternatif olarak **Ctrl + T** kısayolunu da kullanabilirsiniz.)
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht3.png)
4. Aşağıdaki iletişim kutusunu görürsünüz. **Tablom üstbilgi satırı içeriyor** onay kutusunun işaretlendiğinden emin olun ve **Tamam**'ı seçin:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlcreatetbl.png)
5. Artık verileriniz tablo biçimindedir:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xltbl.png)
6. Çalışma kitabınızı kaydedin.
7. Power BI'a geri dönün. Sol gezinti bölmesinin alt kısmındaki Veri Al seçeneğin belirleyin.
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getdata.png)
8. **Dosyalar** kutusunda **Al**'ı seçin.
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getfiles.png)
9. Excel çalışma kitabınızı yeniden içeri aktarın. Bu kez içeri aktarma işlemiyle tablonun bulunması ve işlemin başarılı olması gerekir.
   
    İçeri aktarma işlemi yine de başarısız olursa yardım menüsündeki **Topluluk **seçeneğine tıklayarak bizi haberdar edin:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_questionmenucommunity.png)
