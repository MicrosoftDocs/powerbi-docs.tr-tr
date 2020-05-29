---
title: Power BI sayfalandırılmış raporlarındaki alt raporların sorunlarını giderme
description: Bu makalede Power BI hizmetindeki sayfalandırılmış raporlar için desteklenen veri kaynaklarını ve Azure SQL Veritabanı veri kaynaklarına nasıl bağlanacağınızı öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 04/29/2020
ms.openlocfilehash: 6de85f6dda69e902a98d6ee63d1fc4b86fb4180b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82615646"
---
# <a name="troubleshoot-subreports-in-power-bi-paginated-reports"></a>Power BI sayfalandırılmış raporlarındaki alt raporların sorunlarını giderme

Sayfalandırılmış raporlarda alt raporlar kullandığınızda bazen beklemediğiniz bir sonuç alabilirsiniz veya özellik beklediğiniz gibi çalışmayabilir. Bu makalede alt raporlar özelliği kullanılırken sık karşılaşılan sorunların çözümleri sağlanır. *Alt rapor*, ana sayfalandırılmış raporun gövdesi içinde başka bir rapor görüntüleyen bir rapor öğesidir. Konuyla ilgili daha fazla bilgi için bkz. [Power BI sayfalandırılmış raporlarındaki alt raporlar](subreports.md).

## <a name="subreport-couldnt-be-found"></a>Alt rapor bulunamadı

**Açıklama:** Alt rapor işlenmiyor. Bunun yerine hata iletisi görüntüleniyor.

### <a name="message"></a>İleti

"'Subreport1' alt raporu belirtilen 'CustomerDetails' konumunda bulunamadı. Alt raporun yayımlandığından ve adının doğru olduğundan emin olun."

### <a name="possible-reasons"></a>Olası nedenler

- Ana raporla aynı çalışma alanında veya uygulamada, belirtilen ada sahip bir alt rapor yok.
- Kullanıcının alt rapora erişimi yok.
- Ana rapordaki alt raporların sayısı alt rapor sınırına (50 alt rapor) ulaştı.

### <a name="troubleshooting-steps"></a>Sorun giderme adımları

**Çalışma alanında**

- Hata iletisinde verilen ada sahip bir raporun var olduğunu doğrulayın. Ad büyük/küçük harfe duyarlı değildir.

**Uygulamada**

- Hata iletisinde verilen ada sahip bir raporun uygulamada var olduğunu doğrulayın. Daha fazla yardım almak için uygulamanın yazarına başvurun.

**Rapor paylaşılıyorsa**

1. Hata iletisinde verilen ada sahip bir raporun sizinle paylaşıldığını doğrulayın.
2. Rapor varsa, ana raporla alt rapor için sahip adının aynı olduğunu doğrulayın. Sonra ana raporun sahibine bu bilgilerle başvurun.

## <a name="subreport-renders-with-unexpected-content"></a>Alt rapor beklenmeyen içerikle işleniyor

### <a name="possible-reason"></a>Olası neden

Power BI kullanıcıların aynı çalışma alanında aynı ada sahip birden çok rapor bulundurmasına izin veriyor

### <a name="troubleshooting-steps-for-report-authors"></a>Sorun giderme adımları (rapor yazarları için)

1. Ana raporu Power BI Report Builder’da açın ve alt raporun adını saptayın.
2. Çalışma alanında aynı ada sahip raporları arayın.
3. İstenen raporu bulun ve diğerini yeniden adlandırın.

**Yazar olmayan kullanıcılar için:** Yazara başvurun.

## <a name="data-retrieval-fails"></a>Veri alma işlemi başarısız oldu

**Açıklama:** Alt rapor işlenirken veri alma işlemi başarısız oldu. Alt rapor işlenmiyor. Bunun yerine hata iletisi görüntüleniyor.

### <a name="message"></a>İleti

"'InvoiceDetails' konumundaki 'Subreport1' alt raporu için veriler alınamadı. Daha fazla bilgi için günlük dosyalarına göz atın."

### <a name="troubleshooting-steps"></a>Sorun giderme adımları

Veri erişimi sorunları olan raporlarla aynı genel sorun giderme adımları.

## <a name="rendering-fails-unspecified-parameters"></a>İşleme başarısız oluyor: Belirtilmeyen parametreler

**Açıklama:** Alt rapor işleme işlemi belirtilmeyen parametreler nedeniyle başarısız oluyor. Alt raporun zorunlu parametreleri var ama ana rapor bunların tümünü ayarlamıyor.

### <a name="message"></a>İleti 
"'SubreportAWithDS' konumundaki 'Subreport1' alt raporu için en az bir parametre belirtilmedi."

### <a name="troubleshooting-steps-for-the-report-author"></a>Sorun giderme adımları (rapor yazarı için)

1. Ana raporu Power BI Report Builder’da açın.
2. Alt raporu Power BI Report Builder’da açın.
3. Ana raporda alt rapor öğesinin içine geçirilen parametre kümesinin, alt raporda bulunan parametre kümesiyle eşleştiğini doğrulayın.

**Yazar olmayan kullanıcılar için:** Yazara başvurun.

## <a name="rendering-fails-recursion-limit"></a>İşleme başarısız oluyor: Özyineleme sınırı

**Açıklama:** Alt rapor işleme işlemi özyineleme sınırı nedeniyle başarısız oluyor. Alt raporlar 20 düzeyden fazla iç içe yerleştirilemez.

### <a name="message"></a>İleti

"Rapor veya alt rapor, yinelemeli bir alt rapora ('Subreport1') sahip ve bu alt rapor izin verilen özyineleme üst sınırını aştı."

### <a name="troubleshooting-steps-for-report-authors"></a>Sorun giderme adımları (rapor yazarları için)

- İç içe yerleştirme düzeyini azaltın.
- Rapor yapısını yeniden tasarlayın.

## <a name="other-errors"></a>Diğer hatalar

**Açıklama:** Önceki kategorilerden hiçbirine girmeyen hatalar.

### <a name="message"></a>İleti

"Hata: Alt rapor görüntülenemedi."

### <a name="possible-reasons"></a>Olası nedenler

- Alt rapor işleme işlemi sırasında birden çok hata oluştu, örneğin veri alma sorunlarıyla parametre uyuşmazlığı oldu.
- Beklenmeyen hatalar.

### <a name="troubleshooting-steps-for-report-authors"></a>Sorun giderme adımları (rapor yazarları için)

1. Alt raporun doğrudan işleyebildiğini doğrulayın.
2. Alt rapor işlenebiliyorsa hem alt rapordaki hem de ana rapordaki parametreleri denetleyin.
3. Ana raporda 50’den fazla benzersiz alt rapor bulunmadığından ve iç içe yerleştirilmiş alt raporların 20 düzeyden daha derin olmadığından emin olun.
4. Sorunu çözemiyorsanız Power BI desteğine ulaşın.

**Yazar olmayan kullanıcılar için:** Yazara başvurun.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI sayfalandırılmış raporlarındaki alt raporlar](subreports.md)

[Power BI hizmetinde sayfalandırılmış rapor görüntüleme](../consumer/paginated-reports-view-power-bi-service.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)