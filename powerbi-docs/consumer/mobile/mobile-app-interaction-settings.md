---
title: Rapor etkileşim ayarlarını yapılandırma
description: Raporlar için varsayılan etkileşim ayarlarını geçersiz kılmayı öğrenin.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 01/21/2020
ms.author: painbar
ms.openlocfilehash: fee89c65328b70e1f312b39fbad75d7148bd92f2
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76542301"
---
# <a name="configure-report-interaction-settings"></a>Rapor etkileşim ayarlarını yapılandırma

## <a name="overview"></a>Genel Bakış

Power BI mobil uygulamasının bir dizi yapılandırılabilir "etkileşim" ayarı vardır. Bu ayarlar verilerinizle kurduğunuz etkileşimi denetlemenize ve Power BI mobil uygulamasındaki bazı öğelerin davranışını tanımlamanıza olanak tanır. Şu anda sağlanan ayarlar
* [Rapor görsellerinde tek dokunma veya iki kez dokunma etkileşimi](#single-tap)
* [Yerleşik veya dinamik rapor alt bilgisi](#docked-report-footer-android-phones) (Android)
* [Düğmeyle başlatılan rapor yenileme veya çekerek yenileme](#report-refresh-android-phones) (Android)

Etkileşim ayarlarına ulaşmak için profil resminize dokunarak [yan paneli](./mobile-apps-home-page.md#header) açın, **Ayarlar**'ı seçin ve **Etkileşim** bölümünü bulun.

![Etkileşim ayarları](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-section.png)

>[!NOTE]
>Yenileme düğmesi ve rapor alt bilgisini yerleşik yapma etkileşim ayarlarının şu anda Rapor Sunucusu raporları üzerinde hiçbir etkisi yoktur. Bu durum Ocak 2020 Rapor Sunucusu sürümünde değiştirilecektir.

## <a name="interaction-settings"></a>Etkileşim ayarları

### <a name="single-tap"></a>Tek dokunma
Power BI mobil uygulamasını indirdiğinizde, tek dokunma etkileşimine ayarlanmış durumda olur. Diğer bir deyişle dilimleyici öğesini seçme, çapraz vurgulama, bir bağlantıya veya düğmeye tıklama gibi herhangi bir eylem gerçekleştirmek için görsele dokunduğunuzda, bu dokunma hem görseli seçer hem de istediğiniz eylemi gerçekleştirir.

İsterseniz tek dokunmalı etkileşimi kapatabilirsiniz. Bir de iki kez dokunmalı etkileşim seçeneğiniz vardır. İki kez dokunmalı etkileşimle, önce görsele dokunarak onu seçer ve sonra yeniden dokunarak istenen eylemi gerçekleştirirsiniz.

### <a name="docked-report-footer-android-phones"></a>Yerleşik rapor alt bilgisi (Android telefonları)

Yerleşik rapor alt bilgisi ayarı, rapor alt bilgisinin raporun alt kısmında yerleşik mi kalacağını (sabit ve her zaman görünür) yoksa rapordaki eylemlerinize (örneğin kaydırma) göre gizlenip yeniden mi görüntüleneceğini belirler.

Android telefonlarında yerleşik rapor alt bilgisi ayarı varsayılan olarak **açıktır**, yani rapor alt bilgisi yerleşiktir ve raporun alt kısmında her zaman görünür. Rapordaki eylemleriniz temelinde görüntülenen ve görüntüden kaldırılan dinamik bir rapor alt bilgisini tercih ediyorsanız, ayarı **kapalı** konuma getirin.

### <a name="report-refresh-android-phones"></a>Rapor yenilemesi (Android telefonları)

Rapor yenileme ayarı, rapor yenilemelerini nasıl başlatacağınızı tanımlar. Raporu yenilemek için tüm rapor üst bilgilerinde bir yenileme düğmesi olmasını veya rapor sayfasında çekerek yenileme eylemini (yukarıdan aşağıya doğru hafifçe çekme) kullanmayı seçebilirsiniz. Aşağıdaki şekilde bu iki alternatif gösterilir. 

![Yenileme düğmesi ve çekerek yenileme](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-refresh-button-versus-pull.png)

Android telefonlarında yenileme düğmesi varsayılan olarak eklenir.

Rapor yenileme ayarını değiştirmek için etkileşim ayarlarında rapor yenileme öğesine gidin. Geçerli ayar gösterilir. Değere dokunarak yeni değeri seçebileceğiniz açılan pencereyi açın.

![Yenilemeyi ayarlama](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-set-refresh.png)

## <a name="remote-configuration"></a>Uzaktan yapılandırma

Etkileşimler bir yönetici tarafından, uygulama yapılandırma dosyasıyla MDM aracı kullanılarak uzaktan da yapılandırılabilir. Bu şekilde kuruluş genelinde veya kuruluştaki belirli kullanıcı grupları için rapor etkileşimi deneyimini standart hale getirmek mümkündür. Ayrıntılar için bkz. [Mobil cihaz yönetimini kullanarak etkileşimi yapılandırma](./mobile-app-configuration.md).


## <a name="next-steps"></a>Sonraki adımlar
* [Raporlarla etkileşim kurma](./mobile-reports-in-the-mobile-apps.md#interact-with-reports)
* [Mobil cihaz yönetimini kullanarak etkileşimi yapılandırma](./mobile-app-configuration.md)
