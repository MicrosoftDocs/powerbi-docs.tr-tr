---
title: Power BI Premium'daki büyük veri kümeleri
description: Büyük veri kümesi depolama biçimi, Power BI Premium'daki veri kümelerinin 10 GB'ın üzerine çıkmasını sağlar.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: how-to
ms.date: 01/21/2021
ms.custom: references_regions
LocalizationGroup: Premium
ms.openlocfilehash: 4fd953eac998e954579af83f2acec975f66e7436
ms.sourcegitcommit: 77912d4f6ef2a2b1ef8ffccc50691fe5b38ee97a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98687040"
---
# <a name="large-datasets-in-power-bi-premium"></a>Power BI Premium'daki büyük veri kümeleri

Power BI veri kümeleri, sorgu performansını iyileştirerek daha hızlı kullanıcı etkileşimine olanak tanımak için verileri yüksek oranda sıkıştırılmış bellek içi önbellekte depolayabilir. Premium kapasitelerde, varsayılan sınırın ötesinde büyük veri kümeleri **büyük veri kümesi depolama biçimi** ayarıyla etkinleştirilebilir. Etkinleştirildiğinde, veri kümesi boyutu Premium *kapasite* boyutuyla veya yönetici tarafından ayarlanmış en büyük boyutla sınırlıdır.

Büyük veri kümeleri tüm Premium P SKU'ları ve Embedded A SKU'ları için etkinleştirilebilir. Premium'daki büyük veri kümesi boyutu sınırı, veri modeli boyutu sınırlamaları açısından Azure Analysis Services ile benzerdir.

Veri kümelerinin 10 GB'ın üzerine çıkabilmesi için etkinleştirilmesi gereken Büyük veri kümesi depolama biçimi ayarının sunduğu ek avantajlar da vardır. Veri kümesi yazma işlemleri için XMLA uç noktası tabanlı araçlar kullanmayı planlıyorsanız bu ayarı *büyük* olmayan veri kümeleri için dahi etkinleştirmeniz önerilir. Büyük veri kümesi depolama biçimi etkinleştirildiğinde XMLA yazma işlemlerinin performansını artırabilir.

Hizmetteki büyük veri kümeleri, 10 GB ile sınırlı olan Power BI Desktop model yükleme boyutunu etkilemez. Bunun yerine, veri kümeleri yenileme sırasında hizmette o sınırın ötesine büyüyebilir.

> [!IMPORTANT]
> Power BI Premium, büyük veri kümelerini destekler. **Büyük veri kümesi depolama biçimi** seçeneğini, varsayılan sınırdan daha büyük Power BI Premium veri kümeleri kullanacak şekilde etkinleştirin. 


## <a name="enable-large-datasets"></a>Büyük veri kümelerini etkinleştirme

Buradaki adımlar, hizmette yeni yayımlanan bir modelde büyük veri kümelerini etkinleştirmeye yöneliktir. Var olan veri kümeleri için yalnızca üçüncü adımı gerçekleştirmeniz yeterli olacaktır.

1. Power BI Desktop'ta bir model oluşturun. Veri kümeniz büyüyecek ve büyüdükçe daha fazla bellek kullanacaksa [Artımlı yenileme](service-premium-incremental-refresh.md) ayarını yapılandırmayı unutmayın.

1. Modeli veri kümesi olarak hizmette yayımlayın.

1. Hizmet > Veri kümesi > **Ayarlar** sayfasında **Büyük veri kümesi depolama biçimi**'ni genişletin, kaydırıcıyı **Açık** konumuna getirin ve **Uygula**'ya tıklayın.

    :::image type="content" source="media/service-premium-large-models/enable-large-dataset.png" alt-text="Büyük veri kümesini etkinleştirme kaydırıcısı":::

1. Geçmiş verileri artımlı yenileme ilkesine göre yüklemek için yenileme gerçekleştirin. İlk yenileme işleminin geçmiş verileri yüklemesi uzun sürebilir. Artımlı yenileme ilkenize bağlı olarak sonraki yenileme işlemlerinin daha hızlı tamamlanması gerekir.

## <a name="set-default-storage-format"></a>Varsayılan depolama biçimini ayarlama

Büyük veri kümesi depolama biçimi ayarı, Premium kapasiteye atanmış olan çalışma alanı içindeki tüm yeni veri kümeleri için varsayılan olarak etkin hale getirilebilir.

1. Çalışma alanında **Ayarlar** > **Premium**'a tıklayın.

1. **Varsayılan depolama biçimi** bölümünde **Büyük veri kümesi depolama biçimi**'ni seçip **Kaydet**'e tıklayın.

    :::image type="content" source="media/service-premium-large-models/default-storage-format.png" alt-text="Varsayılan depolama biçimini etkinleştirme":::

### <a name="enable-with-powershell"></a>PowerShell ile etkinleştirme

Büyük veri kümesi depolama biçimini etkinleştirmek için PowerShell'i de kullanabilirsiniz. PowerShell cmdlet'lerini çalıştırabilmek için kapasite yöneticisi ve çalışma alanı yöneticisi ayrıcalıklarına sahip olmanız gerekir.

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

1. Depolama modunu ayarlamak için aşağıdaki cmdlet'leri çalıştırın. Premium Dosyalara dönüştürme işlemi birkaç saniye sürebilir.

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

Büyük veri kümelerini kullanırken aşağıdaki kısıtlamalara dikkat edin:

- **Yeni çalışma alanlarını kullanmanız gerekir**: Büyük veri kümeleri yalnızca [Yeni çalışma alanları](../collaborate-share/service-create-the-new-workspaces.md) ile uyumludur.

- **Power BI Desktop'a indirme**: Premium Dosyalarda depolanan veri kümeleri için [.pbix olarak indirme](../create-reports/service-export-to-pbix.md) işlemi başarısız olur.
- **Desteklenen bölgeler**: Büyük veri kümeleri Premium Dosya Depolama'yı destekleyen tüm Azure bölgelerinde desteklenir. Daha fazla bilgi edinmek için [Bölgeye göre kullanılabilir ürünler](https://azure.microsoft.com/global-infrastructure/services/?products=storage) konusuna bakın ve aşağıdaki bölümde verilen tabloya başvurun.

- **Veri kümesi boyutu üst sınırını ayarlama**: Veri boyutu üst sınırı yöneticiler tarafından ayarlanabilir. Üst sınır 0,1 GB'tan SKU'nun kapasite üst sınırına kadar bir değere ayarlanabilir.

## <a name="region-availability"></a>Bölge kullanılabilirliği

Power BI’da büyük veri kümeleri yalnızca [Azure Premium Dosyalar Depolaması](/azure/storage/files/storage-files-planning#storage-tiers)’nı destekleyen bazı Azure bölgelerinde kullanılabilir.

Aşağıdaki listede, Power BI’da büyük veri kümelerinin kullanılabildiği bölgeler listelenir. Aşağıdaki listede yer almayan bölgeler, büyük modeller için desteklenmez:

|Azure bölgesi  |Azure bölgesi kısaltması  |
|---------|---------|
|Doğu Avustralya     | australiaeast        |
|Avustralya Güneydoğu     | australiasoutheast        |
|Doğu Kanada     | canadaeast        |
|Orta Kanada     | canadacentral        |
|Orta Hindistan     | centralindia        |
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
|Batı Hindistan     | westindia        |
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
