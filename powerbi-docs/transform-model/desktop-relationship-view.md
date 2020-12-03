---
title: Power BI Desktop'taki Meri görünümü
description: Power BI Desktop'taki Meri görünümü
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-transform-model
ms.topic: how-to
ms.date: 01/17/2020
LocalizationGroup: Model your data
ms.openlocfilehash: b257fc5af97cb16798cc27bdbdb92c1b63a65181
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96413783"
---
# <a name="work-with-model-view-in-power-bi-desktop"></a>Power BI Desktop'ta Model görünümüyle çalışma

*Model görünümü*, modelinizdeki tüm tabloları, sütunları ve ilişkileri gösterir. Bu görünüm özellikle birçok tablo arasında karmaşık ilişkiler bulunduğunda kullanışlı olabilir.

Mevcut modelin görünümünü görmek için pencerenin yan tarafındaki **Model** simgesini seçin. İmlecinizi ilişki satırının üzerine getirin ve kullanılan sütunları görüntüleyin.

![Model görünümü, Power BI Desktop](media/desktop-relationship-view/model-view-full-screen.png)

Resimde *Stores* tablosunun *StoreKey* sütununu, yine bir *StoreKey* sütunu bulunan *Sales* tablosuyla ilişkilendirilmiştir. İki tablonun *Çoka Bir* (\*:1) ilişkisi vardır. Satırın ortasındaki ok işareti, filtre bağlamı akışının yönünü gösterir. Çift ok, çapraz filtre yönünün *Her İkisi* olarak ayarlandığı anlamına gelir.

Bir ilişkiye çift tıklayarak **İlişkiyi Düzenle** iletişim kutusunu açabilirsiniz. İlişkiler hakkında daha fazla bilgi edinmek için bkz. [Power BI Desktop'ta ilişki oluşturma ve ilişkileri yönetme](desktop-create-and-manage-relationships.md).
