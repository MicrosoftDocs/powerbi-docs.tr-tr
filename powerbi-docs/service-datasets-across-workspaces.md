---
title: Çalışma alanları arasında veri kümelerine giriş (Önizleme)
description: Kuruluş genelindeki kullanıcılarla veri kümesi paylaşmayı öğrenin. Kendi çalışma alanlarında sizin veri kümelerinizi temel alan raporlar oluşturabilirler.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: e086cc89a24760bce0c4a45efd558dc47495bd04
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020774"
---
# <a name="intro-to-datasets-across-workspaces-preview"></a>Çalışma alanları arasında veri kümelerine giriş (Önizleme)

İş zekası, işbirliğine dayalı bir etkinliktir. 'Tek doğru bilgi kaynağı' olabilecek standartlaştırılmış veri kümeleri oluşturmak önemlidir. Ardından bu standartlaştırılmış veri kümelerini keşfetmek ve yeniden kullanmak kritik önem taşır. Kuruluşunuzdaki uzman veri modelleyicileri iyileştirilmiş veri kümeleri oluşturup paylaştığında, rapor oluşturanlar doğru raporlar hazırlamak için bu veri kümelerinden yola çıkabilirler. Bu sayede kuruluşunuzun aldığı kararlar tutarlı verilere dayanır ve sağlıklı bir veri kültürü olur.

![Paylaşılan veri kümesi seçme](media/service-datasets-across-workspaces/power-bi-select-shared-dataset.png)

Power BI’da veri kümesi oluşturucular verilerine kimlerin erişebileceğini [Derleme iznini](service-datasets-build-permissions.md) kullanarak denetleyebilir. Veri kümesi oluşturucular ayrıca başkalarının bulabilmesi için veri kümelerini *onaylayabilir* veya *tanıtabilir*. Bu yolla, rapor yazarları hangi veri kümelerinin kaliteli ve resmi olduğunu bilir ve Power BI'da yazarken her zaman o veri kümelerini kullanır. Kiracı yöneticilerinin [çalışma alanları arasında veri kümesi kullanımını yönetmelerini](service-datasets-admin-across-workspaces.md) sağlayan yeni bir kiracı ayarı vardır.

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

Derleme izin türüyle, bir veri kümesi oluşturucusuysanız kuruluşunuzda kimlerin veri kümelerinizde yeni içerik oluşturabileceğini belirleyebilirsiniz. Oluşturma iznine sahip kişiler, Excel’de Çözümleme, XMLA ve dışarı aktarma aracılığıyla Excel sayfaları gibi Power BI dışındaki bir veri kümesinde de yeni içerik oluşturabilirler. [Oluşturma izni](service-datasets-build-permissions.md) hakkında daha fazla bilgi edinin.

## <a name="promotion-and-certification"></a>Tanıtma ve onaylama

Başkalarının da yararlanabileceği veri kümeleri oluşturuyorsanız [veri kümenizi tanıtarak](service-datasets-promote.md) daha kolay bulunmasını sağlayabilirsiniz. Kuruluşunuzdaki uzmanların [veri kümenizi onaylamalarını](service-datasets-certify.md) da isteyebilirsiniz.

## <a name="licensing"></a>Lisanslama

Paylaşılan veri kümesi özelliklerinde yerleşik olarak bulunan belirli özellikler ve deneyimler, mevcut senaryolarına göre lisanslanır. Örnek:

- Genel olarak, herkes paylaşılan veri kümelerini keşfedebilir ve onlara bağlanabilir. Bu, Premium ile sınırlı bir özellik değildir.
- Pro lisansı olmayan kullanıcılar, rapor yazmaya yönelik çalışma alanlarındaki veri kümelerini yalnızca bu kümeler kullanıcıların kişisel Çalışma Alanım bölümünde veya Premium destekli çalışma alanında bulunuyorsa kullanabilir. Bu lisanslama kısıtlaması, raporları Power BI Desktop veya Power BI hizmetinde yazmalarına bakılmaksızın uygulanır.
- Çalışma alanları arasında raporların kopyalanması için Pro lisansı gerekir.
- Kurumsal içerik paketlerinde istendiği gibi uygulamadan raporları kopyalamak da Pro lisansı gerektirir.
- Veri kümelerini yükseltmek ve onaylamak için bir Pro lisansı gerekir.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

- Bir uygulama yayımcısı olarak, hedef kitlenizin uygulama çalışma alanının dışında bulunan veri kümelerine erişebildiğinden emin olmanız gerekir. Aksi takdirde, kullanıcılar uygulamanızla etkileşime geçerken, raporların veri kümesi erişimi olmadan açılmaması ve pano kutucuklarının kilitli olarak görünmesi gibi sorunlar yaşar. Ayrıca, bu öğenin gezintisindeki ilk öğe veri kümesine erişimi olmayan bir rapor olursa, kullanıcılar uygulamayı açamaz.
- Raporu farklı çalışma alanında bulunan bir veri kümesinin üstünde oluşturabilmeniz için iki uçta da yeni çalışma alanı deneyimi gerekir: Rapor yeni çalışma alanı deneyiminde olmalı ve veri kümesi de yeni çalışma alanı deneyiminde olmalıdır.
- Klasik çalışma alanında veri kümesi bulma deneyimi yalnızca o çalışma alanındaki veri kümelerini gösterir.
- Tasarım gereği, paylaşılan veri kümesini temel alan bir raporda “Web'de yayımla” özelliği çalışmaz.
- Paylaşılan veri kümesine erişen bir çalışma alanının üyesi olan iki kişiden yalnızca biri çalışma alanındaki ilgili veri kümesini görebiliyor olabilir. Yalnızca veri kümesi üzerinde en azından Okuma izni olan kişiler paylaşılan veri kümelerini görebilir. 

## <a name="next-steps"></a>Sonraki adımlar

- [Veri kümelerini tanıtma](service-datasets-promote.md)
- [Veri kümelerini onaylama](service-datasets-certify.md)
- [Çalışma alanları arasında veri kümeleri kullanımını yönetme](service-datasets-admin-across-workspaces.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
