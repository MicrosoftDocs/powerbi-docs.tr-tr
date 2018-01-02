---
title: "Power BI ile comScore Digital Analytix'e bağlanma"
description: "Power BI için comScore Digital Analytix"
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
ms.openlocfilehash: c53c7f5e0748e186c68bcc2642b381cf17c423eb
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-comscore-digital-analytix-with-power-bi"></a>Power BI ile comScore Digital Analytix'e bağlanma
Power BI içerik paketi ile Power BI'da comScore Digital Analytix verilerinizi görselleştirin ve araştırın. Veriler, günde bir kez otomatik olarak yenilenir.

[Power BI için comScore içerik paketine](https://app.powerbi.com/getdata/services/comscore) bağlanın.

>[!NOTE]
>İçerik paketine bağlanmak için comScore DAx kullanıcı hesabına ve comScore API erişimine sahip olmanız gerekir. Aşağıda daha fazla [ayrıntıya](#Requirements) yer verilmiştir.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki Veri Al seçeneğini belirleyin.
   
   ![](media/service-connect-to-connect-to/getdata.png)
2. **Hizmetler** kutusundaki **Al**'ı seçin.
   
   ![](media/service-connect-to-connect-to/services.png)
3. **comScore Digital Analytix** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-connect-to/comscore.png)
4. Bağlanmak istediğiniz veri merkezini, comScore İstemci Kimliğini ve Siteyi girin. Bu değerleri nasıl bulacağınızla ilgili daha fazla ayrıntı için aşağıdaki [comScore Parametrelerinizi bulma](#FindingParams) bölümüne bakın.
   
   ![](media/service-connect-to-connect-to/parameters.png)
5. Bağlanmak için comScore kullanıcı adınızı ve parolanızı girin. Bu değeri bulmaya ilişkin ayrıntılar için aşağıya bakın.
   
   ![](media/service-connect-to-connect-to/creds.png)
6. İçeri aktarma süreci otomatik olarak başlar. Tamamlandığında, Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.

**Sırada ne var?**

* Panonun üst kısmındaki [Soru-Cevap kutusunda soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenmeye zamanlanacak olsa da yenileme zamanlamasını değiştirebilir veya **Şimdi Yenile** ile istediğiniz zaman yenileme yapabilirsiniz

<a name="Requirements"></a>

## <a name="system-requirements"></a>Sistem gereksinimleri
Bağlanmak için comScore DAx kullanıcı hesabı ve comScore DAx API erişimi gerekir. Hesabınızı doğrulamak için lütfen comScore DAx yöneticinizle iletişime geçin.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
comScore parametrelerinizin her birini nasıl bulacağınıza ilişkin ayrıntılar aşağıdadır.

**Veri Merkezi**

Bağlandığınız veri merkezi comScore'da gittiğiniz URL tarafından belirlenir.

https://dax.comscore.com kullanıyorsanız "US" öğesini, https://dax.comscore.eu kullanıyorsanız "EU" öğesini girin.

![](media/service-connect-to-connect-to/comscore_url.png) 

**İstemci**

İstemci, comScore DAx'te oturum açarken girdiğiniz istemcidir.

![](media/service-connect-to-connect-to/comscore_signin.png) 

**Site**

comScore sitesi, verilerini görmek istediğiniz siteyi belirler. comScore hesabınızdan sitelerin listesini bulabilirsiniz.

![](media/service-connect-to-connect-to/comscore_sites.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)
