---
title: Power BI ile SweetIQ'ya bağlanma
description: Power BI için SweetIQ
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6592405de2d76c14334c8c31e4af84cd5a090ed9
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34247562"
---
# <a name="connect-to-sweetiq-with-power-bi"></a>Power BI ile SweetIQ'ya bağlanma
Power BI içerik paketi, SweetIQ hesabınızdaki verileri çekerek, verilerinizi kolayca araştırmanıza olanak sağlayan, kullanıma hazır bir içerik kümesi oluşturur. Konumlarınız, listeleriniz, derecelendirmeleriniz ve incelemeleriniz hakkındaki verileri çözümlemek için SweetIQ içerik paketini kullanın. Veriler, güncel bir izleme deneyimi elde etmenizi sağlamak üzere günlük olarak yenilenir.

Power BI için [SweetIQ içerik paketine](https://app.powerbi.com/groups/me/getdata/services/sweetiq) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Soldaki gezinti bölmesinde, **Veri Al**'a tıklayın.
   
    ![](media/service-connect-to-sweetiq/getdata.png)
2. **SweetIQ** seçeneğini belirleyin ve **Al**'a tıklayın.
   
    ![](media/service-connect-to-sweetiq/sweetiq.png)
3. SweetIQ Client ID'nizi (İstemci Kimliği) girin. Bu genellikle alfasayısal bir değerdir. Bu değeri bulmaya yönelik daha fazla ayrıntı için aşağıya bakın.
   
    ![](media/service-connect-to-sweetiq/parameter.png)
4. Kimlik doğrulaması türü olarak **Anahtar** seçeneğini belirleyin ve Sweet IQ API Anahtarınızı girin. Bu genellikle alfasayısal bir değerdir. Bu değeri bulmaya yönelik daha fazla ayrıntı için aşağıya bakın.
   
    ![](media/service-connect-to-sweetiq/credentials.png)
5. Power BI, verilerinizi yüklemeye başlar. Hesabınızdaki verilerin boyutuna bağlı olarak bu işlem biraz zaman alabilir. Yükleme tamamlandıktan sonra, sol gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz.
   
    ![](media/service-connect-to-sweetiq/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="finding-parameters"></a>Parametreleri bulma
Bu içerik paketine ilişkin Client ID (İstemci Kimliği) ve API anahtarı, SweetIQ kullanıcı adınız ve parolanızdan farklıdır.

Hesabınızın erişiminin bulunduğu istemcilerden birine ilişkin İstemci Kimliğini seçin. İstemci listesini SweetIQ hesabınızın "Client Management" (İstemci Yönetimi) bölümünde bulabilirsiniz.

Belirli bir istemciye ilişkin verilere erişmek üzere API anahtarını edinmek için yöneticinize başvurun.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI için Veri Alma](service-get-data.md)

