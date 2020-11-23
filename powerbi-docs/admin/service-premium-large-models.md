---
title: Power BI Premium'da büyük modeller (önizleme)
description: Büyük modeller özelliği, Power BI Premium'daki veri kümelerinin 10 GB'ın üzerine çıkmasını sağlar.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: how-to
ms.date: 11/11/2020
LocalizationGroup: Premium
ms.openlocfilehash: 57b1de80112e68849d21e7c34570d9754eaf0058
ms.sourcegitcommit: cc20b476a45bccb870c9de1d0b384e2c39e25d24
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94512827"
---
# <a name="large-models-in-power-bi-premium-preview"></a>Power BI Premium'da büyük modeller (önizleme)

Power BI veri kümeleri, sorgu performansını iyileştirerek büyük veri kümeleri üzerinde daha hızlı kullanıcı etkileşimine olanak tanımak için verileri yüksek oranda sıkıştırılmış bellek içi önbellekte depolayabilir. Büyük modeller özelliği, Power BI Premium'daki veri kümelerinin 10 GB'ın üzerine çıkmasını sağlar. Buna karşılık veri kümesinin boyutu Power BI Premium kapasitenin boyutuyla sınırlıdır. Bu durum Azure Analysis Services’in model boyutu sınırlamaları açısından çalışmasına benzer. Power BI Premium'daki kapasite boyutları hakkında daha fazla bilgi için Kapasite düğümlerini inceleyin. Büyük modelleri tüm Premium P SKU'ları ve Embedded A SKU'ları için ayarlayabilirsiniz ancak bu modeller yalnızca [yeni çalışma alanlarıyla](../collaborate-share/service-create-the-new-workspaces.md) çalışır.

Büyük modeller, PBIX yükleme boyutunu etkilemez ve bu boyut yine 10 GB ile sınırlı olur. Bunun yerine veri kümeleri yenilendiğinde hizmette 10 GB'ı aşar. Bir veri kümesini 10 GB'ın üzerine çıkacak şekilde yapılandırmak için artımlı yenileme özelliğini kullanabilirsiniz.

## <a name="enable-large-models"></a>Büyük modelleri etkinleştirme

10 GB'ı aşan bir veri kümesi oluşturmak için şu adımları izleyin:

1. Power BI Desktop'ta bir veri kümesi oluşturun ve [artımlı yenileme](service-premium-incremental-refresh.md) yapılandırın.

1. Veri kümesini Power BI Premium hizmetinde yayımlayın.

1. Aşağıdaki PowerShell cmdlet'lerini çalıştırarak veri kümesinde büyük modelleri etkinleştirin. Bu cmdlet’ler Power BI’ın veri kümesini Azure Premium Dosyalar’da depolamasına ve 10 GB’lık sınırı zorunlu tutmamasına neden olur.

1. Geçmiş verileri artımlı yenileme ilkesine göre yüklemek için yenileme gerçekleştirin. İlk yenileme işleminin geçmiş verileri yüklemesi uzun sürebilir. Sonraki yenileme işlemleri artımlı olacağından daha hızlı tamamlanacaktır.

### <a name="powershell-cmdlets"></a>PowerShell cmdlet'leri

Büyük modellerin geçerli sürümünde PowerShell cmdlet'lerini kullanarak veri kümesinin Premium Dosyalar depolama alanını kullanmasını sağlayın. PowerShell cmdlet'lerini çalıştırabilmek için kapasite yöneticisi ve çalışma alanı yöneticisi ayrıcalıklarına sahip olmanız gerekir.

1. Veri kümesi kimliğini (GUID) bulun. Kimlik değerini, çalışma alanının **Veri kümeleri** sekmesinin veri kümesi ayarlarında yer alan URL'de görebilirsiniz.

    ![Veri kümesi GUID değeri](media/service-premium-large-models/dataset-guid.png)

1. PowerShell yönetici isteminden [MicrosoftPowerBIMgmt](/powershell/module/microsoftpowerbimgmt.data/) modülünü yükleyin.

    ```powershell
    Install-Module -Name MicrosoftPowerBIMgmt
    ```

