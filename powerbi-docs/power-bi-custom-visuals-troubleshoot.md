---
title: Power BI Power BI görsellerini geliştirme sorunlarını giderme
description: Bu makalede, özel Power BI görseli geliştirme veya oluşturma sırasında karşılaşabileceğiniz bazı yaygın sorunlar açıklanır.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 11/06/2018
ms.openlocfilehash: 4d863ff921df2a5cfb5233d85679f2277542bb44
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71195361"
---
# <a name="troubleshoot-power-bi-power-bi-visuals"></a>Power BI Power BI görselleriyle ilgili sorunları giderme

## <a name="debug"></a>Hata Ayıklama

**Pbiviz komutunun bulanamaması (veya benzer hatalar)**

Terminalinizde/komut satırınızda `pbiviz` komutunu çalıştırdığınızda yardım ekranını görmeniz gerekir. Görmezseniz, yükleme doğru yapılmamıştır. NodeJS 4.0 veya sonraki bir sürümünün yüklendiğinden emin olun.

**Hata ayıklama görselinin Görsel Öğeler sekmesinde bulunamaması**

**Görsel Öğeler** sekmesindeki hata ayıklama görseli bir istem simgesi gibi görünür.

![Görsel seçimi](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

Bu simgeyi görmüyorsanız görselin Power BI ayarlarında etkinleştirildiğinden emin olun.

> [!NOTE]
> Hata ayıklama görseli şu anda yalnızca Power BI hizmetinde kullanılabilir ve Power BI Desktop'ta veya mobil uygulamada kullanılamaz. Paketlenmiş görsel yine de her yerde çalışır.

**Görsel sunucuyla bağlantı kurulamıyor**

Görsel projenizin kökünde, terminalinizin komut satırına `pbiviz start` komutunu girerek görsel sunucuyu çalıştırın. Sunucu çalışmıyorsa SSL sertifikaları düzgün bir şekilde yüklenmemiş olabilir.

Tüm sorularınız, yorumlarınız veya sorunlarınız için Power BI görselleri destek takımına başvurmaktan çekinmeyin: *pbicvsupport@microsoft.com*  .

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi edinmek için [Power BI Power BI görselleri hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#organizational-visuals) bağlantısını ziyaret edin.