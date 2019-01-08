---
title: Power BI özel görseli geliştirme sorunlarını giderme
description: Bu makalede, özel Power BI görseli geliştirme veya oluşturma sırasında karşılaşabileceğiniz bazı yaygın sorunlar açıklanır.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 11/06/2018
ms.openlocfilehash: 264794346a046ceb85c67f77d2fe6d80556d342d
ms.sourcegitcommit: 88ae40a25ea54ef7153885dd04ef57d12522d4e1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54056007"
---
# <a name="troubleshoot-power-bi-custom-visuals"></a>Power BI özel görselleriyle ilgili sorunları giderme

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

Tüm sorularınız, yorumlarınız veya sorunlarınız için özel görseller destek takımına başvurmaktan çekinmeyin: *pbicvsupport@microsoft.com* .

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi edinmek için [Power BI özel görselleri hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#organizational-custom-visuals) bağlantısını ziyaret edin.
