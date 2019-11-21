---
title: Veri akışı depolaması için Azure Data Lake Storage 2. Nesil’i Power BI’a bağlamayı öğrenin
description: Azure Data Lake Storage 2. Nesil kullanarak veri akışlarına kendi verilerinizi getirme
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: c48ae0913d0096546c23d22d3e4596fdb21aef82
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73872730"
---
# <a name="connect-azure-data-lake-storage-gen2-for-dataflow-storage-preview"></a>Azure Data Lake Storage 2. Nesil'i veri akışı depolamasına bağlama (Önizleme)

Veri akışlarını kuruluşunuzun Azure Data Lake Storage 2. Nesil hesabında depolayacak şekilde depolamak için Power BI çalışma alanlarını yapılandırabilirsiniz. Bu makalede, bunu yapmak için gerekli genel adımlar açıklanmakta ve bu süreçteki en iyi uygulamalar ve yönergeler sağlanmaktadır. Çalışma alanlarını, veri akışı tanımlarını ve veri dosyalarını veri gölünüzde depolayacak şekilde yapılandırmanın bazı avantajları vardır. Bu avantajlardan bazıları şunlardır:

* Azure Data Lake Storage 2. Nesil, veriler için büyük ölçüde ölçeklenebilir depolama olanağı sağlar
* [GitHub samples from Azure Data Services](https://aka.ms/cdmadstutorial) içinde gösterildiği gibi Azure Verileri ve yapay zeka (AI) hizmetlerinden yararlanmak için BT departmanınızın geliştiricileri tarafından veri akışı verileri ve tanım dosyaları kullanılabilir
* Kuruluşunuzdaki geliştiricilerin,veri akışları ve Azure için geliştirici kaynaklarını kullanarak veri akışı verilerini iç uygulamalarda ve iş kolu çözümlerinde tümleştirmesine olanak sağlar

Veri akışları için Azure Data Lake Storage 2. Nesil’i kullanmak için aşağıdakiler gerekir:

* **Power BI kiracısı**: Azure Active Directory (AAD) kiracınızdaki hesaplardan en az birinin Power BI hizmetine kaydolmuş olması gerekir
* **Genel Yönetici hesabı**: Veri akışı tanımını ve verileri Azure Data Lake Storage 2. Nesil hesabınızda depolamak amacıyla Power BI’a bağlanmak ve Power BI’ı yapılandırmak için bu hesap gerekir
* **Bir Azure aboneliğine** -Azure Data Lake depolama Gen2 kullanmak için bir Azure aboneliği gerekir
* **Kaynak grubu**: Sahip olduğunuz bir kaynak grubunu kullanabilir veya yeni bir tane oluşturabilirsiniz
* **Data Lake Storage 2. Nesil özelliği etkin olan bir Azure Depolama hesabı** 

> [!TIP]
> Azure aboneliğiniz yoksa başlamadan önce [ücretsiz bir hesap](https://azure.microsoft.com/free/) oluşturun.

> [!WARNING]
> Bir veri akışı depolama konumu yapılandırıldıktan sonra değiştirilemez. Dikkate alınması gereken diğer önemli öğeler için bu makalenin sonunda yer alan [konular ve sınırlamalar](#considerations-and-limitations) bölümüne bakın.

## <a name="prepare-your-azure-data-lake-storage-gen2-for-power-bi"></a>Power BI için Azure Data Lake Storage 2. Nesil hesabınızı hazırlama

Azure Data Lake Storage 2. Nesil hesabıyla Power BI’ı yapılandırabilmeniz için önce bir depolama hesabı oluşturup yapılandırmanız gerekir. Power BI için gereksinimlere göz atalım:

1. Depolama hesabı, Power BI kiracınızla aynı AAD kiracısında oluşturulmalıdır.
2. Depolama hesabı, Power BI kiracınızla aynı bölgede oluşturulmalıdır. Power BI kiracınızın bulunduğu yeri belirlemek için [Power BI kiracım nerede bulunur?](service-admin-where-is-my-tenant-located.md) makalesine bakın.
3. Depolama hesabı için *Hiyerarşik Ad Alanı* özelliği etkinleştirilmiş olmalıdır.
4. Power BI hizmetine, depolama hesabında bir *Okuyucu* rolü verilmelidir.
5. **powerbi** adlı bir Dosya sistemi oluşturulmalıdır.
6. Power BI hizmetleri, oluşturduğunuz **powerbi** dosya sistemi için yetkilendirilmiş olmalıdır.

Aşağıdaki bölümlerde, Azure Data Lake Storage 2. Nesil hesabınızı ayrıntılı şekilde yapılandırmak için gerekli adımlar açıklanmaktadır.

### <a name="create-the-storage-account"></a>Depolama hesabı oluşturma

[Azure Data Lake Storage 2. Nesil depolama hesabı oluştur](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account) makalesindeki adımları izleyin.

1. Power BI kiracınızla aynı konumu seçtiğinizden ve depolama alanınızı **StorageV2 (general purpose v2)** olarak ayarladığınızdan emin olun
2. Hiyerarşik ad alanı özelliğini etkinleştirdiğinizden emin olun
3. Çoğaltma ayarının **Read-access geo-redundant storage (RA-GRS)** olarak belirlenmesi önerilir

### <a name="grant-the-power-bi-service-a-reader-role"></a>Power BI hizmetine okuyucu rolü verme

Daha sonra Power BI hizmetine, oluşturduğunuz depolama hesabında okuyucu rolü vermeniz gerekir. Bu yerleşik bir roldür, bu nedenle adımlar basittir. 

[Yerleşik RBAC rolü atama](https://docs.microsoft.com/azure/storage/common/storage-auth-aad-rbac#assign-a-built-in-rbac-role) adımlarını izleyin.

**Rol ataması ekle** penceresinde, Power BI hizmetine atanacak **Okuyucu** rolünü seçin. Daha sonra **Power BI Hizmeti**’ni arayıp bulup. Aşağıdaki görüntüde, Power BI hizmetine atanan **Okuyucu** rolü gösterilmektedir.

![Okuyucu rolüne atanan Power BI hizmeti](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_05.jpg)


> [!NOTE]
> Portaldan Power BI’a yayma izni için en az 30 dakika bekleyin. Portaldaki izinleri değiştirdiğinizde, bu izinlerin Power BI’a yansıtılması için 30 dakika bekleyin. 


### <a name="create-a-file-system-for-power-bi"></a>Power BI için bir dosya sistemi oluşturma

Depolama hesabınızın Power BI’a eklenebilmesi için önce *powerbi* adlı bir dosya sistemi oluşturmanız gerekir. Azure Databricks, HDInsight, AZCopy veya Azure Depolama Gezgini kullanımı da dahil olmak üzere, böyle bir dosya sistemi oluşturmanın birçok yolu vardır. Bu bölümde, Azure Depolama Gezgini kullanılarak dosya sistemi oluşturmanın basit bir yolu gösterilmektedir.

Bu adım, Azure Depolama Gezgini sürüm 1.6.2'yi veya üstünü yüklemenizi gerektirir. Windows, Macintosh veya Linux için Azure Depolama Gezgini’ni yükleme ile ilgili bkz. [Azure Depolama Gezgini](https://azure.microsoft.com/features/storage-explorer/).

1. Azure Depolama Gezgini’ni başarıyla yüklemenizin ardından ilk başlatmanızda Microsoft Azure Depolama Gezgini - Bağlan penceresi gösterilir. Depolama Gezgini, depolama hesaplarına bağlanmanın birçok yolunu sağlarken, gerekli kurulum için şu anda yalnızca bir yol desteklenmektedir. 

2. Sol bölmede, yukarıda oluşturduğunuz depolama hesabını bulup genişletin.

3. Blob Kapsayıcıları’na tıklayın ve bağlam menüsünden Blob Kapsayıcısı Oluştur’u seçin.

   ![BLOB kapsayıcılarına sağ tıklayın](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_05a.jpg)

4. Blob Kapsayıcıları klasörünün altında bir metin kutusu görüntülenir. *powerbi* adını girin 

   ![“powerbi” adını girin](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_05b.jpg)

5. Blob kapsayıcısı oluşturma işleminiz bittiğinde Enter tuşuna basın

   ![BLOB kapsayıcısı oluşturmak için Enter tuşuna basın](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_05c.jpg)

Sonraki bölümde, Power BI hizmet ailesine, oluşturduğunuz dosya sistemi için tam erişim izni verirsiniz. 

### <a name="grant-power-bi-permissions-to-the-file-system"></a>Dosya sistemine Power BI izinleri verme

Dosya sistemine yönelik izin vermek için, Power BI hizmet erişimi veren Erişim Denetimi Listesi (ACL) ayarlarını uygularsınız. Bunun için ilk adım, kiracınızda Power BI hizmetleri kimliğini almaktır. Azure portalının **Kurumsal uygulamalar** bölümünde Azure Active Directory (AAD) uygulamalarınızı görüntüleyebilirsiniz.

Kiracı uygulamalarınızı bulmak için şu adımları izleyin:

1. [Azure portalında](https://portal.azure.com/), gezinti panelinden **Azure Active Directory**’i seçin.
2. Azure **Active Directory** dikey penceresinde **Kurumsal uygulamalar**’ı seçin.
3. **Uygulama Türü** açılan menüsünden **Tüm Uygulamalar**’ı ve sonra **Uygula**’yı seçin. Aşağıdaki görüntüye benzer şekilde, kiracı uygulamalarınızın bir örneği görüntülenir.

    ![AAD Kurumsal uygulamaları](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_06.jpg)

4. Arama çubuğuna *Power* yazın; böylece Power BI ve Power Query uygulamaları için Nesne Kimliklerinin koleksiyonu görüntülenir. Sonraki adımlarda üç değere de ihtiyacınız olacaktır.  

    ![Power uygulamalarını arama](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_07.jpg)

5. Aramanızın sonuçlarından hem Power BI Premium hizmeti hem de Power Query çevrimiçi için Nesne Kimliklerini seçip kopyalayın. Sonraki adımlarda bu değerleri yapıştırmaya hazır olun.

6. Daha sonra, önceki bölümde oluşturduğunuz *powerbi* dosya sistemine gitmek için **Azure Depolama Gezgini**’ni kullanın. [Azure Depolama gezginini kullanarak dosya ve dizin düzeyinde izinleri ayarlama](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-how-to-set-permissions-storage-explorer) makalesinin [Erişimi yönetme](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-how-to-set-permissions-storage-explorer#managing-access) bölümündeki yönergeleri izleyin.

7. 5\. adımda toplanan iki Power BI Premium Nesne Kimliğinin her biri için, *powerbi* dosya sisteminize **Okuma**, **Yazma**, **Yürütme** Erişimini ve Varsayılan ACL’leri atayın.

   ![her ikisi için de üçünü atayın](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_07a.jpg)

8. Dördüncü adımda toplanan Power Query Çevrimiçi Nesne Kimliği için, *powerbi* dosya sisteminize **Yazma**, **Yürütme** Erişimini ve Varsayılan ACL’leri atayın.

   ![ardından, yazma ve yürütme erişimi atayın](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_07b.jpg)

9. Ayrıca **Diğer** için, **Yürütme** Erişimini ve Varsayılan ACL’leri de atayın.

    ![son olarak, diğer için yürütme erişimi atayın](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_07c.jpg)

## <a name="connect-your-azure-data-lake-storage-gen2-to-power-bi"></a>Azure Data Lake Storage 2. Nesil’inizi Power BI’a bağlama

Azure portalında Azure Data Lake Storage 2. Nesil hesabınızı kurduktan sonra bu hesabı **Power BI yönetici portalında** Power BI’a bağlarsınız. Power BI yönetici portalının **Veri akışı depolama** ayarları kısmında depolanan Power BI veri akışı depolama ayarlarını da yönetirsiniz. Başlatma ve temel kullanım ile ilgili yönergeler için [Yönetici portalına ulaşma](service-admin-portal.md) bölümünden ayrıntılı bilgi edinebilirsiniz.

Aşağıdaki adımlarla **Azure Data Lake Storage 2. Nesil** hesabınızın bağlantısını oluşturursunuz:

1. **Power BI yönetici portalının** **Veri akışı ayarları** sekmesine gidin

    ![Power BI yönetici portalı](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-08b.png) 

2. **Azure Data Lake Storage 2. Nesil’i bağlayın** düğmesini seçin. Aşağıdaki pencere görünür.

    ![Azure Data Lake Storage Gen2](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_09.jpg) 

3. Depolama Hesabının **Abonelik Kimliği**’ni belirtin.
4. İçinde depolama hesabının oluşturulduğu **Kaynak Grubu adını** belirtin.
5. **Depolama Hesabı adını** belirtin.
6. **Bağlan**'ı seçin.

Bu adımlar başarıyla tamamlandıktan sonra Azure Data Lake Storage 2. Nesil hesabınız Power BI’a bağlanır. 

> [!NOTE]
> Power BI yönetim portalında Azure Data Lake Storage 2. Nesil'e bağlantı yapılandırmak için Genel Yönetici izinlerinizin olması gerekir. Öte yandan, Genel Yöneticiler yönetim portalında dış depolamaya bağlanamaz.  

Daha sonra kuruluşunuzdaki kişilerin kendi çalışma alanlarını yapılandırmasını sağlamanız gerekir; böylece bu kişilerin veri akışı tanımı ve veri depolama alanı için bu depolama hesabını kullanmalarına olanak sağlarsınız. Sonraki bölümde bunu yapalım. 


## <a name="allow-admins-to-assign-workspaces"></a>Yöneticilerin çalışma alanı atamasını sağlama

Varsayılan olarak veri akışı tanımı ve veri dosyaları, Power BI tarafından sağlanan depolama alanında depolanır. Kendi depolama hesabınızdaki veri akışı dosyalarına erişmek için çalışma alanı yöneticilerinin ilk olarak yeni depolama hesabında veri akışlarının atama ve depolamasına izin verecek şekilde çalışma alanını yapılandırması gerekir. Bir çalışma alanı yöneticisinin veri akışı depolama alanı ayarlarını yapılandırabilmesi için önce yöneticiye, **Power BI yönetici portalında** depolama atama izinleri verilmesi gerekir.

Depolama atama izinleri vermek için **Power BI yönetici portalında** **Veri akışı ayarları** sekmesine gidin. *Çalışma alanı yöneticilerinin bu depolama hesabına çalışma alanı atamasına izin ver* radyo düğmesi vardır ve bu düğme **izin ver** olarak ayarlanmalıdır. Kaydırıcıyı etkinleştirdikten sonra, değişikliğin geçerli olması için **Uygula** düğmesini seçin. 

![Yöneticilerin çalışma alanı atamasını sağlama](media/service-dataflows-connect-azure-data-lake-storage-gen2/dataflows-connect-adlsg2_10.jpg) 

İşte bu kadar. Power BI çalışma alanı yöneticileri artık oluşturduğunuz dosya sistemine iş akışları atayabilir.


## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Bu özellik bir önizleme özelliği olup, sürüm zamanı yaklaştıkça davranışı değişebilir. Veri akışı depolama alanınızla çalışırken dikkat edilmesi gereken bazı önemli noktalar ve sınırlamalar vardır:

* Bir veri akışı depolama konumu yapılandırıldıktan sonra değiştirilemez.
* Yalnızca Azure Data Lake Storage 2. Nesil’de depolanan bir veri akışının sahipleri varsayılan olarak bunun verilerine erişebilir. Azure’da depolanan veri akışları için ek kişileri yetkilendirmek istiyorsanız, veri akışının CDM klasörüne bunları eklemeniz gerekir 
* Bağlantılı varlıklar ile veri akışları oluşturmak yalnızca bu varlıklar aynı depolama hesabında depolandığında mümkündür
* Power BI paylaşılan kapasitelerinde şirket içi veri kaynakları, kuruluşunuzun veri gölünde depolanan veri akışlarında desteklenmez
* ADLS 2. Nesil'de anlık görüntüler otomatik olarak silinmez. Yer açmak istiyorsanız eski anlık görüntüleri düzenli aralıklarla temizleyen bir Azure işlevi oluşturabilirsiniz.

Bu bölümde açıklandığı gibi bilinen birkaç sorun vardır.

Power BI Desktop müşterileri, veri akışının sahibi olmadığı veya göldeki CDM klasörüne yönelik açıkça yetkilendirilmediği sürece, **Azure Data Lake Storage Hesabında** depolanan veri akışlarına erişemez. Senaryo aşağıdaki gibidir:

1. Ayşe yeni bir çalışma alanı oluşturdu ve veri akışları, kuruluşun veri gölünde depolanacak şekilde bu çalışma alanını yapılandırdı. 
2. Ayşe’nin oluşturduğu çalışma alanının da üyesi olan Berk, Ayşe’nin oluşturduğu Veri Akışından veri almak için Power BI Desktop ve veri akışı bağlayıcısını kullanmak ister.
3. Berk, veri akışının göldeki CDM klasörü için yetkilendirilmediğinden aşağıdakine benzer bir hata alır.

Sık sorulan sorular ve cevaplar arasında şunlar yer alır:

**Soru:** Bir çalışma alanında önceden veri akışları oluşturduysam ve bunların depolama konumunu değiştirmek istiyorsam ne olur?

**Cevap:** Bir veri akışının depolama konumunu oluşturulduktan sonra değiştiremezsiniz. 

**Soru:** Bir çalışma alanının veri akışı depolama konumunu ne zaman değiştirebilirim?

**Cevap:** Yalnızca çalışma alanı herhangi bir veri akışı içermiyorsa bir çalışma alanının veri akışı depolama konumunun değiştirilmesine izin verilir.


## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, veri akışı depolama alanı için bir Azure Data Lake 2. Nesil’e nasıl bağlanılacağına ilişkin yönergeler sağlanmıştır. Ek bilgi için aşağıdaki makalelere göz atın:

Veri akışları, CDM ve Azure Data Lake Storage 2. Nesil hakkında daha fazla bilgi için aşağıdaki makalelere göz atın:

* [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md)
* [Çalışma alanı veri akışı ayarlarını yapılandırma (Önizleme)](service-dataflows-configure-workspace-storage-settings.md)
* [Power BI’a veri akışı olarak bir CDM klasörü ekleme (Önizleme)](service-dataflows-add-cdm-folder.md)

Genel veri akışları hakkında bilgi için şu makalelere göz atın:

* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Power BI Premium'da hesaplanan varlıkları kullanma](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları](service-dataflows-developer-resources.md)

Azure depolama hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:
* [Azure Depolama güvenlik kılavuzu](https://docs.microsoft.com/azure/storage/common/storage-security-guide)

Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:
* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)
* [CDM klasörleri](https://go.microsoft.com/fwlink/?linkid=2045304)
* [CDM model dosyası tanımı](https://go.microsoft.com/fwlink/?linkid=2045521)

Ayrıca her zaman [Power BI Topluluğuna soru sormayı](https://community.powerbi.com/) deneyebilirsiniz.
