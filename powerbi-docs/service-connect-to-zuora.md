---
title: Power BI ile Zuora'ya bağlanma
description: Power BI için Zuora
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 605cd2f135ff6d8626586abbd503bcb44687931d
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008615"
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
4. Zuora URL'nizi belirtin. Bu URL genellikle "<https://www.zuora.com>" olur; [bu parametreleri bulma](#FindingParams) konusundaki ayrıntılı bilgileri aşağıda bulabilirsiniz.

   ![](media/service-connect-to-zuora/params.png)
5. **Kimlik doğrulama yöntemi** için **Temel** seçeneğini belirleyin ve kullanıcı adınızı ve parolanızı sağlayın (büyük/küçük harfe duyarlıdır), ardından **Oturum aç**'ı seçin.

    ![](media/service-connect-to-zuora/creds.png)
6. Onay vermenizin ardından, içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.

     ![](media/service-connect-to-zuora/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

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
| Hesap: Ödemeler |Ödeme geçerlilik tarihlerini temel alan, bir zaman dönemi içindeki toplam ödeme tutarlarıdır. |SUM (Payment.Amount) <br>WHERE<br>Payment.EffectiveDate =< TimePeriod.EndDate<br>AND    Payment.EffectiveDate >= TimePeriod.StartDate |
| Hesap: Para iadeleri |İade tarihini temel alan, bir zaman dönemi içindeki toplam iade tutarlarıdır. Tutar negatif bir sayı olarak bildirilir. |-1*SUM(Refund.Amount)<br>WHERE<br>Refund.RefundDate =< TimePeriod.EndDate<br>AND    Refund.RefundDate >= TimePeriod.StartDate |
| Hesap: Net Ödemeler |Bir zaman dönemi içindeki Account Payments (Hesap Ödemeleri) ile Account Refunds (Hesap İadeleri) toplamıdır. |Account.Payments + Account.Refunds |
| Hesap: Etkin Hesaplar |Bir zaman dönemi içinde etkin olan hesapların sayısıdır. Abonelikler zaman dönemi başlangıç tarihinden önce (veya başlangıç tarihinde) başlamış olmalıdır. |COUNT (Account.AccountNumber)<br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    (Subscription.SubscriptionEndDate > TimePeriod.StartDate<br>OR<br>Subscription.SubscriptionEndDate = null) –evergreen subscription |
| Hesap: Ortalama Yinelenen Gelir |Bir zaman dönemi içindeki etkin hesap başına Gross MRR (Aylık Yinelenen Gelir) anlamına gelir. |Gross MRR / Account.ActiveAccounts |
| Hesap: İptal Edilen Abonelikler |Bir zaman dönemi içinde bir aboneliği iptal eden hesapların sayısıdır. |COUNT (Account.AccountNumber)<br>WHERE<br>Subscription.Status = "Cancelled"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    Subscription.CancelledDate >= TimePeriod.StartDate |
| Hesap: Ödeme Hataları |Ödeme hatalarının toplam değeridir. |SUM (Payment.Amount)<br>WHERE<br>Payment.Status = "Error" |
| Gelir Zamanlama Öğesi: Tanınan Gelir |Bir hesap dönemi içindeki toplam tanınan gelirdir. |SUM (RevenueScheduleItem.Amount)<br>WHERE<br>AccountingPeriod.StartDate = TimePeriod.StartDate |
| Abonelik: Yeni Abonelikler |Bir zaman dönemi içindeki yeni aboneliklerin sayısıdır. |COUNT (Subscription.ID)<br>WHERE<br>Subscription.Version = "1"<br>AND    Subscription.CreatedDate <= TimePeriod.EndDate<br>AND    Subscription.CreatedDate >= TimePeriod.StartDate |
| Fatura: Fatura Öğeleri |Bir zaman dönemi içindeki toplam fatura madde gideri tutarlarıdır. |SUM (InvoiceItem.ChargeAmount)<br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Fatura: Vergi Öğeleri |Bir zaman dönemi içindeki toplam vergilendirme maddesi vergi tutarlarıdır. |SUM (TaxationItem.TaxAmount)<br>WHERE<br>Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Fatura: Fatura Öğesi Ayarlamaları |Bir zaman dönemi içindeki toplam fatura maddesi ayarlama tutarlarıdır. |SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceItemAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceItemAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Fatura: Fatura Ayarlamaları |Bir zaman dönemi içindeki toplam fatura ayarlama tutarlarıdır. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Fatura: Net Faturalar |Bir zaman dönemi içindeki fatura maddelerinin, vergilendirme maddelerinin, fatura maddesi ayarlamalarının ve fatura ayarlamalarının toplamıdır. |Invoice.InvoiceItems + Invoice.TaxationItems + Invoice.InvoiceItemAdjustments + Invoice.InvoiceAdjustments |
| Fatura: Fatura Yaşlandırma Bakiyesi |Deftere nakledilen fatura bakiyelerinin toplamıdır. |SUM (Invoice.Balance) <br>WHERE<br>    Invoice.Status = "Posted" |
| Fatura: Genel Faturalar |Bir zaman dönemi içinde, deftere nakledilen faturalar için fatura madde gideri tutarlarının toplamıdır. |SUM (InvoiceItem.ChargeAmount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Fatura: Toplam Ayarlamalar |Deftere nakledilen faturalarla ilişkili işlenen fatura ayarlamalarının ve fatura maddesi ayarlamalarının toplamıdır. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.Status = "Processed"<br>+<br>SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    invoiceItemAdjustment.Status = "Processed" |
| Fiyat Planı Ödemesi: Brüt MRR |Bir zaman dönemi içindeki aboneliklere yönelik aylık yinelenen gelirin toplamıdır. |SUM (RatePlanCharge.MRR) <br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    RatePlanCharge.EffectiveStartDate <= TimePeriod.StartDate<br>AND        RatePlanCharge.EffectiveEndDate > TimePeriod.StartDate<br>    OR    RatePlanCharge.EffectiveEndDate = null --evergreen subscription |

## <a name="system-requirements"></a>Sistem gereksinimleri
Zuora API erişimi gereklidir.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Genellikle Zuora verilerinize erişmek için kullandığınız oturum açma URL'sini sağlayın. Geçerli seçenekler şunlardır:  

* https://www.zuora.com  
* Hizmet örneğinize ilişkin URL  

## <a name="troubleshooting"></a>Sorun giderme
Zuora içerik paketi, Zuora hesabınızın birçok farklı özelliğini çeker. Belirli özellikleri kullanmazsanız ilişkili kutucukları/raporları boş olarak görebilirsiniz. Yüklemede herhangi bir sorunla karşılaşırsanız lütfen Power BI Destek ekibi ile iletişime geçin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)
