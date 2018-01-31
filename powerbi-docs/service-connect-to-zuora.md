---
title: "Power BI ile Zuora'ya bağlanma"
description: "Power BI için Zuora"
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
ms.openlocfilehash: 408f41e1a50b895166308fcba129d86f5c05d0e7
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-zuora-with-power-bi"></a>Power BI ile Zuora'ya bağlanma
Power BI için Zuora; önemli gelir, faturalandırma ve abonelik verilerini görselleştirmenizi sağlar. Kullanım eğilimlerini çözümlemek, fatura ve ödemeleri takip etmek ve yinelenen geliri izlemek için varsayılan pano ve raporları kullanın veya bunları kendi benzersiz pano ve raporlama ihtiyaçlarınızı karşılayacak şekilde özelleştirin.

Power BI için [Zuora](https://app.powerbi.com/getdata/services/Zuora)'ya bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.

   ![](media/service-connect-to-zuora/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.

   ![](media/service-connect-to-zuora/services.png)
3. **Zuora** \> **Al** seçeneğini belirleyin.

   ![](media/service-connect-to-zuora/zuora.png)
4. Zuora URL'nizi belirtin. Bu genellikle "https://www.zuora.com" dur, aşağıdaki [bu parametreleri bulma](#FindingParams) başlığından ayrıntıları bulabilirsiniz.

   ![](media/service-connect-to-zuora/params.png)
5. **Kimlik Doğrulama Yöntemi** için **Temel** seçeneğini belirleyin ve kullanıcı adınızı ve parolanızı sağlayın (büyük/küçük harfe duyarlıdır), ardından **Oturum aç**'ı seçin.

    ![](media/service-connect-to-zuora/creds.png)
6. Onaylamanızın ardından, içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.

     ![](media/service-connect-to-zuora/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
İçerik paketi, Zuora AQUA API'sini kullanarak şu tabloları çeker:

| Tablolar |  |  |
| --- | --- | --- |
| Account |InvoiceItemAdjustment |Refund |
| AccountingCode |Payment |RevenueSchedule |
| AccountingPeriod |PaymentMethod |RevenueScheduleItem |
| BillTo |Product |Subscription |
| DateDim |ProductRatePlan |TaxationItem |
| Invoice |ProductRatePlanCharge |Usage |
| InvoiceAdjustment |RatePlan | |
| InvoiceItem |RatePlanCharge | |

İçerik paketi aynı zamanda şu hesaplanmış ölçüleri içerir:

| Ölçü | Açıklama | Sözde Hesaplama |
| --- | --- | --- |
| Account: Payments |Ödeme geçerlilik tarihlerini temel alan, bir zaman dönemi içindeki toplam ödeme tutarlarıdır. |SUM (Payment.Amount) <br>WHERE<br>Payment.EffectiveDate =< TimePeriod.EndDate<br>AND    Payment.EffectiveDate >= TimePeriod.StartDate |
| Account: Refunds |İade tarihini temel alan, bir zaman dönemi içindeki toplam iade tutarlarıdır. Tutar negatif bir sayı olarak bildirilir. |-1*SUM(Refund.Amount)<br>WHERE<br>Refund.RefundDate =< TimePeriod.EndDate<br>AND    Refund.RefundDate >= TimePeriod.StartDate |
| Account: Net Payments |Bir zaman dönemi içindeki Account Payments (Hesap Ödemeleri) ile Account Refunds (Hesap İadeleri) toplamıdır. |Account.Payments + Account.Refunds |
| Account: Active Accounts |Bir zaman dönemi içinde etkin olan hesapların sayısıdır. Abonelikler zaman dönemi başlangıç tarihinden önce (veya başlangıç tarihinde) başlamış olmalıdır. |COUNT (Account.AccountNumber)<br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    (Subscription.SubscriptionEndDate > TimePeriod.StartDate<br>OR<br>Subscription.SubscriptionEndDate = null) –evergreen subscription |
| Account: Average Recurring Revenue |Bir zaman dönemi içindeki etkin hesap başına Gross MRR (Aylık Yinelenen Gelir) anlamına gelir. |Gross MRR / Account.ActiveAccounts |
| Account: Cancelled Subscriptions |Bir zaman dönemi içinde bir aboneliği iptal eden hesapların sayısıdır. |COUNT (Account.AccountNumber)<br>WHERE<br>Subscription.Status = "Cancelled"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    Subscription.CancelledDate >= TimePeriod.StartDate |
| Account: Payment Errors |Ödeme hatalarının toplam değeridir. |SUM (Payment.Amount)<br>WHERE<br>Payment.Status = "Error" |
| Revenue Schedule Item: Recognized Revenue |Bir hesap dönemi içindeki toplam tanınan gelirdir. |SUM (RevenueScheduleItem.Amount)<br>WHERE<br>AccountingPeriod.StartDate = TimePeriod.StartDate |
| Subscription: New Subscriptions |Bir zaman dönemi içindeki yeni aboneliklerin sayısıdır. |COUNT (Subscription.ID)<br>WHERE<br>Subscription.Version = "1"<br>AND    Subscription.CreatedDate <= TimePeriod.EndDate<br>AND    Subscription.CreatedDate >= TimePeriod.StartDate |
| Invoice: Invoice Items |Bir zaman dönemi içindeki toplam fatura madde gideri tutarlarıdır. |SUM (InvoiceItem.ChargeAmount)<br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Invoice: Taxation Items |Bir zaman dönemi içindeki toplam vergilendirme maddesi vergi tutarlarıdır. |SUM (TaxationItem.TaxAmount)<br>WHERE<br>Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Invoice: Invoice Item Adjustments |Bir zaman dönemi içindeki toplam fatura maddesi ayarlama tutarlarıdır. |SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceItemAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceItemAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Invoice: Invoice Adjustments |Bir zaman dönemi içindeki toplam fatura ayarlama tutarlarıdır. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Invoice: Net Billings |Bir zaman dönemi içindeki fatura maddelerinin, vergilendirme maddelerinin, fatura maddesi ayarlamalarının ve fatura ayarlamalarının toplamıdır. |Invoice.InvoiceItems + Invoice.TaxationItems + Invoice.InvoiceItemAdjustments + Invoice.InvoiceAdjustments |
| Invoice: Invoice Aging Balance |Deftere nakledilen fatura bakiyelerinin toplamıdır. |SUM (Invoice.Balance) <br>WHERE<br>    Invoice.Status = "Posted" |
| Invoice: Gross Billings |Bir zaman dönemi içinde, deftere nakledilen faturalar için fatura madde gideri tutarlarının toplamıdır. |SUM (InvoiceItem.ChargeAmount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Invoice: Total Adjustments |Deftere nakledilen faturalarla ilişkili işlenen fatura ayarlamalarının ve fatura maddesi ayarlamalarının toplamıdır. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.Status = "Processed"<br>+<br>SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    invoiceItemAdjustment.Status = "Processed" |
| Rate Plan Charge: Gross MRR |Bir zaman dönemi içindeki aboneliklere yönelik aylık yinelenen gelirin toplamıdır. |SUM (RatePlanCharge.MRR) <br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    RatePlanCharge.EffectiveStartDate <= TimePeriod.StartDate<br>AND        RatePlanCharge.EffectiveEndDate > TimePeriod.StartDate<br>    OR    RatePlanCharge.EffectiveEndDate = null --evergreen subscription |

## <a name="system-requirements"></a>Sistem gereksinimleri
Zuora API erişimi gereklidir.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Genellikle Zuora verilerinize erişmek için kullandığınız oturum açma URL'sini sağlayın. Geçerli seçenekler şunlardır:  

* https://www.zuora.com  
* https://www.apisandbox.zuora.com  
* Hizmet örneğinize ilişkin URL  

## <a name="troubleshooting"></a>Sorun giderme
Zuora içerik paketi, Zuora hesabınızın birçok farklı özelliğini çeker. Belirli özellikleri kullanmazsanız ilişkili kutucukları/raporları boş olarak görebilirsiniz. Yüklemede herhangi bir sorunla karşılaşırsanız lütfen Power BI Destek ekibi ile iletişime geçin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)
