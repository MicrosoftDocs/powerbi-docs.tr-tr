---
title: Dinamik bağlama kullanarak bir Power BI raporunu veri kümesine bağlama
description: Power BI ekli analizinde dinamik bağlama kullanarak bir Power BI raporu eklemeyi öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 01/17/2021
ms.openlocfilehash: 0bc33ed37e389b42f5c27f8271cc461eb99e229a
ms.sourcegitcommit: 1cad78595cca1175b82c04458803764ac36e5e37
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2021
ms.locfileid: "98565820"
---
# <a name="connect-a-report-to-a-dataset-using-dynamic-binding"></a>Dinamik bağlama kullanarak bir raporu veri kümesine bağlama 

Rapor bir veri kümesine bağlı olduğunda dinamik bağlamayı kullanabilirsiniz. Rapor ve veri kümesi arasındaki bağlantı, *bağlama* olarak bilinir. Bağlama, daha önceden belirlenmesinin aksine ekleme sırasında belirlendiğinde, bu işlem dinamik bağlama olarak bilinir.

*Dinamik bağlama* kullanarak bir Power BI raporu eklerken, kullanıcının kimlik bilgilerine bağlı olarak aynı raporu farklı veri kümelerine bağlayabilirsiniz.

Bu, farklı bilgileri göstermek için bağlı olduğu veri kümesine bağlı olarak bir rapor kullanabileceğiniz anlamına gelir. Örneğin, perakende satış değerlerini gösteren bir rapor farklı perakende satıcı veri kümelerine bağlanabilir ve bağlı olduğu perakende satıcının veri kümesine bağlı olarak farklı sonuçlar oluşturabilir.

Raporun ve veri kümesinin aynı çalışma alanında bulunması gerekmez. Her iki çalışma alanı da (raporu içeren çalışma alanı ve veri kümesini içeren çalışma alanı) bir [kapasiteye](azure-pbie-create-capacity.md) atanmalıdır.

Ekleme sürecinin bir parçası olarak, *yeterli izinlere sahip bir belirteç oluşturduğunuzdan* ve *yapılandırma nesnesini ayarladığınızdan* emin olun.

## <a name="generating-a-token-with-sufficient-permissions"></a>Yeterli izinlere sahip bir belirteç oluşturma

Dinamik bağlama, *Kuruluşunuz için ekleme* ve *Müşterileriniz için ekleme* senaryolarının her ikisi için de desteklenir. Aşağıdaki tabloda her senaryoya ilişkin değerlendirmeler açıklanmaktadır.

|Senaryo  |Veri sahipliği  |Belirteç  |Gereksinimler  |
|---------|---------|---------|---------|
|*Kuruluşunuz için içerik ekleme*    |Veriler kullanıcıya aittir         |Power BI kullanıcıları için erişim belirteci         |Azure AD belirteci kullanılan kullanıcının tüm yapıtlar için uygun izinlere sahip olması gerekir.         |
|*Müşterileriniz için içerik ekleme*     |Veriler uygulamaya aittir         |Power BI kullanıcısı olmayan kişiler için erişim belirteci         |Hem rapora hem de dinamik olarak bağlı veri kümesine yönelik izinleri içermelidir. [Birden çok öğe için ekleme belirteci oluşturmayı sağlayan API](/rest/api/power-bi/embedtoken/generatetoken)’yi kullanarak birden çok yapıtı destekleyen bir ekleme belirteci oluşturun.         |

## <a name="adjusting-the-config-object"></a>Yapılandırma nesnesini ayarlama

Dinamik bağlamayı kullanabilmek için `datasetBinding` öğesini yapılandırma nesnesine eklemeniz gerekir. Bunun nasıl yapıldığını öğrenmek için bkz. [Veri kümelerini dinamik olarak bir rapora bağlama](/javascript/api/overview/powerbi/bind-report-datasets). 

## <a name="next-steps"></a>Sonraki adımlar

Power BI’da ekleme konusuna yeni başladıysanız, Power BI içeriğinizi nasıl ekleyeceğinizi öğrenmek için aşağıdaki öğreticileri inceleyin.

>[!div class="nextstepaction"]
>[Müşterileriniz için Power BI içeriğini bir uygulamaya ekleme](embed-sample-for-customers.md)

>[!div class="nextstepaction"]
>[Kuruluşunuz için Power BI içeriğini bir uygulamaya ekleme](embed-sample-for-your-organization.md)