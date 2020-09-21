---
title: Dağıtım işlem hatlarına genel bakış
description: Power BI dağıtım işlem hatları hakkında bilgi edinin
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 09/09/2020
ms.openlocfilehash: 3994a5cdad4d80c87d4153ffe57af685d7a21d36
ms.sourcegitcommit: 92b033ee7a6e36808371b247b7b41536cee6c2f6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2020
ms.locfileid: "90008595"
---
# <a name="introduction-to-deployment-pipelines-preview"></a>Dağıtım işlem hatlarına giriş (önizleme)

Günümüzde analiz, neredeyse tüm kuruluşların karar verme sürecinin önemli bir parçasıdır. Analiz alanında her geçen gün daha fazla kullanıcıya ulaşan Power BI'ın daha fazla veriye ulaşması, ilgi çekici görünmesi ve kullanıcı dostu olması gerekmektedir. Ancak bunların da ötesinde Power BI her zaman kullanılabilir durumda ve güvenilir olmalıdır. BI ile içerik oluşturanlar bu gereksinimleri karşılamak için verimli bir şekilde işbirliği yapmalıdır.

Dağıtım işlem hatları aracı, BI oluşturucularının kurumsal içeriğin yaşam döngüsünü yönetmesine olanak sağlar. Araç, Premium kapasiteye sahip bir kuruluştaki oluşturucular için verimlidir ve yeniden kullanılabilir. Araç, oluşturucuların Power BI içeriklerini, kullanıcılar tarafından kullanılmadan önce geliştirmesine ve test etmesine olanak sağlar. İçerik türleri arasında raporlar, panolar ve veri kümeleri yer alır.

Bu araç üç aşamalı bir işlem hattı olarak tasarlanmıştır:

* **<a name="development"></a>Geliştirme**
    
    Bu aşamada içerik oluşturucular yeni içerik tasarlar, oluşturur ve karşıya yükler. Bu, dağıtım işlem hattının ilk aşamasıdır.

* **<a name="test"></a>Test**

    İçerikleriniz üzerinde tüm değişiklikleri yaptıktan sonra test aşamasına girmeye hazırsınız demektir. Değiştirilen içeriği, bu test aşamasına taşınabilmesi için karşıya yüklersiniz. Test ortamında yapılabilecek işlemlere yönelik üç örnek aşağıda verilmiştir:

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
