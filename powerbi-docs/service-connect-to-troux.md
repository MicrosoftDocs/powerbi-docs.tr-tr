---
title: "Power BI ile Troux'a bağlanma"
description: "Power BI için Troux"
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
ms.openlocfilehash: c2d8e22758e3d28a3851b99140876ff1646a6be0
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-troux-for-power-bi"></a>Power BI için Troux'a bağlanma
Troux içerik paketiyle Enterprise Architecture deponuzu tamamen yeni yöntemlerle doğrudan Power BI'da görselleştirebilirsiniz. İçerik paketi; iş becerileriniz, bunları size sağlayan uygulamalar ve Power BI ile tamamen özelleştirilebilecek bu uygulamaları destekleyen teknolojilere ilişkin bir dizi öngörü sunar.

Power BI için [Troux içerik paketine](https://app.powerbi.com/getdata/services/troux) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-troux/getdata.png)
2. **Hizmetler** kutusundaki **Al**'ı seçin.
   
   ![](media/service-connect-to-troux/services.png)
3. **Troux** \>  **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-troux/troux.png)
4. Troux OData URL'nizi belirtin. [Bu parametreleri bulma](#FindingParams) konusundaki ayrıntılı bilgileri aşağıda bulabilirsiniz.
   
   ![](media/service-connect-to-troux/params.png)
5. **Kimlik doğrulama yöntemi** için **Temel** seçeneğini belirleyin ve kullanıcı adınızı ve parolanızı sağlayın (büyük/küçük harfe duyarlıdır), ardından **Oturum aç**'ı seçin.
   
    ![](media/service-connect-to-troux/creds.png)
6. Onaylamanızın ardından, içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
     ![](media/service-connect-to-troux/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Troux OData akışına erişim ve Troux 9.5.1 veya sonraki bir sürümü gereklidir.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Benzersiz Troux OData akışı URL'nizi Müşteri Hizmetleri ekibinizden alabilirsiniz

## <a name="troubleshooting"></a>Sorun giderme
Kimlik bilgilerini girdikten sonra bir zaman aşımı hatası alırsanız tekrar bağlanmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

