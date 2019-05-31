---
ms.openlocfilehash: 9aac366f04d53da56b62c10fdb85229d0d412834
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61397959"
---
*Eksen* alanı demetindeki bir görsele *tarih* alanı eklediğinizde Power BI otomatik olarak; *Year*, *Quarter*, *Month* ve *Day* içeren bir zaman hiyerarşisi ekler. Power BI bunu yaparak görsellerinizle raporlarınızı görüntüleyen kullanıcıların zamana bağlı etkileşime geçmesine olanak tanır, böylece kullanıcılar bu farklı zaman düzeylerinde detaya gidebilir.

![](media/3-11g-visual-hierarchies-drilling/3-11g_1.png)

Hiyerarşi eklendiğinde, zaman hiyerarşisi aracılığıyla detaya gitmeye başlayabilirsiniz. Örneğin, grafikteki bir yıla tıklamak hiyerarşideki bir üst düzeye (bu durumda *Quarters*) kadar detaya gidilmesini sağlar ve bunlar daha sonra görselde görüntülenir.

![](media/3-11g-visual-hierarchies-drilling/3-11g_2.png)

Otomatik olarak oluşturulan bu hiyerarşide, paylaşılan raporunuzda kullanıcıların hangi düzeye kadar detaya gidebileceğini de yönetebilirsiniz. Bunu yapmak için Görsel Öğeler bölmesinde kaldırmak istediğiniz hiyerarşinin yanındaki X işaretine tıklamanız yeterlidir. Silinen düzey rapordan kaldırılır ve detaya gitme işlemiyle artık bu düzey görüntülenmez.

![](media/3-11g-visual-hierarchies-drilling/3-11g_3.png)

Bu hiyerarşi düzeyini geri almanız gerekiyorsa *tarih* alanını kaldırıp **Alanlar** bölmesinden tekrar eklemeniz yeterlidir, böylece hiyerarşi sizin için bir kez daha otomatik olarak oluşturulur.

Hiyerarşinin bir görselde kullanılmasını istemediğiniz zamanlar olabilir. *Date* alanının (görsele bu alanı eklemenizin ardından) yanındaki aşağı ok düğmesini seçerek bunu denetleyebilir ve **Date Hierarchy** yerine **Date**'i seçebilirsiniz. Bu, Power BI'dan görselde ham tarih değerlerini göstermesini ister.

![](media/3-11g-visual-hierarchies-drilling/3-11g_4.png)

Tek bir üç aylık dönem veya tek bir yıl seçmek yerine, o sırada görünür halde olan tüm veri öğelerini aynı anda da genişletebilirsiniz. Bunu yapmak için görselin sol üst tarafındaki, aşağı çift ok simgesi olan *Tüm öğelerin detayına git* simgesini seçin.

![](media/3-11g-visual-hierarchies-drilling/3-11g_5.png)

