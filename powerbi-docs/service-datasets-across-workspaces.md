---
title: Çalışma alanları arasında veri kümelerine giriş (Önizleme)
description: Kuruluş genelindeki kullanıcılarla veri kümesi paylaşmayı öğrenin. Kendi çalışma alanlarında sizin veri kümelerinizi temel alan raporlar oluşturabilirler.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/15/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 258dd735c5ba97122d9e93f888e65cf2030f01eb
ms.sourcegitcommit: 4d5166944fcc6fe4666cab055ae75e7a0a77866d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69530472"
---
# <a name="intro-to-datasets-across-workspaces-preview"></a>Çalışma alanları arasında veri kümelerine giriş (Önizleme)

İş zekası, işbirliğine dayalı bir etkinliktir. 'Tek doğru bilgi kaynağı' olabilecek standartlaştırılmış veri kümeleri oluşturmak önemlidir. Ardından bu standartlaştırılmış veri kümelerini keşfetmek ve yeniden kullanmak kritik önem taşır. Kuruluşunuzdaki uzman veri modelleyicileri iyileştirilmiş veri kümeleri oluşturup paylaştığında, rapor oluşturanlar doğru raporlar hazırlamak için bu veri kümelerinden yola çıkabilirler. Bu sayede kuruluşunuzun aldığı kararlar tutarlı verilere dayanır ve sağlıklı bir veri kültürü olur.

![Paylaşılan veri kümesi seçme](media/service-datasets-across-workspaces/power-bi-select-shared-dataset.png)

