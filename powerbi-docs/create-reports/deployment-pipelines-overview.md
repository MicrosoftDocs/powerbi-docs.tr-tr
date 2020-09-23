---
title: Dağıtım işlem hatlarına genel bakış
description: Power BI dağıtım işlem hatları hakkında bilgi edinin
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: contperfq1
ms.date: 09/15/2020
ms.openlocfilehash: 58d1adef9a9b2a8a4f818f94da2cb34e6529db83
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90855507"
---
# <a name="introduction-to-deployment-pipelines"></a>Dağıtım işlem hatlarına giriş

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
