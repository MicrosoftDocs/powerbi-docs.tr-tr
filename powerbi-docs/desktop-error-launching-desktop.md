---
title: "Power BI Desktop'ı başlatma ile ilgili sorunları giderme"
description: "Power BI Desktop'ı başlatma ile ilgili sorunları giderme"
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 6d5e4592d1bf041672f89dd38f03ddc6ff196735
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Power BI Desktop'ın çalışmamasına neden olan sorunları giderme
**Power BI Desktop**'ta eski **Power BI şirket içi veri ağ geçidi** sürümlerini yüklemiş ve çalıştırıyor olan kullanıcılar, Power BI şirket içi veri ağ geçidinin yerel makinedeki adlandırılmış kanallara uyguladığı yönetimsel ilke kısıtlamaları nedeniyle Power BI Desktop uygulamasını çalıştıramayabilir. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Şirket içi veri ağ geçidi ve Power BI Desktop ile ilgili sorunları giderme
Şirket içi veri ağ geçidiyle ilgili sorunları gidermek ve Power BI Desktop'ın açılmasını sağlamak için kullanabileceğiniz üç seçenek vardır:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>1. Çözüm: Power BI şirket içi veri ağ geçidinin en son sürümünü yükleyin
Power BI şirket içi veri ağ geçidinin en son sürümü yerel makinede adlandırılmış kanal kısıtlaması gerçekleştirmez ve Power BI Desktop uygulamasının düzgün şekilde çalışmasını sağlar. Power BI şirket içi veri ağ geçidini kullanmaya devam etmeniz gerekiyorsa sizin için önerilen çözüm budur. Power BI şirket içi veri ağ geçidinin en son sürümünü [buradan](https://go.microsoft.com/fwlink/?LinkId=698863) indirebilirsiniz. Bunun yükleme dosyasının doğrudan bağlantısı olduğunu unutmayın.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>2. Çözüm: Power BI şirket içi veri ağ geçidi Windows hizmetini kaldırın ve ya durdurun
Power BI şirket içi veri ağ geçidine ihtiyacınız kalmadıysa yüklemesini kaldırabilir veya Power BI şirket içi veri ağ geçidi Windows hizmetini durdurabilirsiniz. Bu durumda ilke kısıtlaması kaldırılır ve Power BI Desktop uygulaması çalıştırılabilir.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>3. Çözüm: Power BI Desktop uygulamasını yönetici ayrıcalıklarıyla çalıştırın
Alternatif olarak, Power BI Desktop uygulamasını yönetici olarak çalıştırabilir, başarıyla açılmasını sağlayabilirsiniz. Yine de bu makalenin önceki bölümlerinde anlatılan şekilde Power BI şirket içi veri ağ geçidinin en son sürümünü yüklemeniz önerilir.

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Diğer Power BI Desktop başlatma sorunlarıyla ilgili yardım
**Power BI Desktop** ile ilgili mümkün olduğu kadar çok sayıda sorunu ele almak için elimizden geleni yapıyoruz. Müşterileri etkiliyor olabilecek sorunları düzenli olarak kontrol edip makalelerimizde bu sorunlara yer veriyoruz.

**Power BI Desktop** uygulamasını başlatma sorunları şirket içi veri ağ geçidiyle ilgili değilse veya yukarıdaki adımlar sorunu gidermediyse sorununuzun tanımlanması ve çözülmesi için [Power BI destek ekibine](https://support.powerbi.com) (https://support.powerbi.com) destek çağrısı gönderebilirsiniz.

İleride karşılaşabileceğiniz diğer **Power BI Desktop** sorunları için (hiç olmayacağını veya az sayıda olacağını umuyoruz) sorunu daha ayrıntılı bir şekilde incelemek ve tanımlamak için izleme yapmak ve günlük dosyalarını toplamak yararlı olabilir. İzlemeyi açmak için **Dosya > Seçenekler ve ayarlar > Seçenekler** yolunu izleyip **Tanılama**'ı seçin ve *Tanılama Seçenekleri*'nin altındaki **İzlemeyi etkinleştir** seçeneğini işaretleyin. Bu seçeneği belirlemek için **Power BI Desktop** uygulamasının açık olması gerektiğinin farkındayız ve bu işlevin ileride ortaya çıkabilecek **Power BI Desktop** uygulamasını başlatma sorunları konusunda faydalı olacağını düşünüyoruz.

