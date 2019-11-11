---
title: Azure portalda Power BI Embedded kapasitenizi duraklatma ve başlatma | Microsoft Docs
description: Bu makalede Microsoft Azure'daki bir Power BI Embedded kapasitesini duraklatma ve başlatma adımları anlatılmaktadır.
services: power-bi-embedded
author: rkarlin
ms.author: rkarlin
editor: ''
tags: ''
ms.service: power-bi-embedded
ms.topic: conceptual
ms.date: 09/28/2017
ms.openlocfilehash: c851e76a57618ad1b683e1fa56251423b8d6eeb3
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73865012"
---
# <a name="pause-and-start-your-power-bi-embedded-capacity-in-the-azure-portal"></a>Azure portalda Power BI Embedded kapasitenizi duraklatma ve başlatma

Bu makalede Microsoft Azure'daki bir Power BI Embedded kapasitesini duraklatma ve başlatma adımları anlatılmaktadır. Bu makalede önceden bir Power BI Embedded kapasitesi oluşturduğunuz kabul edilmektedir. Henüz oluşturmadıysanız başlamak için bkz. [Azure portalda Power BI Embedded kapasitesi oluşturma](azure-pbie-create-capacity.md).

Azure aboneliğiniz yoksa başlamadan önce [ücretsiz bir hesap](https://azure.microsoft.com/free/) oluşturun.

## <a name="pause-your-capacity"></a>Kapasitenizi duraklatma

Kapasitenizi duraklattığınızda faturalama gerçekleşmez. Kapasitenizi uzun bir süre boyunca kullanmayacaksanız duraklatma çok iyi bir seçenektir. Kapasitenizi duraklatmak için aşağıdaki adımları kullanın.

> [!NOTE]
> Kapasiteyi duraklattığınızda içerikler Power BI hizmetinde kullanım dışı kalabilir. Hizmetin kesintiye uğramasını önlemek için kapasitenizi duraklatmadan önce çalışma alanlarının atamasını kaldırdığınızdan emin olun.

1. [Azure portalında](https://portal.azure.com/) oturum açın.

2. Kapasitelerinizi görmek için **Tüm hizmetler** > **Power BI Embedded** yolunu izleyin.

    ![Azure portaldaki Tüm hizmetler](media/azure-pbie-pause-start/azure-portal-more-services.png)

3. Duraklatmak istediğiniz kapasiteyi seçin.

    ![Azure portalda Power BI Embedded kapasitesi listesi](media/azure-pbie-pause-start/azure-portal-capacity-list.png)

4. Kapasite ayrıntılarında **Duraklat**'ı seçin.

    ![Kapasitenizi duraklatma](media/azure-pbie-pause-start/azure-portal-pause-capacity.png)

5. **Evet**'i seçerek kapasiteyi duraklatmak istediğinizi onaylayın.

    ![Duraklatma onayı](media/azure-pbie-pause-start/azure-portal-confirm-pause.png)

## <a name="start-your-capacity"></a>Kapasitenizi başlatma

Kapasitenizi başlatarak kullanmaya devam edebilirsiniz. Kapasiteyi başlattığınızda faturalandırma da devam eder.

1. [Azure portalında](https://portal.azure.com/) oturum açın.

2. Kapasitelerinizi görmek için **Tüm hizmetler** > **Power BI Embedded** yolunu izleyin.

    ![Azure portaldaki Tüm hizmetler](media/azure-pbie-pause-start/azure-portal-more-services.png)

3. Başlatmak istediğiniz kapasiteyi seçin.

    ![Azure portalda Power BI Embedded kapasitesi listesi](media/azure-pbie-pause-start/azure-portal-capacity-list.png)

4. Kapasite ayrıntılarında **Başlat**'ı seçin.

    ![Kapasitenizi başlatma](media/azure-pbie-pause-start/azure-portal-start-capacity.png)

5. **Evet**'i seçerek kapasiteyi başlatmak istediğinizi onaylayın.

    ![Başlatma onayı](media/azure-pbie-pause-start/azure-portal-confirm-start.png)

Kapasiteyi başlattıktan sonra atanmış içerikler kullanılmaya devam eder.

## <a name="next-steps"></a>Sonraki adımlar

Kapasitenizin ölçeğini büyütmek veya küçültmek isterseniz bkz. [Power BI Embedded kapasitenizi ölçeklendirme](azure-pbie-scale-capacity.md).

Uygulamanıza Power BI içeriği eklemeye başlamak için bkz. [Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)