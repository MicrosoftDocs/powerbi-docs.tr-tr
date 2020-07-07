---
title: Desteklenen Python paketlerini öğrenin
description: Power BI’da desteklenen ve desteklenmeyen Python paketleri
author: otarb
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/26/2020
ms.author: otarb
LocalizationGroup: Connect to data
ms.openlocfilehash: b1dc77d2ebf0803430ceeace7e14bfa62a6d2a60
ms.sourcegitcommit: e8b12d97076c1387088841c3404eb7478be9155c
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85785245"
---
# <a name="create-visuals-by-using-python-packages-in-the-power-bi-service"></a>Power BI hizmetinde Python paketlerini kullanarak görsel oluşturma
Power BI hizmetinde görseller oluşturmak için güçlü [Python programlama dilini](https://www.python.org/) kullanabilirsiniz. Birçok Python paketi Power BI hizmetinde, çok daha fazlası ise sürekli desteklenir.

Aşağıdaki bölümde, Power BI’da desteklenen Python paketlerinin alfabetik bir tablosu bulunmaktadır. 

## <a name="request-support-for-a-new-python-package"></a>Yeni bir Python paketi için destek isteme
**Power BI hizmetinde** desteklenen Python paketleri, **Desteklenen Paketler** adlı bir sonraki bölümde yer almaktadır. Söz konusu listede bulunmayan bir Python paketi için destek isteğinde bulunmak isterseniz isteğinizi lütfen [Power BI Fikirleri](https://ideas.powerbi.com) üzerinden gönderin.

## <a name="requirements-and-limitations-of-python-packages"></a>Python paketleri Gereksinimleri ve Sınırlamaları
Python paketlerine yönelik birçok gereksinim ve sınırlama bulunmaktadır:

* Geçerli Python çalışma zamanı: Python 3.7.7.
* Power BI hizmeti, Python paketlerini çoğunlukla GPL-2, GPL-3, MIT+ ve bu tür ücretsiz ve açık kaynaklı yazılım lisanslarıyla destekler.
* Power BI hizmeti, PyPI’da yayımlanan paketleri destekler. Hizmet, kişisel veya özel Python paketlerini desteklemez. Kullanıcılarımıza, kişisel paketlerinin Power BI hizmetinde kullanılması isteğinde bulunmadan önce bu paketlerini PyPI’da kullanılabilir hale getirmeleri önerilir.
* **Power BI Desktop**’taki Python görselleri için, özel Python paketleri dahil olmak üzere tüm paketleri yükleyebilirsiniz.
* Güvenlik ve gizlilik nedenleriyle, World-Wide Web üzerinden istemci-sunucu sorguları sağlayan Python paketleri desteklenmemektedir. Bu tür denemeler yapıldığında ağ engellenir.
* Yeni bir Python paketi eklemeye yönelik onay süreci birçok bağımlılık gerektirir; hizmete yüklenmesi gereken bazı bağımlılıklar desteklenmemektedir.

## <a name="python-packages-that-are-supported-in-power-bi"></a>Power BI’da desteklenen Python paketleri
Aşağıdaki tabloda Power BI'da **desteklenen** paketler gösterilmektedir.


|        Paket        |   Sürüm   |                                   Bağlantı                                   |
|-----------------------|-------------|--------------------------------------------------------------------------|
|matplotlib|3.2.1|https://pypi.org/project/matplotlib|
|numpy|1.18.4|https://pypi.org/project/numpy|
|pandas|1.0.1|https://pypi.org/project/pandas|
|scikit-learn|0.23.0|https://pypi.org/project/scikit-learn|
|scipy|1.4.1|https://pypi.org/project/scipy|
|seaborn|0.10.1|https://pypi.org/project/seaborn|
|statsmodels|0.11.1|https://pypi.org/project/statsmodels|
|xgboost|1.1.0|https://pypi.org/project/xgboost|

## <a name="next-steps"></a>Sonraki adımlar
Power BI’da Python hakkında daha fazla bilgi edinmek için şu makalelere göz atın:

* [Python programlama dilini kullanarak Power BI görselleri oluşturma](desktop-python-visuals.md)
* [Power BI Desktop’ta Python betikleri çalıştırma](desktop-python-scripts.md)
* [Sorgu Düzenleyicisi’nde Python Kullanma](desktop-python-in-query-editor.md)
