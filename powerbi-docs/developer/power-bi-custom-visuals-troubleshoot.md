---
title: Power BI görsellerini geliştirme sorunlarını giderme
description: Bu makalede, özel Power BI görseli geliştirme veya oluşturma sırasında karşılaşabileceğiniz bazı yaygın sorunlar açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: troubleshooting
ms.subservice: powerbi-custom-visuals
ms.date: 11/06/2018
ms.openlocfilehash: c2680a5818488a7822f38b8286a3e5a1782a487a
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2020
ms.locfileid: "74999779"
---
# <a name="troubleshoot-power-bi-visuals"></a>Power BI görselleriyle ilgili sorunları giderme

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

Tüm sorularınız, yorumlarınız veya sorunlarınız için Power BI görselleri destek takımına başvurmaktan çekinmeyin: *pbicvsupport@microsoft.com* .

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi edinmek için [Power BI görselleri hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#organizational-power-bi-visuals) bağlantısını ziyaret edin.