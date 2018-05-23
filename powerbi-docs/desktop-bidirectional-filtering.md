---
title: Power BI Desktop'ta çift yönlü çapraz filtreleme
description: Power BI Desktop'ta DirectQuery'yi kullanarak çapraz filtrelemeyi etkinleştirin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a584d61e1f2f55c244b453e6c086f3222217ee9a
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop"></a>Power BI Desktop'ta DirectQuery'yi kullanarak çift yönlü çapraz filtreleme

Rapor oluşturan (ve veri modelleyen) kullanıcılar, verilerin uygun görünümünü elde etmek üzere tabloları filtrelerken, filtreleme işleminin raporlara nasıl uygulanacağını belirleme konusunda bazı güçlüklerle karşılaşabilir. Bir tablonun filtre bağlamı, ilişkinin bir tarafında tutulurken diğer tarafında tutulmaz ve genellikle istenen sonuçların elde edilmesi için karmaşık DAX formülleri gerekir.

Çift yönlü çapraz filtreleme sayesinde, rapor oluşturan (ve veri modelleyen) kullanıcılar artık ilişkili tablolarla çalışırken filtrelerin nasıl uygulanacağı konusunda daha fazla denetime sahip olur. Bu özellik, söz konusu filtrelerin bir tablo ilişkisinin *her iki* tarafında da uygulanmasını sağlar. Bu işlem, filtre bağlamının, bir tablo ilişkisinin diğer tarafındaki ikinci bir ilişkili tabloya da uygulanması sağlanarak gerçekleştirilir.

Power BI Desktop'taki çift yönlü çapraz filtreleme özelliğinin açıklandığı [ayrıntılı bir teknik inceleme](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) vardır. (Ayrıca bu teknik incelemede, aynı davranışa sahip SQL Server Analysis Services 2016 da ele alınmıştır.)

* [Power BI Desktop için çift yönlü çapraz filtreleme](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) konusunun ele alındığı teknik incelemeyi indirin

### <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>DirectQuery için çift yönlü çapraz filtrelemeyi etkinleştirme

Çapraz filtrelemeyi etkinleştirmek için bir ilişkiye ait **İlişkiyi Düzenle** iletişim kutusunda aşağıdakilerin seçilmesi gerekir:

* **Çapraz filtre yönü**, **Her ikisi de** olarak ayarlanmalıdır
* Ayrıca, **Güvenlik filtrelerini her iki yönde de uygula** seçeneği de belirlenmelidir
  
  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

> [!NOTE]
> Power BI Desktop'ta çapraz filtreleme için DAX formülleri oluştururken *UserName* yerine *UserPrincipalName* parametresini (genellikle, *joe@contoso.com* gibi kullanıcı oturum açma bilgileri ile aynıdır) kullanın. Benzer şekilde, *UserName* (veya örneğin, EmployeeID) ile *UserPrincipleName* parametrelerini eşleyen bir ilişkili tablo oluşturmanız gerekebilir.
> 
> 

Daha fazla bilgi edinmek ve çift yönlü çapraz filtrelemenin nasıl çalıştığına ilişkin örnekler görmek için daha önce bu makalede bahsedilen [teknik incelemeye](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) göz atın.

