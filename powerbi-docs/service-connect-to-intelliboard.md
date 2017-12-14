---
title: "Power BI ile IntelliBoard'a bağlanma"
description: "Power BI için IntelliBoard"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: f668a1c9bfefb1b0b0c7c15f9d68c82312d38105
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Power BI ile IntelliBoard'a bağlanma
IntelliBoard, raporlama hizmetleri üzerinden Moodle öğrenme yönetim sistemi verilerinize yönelik basitleştirilmiş erişim sunar. Power BI için IntelliBoard içerik paketi; kurslarınız, kayıtlı kullanıcılarınız, genel performansınız ve LMS etkinliklerinize ilişkin ölçümler de dahil olmak üzere ek analizler sunar.

Power BI için [IntelliBoard içerik paketine](https://app.powerbi.com/getdata/services/intelliboard) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki **Veri Al**'ı seçin.  
   
    ![](media/service-connect-to-intelliboard/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.  
   
    ![](media/service-connect-to-intelliboard/services.png)
3. **IntelliBoard**'u ve ardından **Al**'ı seçin.  
   
    ![](media/service-connect-to-intelliboard/intelliboard.png)
4. **OAuth2**'yi ve ardından **Oturum Aç**'ı seçin. İstendiğinde IntelliBoard kimlik bilgilerinizi girin.
   
    ![](media/service-connect-to-intelliboard/creds.png)
   
    ![](media/service-connect-to-intelliboard/creds2.png)
5. Bağlandıktan sonra bir pano, rapor ve veri kümesi otomatik olarak yüklenir. Bu işlem tamamlandığında kutucuklar, IntelliBoard hesabınızdaki veriler ile güncelleştirilir.
   
    ![](media/service-connect-to-intelliboard/dashboard.png)

**Sırada ne var?**

* Panonun üst kısmındaki [Soru-Cevap kutusunu kullanarak bir soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
İçerik paketi şu tablolardaki verileri içerir:  

    - Activity  
    - Agents  
    - Auth  
    - Countries  
    - CoursesProgress  
    - Enrollments
    - Lang  
    - Platform  
    - Totals  
    - UsersProgress    

## <a name="system-requirements"></a>Sistem Gereksinimleri
Bu içerik paketinin bir örneğini oluşturmak için, yukarıdaki tablolara yönelik izinlere sahip bir IntelliBoard hesabı gereklidir.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