1. Oturum açmak ve veri kümesi depolama modunu denetlemek için aşağıdaki cmdlet'leri çalıştırın.

    ```powershell
    Login-PowerBIServiceAccount

    (Get-PowerBIDataset -Scope Organization -Id <Dataset ID> -Include actualStorage).ActualStorage
    ```

    Yanıt aşağıdaki gibi olmalıdır. Depolama modu varsayılan ayar olan ABF (Analysis Services yedekleme dosyası) olacaktır.

    ```
    Id                   StorageMode

    --                   -----------

    <Dataset ID>         Abf
    ```

1. Depolama modunu Premium Dosyalar olarak değiştirmek ve bunu denetlemek için aşağıdaki cmdlet'leri çalıştırın. Premium Dosyalara dönüştürme işlemi birkaç saniye sürebilir.

    ```powershell
    Set-PowerBIDataset -Id <Dataset ID> -TargetStorageMode PremiumFiles

    (Get-PowerBIDataset -Scope Organization -Id <Dataset ID> -Include actualStorage).ActualStorage
    ```

    Yanıt aşağıdaki gibi olmalıdır. Depolama modu artık Premium Dosyalar olarak ayarlanmıştır.

    ```
    Id                   StorageMode
    
    --                   -----------
    
    <Dataset ID>         PremiumFiles
    ```

Veri kümelerini Premium Dosyalara dönüştürme durumunu [Get-PowerBIWorkspaceMigrationStatus](/powershell/module/microsoftpowerbimgmt.workspaces/get-powerbiworkspacemigrationstatus) cmdlet'ini kullanarak denetleyebilirsiniz.

## <a name="dataset-eviction"></a>Veri kümesi çıkarma

