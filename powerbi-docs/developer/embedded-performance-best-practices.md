---
title: Performans açısından en iyi Power BI Embedded yöntemleri
description: Bu makalede en iyi tümleşik analiz yöntemlerine yönelik rehberlik sağlanır
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-embedded
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: 025d843158795e7c36a5a278f2022349a9b72ca6
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277170"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Performans açısından en iyi Power BI Embedded yöntemleri

Bu makalede uygulamanızdaki raporları, panoları ve kutucukları daha hızlı işlemeye yönelik öneriler sağlanır

## <a name="embed-parameters"></a>Ekleme parametreleri

Powerbi.embed() yöntemi bir rapor, pano veya kutucuk eklemek için birkaç parametre alır. Bu parametreler performansı etkiler.

### <a name="embed-url"></a>Ekleme URL'si

Ekleme URL'sini kendiniz oluşturmaktan kaçının. Bunun yerine, [Get reports](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Freports%2Fgetreportsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=22lkqRM2w1MQfrM8dooedaPqqIU8PufTq9TT4VDzRo0%3D&reserved=0), [Get dashboards](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgetdashboardsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=nfWRgbSoXVF42Rg%2Ba9491u19uksXp%2FAyz%2Fa%2Ba7%2FCtdA%3D&reserved=0) veya [Get tiles](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgettilesingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256178318&sdata=LgZ27TynNpqQJDrb3aHWGQXIS%2FzichAO9De5M2uhF1Q%3D&reserved=0) API'sini çağırarak Ekleme URL'sini aldığınızdan emin olun. Performans geliştirmeleri için kullanmak üzere URL'ye **_config_** adlı yeni bir parametre ekledik.

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

* Her zaman [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/)'ın en son sürümünü kullanın.

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
