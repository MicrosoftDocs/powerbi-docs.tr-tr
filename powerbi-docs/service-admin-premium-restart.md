---
title: Power BI Premium kapasitesini yeniden başlatma
description: Performans sorunlarını gidermek için Power BI Premium kapasitesinin nasıl yeniden başlatılacağını öğrenin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/10/2018
ms.author: mblythe
LocalizationGroup: Premium
ms.openlocfilehash: f27bc96fc1bea9ff4720d320bda7b448687739a8
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282207"
---
# <a name="restart-a-power-bi-premium-capacity"></a>Power BI Premium kapasitesini yeniden başlatma

Power BI yöneticisi olarak Premium kapasiteyi yeniden başlatmanız gerekebilir. Bu makalede kapasiteyi yeniden başlatma işlemi açıklanır, ayrıca yeniden başlatma ve performans hakkındaki çeşitli sorular yanıtlanır.

## <a name="why-does-power-bi-provide-this-option"></a>Power BI bu seçeneği neden sağlıyor?

Power BI kullanıcılara muazzam miktarlardaki veriler üzerinde karmaşık analizler yapma olanağı sunuyor. Ne yazık ki kullanıcılar Power BI hizmetini işlerle, yazdıkları aşırı karmaşık sorgularla, oluşturdukları döngüsel başvurularla ve benzer işlemlerle aşırı yükleyerek performans sorunlarına neden olabiliyor.

Power BI paylaşılan kapasitesi dosya boyutlarına, yenileme zamanlamalarına ve hizmetin diğer yönlerine sınırlar uygulayarak bu tür durumlara karşı bir düzeyde koruma sağlıyor. Buna karşılık Power BI Premium kapasitesinde bu sınırların çoğu yükseltiliyor. Sonuç olarak, hatalı bir DAX ifadesi veya çok karmaşık bir model içeren tek bir rapor önemli performans sorunlarına yol açabiliyor. Rapor işlenirken, kapasitede sağlanan kaynakların tümünü tüketebiliyor. 

Power BI, Premium kapasite kullanıcılarını bu tür sorunlara karşı koruma yöntemini sürekli geliştiriyor. Ayrıca kapasitelerin ne zaman ve neden aşırı yüklendiğini analiz eden araçlar sağlayarak yöneticileri güçlendiriyoruz. Daha fazla bilgi için [kısa eğitim oturumumuza](https://www.youtube.com/watch?v=UgsjMbhi_Bk&feature=youtu.be) ve [uzun eğitim oturumumuza](https://www.microsoft.com/businessapplicationssummit/video/BAS2018-2174) bakın. Aynı zamanda, önemli sorunlar çıktığında bunları hafifletebilmeniz de gerekiyor. Bu sorunları hafifletmenin en hızlı yolu, kapasiteyi yeniden başlatmaktır.

## <a name="is-the-restart-process-safe-will-i-lose-any-data"></a>Yeniden başlatma işlemi güvenli mi? Verileri kaybedecek miyim?

Kapasitenizdeki tüm kaydedilmiş veriler, tanımlar, raporlar ve panolar yeniden başlatma sonrasında olduğu gibi korunur. Kapasiteyi yeniden başlattığınızda, devam eden tüm zamanlanmış ve zamanlanmamış yenilemeler durdurulur. Kapasite kullanılabilir duruma geldiğinde yenilemeler yeniden başlatılır. Kapasiteyle etkileşimli çalışan kullanıcılar kaydedilmemiş çalışmalarını kaybeder. Yeniden başlatma tamamlandıktan sonra tarayıcılarını yenilemeleri gerekir.

## <a name="how-do-i-restart-a-capacity"></a>Kapasiteye nasıl yeniden başlatabilirim?

Kapasiteyi yeniden başlatmak için aşağıdaki adımları izleyin.

1. Power BI yönetici portalının **Kapasite Ayarları** sekmesinde kapasitenize gidin. 

1. Kapasite URL'nize **CapacityRestart** *özellik bayrağını* ekleyin: https://app.powerbi.com/admin-portal/capacities/<YourCapacityId>?capacityRestartButton=true.

1. **Gelişmiş Ayarlar** > **KAPASİTE YENİDEN BAŞLATMA**'nın altında **Kapasiteyi yeniden başlat**'ı seçin.

    ![Kapasiteyi yeniden başlat](media/service-admin-premium-restart/restart-capacity.png)

1. **Kapasite yeniden başlatma** iletişim kutusunda **Evet, kapasiteyi yeniden başlat**'ı seçin.

    ![Yeniden başlatma işlemini onaylama](media/service-admin-premium-restart/confirm-restart.png)

## <a name="how-can-i-prevent-issues-from-happening-in-the-future"></a>Gelecekte sorun çıkmasını nasıl önleyebilirim?

Sorunları önlemenin en iyi yolu kullanıcıları verimli veri modelleme konusunda eğitmektir. Daha fazla bilgi için [eğitim oturumumuza](https://www.microsoft.com/businessapplicationssummit/video/BAS2018-2170) bakın.

Ayrıca, altında yatan sorunlara işaret eden eğilimleri saptamak için düzenli aralıklarla [kapasitelerinizi izlemenizi](service-admin-premium-monitor-capacity.md) öneririz. Kapasitelerinizi daha verimli izleyebilmeniz ve yönetebilmeniz için izleme uygulamasının ve diğer araçların düzenli sürümlerini sağlamayı planlıyoruz.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium nedir?](service-premium.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)