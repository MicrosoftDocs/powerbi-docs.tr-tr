---
title: Power BI ile VMob'a bağlanma
description: Power BI için VMob
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e6c63d93c876377da7a5d36e814431dfda8665c3
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70185789"
---
# <a name="connect-to-vmob-with-power-bi"></a>Power BI ile VMob'a bağlanma
Power BI ve VMob içerik paketi ile VMob verilerinizi izlemek ve araştırmak çok kolay. Power BI şu verileri alır: Tüm zamanlara ve son 30 güne ait Kullanıcı İstatistikleri, son 30 güne ait Perakende KPI'si ve son 30 güne ait Kampanya Performansı.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

Power BI için [VMob içerik paketine](https://app.powerbi.com/getdata/services/vmob) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
    ![](media/service-connect-to-vmob/getdata.png)
2. **Hizmetler** kutusundaki **Al** düğmesini seçin.
   
   ![](media/service-connect-to-vmob/services.png)
3. **VMob** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-vmob/vmob.png)
4. İstendiğinde VMob URL'nizi girin ve Sonraki düğmesine tıklayın. Bu URL, VMob tarafından ayrı olarak sağlanır.
   
    ![](media/service-connect-to-vmob/params.png)
5. Kimlik doğrulama yöntemi açılan listesinde **Temel** seçeneğini belirleyin, VMob kullanıcı adınızı ve parolanızı girin ve **Oturum aç**'a tıklayın.
   
    ![](media/service-connect-to-vmob/creds.png)
6. İçeri aktarma işlemi otomatik olarak başlar ve Power BI, sizin için kullanıma hazır bir pano ve rapor oluşturmak üzere VMob verilerinizi alır.
   
   ![](media/service-connect-to-vmob/dashboard2.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

