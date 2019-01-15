---
title: Şirket içinde ve bulutta veri kaynakları birleştirme ya da ekleme
description: Şirket içi ve bulut veri kaynaklarını birleştirmek veya aynı sorguya eklemek için şirket içi veri ağ geçidini kullanın.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 06/06/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 7b863af882604be8c2c59fd21f26cd8441f9e170
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54272666"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Şirket içinde ve bulutta veri kaynakları birleştirme ya da ekleme

Şirket içi veri ağ geçidini kullanarak, şirket içi ve bulut veri kaynaklarını birleştirebilir veya aynı sorguya ekleyebilirsiniz. Bu özellik, ayrı sorgular kullanmak zorunda kalmadan birden fazla kaynaktaki verileri karma hale getirmek istediğinizde yararlıdır.

## <a name="prerequisites"></a>Önkoşullar

- Yerel bir bilgisayarda [yüklü ağ geçidi](service-gateway-install.md).
- Şirket içi ve bulut veri kaynaklarını birleştiren sorgularla birlikte bir Power BI Desktop dosyası.

1. Power BI hizmetinin sağ üst köşesinde ![Ayarlar dişli simgesi](media/service-gateway-mashup-on-premises-cloud/icon-gear.png) > **Ağ geçitlerini yönet** öğesini seçin.

    ![Ağ geçitlerini yönet](media/service-gateway-mashup-on-premises-cloud/manage-gateways.png)

2. Yapılandırmak istediğiniz ağ geçidini seçin.

3. **Ağ Geçidi Küme Ayarları** altında **Kullanıcıya ait bulut veri kaynaklarının bu ağ geçidi kümesi aracılığıyla yenilenmesine izin ver** > **Uygula**’yı seçin.

    ![Bu ağ geçidi kümesi aracılığıyla yenile](media/service-gateway-mashup-on-premises-cloud/refresh-gateway-cluster.png)

4. Bu ağ geçidi kümesi altında, sorgularınızda kullanılan herhangi bir [şirket içi veri kaynağını](service-gateway-enterprise-manage-scheduled-refresh.md#add-a-data-source) ekleyin. Burada bulut veri kaynaklarını eklemenize gerek yoktur.

5. Şirket içi ve bulut veri kaynaklarını birleştiren sorgularla birlikte Power BI Desktop dosyanızı Power BI hizmetine yükleyin.

6. Yeni veri kümesinin **Veri kümesi ayarları** sayfasında:

   - Şirket içi kaynak için bu veri kaynağı ile ilişkili ağ geçidini seçin.

   - **Veri kaynağı kimlik bilgileri** altında, bulut veri kaynağı kimlik bilgilerini gerektiği gibi düzenleyin.

     ![Veri kümesi ayarları](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. Bulut kimlik bilgileri ayarlandıktan sonra **Şimdi yenile** seçeneğini kullanarak veri kümesini yenileyebilir veya düzenli aralıklarla yenilenecek şekilde zamanlayabilirsiniz.


## <a name="next-steps"></a>Sonraki adımlar

Ağ geçitleri için veri yenileme hakkında daha fazla bilgi için bkz. [Zamanlanmış yenileme için veri kaynağını kullanma](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).