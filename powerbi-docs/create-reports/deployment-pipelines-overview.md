---
title: Dağıtım işlem hatlarına genel bakış
description: Power BI dağıtım işlem hatları hakkında bilgi edinin
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: contperfq1
ms.date: 10/21/2020
ms.openlocfilehash: b0b8d61224a91cd069caf48a2d321979ac2d291d
ms.sourcegitcommit: cc20b476a45bccb870c9de1d0b384e2c39e25d24
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94513310"
---
# <a name="introduction-to-deployment-pipelines"></a>Dağıtım işlem hatlarına giriş

Günümüzde analiz, neredeyse tüm kuruluşların karar verme sürecinin önemli bir parçasıdır. Analiz alanında her geçen gün daha fazla kullanıcıya ulaşan Power BI'ın daha fazla veriye ulaşması, ilgi çekici görünmesi ve kullanıcı dostu olması gerekmektedir. Ancak bunların da ötesinde Power BI her zaman kullanılabilir durumda ve güvenilir olmalıdır. BI ile içerik oluşturanlar bu gereksinimleri karşılamak için verimli bir şekilde işbirliği yapmalıdır.

Dağıtım işlem hatları aracı, BI oluşturucularının kurumsal içeriğin yaşam döngüsünü yönetmesine olanak sağlar. Bu araç, Premium kapasiteye sahip bir kuruluştaki oluşturucular için verimlidir ve yeniden kullanılabilir. Dağıtım işlem hatları, oluşturucuların Power BI içeriklerini, kullanıcılar tarafından kullanılmadan önce geliştirmesine ve test etmesine olanak sağlar. İçerik türleri arasında raporlar, panolar ve veri kümeleri yer alır.

Bu araç üç aşamalı bir işlem hattı olarak tasarlanmıştır:

* **<a name="development"></a>Geliştirme**
    
    Bu aşamada içerik oluşturucular yeni içerik tasarlar, oluşturur ve karşıya yükler. Bu, dağıtım işlem hattının ilk aşamasıdır.

* **<a name="test"></a>Test**

    İçerikleriniz üzerinde gereken tüm değişiklikleri yaptıktan sonra test aşamasına girmeye hazırsınız demektir. Değiştirilen içeriği, bu test aşamasına taşınabilmesi için karşıya yüklersiniz. Test ortamında yapılabilecek işlemlere yönelik üç örnek aşağıda verilmiştir:

    * İçeriği test edenler ve gözden geçirenlerle paylaşma

    * Daha büyük hacimli veriler yükleme ve test çalıştırma

    * Uygulamanızı test ederek son kullanıcılarınız tarafından nasıl görüntüleneceğini görme

* **<a name="production"></a>Üretim**

    İçeriği test ettikten sonra üretim aşamasını kullanarak içeriğinizin son sürümünü kuruluşunuzdaki iş kullanıcılarıyla paylaşabilirsiniz.

![Dağıtım, test ve üretim aşamalarının doldurulmuş olduğu çalışan bir dağıtım işlem hattının ekran görüntüsü.](media/deployment-pipelines-overview/deployment-pipelines.png)

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarını kullanmaya başlama](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[Dağıtım işlem hattı sürecini anlama](deployment-pipelines-process.md)

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarıyla ilgili sorunları giderme](deployment-pipelines-troubleshooting.md)

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarına yönelik en iyi yöntemler](deployment-pipelines-best-practices.md)