Power BI’da veri kümesi oluşturucular verilerine kimlerin erişebileceğini [Derleme iznini](service-datasets-build-permissions.md#build-permissions-for-shared-datasets) kullanarak denetleyebilir. Veri kümesi oluşturucular ayrıca başkalarının bulabilmesi için veri kümelerini *onaylayabilir* veya *tanıtabilir*. Bu yolla, rapor yazarları hangi veri kümesinin kaliteli ve resmi olduğunu bilir ve Power BI'da yazarken her zaman o veri kümelerini kullanır. Kiracı yöneticilerinin [çalışma alanları arasında veri kümesi kullanımını yönetmelerini](service-datasets-admin-across-workspaces.md) sağlayan yeni bir kiracı ayarı vardır.

## <a name="dataset-sharing-and-the-new-workspace-experience"></a>Veri kümesi paylaşma ve yeni çalışma alanı deneyimi

Farklı çalışma alanlarındaki veri kümelerini temel alan raporlar oluşturmak ve raporları farklı çalışma alanlarına kopyalamak [yeni çalışma alanı deneyimine](service-create-the-new-workspaces.md) sıkıca bağlıdır:

- Hizmette yeni bir çalışma alanı deneyiminden veri kümesi kataloğunu açtığınızda, veri kümesi kataloğu Çalışma Alanım klasörünüzdeki ve diğer yeni çalışma alanı deneyimi çalışma alanlarındaki veri kümelerini gösterir. 
- Klasik çalışma alanından veri kümesi kataloğunu açtığınızda yalnızca o çalışma alanındaki veri kümelerini görebilirsiniz; diğer çalışma alanlarındakileri göremezsiniz.
- Power BI Desktop'ta, veri kümeleri yeni deneyimin çalışma alanlarında bulunduğu sürece Live Connect raporlarını farklı çalışma alanlarına yayımlayabilirsiniz.
- Raporları çalışma alanları arasında kopyalarken hedef çalışma alanının yeni deneyimin çalışma alanı olması gerekir.

## <a name="discover-datasets-preview"></a>Veri kümelerini keşfetme (Önizleme)

Mevcut veri kümesinin üzerinde rapor oluştururken ilk adım Power BI hizmetinde veya Power BI Desktop’ta veri kümesine bağlanmaktır. [Farklı çalışma alanlarındaki veri kümelerini keşfetme (Önizleme)](service-datasets-discover-across-workspaces.md) konusunu okuyun

## <a name="copy-a-report"></a>Rapor kopyalama

Çalışma alanında veya uygulamada hoşunuza giden bir rapor bulduğunuzda kopyasını alıp ihtiyaçlarınıza göre değiştirebilirsiniz. Veri modelini oluşturmaya kafa yormanız gerekmez. Bu model sizin için zaten oluşturulmuştur. Mevcut raporu değiştirmek, en baştan başlamaktan çok daha kolaydır. [Raporları kopyalama](service-datasets-copy-reports.md) hakkında daha fazla bilgi edinin.

## <a name="build-permission-for-datasets"></a>Veri kümeleri için oluşturma izni

Derleme izin türüyle bir veri kümesi oluşturucusuysanız kuruluşunuzda kimlerin veri kümeleriniz üzerinde yeni içerikler derleyebileceğini belirleyebilirsiniz. Derleme iznine sahip kişiler Excel’de Çözümleme, XMLA ve dışarı aktarma aracılığıyla Excel sayfaları gibi Power BI dışındaki bir veri kümesinde de yeni içerik oluşturabilirler. [Oluşturma izni](service-datasets-build-permissions.md#build-permissions-for-shared-datasets) hakkında daha fazla bilgi edinin.

## <a name="promotion-and-certification"></a>Tanıtma ve onaylama

Başkalarının da yararlanabileceği veri kümeleri oluşturuyorsanız [veri kümenizi tanıtarak](service-datasets-promote.md) daha kolay bulunmasını sağlayabilirsiniz. Kuruluşunuzdaki uzmanların [veri kümenizi onaylamalarını](service-datasets-certify.md) da isteyebilirsiniz.

## <a name="licensing"></a>Lisanslama

Paylaşılan veri kümesi özelliklerinde yerleşik olarak bulunan belirli özellikler ve deneyimler, mevcut senaryolarına göre lisanslanır. Örnek:

- Genel olarak, herkes paylaşılan veri kümelerini keşfedebilir ve onlara bağlanabilir. Öte yandan Pro lisansı olmayan kullanıcılar yalnızca kendi kişisel Çalışma Alanım klasöründe yer alan veri kümelerine bağlanabilir.
- Power BI Desktop’ta Pro lisansı olmayan kullanıcılar veri kümelerini yalnızca Çalışma Alanım'dan görebilirler.
- Çalışma alanları arasında raporların kopyalanması için Pro lisansı gerekir.
- Kurumsal içerik paketlerinde istendiği gibi uygulamadan raporları kopyalamak da Pro lisansı gerektirir.
- Veri kümelerini yükseltmek ve onaylamak için bir Pro lisansı gerekir.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

- Raporu farklı çalışma alanında bulunan bir veri kümesinin üstünde oluşturabilmeniz için iki uçta da yeni çalışma alanı deneyimi gerekir: Rapor yeni çalışma alanı deneyiminde olmalı ve veri kümesi de yeni çalışma alanı deneyiminde olmalıdır.
- A Çalışma Alanında B Çalışma Alanındaki bir veri kümesini temel alan rapor oluşturduğunuzu varsayalım. A Çalışma Alanı için bir uygulama oluşturduğunuzda, bu raporu A Çalışma Alanına ekleyebilmek için aynı zamanda B Çalışma Alanının da üyesi olmanız gerekir.
- Klasik çalışma alanında veri kümesi bulma deneyimi yalnızca o çalışma alanındaki veri kümelerini gösterir.
- Uygulamaya paylaşılan veri kümesini temel alan bir rapor eklemek istiyorsanız veri kümesi çalışma alanının üyesi olmanız gerekir. Bu bilinen bir sorundur.
- Paylaşılan veri kümesini temel alan bir raporda “Web'de yayımla” çalışmaz. Bu tasarım gereğidir.
- Paylaşılan veri kümesine erişen bir çalışma alanının üyesi olan iki kişiden yalnızca biri çalışma alanındaki ilgili veri kümesini görebiliyor olabilir. Yalnızca veri kümesi üzerinde en azından Okuma izni olan kişiler paylaşılan veri kümelerini görebilir. 

## <a name="next-steps"></a>Sonraki adımlar

- [Veri kümelerini tanıtma](service-datasets-promote.md)
- [Veri kümelerini onaylama](service-datasets-certify.md)
- [Çalışma alanları arasında veri kümeleri kullanımını yönetme](service-datasets-admin-across-workspaces.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
