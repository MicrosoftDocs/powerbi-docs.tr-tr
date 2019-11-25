---
title: Power BI Embedded kapasitenizi ölçeklendirme | Microsoft Docs
description: Bu makalede Microsoft Azure'daki bir Power BI Embedded kapasitesini ölçeklendirme adımları anlatılmaktadır.
services: power-bi-embedded
author: KesemSharabi
ms.author: kesharab
editor: ''
tags: ''
ms.service: power-bi-embedded
ms.topic: conceptual
ms.date: 01/31/2019
ms.openlocfilehash: 365f24ec80d58297a852fa3d040c04c8c763eeda
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74265613"
---
# <a name="scale-your-power-bi-embedded-capacity-in-the-azure-portal"></a>Azure portalda Power BI Embedded kapasitenizi ölçeklendirme

Bu makalede Microsoft Azure'daki bir Power BI Embedded kapasitesini ölçeklendirme adımları anlatılmaktadır. Ölçeklendirme, kapasitenizin boyutunu artırmanızı veya azaltmanızı sağlar.

Bu makalede önceden bir Power BI Embedded kapasitesi oluşturduğunuz kabul edilmektedir. Henüz oluşturmadıysanız başlamak için bkz. [Azure portalda Power BI Embedded kapasitesi oluşturma](azure-pbie-create-capacity.md).

> [!NOTE]
> Ölçeklendirme işlemi bir dakika kadar sürebilir. Kapasite bu süre boyunca kullanım dışı olacaktır. Eklenmiş içerikler yüklenemeyebilir.

## <a name="scale-a-capacity"></a>Bir kapasiteyi ölçeklendirme

1. [Azure portalında](https://portal.azure.com/) oturum açın.

2. Kapasitelerinizi görmek için **Tüm hizmetler** > **Power BI Embedded** yolunu izleyin.

    ![Azure portaldaki Tüm hizmetler](media/azure-pbie-scale-capacity/azure-portal-more-services.png)

3. Ölçeklendirmek istediğiniz kapasiteyi seçin.

    ![Azure portalda Power BI Embedded kapasitesi listesi](media/azure-pbie-scale-capacity/azure-portal-capacity-list.png)

4. Kapasitenizin içinde **Ölçeklendirme** bölümündeki **Fiyatlandırma katmanı**'nı seçin.

    ![Ölçeklendirme altındaki Fiyatlandırma katmanı seçeneği](media/azure-pbie-scale-capacity/azure-portal-scale-pricing-tier.png)

    Geçerli fiyatlandırma katmanınızı mavi renkle vurgulanır.

    ![Mavi renkle vurgulanmış geçerli fiyatlandırma katmanı](media/azure-pbie-scale-capacity/azure-portal-current-tier.png)

5. Ölçeği artırmak veya azaltmak için geçmek istediğiniz yeni katmanı seçin. Seçtiğiniz yeni katmanın etrafında mavi renkli kesik çizgi görüntülenir. Ölçeği yeni katmanla değiştirmek için **Seç**'e tıklayın.

    ![Yeni katmanı seçme](media/azure-pbie-scale-capacity/azure-portal-select-new-tier.png)

    Kapasitenizin ölçeklendirilmesi bir-iki dakika sürebilir.

6. Genel bakış sekmesini görüntüleyerek katmanınızı onaylayın. Geçerli fiyatlandırma katmanı listelenir.

    ![Geçerli katmanı onayla](media/azure-pbie-scale-capacity/azure-portal-confirm-tier.png)

## <a name="next-steps"></a>Sonraki adımlar

Kapasitenizi duraklatmak veya başlatmak için bkz. [Azure portalda Power BI Embedded kapasitenizi duraklatma ve başlatma](azure-pbie-pause-start.md).

Uygulamanıza Power BI içeriği eklemeye başlamak için bkz. [Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
