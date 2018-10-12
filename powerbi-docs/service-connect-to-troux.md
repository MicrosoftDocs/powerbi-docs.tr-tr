---
title: Power BI ile Troux'a bağlanma
description: Power BI için Troux
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: ccb7828bf22f364ae0982d5c80a17b075bb5b143
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46549593"
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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

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

