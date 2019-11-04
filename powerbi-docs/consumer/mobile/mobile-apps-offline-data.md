---
title: Power BI mobil uygulamalarında verilerinizi çevrimdışı olarak görüntüleme
description: "Power BI'ı mobil tarayıcı yerine mobil uygulamada görüntülemenin avantajlarından biri hakkında bilgi edinin: Bir ağa bağlı olmasanız bile verilerinizi görebilirsiniz."
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/27/2018
ms.author: mshenhav
ms.openlocfilehash: d0d9b10c24d3d9da60ecf1afde7347f53d20f224
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73059427"
---
# <a name="view-your-data-offline-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında verilerinizi çevrimdışı olarak görüntüleme
Aşağıdakiler cihazlar için geçerlidir:

| ![iPhone](./media/mobile-apps-offline-data/iphone-logo-50-px.png) | ![iPad](./media/mobile-apps-offline-data/ipad-logo-50-px.png) | ![Android telefon](./media/mobile-apps-offline-data/android-phone-logo-50-px.png) | ![Android tablet](./media/mobile-apps-offline-data/android-tablet-logo-50-px.png) | ![Windows 10](./media/mobile-apps-offline-data/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |Windows 10 cihazları |

Power BI'ı mobil tarayıcı yerine mobil uygulamada görüntülemenin avantajlarından biri de ağ bağlantınız bulunmasa bile verilerinizi görebilmenizdir. 

![Ağ yok iletisi](./media/mobile-apps-offline-data/power-bi-iphone-no-network.png)

Varsayılan olarak Power BI, hareket halinde veya dolaşımdayken bile işle ilgili sorularınıza dilediğiniz zaman güncel yanıtlar almanızı sağlamak için verileri sık sık yeniler.

## <a name="data-access-while-youre-offline"></a>Çevrimdışıyken veri erişimi
Çevrimdışıyken, daha önce mobil uygulamadan eriştiğiniz panolara erişebilir ve bunlarla etkileşim kurabilirsiniz.

Ayrıca, daha önce mobil uygulamadan eriştiğiniz Power BI raporlarına da salt okunur erişim elde edersiniz. Raporun tamamını görebilirsiniz ancak rapor üzerinde filtreleme, çapraz filtreleme veya sıralama yapamaz ya da dilimleyici kullanamazsınız.

## <a name="background-data-refresh"></a>Arka planda veri yenileme
Arka planda yenileme; sık kullandığınız panolarınızın yanı sıra son iki hafta içinde görüntülediğiniz panolarınızı ve raporlarınızı Power BI hizmetindeki verilerle (veri kaynağı ile değil) güncelleştirir. Wi-Fi bağlantınız varsa arka planda yenileme, her 2 saatte bir gerçekleştirilir. 3G bağlantısı kullanmanız durumunda ise Power BI, içeriği her 24 saatte bir güncelleştirir.

Örneğin, ağ kullanımını önlemek için arka planda yenileme özelliğini devre dışı bırakabilirsiniz. Cihazınızdaki ayarları kontrol edin.

> [!NOTE]
> Bir iOS cihazında Power BI mobil uygulamasını kullanıyorsanız ve kuruluşunuzda Microsoft Intune MAM yapılandırıldıysa arka planda veri yenileme devre dışıdır. Uygulamaya bir sonraki girişinizde Power BI, web üzerindeki Power BI hizmetinden verileri yeniler.
> 
> [Microsoft Intune ile Power BI mobil uygulamalarını yapılandırma](../../service-admin-mobile-intune.md) hakkında daha fazla bilgi edinin. 
> 
> 

## <a name="offline-indicators"></a>Çevrimdışı göstergeleri
Power BI, çevrimdışı moda girdiğinizi ve çevrimdışı moddan çıktığınızı açık bir şekilde belirten göstergelerin yanı sıra eksik panolara, raporlara ve çevrimdışı olarak kullanılamayan kutucuklara ilişkin göstergeler sunar.

## <a name="limitations"></a>Sınırlamalar
Power BI'ı mobil cihazınızda çevrimdışı bir şekilde kullanırken şu sınırlamalarla karşılaşabilirsiniz:

* Power BI, 250 MB'a kadar veriyi çevrimdışı olarak önbelleğe alabilir.
* Bazı kutucuk türleri için etkin sunucu bağlantısı gerektiğinden bunlar (örneğin, Bing harita kutucukları ve bazı özel kutucuklar) çevrimdışı olarak kullanılamaz.
* Power BI'da bütün halde bulunan Excel çalışma kitapları, çevrimdışı olarak kullanılamaz.
* Bağlantınız varken görüntülediğiniz Reporting Services mobil raporlarını ve KPI'leri çevrimdışı olarak görebilirsiniz. Bunlar, arka planda yenilenmez. Açılışta yenilenirler.
* Power BI mobil uygulamalarında, Power BI Rapor Sunucusu'na kaydedilmiş Power BI Desktop (.pbix) dosyalarını göremezsiniz. 
* Ağ çevrimdışı olduğunda sayfalandırılmış raporlar (RDL) kullanılamaz.

## <a name="next-steps"></a>Sonraki adımlar
Geri bildiriminiz gelecekte neler yapacağımıza karar verme konusunda bize yardımcı olur, bu nedenle Power BI mobil uygulamalarında görmek istediğiniz diğer özellikleri oylamayı unutmayın. 

* [Mobil cihazlar için Power BI uygulamaları](mobile-apps-for-mobile-devices.md)
* Bizi Twitter'da takip edin: @MSPowerBI
* [Power BI Topluluğu](http://community.powerbi.com/)'nda sohbete katılın
* [Power BI nedir?](../../fundamentals/power-bi-overview.md)

