---
title: DAX örnek modeli
description: Başvuru makalelerini desteklemek için DAX örnek modeli.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/25/2020
ms.author: v-pemyer
ms.openlocfilehash: 0efa26a6ef3e47272d1434fab453a17ad9823c8c
ms.sourcegitcommit: cff93e604e2c5f24e0f03d6dbdcd10c2332aa487
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90965441"
---
# <a name="dax-sample-model"></a>DAX örnek modeli

**Adventure Works DW 2020** Power BI Desktop örnek modeli, DAX öğreniminizi desteklemek için tasarlanmıştır. Model, AdventureWorksDW2017’ye yönelik [Adventure Works veri ambarı örneğini](/sql/samples/adventureworks-install-configure#data-warehouse-downloads) temel alır, ancak veriler örnek modelin hedeflerine uygun olacak şekilde değiştirilmiştir.

## <a name="scenario"></a>Senaryo

:::image type="content" source="media/dax-sample-model/adventure-works-logo-150x150.png" alt-text="Adventure Works şirket logosunun bir resmi gösterilir.":::

Adventure Works şirketi, küresel pazarlara bisiklet ve aksesuarlar satan bir bisiklet üreticisini temsil eder. Şirket, veri ambarı verilerini bir Azure SQL Veritabanı’nda depolar.

## <a name="model-structure"></a>Model yapısı

Modelde yedi tablo vardır:

|Tablo|Açıklama|
|-----|-------|
|**Customer**|Müşterileri ve coğrafi konumlarını açıklar. Müşteriler, ürünleri çevrimiçi olarak (İnternet satışları) satın alır.|
|**Date**|**Tarih** ve **Satış** tabloları arasında sipariş tarihi, teslim tarihi ve son tarih için üç ilişki vardır. Sipariş tarihi ilişkisi etkindir. Şirket, satışlarını her yıl 1 Temmuz’da başlayan bir mali yıl kullanarak raporlar. Tablo, **Tarih** sütunu kullanılarak bir tarih tablosu halinde işaretlenmiştir.|
|**Ürün**|Yalnızca tamamlanmış ürünleri depolar.|
|**Kurumsal Bayi**|Satıcıları ve coğrafi konumlarını açıklar. Ürünleri müşterilere satan kurumsal bayi.|
|**Sales**|Satırları, satış siparişi hat diliminde depolar. Tüm mali değerler ABD doları (USD) cinsindendir. En erken sipariş tarihi 1 Temmuz 2017, en geç sipariş tarihi ise 15 Haziran 2020’dir.|
|**Satış Siparişi**|Satış siparişini ve sipariş hattı sayılarını, ayrıca **Kurumsal Bayi** veya **İnternet** olan satış kanalını tanımlar. Bu tablonun **Satış** tablosuyla bire bir ilişkisi vardır.|
|**Satış Bölgesi**|Satış bölgeleri gruplar (Kuzey Amerika, Avrupa ve Pasifik), ülkeler ve bölgeler halinde düzenlenir. Ürünleri yalnızca Amerika Birleşik Devletleri bölge düzeyinde satar.|

Model DAX hesaplaması içermez.

## <a name="download-sample"></a>Örnek indirme

Power BI Desktop örnek model dosyasını [buradan](https://aka.ms/dax-docs-sample-file) indirebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- Öğrenme yolu: [Power BI Desktop’ta DAX kullanma](/learn/paths/dax-power-bi/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)