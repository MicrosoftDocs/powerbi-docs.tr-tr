---
title: Dağıtım işlem hatlarına genel bakış
description: Power BI dağıtım işlem hatları hakkında bilgi edinin
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 05/06/2020
ms.openlocfilehash: be945d1d9612804a90c14c47d2c468f5ed5a843f
ms.sourcegitcommit: 008467dc9d4f88f91728c59caeb68b7db94f267c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82885042"
---
# <a name="introduction-to-deployment-pipelines-preview"></a>Dağıtım işlem hatlarına giriş (önizleme)

Günümüzde analiz, neredeyse tüm kuruluşların karar verme sürecinin önemli bir parçasıdır. Analiz alanında her geçen gün daha fazla kullanıcıya ulaşan Power BI'ın daha fazla veriye ulaşması, ilgi çekici görünmesi ve kullanıcı dostu olması gerekmektedir. Ancak bunların da ötesinde Power BI her zaman kullanılabilir durumda ve güvenilir olmalıdır. BI ile içerik oluşturanlar bu gereksinimleri karşılamak için verimli bir şekilde işbirliği yapmalıdır.

Dağıtım işlem hatları, bir kuruluş içindeki Premium kapasiteye sahip olan BI içerik oluşturucuların kurumsal içeriğin yaşam döngüsünü yönetmesini sağlayan verimli ve yeniden kullanılabilir bir araçtır. Bu araç sayesinde raporlar, panolar ve veri kümeleri gibi Power BI içerikleri geliştirilebilir ve son kullanıcılara sunulmadan önce test edilebilir.

Bu araç üç aşamalı bir işlem hattı olarak tasarlanmıştır:

* **<a name="development"></a>Geliştirme**
    
    Bu aşamada içerik oluşturucular yeni içerik tasarlar, oluşturur ve karşıya yükler. Bu, dağıtım işlem hattının ilk aşamasıdır.

* **<a name="test"></a>Test**

    Geliştirme aşamasında içerik karşıya yüklendikten ve gerekli tüm değişiklikler yapıldıktan sonra test için bu aşamaya geçilebilir. Test ortamında yapılabilecek işlemlere yönelik üç örnek aşağıda verilmiştir:

    * İçeriği test edenler ve gözden geçirenlerle paylaşma

    * Daha büyük hacimli veriler yükleme ve test çalıştırma

    * Uygulamanızı test ederek son kullanıcılarınız tarafından nasıl görüntüleneceğini görme

* **<a name="production"></a>Üretim**

    İçeriği test ettikten sonra üretim aşamasını kullanarak içeriğinizin son sürümünü kuruluşunuzdaki iş kullanıcılarıyla paylaşabilirsiniz.

![dağıtım işlem hatları](media/deployment-pipelines-overview/deployment-pipelines.png)

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarını kullanmaya başlama](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[Dağıtım işlem hattı sürecini anlama](deployment-pipelines-process.md)

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarıyla ilgili sorunları giderme](deployment-pipelines-troubleshooting.md)

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarına yönelik en iyi yöntemler](deployment-pipelines-best-practices.md)