Power BI, bellekteki etkin olmayan veri kümelerini çıkarmak için dinamik bellek yönetimi özelliğini kullanır. Power BI, kullanıcı sorgularını karşılama amacıyla farklı veri kümelerini yükleyebilmek için kullanılmayan veri kümelerini çıkarır. Dinamik bellek yönetimi, veri kümesi boyutlarının kapasitedeki kullanılabilir bellekten çok daha büyük olmasına izin verir ancak bunun için tek bir veri kümesinin belleğe sığacak boyutta olması gerekir. Dinamik bellek yönetimi hakkında daha fazla bilgi için bkz. [Kapasiteler nasıl çalışır?](service-premium-what-is.md#how-capacities-function)

Büyük modellerde çıkarmanın etkisini göz önünde bulundurmanız gerekir. Veri kümesi yükleme süreleri kısa olsa da çıkarılan büyük veri kümelerinin yeniden yüklenmesi, kullanıcılar için önemli bir gecikme süresi yaratabilir. Bu nedenle büyük modeller özelliği mevcut halinde self servis BI gereksinimleriyle karma kapasitelerden çok kurumsal BI gereksinimlerine ayrılmış olan kapasiteler için önerilir. Kurumsal BI gereksinimlerine ayrılmış olan kapasitelerde veri kümesi çıkarma ve yeniden yükleme gereksinimi daha az olacaktır. Diğer yandan self servis BI ortamlarında belleğe girip çıkan çok sayıda küçük veri kümesi bulunabilir.

## <a name="checking-dataset-size"></a>Veri kümesi boyutunu denetleme

Geçmiş verileri yükledikten sonra [XMLA uç noktası](service-premium-connect-tools.md) aracılığıyla [SSMS](/sql/ssms/download-sql-server-management-studio-ssms) kullanarak model özellikleri penceresinden tahmini veri kümesi boyutunu denetleyebilirsiniz.

![Tahmini veri kümesi boyutu](media/service-premium-large-models/estimated-dataset-size.png)

Veri kümesi boyutunu denetlemek için SSMS'ten aşağıdaki DMV sorgularını da çalıştırabilirsiniz. Veri kümesi boyutunu bayt cinsinden görmek için çıkıştaki DICTIONARY\_SIZE ve USED\_SIZE sütunlarını toplayın.

```sql
SELECT * FROM SYSTEMRESTRICTSCHEMA
($System.DISCOVER_STORAGE_TABLE_COLUMNS,
 [DATABASE_NAME] = '<Dataset Name>') //Sum DICTIONARY_SIZE (bytes)

SELECT * FROM SYSTEMRESTRICTSCHEMA
($System.DISCOVER_STORAGE_TABLE_COLUMN_SEGMENTS,
 [DATABASE_NAME] = '<Dataset Name>') //Sum USED_SIZE (bytes)
```

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

Büyük modelleri kullanırken aşağıdaki kısıtlamalara dikkat edin:

- **Multi-geo desteği**: Premium Dosyaların etkinleştirildiği veri kümeleri, [multi-geo](service-admin-premium-multi-geo.md) özelliğinin de etkin olduğu kapasitelerde hata verecektir.

- **Power BI Desktop'a indirme**: Premium Dosyalarda depolanan veri kümeleri için [.pbix olarak indirme](../create-reports/service-export-to-pbix.md) işlemi başarısız olur.
- **Desteklenen bölgeler**: Büyük modeller Premium Dosya Depolama'yı destekleyen tüm Azure bölgelerinde desteklenir. Daha fazla bilgi edinmek için [Bölgeye göre kullanılabilir ürünler](https://azure.microsoft.com/global-infrastructure/services/?products=storage) konusuna bakın ve aşağıdaki bölümde verilen tabloya başvurun.


## <a name="availability-in-regions"></a>Bölgelerdeki kullanılabilirlik

Power BI’da büyük modeller yalnızca [Azure Premium Dosyalar Depolaması](/azure/storage/files/storage-files-planning#storage-tiers)’nı destekleyen bazı Azure bölgelerinde kullanılabilir.

Aşağıdaki listede, Power BI’da büyük modellerin kullanılabildiği bölgeler listelenir. Aşağıdaki listede yer almayan bölgeler, büyük modeller için desteklenmez:


|Azure bölgesi  |Azure bölgesi kısaltması  |
|---------|---------|
|Doğu Avustralya     | australiaeast        |
|Avustralya Güneydoğu     | australiasoutheast        |
|Central US     | centralus        |
|Doğu Asya     | eastasia        |
|Doğu ABD     | eastus        |
|Doğu ABD 2     | eastus2        |
|Doğu Japonya     | japaneast        |
|Batı Japonya     | japanwest        |
|Güney Kore - Orta     | koreacentral        |
|Güney Kore - Güney     | koreasouth        |
|Orta Kuzey ABD     | northcentralus        |
|Kuzey Avrupa     | northeurope        |
|Orta Güney ABD     | southcentralus        |
|Güneydoğu Asya     | southeastasia        |
|Güney Birleşik Krallık     | uksouth        |
|Batı Birleşik Krallık     | ukwest        |
|West Europe     | westeurope        |
|Batı ABD     | westus        |
|Batı ABD 2     | westus2        |



## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki bağlantılarda, büyük modellerle çalışırken yararlı olabilecek bilgiler sağlanır:

* [Azure Premium Dosyalar Depolaması](/azure/storage/files/storage-files-planning#storage-tiers)
* [Power BI Premium için Multi-Geo desteğini yapılandırma](service-admin-premium-multi-geo.md)
* [Power BI için kendi anahtarını getir şifrelemesi](service-encryption-byok.md)
* [Kapasiteler nasıl çalışır?](service-premium-what-is.md#how-capacities-function)
* [Artımlı yenileme](service-premium-incremental-refresh.md).


Power BI, aşağıdaki iyileştirmelerle Power BI Premium deneyimini geliştiren bir önizleme teklifi olarak Power BI Premium 2. Nesil’i kullanıma sundu:
* Performans
* Kullanıcı başına lisanslama
* Daha yüksek ölçek
* İyileştirilmiş ölçümler
* Otomatik ölçeklendirme
* Azaltılmış yönetim yükü

Power BI Premium 2. Nesil hakkında daha fazla bilgi için bkz. [Power BI Premium 2. Nesil (önizleme)](service-premium-what-is.md#power-bi-premium-generation-2-preview).