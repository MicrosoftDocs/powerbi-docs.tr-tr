---
title: Power BI Desktop'ta Power BI veri akışlarıyla oluşturulan verilere bağlanma (Beta)
description: Power BI Desktop'ta veri akışlarına kolayca bağlanın ve bu akışları kullanın
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f1d782aa7409dce43d960956406e996cc7951a57
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73876464"
---
# <a name="connect-to-data-created-by-power-bi-dataflows-in-power-bi-desktop-beta"></a>Power BI Desktop'ta Power BI veri akışlarıyla oluşturulan verilere bağlanma (Beta)
Tıpkı Power BI Desktop'taki diğer veri kaynaklarında olduğu gibi **Power BI Desktop**'ta **Power BI veri akışları** tarafından oluşturulan verilere bağlanabilirsiniz.

![Veri akışlarına bağlanma](media/desktop-connect-dataflows/connect-dataflows_01.png)

**Power BI veri akışları (Beta)** bağlayıcısı, Power BI hizmetinde veri akışları tarafından oluşturulan varlıklara bağlanmanızı sağlar. 

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

**Power BI veri akışları bağlayıcısının** bu Beta sürümünü kullanmak için **Power BI Desktop** uygulamasının son sürümünü çalıştırıyor olmanız gerekir. En son sürüme sahip olduğunuzdan emin olmak için [Power BI Desktop](desktop-get-the-desktop.md) uygulamasını yeniden indirip bilgisayarınıza yükleyebilirsiniz.  

> [!NOTE]
> Power BI veri akışları bağlayıcısının önceki sürümünde bir .MEZ dosyası indirip bir klasöre yerleştirmeniz gerekiyordu. Geçerli **Power BI Desktop** sürümleri ise Power BI veri akışlarını bağlayıcısını içerdiği için dosya artık gerekli değildir ve bağlayıcının dahil edilen sürümüyle çakışmalara neden olmaz. .MEZ dosyasını klasöre el ile yerleştirdiyseniz, çakışmaları önlemek için indirilen o .MEZ dosyasını **Belgeler > Power BI Desktop > Özel bağlayıcılar** klasöründen silmeniz *zorunludur*. 

## <a name="desktop-performance"></a>Masaüstü performansı
**Power BI Desktop**, yüklü olduğu bilgisayarda yerel olarak çalışır. Veri akışlarının veri alımı performansı çeşitli faktörler tarafından belirlenir. Bu faktörler veri boyutu, bilgisayarınızın CPU ve RAM boyutu, ağ bant genişliği, veri merkezi ile mesafe ve diğer faktörlerdir.

Veri akışları için veri alım performansını artırabilirsiniz. Örneğin, alınan veri boyutu **Power BI Desktop**’ın bilgisayarınızda yönetmesi için çok büyükse, veri akışlarının içindeki bağlantılı ve hesaplanan varlıkları kullanarak verileri toplayabilir (veri akışları içinde) ve yalnızca önceden hazırlanmış, toplu verileri alabilirsiniz. Bu şekilde, büyük verilerin işlenmesi çalışan **Power BI Desktop** örneğinizde yerel olarak gerçekleştirilmek yerine veri akışlarında çevrimiçi olarak gerçekleştirilir. Bu yaklaşım, Power BI Desktop'ın daha küçük miktarlarda veri almasına olanak tanır ve veri akışlarıyla hızlı duyarlı ve hızlı bir deneyim sağlar.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Çoğu veri akışı, Power BI hizmet kiracısında yer alır. Ancak **Power BI Desktop** kullanıcıları, veri akışının sahibi olmadığı veya veri akışının CDM klasörüne yönelik açıkça yetkilendirilmediği sürece, Azure Data Lake Storage 2. Nesil hesabında depolanan veri akışlarına erişemez. Aşağıdaki durumu dikkate alın:

1.  Ayşe yeni bir çalışma alanı oluşturuyor ve veri akışları, kuruluşun veri gölünde depolanacak şekilde bu çalışma alanını yapılandırıyor.
2.  Ayşe’nin oluşturduğu çalışma alanının da üyesi olan Berk, Ayşe’nin oluşturduğu veri akışından veri almak için Power BI Desktop ve veri akışı bağlayıcısını kullanmak ister.
3.  Berk, veri gölünde veri akışının CDM klasörüne yetkili bir kullanıcı olarak eklenmediği için oluşan bir hata alır.

    ![Veri akışını kullanma girişimi sırasında hata oluştu](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_08.jpg)

Bu sorunu çözmek için Berk’e, CDM Klasörü ve dosyaları için okuyucu izinleri verilmelidir. [Bu makalede](https://go.microsoft.com/fwlink/?linkid=2029121) CDM Klasörü için nasıl erişim izni verileceği hakkında daha fazla bilgi edinebilirsiniz.




## <a name="next-steps"></a>Sonraki adımlar
Power BI veri akışları ile pek çok ilgi çekici işlem yapabilirsiniz. Daha fazla bilgi için aşağıdaki kaynaklara göz atın:

* [Veri akışları ile self servis veri hazırlığı](service-dataflows-overview.md)
* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Power BI Premium’da hesaplanan varlıkları kullanma (Önizleme)](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma (Önizleme)](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları (Önizleme)](service-dataflows-developer-resources.md)

Azure Data Lake Storage 2. Nesil ile tümleştirme hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

* [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md)
* [Çalışma alanı veri akışı ayarlarını yapılandırma (Önizleme)](service-dataflows-configure-workspace-storage-settings.md)
* [Power BI’a veri akışı olarak bir CDM klasörü ekleme (Önizleme)](service-dataflows-add-cdm-folder.md)
* [Azure Data Lake Storage 2. Nesil'i veri akışı depolamasına bağlama (Önizleme)](service-dataflows-connect-azure-data-lake-storage-gen2.md)

Ayrıca **Power BI Desktop** hakkında yararlı bulabileceğiniz makaleler vardır:

* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   

