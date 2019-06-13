---
title: Performans açısından en iyi Power BI Embedded yöntemleri
description: Bu makalede en iyi tümleşik analiz yöntemlerine yönelik rehberlik sağlanır
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: d2e4a29b3dd7e36081458ff6ca51b0006a10466f
ms.sourcegitcommit: 81ba3572531cbe95ea0b887b94e91f94050f3129
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66750951"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Performans açısından en iyi Power BI Embedded yöntemleri

Bu makalede uygulamanızdaki raporları, panoları ve kutucukları daha hızlı işlemeye yönelik öneriler sağlanır

## <a name="embed-parameters"></a>Ekleme parametreleri

Powerbi.embed() yöntemi bir rapor, pano veya kutucuk eklemek için birkaç parametre alır. Bu parametreler performansı etkiler.

### <a name="embed-url"></a>Ekleme URL'si

Ekleme URL'sini kendiniz oluşturmaktan kaçının. Bunun yerine, [Get reports](/rest/api/power-bi/reports/getreportsingroup), [Get dashboards](/rest/api/power-bi/dashboards/getdashboardsingroup) veya [Get tiles](/rest/api/power-bi/dashboards/gettilesingroup) API'sini çağırarak Ekleme URL'sini aldığınızdan emin olun. Performans geliştirmeleri için kullanmak üzere URL'ye **_config_** adlı yeni bir parametre ekledik.

### <a name="permissions"></a>İzinler

Raporu **Düzenleme modunda** eklemeyi düşünmüyorsanız, **Görüntüleme** izinleri sağlayın. Bu şekilde, ekleme kodu Düzenleme modu için kullanılan bileşenleri başlatmaz.

### <a name="filters-bookmarks-and-slicers"></a>Filtreler, yer işaretleri ve dilimleyiciler

Genellikle, rapor görselleri önbelleğe alınmış verilerle birlikte kaydedilir. Önbelleğe alınmış veriler, algılanan performansı vermek için kullanılır. Sorgular yürütülürken raporlar önbelleğe alınmış verileri işler. Filtreler, yer işaretleri veya dilimleyiciler sağlanıyorsa, önbelleğe alınmış veriler uygun olmaz. Bu durumda görseller ancak görsel sorgusu çalıştırıldıktan sonra işlenir.

Raporları aynı filtrelerle eklerseniz, yük yapılandırmasında filtre listesinin geçirilmesini önlemek için raporu zaten uygulanmış olan filtrelerle kaydedin.

## <a name="preload"></a>Önceden yükleme

Son kullanıcı performansını geliştirmek için *preload* JavaScript API'sini kullanın.
Powerbi.preload(), daha sonra raporda ekleme amacıyla kullanılacak javascript kodlarını, css dosyalarını ve diğer yapıtları indirir.

Raporu hemen eklemiyorsanız preload çağrısı yapın. Örneğin, bir düğme tıklamasına rapor eklerseniz, preload çağrısını önceki sayfa yüklenirken yapmanız iyi olur. Bu durumda uygulama kullanıcısı düğmeye tıkladığında işleme daha hızlı gerçekleştirilir.

## <a name="measure-performance"></a>Performansı ölçme

Performansını ölçmek için aşağıdakileri kullanın:

1. Yüklendi: raporun başlatılmasına kadar geçen süre (kullanıcı dönen daire görmez).
2. İşlendi: rapor gerçek veriler kullanılarak tam olarak işlenene kadar geçen süre. Rapor yeniden her işlendiğinde (başka bir deyişle filtreler uygulandıktan sonra), İşlendi olayı tetiklenir. Önce raporu ölçmek için, hesaplamaları ilk tetiklenen olayda yaptığınızdan emin olun.

Kullanılabilir olduğunda önbelleğe alınmış veriler işlenir ama bu veriler için henüz bir olayımız yoktur.

## <a name="update-tools-and-sdk-packages"></a>Araçları ve SDK paketlerini güncelleştirme

Araçların ve SDK paketlerinin güncel kalmasını sağlayın.

* Her zaman [Power BI Desktop](https://powerbi.microsoft.com/desktop/)'ın en son sürümünü kullanın.

* [Power BI istemci SDK'sının](https://github.com/Microsoft/PowerBI-JavaScript) en son sürümünü yükleyin. Sürekli iyileştirmeler sağlamaya devam ediyoruz, bu nedenle zaman zaman takip etmeyi unutmayın.

* Yüklenecek paketler:
    * Npm paketi: powerbi-client
    * NuGet paketi: Microsoft.PowerBI.JavaScript

> [!Note]
> Yükleme süresinin temelde raporla ve verilerle ilgili öğelere bağlı olduğunu unutmayın. Bu öğeler arasında görsellerin sayısı, verilerin boyutu, sorguların ve hesaplanan ölçülerin karmaşıklığı sayılabilir. Raporun yükleme süresini geliştirmek için lütfen [en iyi yöntemleri](../power-bi-reports-performance.md) izleyin.

## <a name="next-steps"></a>Sonraki adımlar

* [Rapor performans açısından en iyi Power BI yöntemleri](../power-bi-reports-performance.md)
* [Power BI Embedded sorunlarını giderme](embedded-troubleshoot.md)
* [Power BI Embedded SSS](embedded-faq.md)
