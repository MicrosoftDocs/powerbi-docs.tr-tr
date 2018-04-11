---
title: Power BI ile VMob'a bağlanma
description: Power BI için VMob
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 89d1a4cecb7c62dffe71524353bcd48957245594
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-vmob-with-power-bi"></a>Power BI ile VMob'a bağlanma
Power BI ve VMob içerik paketi ile VMob verilerinizi izlemek ve araştırmak çok kolay. Power BI şu verileri alır: tüm zamanlara ve son 30 güne ait Kullanıcı İstatistikleri, son 30 güne ait Perakende KPI'si ve son 30 güne ait Kampanya Performansı.

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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

