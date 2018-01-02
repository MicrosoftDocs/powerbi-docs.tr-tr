---
title: "Power BI Desktop'ta çift yönlü çapraz filtreleme (Önizleme)"
description: "Power BI Desktop'ta DirectQuery'yi kullanarak çapraz filtrelemeyi etkinleştirin"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 7946a9389897c4401e581482c0630547a764616d
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop-preview"></a>Power BI Desktop'ta DirectQuery'yi kullanarak çift yönlü çapraz filtreleme (Önizleme)

Rapor oluşturan (ve veri modelleyen) kullanıcılar, verilerin uygun görünümünü elde etmek üzere tabloları filtrelerken, filtreleme işleminin raporlara nasıl uygulanacağını belirleme konusunda bazı güçlüklerle karşılaşabilir. Bir tablonun filtre bağlamı, ilişkinin bir tarafında tutulurken diğer tarafında tutulmaz ve genellikle istenen sonuçların elde edilmesi için karmaşık DAX formülleri gerekir.

Çift yönlü çapraz filtreleme sayesinde, rapor oluşturan (ve veri modelleyen) kullanıcılar artık ilişkili tablolarla çalışırken filtrelerin nasıl uygulanacağı konusunda daha fazla denetime sahip olur. Bu özellik, söz konusu filtrelerin bir tablo ilişkisinin *her iki* tarafında da uygulanmasını sağlar. Bu işlem, filtre bağlamının, bir tablo ilişkisinin diğer tarafındaki ikinci bir ilişkili tabloya da uygulanması sağlanarak gerçekleştirilir.

Power BI Desktop'taki çift yönlü çapraz filtreleme özelliğinin açıklandığı [ayrıntılı bir teknik inceleme](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) vardır. (Ayrıca bu teknik incelemede, aynı davranışa sahip SQL Server Analysis Services 2016 da ele alınmıştır.)

* [Power BI Desktop için çift yönlü çapraz filtreleme](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) konusunun ele alındığı teknik incelemeyi indirin

### <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>DirectQuery için çift yönlü çapraz filtrelemeyi etkinleştirme
DirectQuery için çapraz filtreleme özelliğini kullanmak istiyorsanız öncelikle bu özelliği etkinleştirmeniz gerekir. Bu bir önizleme özelliğidir. Başka bir deyişle, bu özelliğin kullanılabilirliği ve davranışı, Power BI Desktop'ın gelecek sürümlerinde değişebilir.

Power BI Desktop'ta DirectQuery için çapraz filtreleme özelliğini etkinleştirmek istiyorsanız **Dosya > Seçenekler ve ayarlar > Seçenekler**'i seçin ve ardından, aşağıda gösterildiği gibi, **DirectQuery için her iki yönde çapraz filtrelemeyi etkinleştir** ifadesinin yanındaki kutuyu işaretleyin.

![](media/desktop-bidirectional-filtering/bidirectional-filtering_1.png)

> [!NOTE]
> Power BI Desktop'ta çapraz filtreleme için DAX formülleri oluştururken *UserName* yerine *UserPrincipalName* parametresini (genellikle, *joe@contoso.com* gibi kullanıcı oturum açma bilgileri ile aynıdır) kullanın. Benzer şekilde, *UserName* (veya örneğin, EmployeeID) ile *UserPrincipleName* parametrelerini eşleyen bir ilişkili tablo oluşturmanız gerekebilir.
> 
> 

Çapraz filtrelemeyi etkinleştirmek için bir ilişkiye ait **İlişkiyi Düzenle** iletişim kutusunda aşağıdakilerin seçilmesi gerekir:

* **Çapraz filtre yönü**, **Her ikisi de** olarak ayarlanmalıdır
* Ayrıca, **Güvenlik filtrelerini her iki yönde de uygula** seçeneği de belirlenmelidir
  
  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

Daha fazla bilgi edinmek ve çift yönlü çapraz filtrelemenin nasıl çalıştığına ilişkin örnekler görmek için daha önce bu makalede bahsedilen [teknik incelemeye](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) göz atın.

