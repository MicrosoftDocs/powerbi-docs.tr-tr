---
title: Çalışma alanı veri akışı ayarlarını yapılandırma
description: Power BI’da bir uygulama çalışma alanını, veri akışı tanımını ve veri dosyalarını Azure Data Lake Storage 2. Nesil içinde depolayacak şekilde yapılandırın
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/10/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 96b6e1a8a92b19181463de404967625b37418582
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291959"
---
# <a name="configure-workspace-dataflow-settings-preview"></a>Çalışma alanı veri akışı ayarlarını yapılandırma (Önizleme)

Power BI ve veri akışları ile, bir çalışma alanının veri akışı tanım dosyasını ve veri dosyalarını Azure Data Lake Storage 2. Nesil hesabınızda depolayabilirsiniz. Çalışma alanı yöneticileri, Power BI’ı bunu yapacak şekilde yapılandırabilir ve bu makalede, gerekli adımlar için size yol gösterilmektedir. 

Bir çalışma alanının veri akışı depolama konumunu yapılandırabilmeniz için önce şirketinizin genel yöneticisinin, kuruluşunuzun depolama hesabını Power BI’a bağlaması ve o depolama hesabına yönelik depolama atama izinlerini etkinleştirmesi gerekir. * [Azure Data Lake Storage 2. Nesil'i veri akışı depolamasına bağlama (Önizleme)](service-dataflows-connect-azure-data-lake-storage-gen2.md) 

Çalışma alanı veri akışı depolama ayarlarını yapılandırmanın iki yolu vardır: 

* Çalışma alanı oluşturma sırasında
* Mevcut bir çalışma alanını düzenleme

Aşağıdaki bölümlerde her birine göz atacağız. 

> [!IMPORTANT]
> Yalnızca çalışma alanı herhangi bir veri akışı içermiyorsa çalışma alanı veri akışı depolama ayarı değiştirilebilir. Bu özellik ayrıca, yalnızca yeni çalışma alanı deneyiminde de mevcuttur. [Power BI’da yeni çalışma alanları (önizleme) oluşturma](service-create-the-new-workspaces.md) makalesinde yeni çalışma alanı hakkında daha fazla bilgi edinebilirsiniz.

## <a name="create-a-new-workspace-configure-its-dataflow-storage"></a>Yeni bir çalışma alanı oluşturma, veri akışı depolamasını yapılandırma

Power BI hizmetinde yeni bir uygulama çalışma alanı oluşturmak için **Çalışma Alanları > Uygulama çalışma alanı oluştur** seçeneğini belirleyin.

![Yeni çalışma alanı ekleme](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_01.jpg)

Uygulama çalışma alanı oluştur iletişim kutusunda, **Geliştirilmiş çalışma alanlarını önizle** başlıklı sarı bir kutu görüntülenebilir. Bu alanda **Şimdi deneyin**’i seçin.

![Geliştirilmiş çalışma alanlarını önizle](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_02.jpg)

Görüntülenen iletişim kutusunda yeni çalışma alanınıza benzersiz bir ad verebilirsiniz. Gelişmiş ayarlar yapmanız gerektiğinden henüz **Kaydet**’i seçmeyin.

![Yeni çalışma alanınızı adlandırma](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_03.jpg)

Daha sonra, **Uygulama çalışma alanı oluştur** iletişim kutusunun **Gelişmiş** alanını genişletin; burada **Veri akışı depolama (önizleme)** ayarını etkinleştirebilirsiniz.

![Yeni çalışma alanı için gelişmiş ayarlar](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_04.jpg)

Yeni çalışma alanınızı oluşturmak için **Kaydet**’i seçin. Bu çalışma alanı alanında oluşturulan yeni veri akışları artık tanım dosyasını (Model.json dosyasını) ve verilerini kuruluşunuzun Azure Data Lake Storage 2. Nesil hesabında depolar. 

> [!NOTE]
> Veri akışları işlevselliği önizleme aşamasındadır ve genel kullanıma sunulmadan önce değiştirilip güncelleştirilebilir.

## <a name="update-dataflow-storage-for-an-existing-workspace"></a>Mevcut bir çalışma alanı için veri akışı depolamayı güncelleştirme

Yeni bir çalışma alanı oluşturmaya alternatif olarak, tanım dosyasını ve verileri kuruluşunuzun Azure Data Lake Storage 2. Nesil hesabında depolamak için mevcut bir çalışma alanını güncelleştirebilirsiniz. Yalnızca çalışma alanı önceden bir veri akışı içermiyorsa veri akışı depolama ayarının değiştirilebileceğini unutmayın.

Bir uygulama çalışma alanını düzenlemek için üç nokta **(...)** simgesini ve **Çalışma alanını düzenle**’yi seçin. 

![Çalışma alanını düzenle](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_05.jpg)

Görüntülenen **Çalışma alanını düzenle** penceresinde, **Gelişmiş**’i genişletin ve sonra **Veri akışı depolama (önizleme)** ayarını **Açık** durumuna getirin. 

![Veri akışı depolama Açık](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_06.jpg)

Daha sonra **Kaydet**’i seçin, böylece o çalışma alanında oluşturulan yeni veri akışları, tanım dosyasını ve verilerini kuruluşunuzun Azure Data Lake Storage 2. Nesil hesabında depolar.


## <a name="get-the-uri-of-stored-dataflow-files"></a>Depolanan veri akışı dosyalarının URI’sini alma

Kuruluşunuzun Azure Data Lake Storage 2. Nesil hesabına atanan çalışma alanında bir veri akışı oluşturduktan sonra bunun tanım ve veri dosyalarına doğrudan erişebilirsiniz. Konumları **Veri akışı ayarları** sayfasında mevcuttur. Bu sayfaya ulaşmak için şu adımları izleyin:

Çalışma alanında **Veri Akışları** bölümünde listelenen bir veri akışının yanındaki üç nokta **(...)** simgesini seçin. Görüntülenen menüde **Ayarlar**’ı seçin.

![Veri akışı dosyalarının URI’sini alma](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_07.jpg)

Görüntülenen bilgilerde veri akışının CDM klasörü konumu, aşağıdaki görüntüde gösterildiği gibi **Veri Akışı Depolama konumu** altında görüntülenir.

![Veri akışı dosyalarının konumu](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_08.jpg)

> [!NOTE]
> Power BI, veri akışı dosyalarının depolandığı CDM klasörüne yönelik okuyucu izinleri ile veri akışı sahibini yapılandırır. Diğer kişi veya hizmetlere, veri akışı depolama konumuna erişme izni verilmesi için depolama hesabı sahibinin Azure’da erişim izni vermesi gerekir.



## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Veri akışı depolama, Azure Data Lake Storage 2. Nesil’de olduğunda, belirli veri akışı özellikleri desteklenmez: 

Power BI Pro, Premium ve Embedded çalışma alanları:
* **Bağlantılı varlıklar** özelliği yalnızca aynı depolama hesabında bulunan çalışma alanları arasında desteklenir
* Çalışma alanı izinleri, Azure Data Lake Storage 2. Nesil’de depolanan veri akışları için geçerli değildir; yalnızca veri akışının sahibi buna erişebilir.
* Aksi takdirde, tüm veri hazırlığı özellikleri, Power BI depolamada depolanan veri akışları için de aynıdır


Aşağıdaki listede açıklandığı gibi, dikkate alınacak bazı ek unsurlar da vardır:

* Bir veri akışı depolama konumu yapılandırıldıktan sonra değiştirilemez.
* Yalnızca Azure Data Lake Storage 2. Nesil’de depolanan bir veri akışının sahibi onun verilerine erişebilir.
* Power BI Paylaşılan kapasitelerinde şirket içi veri kaynakları, kuruluşunuzun Azure Data Lake Storage 2. Nesil hesabında depolanan veri akışlarında desteklenmez.

**Power BI Desktop** müşterileri, veri akışının sahibi olmadığı sürece, Azure Data Lake Storage 2. Nesil hesabında depolanan veri akışlarına erişemez. Aşağıdaki durumu dikkate alın:

1.  Ayşe yeni bir uygulama çalışma alanı oluşturur ve veri akışları, kuruluşun veri gölünde depolanacak şekilde bu çalışma alanını yapılandırır.
2.  Ayşe’nin oluşturduğu çalışma alanının da üyesi olan Berk, Ayşe’nin oluşturduğu veri akışından veri almak için Power BI Desktop ve veri akışı bağlayıcısını kullanmak ister.
3.  Berk, veri gölünde veri akışının CDM klasörüne yetkili bir kullanıcı olarak eklenmediğinden bir hata alır.

    ![Veri akışını kullanma girişimi sırasında hata oluştu](media/service-dataflows-configure-workspace-storage-settings/dataflow-storage-settings_08.jpg)


## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, veri akışları için çalışma alanı depolamanın nasıl yapılandırılacağına ilişkin yönergeler sağlanmıştır. Ek bilgi için aşağıdaki makalelere göz atın:

Veri akışları, CDM ve Azure Data Lake Storage 2. Nesil hakkında daha fazla bilgi için aşağıdaki makalelere göz atın:

* [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md)
* [Power BI’a veri akışı olarak bir CDM klasörü ekleme (Önizleme)](service-dataflows-add-cdm-folder.md)
* [Azure Data Lake Storage 2. Nesil'i veri akışı depolamasına bağlama (Önizleme)](service-dataflows-connect-azure-data-lake-storage-gen2.md)

Genel veri akışları hakkında bilgi için şu makalelere göz atın:

* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Power BI Premium’da hesaplanan varlıkları kullanma (Önizleme)](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma (Önizleme)](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları (Önizleme)](service-dataflows-developer-resources.md)

Azure depolama hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:

* [Azure Depolama güvenlik kılavuzu](https://docs.microsoft.com/azure/storage/common/storage-security-guide)
* [Azure Veri Hizmetleri’nden github örneklerini kullanmaya başlama](https://aka.ms/cdmadstutorial)

Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:

* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)
* [CDM klasörleri](https://go.microsoft.com/fwlink/?linkid=2045304)
* [CDM model dosyası tanımı](https://go.microsoft.com/fwlink/?linkid=2045521)

Ayrıca her zaman [Power BI Topluluğuna soru sormayı](http://community.powerbi.com/) deneyebilirsiniz.
