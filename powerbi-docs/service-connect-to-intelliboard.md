---
title: Power BI ile IntelliBoard'a bağlanma
description: Power BI için IntelliBoard
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6f3a335bea711f1785f498caf7fbc828abb01c18
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007902"
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Power BI ile IntelliBoard'a bağlanma
IntelliBoard, raporlama hizmetleri üzerinden Moodle öğrenme yönetim sistemi verilerinize yönelik basitleştirilmiş erişim sunar. Power BI için IntelliBoard içerik paketi; kurslarınız, kayıtlı kullanıcılarınız, genel performansınız ve LMS etkinliklerinize ilişkin ölçümler de dahil olmak üzere ek analizler sunar.

Power BI için [IntelliBoard içerik paketine](https://app.powerbi.com/getdata/services/intelliboard) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.  
   
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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

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
[Power BI nedir?](power-bi-overview.md)

[Power BI - Temel Kavramlar](consumer/end-user-basic-concepts.md)

