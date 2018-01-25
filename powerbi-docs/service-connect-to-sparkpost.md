---
title: "Power BI ile SparkPost'a bağlanma"
description: "Power BI için SparkPost"
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
ms.openlocfilehash: 0547f288649ef9d2c494d979c39bb9661b8b35f4
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-sparkpost-with-power-bi"></a>Power BI ile SparkPost'a bağlanma
Power BI'daki SparkPost içerik paketi sayesinde SparkPost hesabınızdaki tüm değerli veri kümelerini öngörüler sunan tek bir panoya ayıklayabilirsiniz. SparkPost içerik paketini kullanarak, ISS'lere göre etki alanlarını, kampanyaları ve etkileşimi içeren genel e-posta istatistiklerinizi görselleştirebilirsiniz.

[Power BI için SparkPost içerik paketine](https://app.powerbi.com/getdata/services/spark-post) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-sparkpost/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-sparkpost/services.png)
3. **SparkPost** içerik paketini seçin ve **Al**'a tıklayın. 
   
   ![](media/service-connect-to-sparkpost/sparkpost.png)
4. İstendiğinde SparkPost API anahtarınızı girin ve Oturum Aç'ı seçin. [Bu parametreleri bulma](#FindingParams) ile ilgili ayrıntılar için aşağıya bakın.
   
   ![](media/service-connect-to-sparkpost/creds.png)
5. Verileriniz yüklenmeye başlar. Hesabınızın boyutuna bağlı olarak bu işlem biraz zaman alabilir. Verileriniz Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde, geçtiğimiz 90 güne ait e-posta istatistikleriniz ile doldurulmuş varsayılan panoyu, raporu ve veri kümesini görürsünüz. Yeni öğeler sarı yıldız işareti \* ile gösterilir.
   
   ![](media/service-connect-to-sparkpost/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
Power BI için SparkPost içerik paketinde; benzersiz tıklamaları, iletilme oranlarını, geri dönüş oranlarını, gecikme oranlarını, ret oranlarını ve daha fazlasını içeren bilgiler bulunur.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
İçerik paketi, SparkPost hesabınızı Power BI'a bağlamak için API anahtarı kullanır. Hesabınızdaki API anahtarını Account (Hesap) \> API & SMTP bölümünde bulabilirsiniz ([buradan](https://support.sparkpost.com/customer/portal/articles/1933377-create-api-keys) daha fazla ayrıntıya ulaşabilirsiniz). `Message Events: Read-only `ve `Metrics: Read-only` izinlerini içeren bir API anahtarı kullanmanızı öneririz

![](media/service-connect-to-sparkpost/sparkpost1.png)

