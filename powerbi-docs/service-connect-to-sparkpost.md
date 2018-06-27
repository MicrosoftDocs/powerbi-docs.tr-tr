---
title: Power BI ile SparkPost'a bağlanma
description: Power BI için SparkPost
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6f914a031c70c68703116083f42885e2fe79cf30
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34247907"
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

