---
title: Power BI Premium kapasitesini yeniden başlatma
description: Performans sorunlarını gidermek için Power BI Premium kapasitesinin nasıl yeniden başlatılacağını öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: how-to
ms.date: 11/11/2020
LocalizationGroup: Premium
ms.openlocfilehash: da6108927e9d6182c08db68972a5452514eedca7
ms.sourcegitcommit: c33e53e1fab1f29872297524a7b4f5af6c806798
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99532970"
---
# <a name="restart-a-power-bi-premium-capacity"></a>Power BI Premium kapasitesini yeniden başlatma

Power BI yöneticisi olarak Premium kapasiteyi yeniden başlatmanız gerekebilir. Bu makalede kapasiteyi yeniden başlatma işlemi açıklanır, ayrıca yeniden başlatma ve performans hakkındaki çeşitli sorular yanıtlanır.

## <a name="why-does-power-bi-provide-this-option"></a>Power BI bu seçeneği neden sağlıyor?

Power BI kullanıcılara muazzam miktarlardaki veriler üzerinde karmaşık analizler yapma olanağı sunuyor. Ne yazık ki kullanıcılar Power BI hizmetini işlerle, yazdıkları aşırı karmaşık sorgularla, oluşturdukları döngüsel başvurularla ve benzer işlemlerle aşırı yükleyerek performans sorunlarına neden olabiliyor.

Power BI paylaşılan kapasitesi dosya boyutlarına, yenileme zamanlamalarına ve hizmetin diğer yönlerine sınırlar uygulayarak bu tür durumlara karşı bir düzeyde koruma sağlıyor. Buna karşılık Power BI Premium kapasitesinde bu sınırların çoğu yükseltiliyor. Sonuç olarak, hatalı bir DAX ifadesi veya çok karmaşık bir model içeren tek bir rapor önemli performans sorunlarına yol açabiliyor. Rapor işlenirken, kapasitede sağlanan kaynakların tümünü tüketebiliyor. 

Power BI, Premium kapasite kullanıcılarını bu tür sorunlara karşı koruma yöntemini sürekli geliştiriyor. Ayrıca kapasitelerin ne zaman ve neden aşırı yüklendiğini analiz eden araçlar sağlayarak yöneticileri güçlendiriyoruz. Daha fazla bilgi için [kısa eğitim oturumumuza](https://www.youtube.com/watch?v=UgsjMbhi_Bk&feature=youtu.be) ve [uzun eğitim oturumumuza](https://powerbi.tips/2018/07/) bakın. Aynı zamanda, önemli sorunlar çıktığında bunları hafifletebilmeniz de gerekiyor. Bu sorunları hafifletmenin en hızlı yolu, kapasiteyi yeniden başlatmaktır.

> [!NOTE]
> Yakın zamanda Power BI Premium, şu anda önizleme aşamasında olan **Premium 2. Nesil** adlı yeni bir Premium sürümünü kullanıma sundu. Önizleme 2. Nesil kapasiteleri için yeniden başlatma işlemleri gerekmediğinden, bu özellik Premium 2. Nesil’de sunulmaz.
>
> **Gömülü Gen2** kapasiteleri de yeniden başlatma gerektirmez. Power BI Embedded Gen2 geliştirmelerini gözden geçirmek için [Power BI Embedded 2. nesil](../developer/embedded/power-bi-embedded-generation-2.md)bölümüne bakın.

## <a name="is-the-restart-process-safe-will-i-lose-any-data"></a>Yeniden başlatma işlemi güvenli mi? Verileri kaybedecek miyim?

Kapasitenizdeki tüm kaydedilmiş veriler, tanımlar, raporlar ve panolar yeniden başlatma sonrasında olduğu gibi korunur. Bir kapasiteyi yeniden başlattığınızda, çoğu durumda devam eden zamanlanmış ve geçici yenilemeler, yenileme altyapısı tarafından geçici olarak durdurulur. Daha sonra Power BI’da yerleşik olan yenileme yeniden deneme mantığı nedeniyle yeniden başlatılır. Kapasite kullanılabilir hale geldiğinde hizmet, etkilenen yenilemeleri yeniden deneme girişiminde bulunur. Yeniden başlatma işlemi sırasında, kullanıcı arabiriminde yenilemelerin durumu değişmeyebilir. 

Yeniden başlatma işlemi sırasında, kapasiteyle etkileşimde bulunan kullanıcılar, kaydedilmemiş çalışmalarını kaybeder. Yeniden başlatma tamamlandıktan sonra kullanıcıların tarayıcılarını yenilemesi gerekir.

## <a name="how-do-i-restart-a-capacity"></a>Kapasiteye nasıl yeniden başlatabilirim?

Kapasiteyi yeniden başlatmak için aşağıdaki adımları izleyin.

1. Power BI yönetici portalının **Kapasite Ayarları** sekmesinde kapasitenize gidin. 

1. Kapasite URL’nize **CapacityRestart** *özellik bayrağını* ekleyin: `https://app.powerbi.com/admin-portal/capacities/<YourCapacityId>?capacityRestartButton=true`.

1. **Gelişmiş Ayarlar** > **KAPASİTE YENİDEN BAŞLATMA**'nın altında **Kapasiteyi yeniden başlat**'ı seçin.

    ![Kapasiteyi yeniden başlat](media/service-admin-premium-restart/restart-capacity.png)

1. **Kapasite yeniden başlatma** iletişim kutusunda **Evet, kapasiteyi yeniden başlat**'ı seçin.

    ![Yeniden başlatma işlemini onaylama](media/service-admin-premium-restart/confirm-restart.png)

## <a name="how-can-i-prevent-issues-from-happening-in-the-future"></a>Gelecekte sorun çıkmasını nasıl önleyebilirim?

Sorunları önlemenin en iyi yolu kullanıcıları verimli veri modelleme konusunda eğitmektir. Daha fazla bilgi için [eğitim oturumumuza](https://powerbi.tips/2018/07/) bakın.

Ayrıca, altında yatan sorunlara işaret eden eğilimleri saptamak için düzenli aralıklarla [kapasitelerinizi izlemenizi](service-admin-premium-monitor-capacity.md) öneririz. Kapasitelerinizi daha verimli izleyebilmeniz ve yönetebilmeniz için izleme uygulamasının ve diğer araçların düzenli sürümlerini sağlamayı planlıyoruz.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium nedir?](service-premium-what-is.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
