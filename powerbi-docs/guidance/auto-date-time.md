---
title: Power BI Desktop’ta otomatik tarih/saat kılavuzu
description: Power BI Desktop'taki otomatik tarih/saat işlevini kullanma kılavuzu.
author: peter-myers
ms.author: kfollis
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 10/23/2019
ms.openlocfilehash: e7fcab58dc61735639689c4574a9ce89757882ca
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99088684"
---
# <a name="auto-datetime-guidance-in-power-bi-desktop"></a>Power BI Desktop’ta otomatik tarih/saat kılavuzu

Bu makale, Power BI Desktop'ta İçeri Aktarma modelleri veya Bileşik modeller geliştiren veri modelleyicilerine yöneliktir. Power BI Desktop _Otomatik tarih/saat_ işlevini belirli koşullarda kullanmaya yönelik yönergeler, öneriler ve dikkate alınacak noktalar sağlanır. _Otomatik tarih/saat_ işlevine genel bakış ve giriş bilgileri için bkz. [Power BI Desktop'ta otomatik tarih/saat](../transform-model/desktop-auto-date-time.md).

_Otomatik tarih/saat_ seçeneği kullanışlı, hızlı ve kullanımı kolay bir akıllı zaman gösterimi sağlar. Rapor yazarları takvim zaman aralıklarında filtreleme, gruplandırma ve detaya gitme işlemleri yaparken akıllı zaman gösterimiyle çalışabilir.

## <a name="considerations"></a>Önemli noktalar

Aşağıdaki madde işaretli listede _Otomatik tarih/saat_ seçeneğiyle ilgili olarak dikkate alınacak noktalar ve olası sınırlamalar açıklanır.

- **Tümüne uygulanır veya hiçbirine uygulanmaz:** _Otomatik tarih/saat_ seçeneği etkinleştirildiğinde, ilişkinin &quot;çok&quot; tarafında yer almayan İçeri Aktarma tablolarındaki tüm tarih sütunlarına uygulanır. Tek tek sütunlar için seçmeli olarak etkinleştirilemez veya devre dışı bırakılamaz.
- **Yalnızca takvim zaman aralıkları:** Yıl ve çeyrek sütunları takvim zaman aralıklarıyla ilgilidir. Diğer bir deyişle yıl 1 Ocak'ta başlar ve 31 Aralık'ta biter. Yılın başlangıç (veya tamamlanma) tarihini özelleştirme olanağı sağlanmaz.
- **Özelleştirme:** Zaman aralıklarını açıklamak için kullanılan değerleri özelleştirmek mümkün değildir. Ayrıca diğer zaman aralıklarını, örneğin haftaları açıklamak üzere başka sütunlar eklemek de mümkün değildir.
- **Yıl filtreleme:** **Çeyrek**, **Ay** ve **Gün** sütunu değerleri yıl değerini içermez. Örneğin **Ay** sütununda yalnızca ay adları bulunur (Ocak, Şubat vb.). Değerler tam olarak açıklayıcı değildir ve bazı rapor tasarımlarında yıl filtresi bağlamı iletilmeyebilir.

    Bu nedenle filtrelerin ve gruplandırmaların **Yıl** sütununda yapılması önemlidir. Hiyerarşi kullanılarak detaya gidildiğinde, **Yıl** düzeyi bilinçli olarak kaldırılmadığı sürece yıl filtrelenir. Yıla göre filtre veya gruplandırma yoksa, örneğin aya göre yapılan bir gruplandırma söz konusu ay için tüm yılların değerlerini özetler.
- **Tek tablo tarih filtrelemesi:** Her tarih sütunu kendi (gizli) otomatik tarih/saat tablosunu oluşturduğundan, tek tabloya bir zaman filtresi uygulayıp bunun birden çok model tablosuna yayılmasını sağlamak mümkün değildir. Satış ve satış bütçesi gibi birden çok konuda raporlama yaparken (olgu türünde tablolar), bu şekilde filtreleme yaygın bir modelleme gereksinimidir. Otomatik tarih/saat seçeneğini kullanan rapor yazarının farklı tarih sütunlarından her birine filtreleri uygulaması gerekir.
- **Model boyutu:** Gizli bir otomatik tarih/saat tablosu oluşturan her tarih sütunu için, sonuçta model boyutu artar ve ayrıca veri yenileme süresi uzar.
- **Diğer raporlama araçları:** Aşağıdaki durumlarda otomatik tarih/saat tablolarıyla çalışmak mümkün değildir:
  - [Excel’de Çözümleme](../collaborate-share/service-analyze-in-excel.md) kullanılırken
  - Power BI sayfalandırılmış raporu Analysis Services sorgu tasarımcıları kullanılırken.
  - Power BI dışındaki rapor tasarımcıları kullanılarak modele bağlanılırken.

## <a name="recommendations"></a>Öneriler

_Otomatik tarih/saat_ seçeneğini yalnızca takvim zaman aralıklarıyla çalışırken ve zamanla ilişkili olarak basit model gereksinimleriniz olduğunda etkinleştirmenizi öneririz. Ayrıca geçici modeller oluştururken ya da veri araştırması veya profil oluşturma işlemleri yaparken bu seçenek kullanışlı olabilir.

Veri kaynağınız zaten bir tarih boyutu tablosu tanımladığında, kuruluşunuzda zamanı tutarlı bir şekilde tanımlamak için bu tablo kullanılmalıdır. Veri kaynağınız bir veri ambarıysa büyük olasılıkla bu durum geçerli olacaktır. Aksi takdirde DAX [CALENDAR](/dax/calendar-function-dax) veya [CALENDARAUTO](/dax/calendarauto-function-dax) işlevlerini kullanarak modelinizde tarih tabloları oluşturabilirsiniz. Ardından bilinen zaman filtreleme ve gruplandırma gereksinimlerini desteklemek üzere hesaplanmış sütunlar ekleyebilirsiniz. Bu tasarım yaklaşımı, tüm olgu türünde tablolara yayılan tek bir tarih tablosu oluşturmanıza olanak tanıyabilir ve sonuçta büyük olasılıkla zaman filtrelerinin uygulanacağı tek tablo olur. Tarih tabloları oluşturma hakkında daha fazla bilgi için [Power BI Desktop'ta tarih tablolarını ayarlama ve kullanma](../transform-model/desktop-date-tables.md) makalesini okuyun.

_Otomatik tarih/saat_ seçeneği projelerinize uygun değilse, Genel _Otomatik tarih/saat_ seçeneğini devre dışı bırakmanızı öneririz. Bu şekilde oluşturduğunuz tüm yeni Power BI Desktop dosyalarında _Otomatik tarih/saat_ seçeneğinin etkinleştirilmemesi sağlanır.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Desktop’ta tarih tabloları oluşturma](model-date-tables.md)
- [Power BI Desktop’ta otomatik tarih/saat](../transform-model/desktop-auto-date-time.md)
- [Power BI Desktop'ta tarih tabloları ayarlama ve kullanma](../transform-model/desktop-date-tables.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
