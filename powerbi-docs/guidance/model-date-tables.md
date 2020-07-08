---
title: Power BI Desktop’ta tarih tabloları oluşturma
description: Power BI Desktop’ta tarih tabloları oluşturmaya yönelik teknikler ve kılavuz.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2020
ms.author: v-pemyer
ms.openlocfilehash: ad85ad56db907ca19af7dc14681eb34f8c2b9abc
ms.sourcegitcommit: 46a340937d9f01c6daba86a4ab178743858722ec
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85398340"
---
# <a name="create-date-tables-in-power-bi-desktop"></a>Power BI Desktop’ta tarih tabloları oluşturma

Bu makale, Power BI Desktop'la çalışan veri modelleyicilerine yöneliktir. Veri modellerinizde tarih tabloları oluşturmaya yönelik iyi tasarım uygulamaları açıklanmaktadır.

Veri Çözümleme İfadeleri (DAX) [akıllı zaman gösterimi işlevleri](/dax/time-intelligence-functions-dax) ile çalışmak için bir önkoşul modeli gereksinimi vardır: Modelinizde en az bir _tarih tablosu_ olmalıdır. Tarih tablosu, aşağıdaki gereksinimleri karşılayan bir tablodur:

> [!div class="checklist"]
> - _Tarih sütunu_ olarak bilinen **tarih** (veya **tarih/saat**) veri türü sütununa sahip olması gerekir.
> - Tarih sütunu benzersiz değerler içermelidir.
> - Tarih sütunu BOŞLUKLAR içermemelidir.
> - Tarih sütununda eksik tarihler olmamalıdır.
> - Tarih sütunu tam yıllara yayılmalıdır. Yılın bir takvim yılı (Ocak-Aralık) olması gerekmez.
> - Tarih tablosunun [tarih tablosu olarak işaretlenmiş olması](../transform-model/desktop-date-tables.md#setting-your-own-date-table) gerekir.

Modelinize tarih tablosu eklemek için çeşitli tekniklerden birini kullanabilirsiniz:

- Otomatik tarih/saat seçeneği
- Tarih boyut tablosuna bağlanmak için Power Query
- Tarih tablosu oluşturmak için Power Query
- Tarih tablosu oluşturmak için DAX
- Mevcut bir tarih tablosunu kopyalamak için DAX

> [!TIP]
> Tarih tablosu, belki de modellerinize ekleyeceğiniz en tutarlı özelliktir. Dahası, bir kuruluşta tarih tablosunun tutarlı bir şekilde tanımlanması gerekir. Bu nedenle, kullanmaya karar verdiğiniz tarihten bağımsız olarak, tam olarak yapılandırılmış tarih tablosu içeren bir [Power BI Desktop şablonu](../create-reports/desktop-templates.md) oluşturmanızı öneririz. Şablonu kuruluşunuzdaki tüm modelleyicilerle paylaşın. Böylece, birisi her yeni model geliştirdiğinde tutarlı bir şekilde tanımlanmış tarih tablosuyla işe başlayabilir.

## <a name="use-auto-datetime"></a>Otomatik tarih ve saati kullanma

[Otomatik tarih/saat](../transform-model/desktop-auto-date-time.md) seçeneği kullanışlı, hızlı ve kullanımı kolay bir akıllı zaman gösterimi sağlar. Rapor yazarları takvim zaman aralıklarında filtreleme, gruplandırma ve detaya gitme işlemleri yaparken akıllı zaman gösterimiyle çalışabilir.

Otomatik tarih/saat seçeneğini yalnızca takvim zaman aralıklarıyla çalışırken ve zamanla ilişkili olarak basit model gereksinimleriniz olduğunda etkinleştirmenizi öneririz. Ayrıca geçici modeller oluştururken ya da veri araştırması veya profil oluşturma işlemleri yaparken bu seçenek kullanışlı olabilir. Ancak bu yaklaşım, filtreleri birden çok tabloya yayabilen tek bir tarih tablosunu desteklemez. Daha fazla bilgi için bkz. [Power BI Desktop’ta Otomatik tarih/saat kılavuzu](auto-date-time.md).

## <a name="connect-with-power-query"></a>Power Query ile bağlanma

Veri kaynağınızda zaten bir tarih tablosu varsa bunu model tarih tablonuzun kaynağı olarak kullanmanızı öneririz. Veri ambarına bağlanırken tarih boyutu tablosuna sahip olacağından, genellikle durum budur. Bu şekilde, modeliniz kuruluşunuzda zaman için tek bir gerçek kaynaktan yararlanır.

Bir DirectQuery modeli geliştiriyorsanız ve veri kaynağınızda bir tarih tablosu bulunmuyorsa veri kaynağınıza tarih tablosu eklemenizi şiddetle öneririz. Tarih tablosunun tüm modelleme gereksinimlerini karşılaması gerekir. Daha sonra veri tablosuna bağlanmak için Power Query’yi kullanabilirsiniz. Bu şekilde, model hesaplamalarınız DAX akıllı zaman gösterimi özelliklerinden yararlanabilir.

## <a name="generate-with-power-query"></a>Power Query ile oluşturma

Power Query kullanarak bir tarih tablosu oluşturabilirsiniz. Size nasıl yapılacağını gösteren iki blog girişi aşağıda verilmiştir:

- [Creating a Date Dimension with a Power Query Script](https://www.mattmasson.com/2014/02/creating-a-date-dimension-with-a-power-query-script/) (Power Query Betiğiyle Tarih Boyutu Oluşturma) - Matt Masson
- [Generating A Date Dimension Table In Power Query](https://blog.crossjoin.co.uk/2013/11/19/generating-a-date-dimension-table-in-power-query/) (Power Query’de Tarih Boyutu Tablosu Oluşturma) - Chris Webb

> [!TIP]
> Kuruluşunuzda zaman için veri ambarı veya başka bir tutarlı tanım yoksa [veri akışı](../transform-model/service-dataflows-overview.md) yayımlamak için Power Query’yi kullanmanız faydalı olabilir. Daha sonra, tüm veri modelleyicileri kendi modellerine tarih tablosu eklemek için veri akışına bağlanır. Böylece veri akışı, kuruluşunuzda zaman için tek gerçek kaynak haline gelir.

Tarih tablosu oluşturmanız gerekiyorsa bunu DAX ile yapmanız faydalı olabilir. Bu, size daha kolay gelecektir. Ayrıca, DAX tarih tablolarını oluşturup yönetmeyi basitleştirmek için yerleşik zeka içerdiğinden, muhtemelen daha uygun olacaktır.

## <a name="generate-with-dax"></a>DAX ile oluşturma

[CALENDAR](/dax/calendar-function-dax) veya [CALENDARAUTO](/dax/calendarauto-function-dax) DAX işlevlerinden biri aracılığıyla, hesaplanmış bir tablo oluşturarak modelinizde bir tarih tablosu oluşturabilirsiniz. Her işlev, tek sütunlu tarih tablosu döndürür. Daha sonra hesaplanmış tabloyu, tarih aralığı filtreleme ve gruplandırma gereksinimlerinizi destekleyecek şekilde hesaplanmış sütunlarla genişletebilirsiniz.

- Bir tarih aralığı tanımlamanız gerektiğinde **CALENDAR** işlevini kullanın. İki değeri geçirirsiniz: başlangıç tarihi ve bitiş tarihi. Bu değerler, `MIN(Sales[OrderDate])` veya `MAX(Sales[OrderDate])` gibi diğer DAX işlevleriyle tanımlanabilir.
- Tarih aralığının modelde depolanan tüm tarihleri otomatik olarak kapsamasını istediğinizde **CALENDARAUTO** işlevini kullanın. Yılın son ayı olan (yılınız Aralık ayında biten bir takvim ayıysa bir değer geçirmeniz gerekmez) tek bir isteğe bağlı parametreyi geçirebilirsiniz. Tarihlerin tüm yıllarının döndürülmesini sağladığından (işaretli tarih tablosu için bu bir gereksinimdir), yararlı bir işlevdir. Dahası, tabloyu sonraki yıllara genişletmeyi yönetmeniz gerekmez: Veri yenilemesi tamamlandığında, tablonun yeniden hesaplanmasını tetikler. Yeni yılın tarihleri modele yüklendiğinde yeniden hesaplama işlemi, tablonun tarih aralığını otomatik olarak genişletir.

## <a name="clone-with-dax"></a>DAX ile kopyalama

Modelinizde zaten bir tarih tablosu olduğunda ve başka tarih tablosu eklemeniz gerektiğinde, mevcut tarih tablosunu kolayca kopyalayabilirsiniz. Bu, tarihin [rol oynadığı bir boyut](star-schema.md#role-playing-dimensions) olduğu durumdur. Hesaplanmış bir tablo oluşturarak bir tabloyu kopyalayabilirsiniz. Hesaplanmış tablo ifadesi, basitçe mevcut tarih tablosunun adıdır.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Desktop’ta otomatik tarih/saat](../transform-model/desktop-auto-date-time.md)
- [Power BI Desktop’ta otomatik tarih/saat kılavuzu](auto-date-time.md)
- [Power BI Desktop'ta tarih tabloları ayarlama ve kullanma](../transform-model/desktop-date-tables.md)
- [Power BI’da self servis veri hazırlığı](../transform-model/service-dataflows-overview.md)
- [CALENDAR işlevi (DAX)](/dax/calendar-function-dax)
- [CALENDARAUTO işlevi (DAX)](/dax/calendarauto-function-dax)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)