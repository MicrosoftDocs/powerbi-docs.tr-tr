---
title: Şirket içinde ve bulutta veri kaynakları birleştirme ya da ekleme
description: Şirket içi ve bulut veri kaynaklarını birleştirmek veya aynı sorguya eklemek için şirket içi veri ağ geçidini kullanın.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 39f5a01a396e45207777b1a5e58e73808ddf3f88
ms.sourcegitcommit: a58461fe7dfa65c751490b52de5fc73f8e69a17f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68352183"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Şirket içinde ve bulutta veri kaynakları birleştirme ya da ekleme

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Şirket içi veri ağ geçidini kullanarak, şirket içi ve bulut veri kaynaklarını birleştirebilir veya aynı sorguya ekleyebilirsiniz. Bu özellik, ayrı sorgular kullanmak zorunda kalmadan birden fazla kaynaktaki verileri birleştirmek istediğinizde yararlıdır.

>[!NOTE]
>Bu makale, bulut ve şirket içi veri kaynakları tek bir sorguda birleştirilmiş veya eklenmiş veri kümeleri için geçerlidir. Ayrı sorguları içeren (biri şirket içindeki diğeri buluttaki veri kaynağın bağlanan) veri kümeleri için bulut veri kaynağını kullanarak yapılan sorgu, ağ geçidi kullanılarak yürütülmez.

## <a name="prerequisites"></a>Önkoşullar

- Yerel bir bilgisayarda [yüklü ağ geçidi](/data-integration/gateway/service-gateway-install).
- Şirket içi ve bulut veri kaynaklarını birleştiren sorgularla birlikte bir Power BI Desktop dosyası.

>[!NOTE]
>Herhangi bir bulut veri kaynağına erişmek için, ağ geçidinin bu veri kaynaklarına erişimi bulunduğundan emin olmanız gerekir.

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

    Birleştirmelerin güvenli bir şekilde işlendiğinden emin olmak için hem bulut hem de şirket içi veri kaynaklarınıza yönelik gizlilik düzeylerinin uygun biçimde ayarlandığından emin olun.

     ![Veri kümesi ayarları](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. Bulut kimlik bilgileri ayarlandıktan sonra **Şimdi yenile** seçeneğini kullanarak veri kümesini yenileyebilir veya düzenli aralıklarla yenilenecek şekilde zamanlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Ağ geçitleri için veri yenileme hakkında daha fazla bilgi için bkz. [Zamanlanmış yenileme için veri kaynağını kullanma](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).
