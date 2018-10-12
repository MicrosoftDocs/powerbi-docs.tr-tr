---
title: Power BI ile comScore Digital Analytix'e bağlanma
description: Power BI için comScore Digital Analytix
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: f125edf58ab80da68a236d671495fc48e475c212
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46548546"
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
6. İçeri aktarma süreci otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Sistem gereksinimleri
Bağlanmak için comScore DAx kullanıcı hesabı ve comScore DAx API erişimi gerekir. Hesabınızı doğrulamak için lütfen comScore DAx yöneticinizle iletişime geçin.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
comScore parametrelerinizin her birini nasıl bulacağınıza ilişkin ayrıntılar aşağıdadır.

**Veri Merkezi**

Bağlandığınız veri merkezi comScore'da gittiğiniz URL tarafından belirlenir.

https://dax.comscore.com kullanıyorsanız “US”, https://dax.comscore.eu kullanıyorsanız “EU” değerini girin.

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

