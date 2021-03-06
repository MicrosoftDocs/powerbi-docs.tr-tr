---
title: Power BI için kendi şifreleme anahtarlarınızı getirme
description: Power BI Premium'da kendi şifreleme anahtarlarınızı kullanmayı öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 11/11/2020
LocalizationGroup: Premium
ms.openlocfilehash: 2313e736dee73666bb5ddb380b39a217c6b61237
ms.sourcegitcommit: c33e53e1fab1f29872297524a7b4f5af6c806798
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99532648"
---
# <a name="bring-your-own-encryption-keys-for-power-bi"></a>Power BI için kendi şifreleme anahtarlarınızı getirme

Power BI _bekleyen_ ve _işlenmekte olan_ verileri şifreler. Varsayılan olarak Power BI verilerinizi şifrelemek için Microsoft tarafından yönetilen anahtarları kullanır. Power BI Premium'da veri kümesinde içeri aktarılan ve bekleyen veriler için de kendi anahtarlarınızı kullanabilirsiniz (daha fazla bilgi için bkz. [Veri kaynağı ve depolama konusunda dikkat edilmesi gerekenler](#data-source-and-storage-considerations)). Bu yaklaşım genellikle _kendi anahtarını getir_ (KAG) olarak tanımlanır.

## <a name="why-use-byok"></a>Neden KAG kullanılmalı?

KAG bulut hizmeti sağlayıcısıyla (bu durumda Microsoft) anahtar düzenlemelerini belirleyen uyumluluk gereksinimlerini karşılamayı kolaylaştırır. KAG ile bekleyen Power BI verileriniz için şifreleme anahtarlarını uygulama düzeyinde siz sağlar ve denetlersiniz. Sonuç olarak, denetim sizde olur ve hizmette çıkmaya karar verirseniz kuruluşunuzun anahtarlarını iptal edebilirsiniz. Anahtarlar iptal edildikten sonra 30 dakika içinde veriler hizmet tarafından okunamaz hale gelir.

> [!IMPORTANT]
> Yakın zamanda Power BI Premium, şu anda önizleme aşamasında olan **Premium 2. Nesil** adlı yeni bir Premium sürümünü kullanıma sundu. Önizleme aşamasındayken Önizleme 2. Nesil kapasiteleri Kendi Anahtarını Getir’i **desteklemez**.
>
>**Gömülü Gen2** kapasiteleri önizleme sırasında **bYok 'ı da desteklemez.** Power BI Embedded Gen2 geliştirmelerini gözden geçirmek için [Power BI Embedded 2. nesil](../developer/embedded/power-bi-embedded-generation-2.md)bölümüne bakın.

## <a name="data-source-and-storage-considerations"></a>Veri kaynağı ve depolama konusunda dikkat edilmesi gerekenler

KAG kullanmak için verileri bir Power BI Desktop (PBIX) dosyasından Power BI hizmetine yüklemeniz gerekir. Aşağıdaki senaryolarda KAG kullanamazsınız:

- Analysis Services Canlı Bağlantısı
- Excel çalışma kitapları (veriler önce Power BI Desktop'a içeri aktarılmadıysa)
- [Gönderme veri kümeleri](/rest/api/power-bi/pushdatasets)
- [Akış veri kümeleri](../connect-data/service-real-time-streaming.md#set-up-your-real-time-streaming-dataset-in-power-bi)


KAG yalnızca veri kümeleri için geçerlidir. Gönderme veri kümeleri, Excel dosyaları ve kullanıcıların hizmete yükleyebileceği CSV dosyaları kendi anahtarınız kullanılarak şifrelenmez. Çalışma alanınızda depolanan yapıtları tanımlamak için şu PowerShell komutunu kullanın:

```PS C:\> Get-PowerBIWorkspace -Scope Organization -Include All```

> [!NOTE]
> Bu cmdlet için Power BI yönetim modülü v1.0.840 gerekir. Get-InstalledModule -Name MicrosoftPowerBIMgmt komutunu kullanarak sahip olduğunuz sürümü görebilirsiniz. Son sürümü yüklemek için Install-Module -Name MicrosoftPowerBIMgmt komutunu çalıştırın. Power BI cmdlet'i ve parametreleri hakkında daha fazla bilgi için bkz. [Power BI PowerShell cmdlet modülü](/powershell/power-bi/overview).

## <a name="configure-azure-key-vault"></a>Azure Key Vault'u yapılandırma

Bu bölümde, şifreleme anahtarları gibi gizli dizileri güvenle depolamaya ve bunlara erişmeye yönelik bir araç olan Azure Key Vault’u yapılandırmayı öğreneceksiniz. Şifreleme anahtarlarını depolamak için mevcut anahtar kasasını kullanabilir veya özel olarak Power BI ile kullanmak üzere yeni anahtar kasası oluşturabilirsiniz.

Bu bölümdeki yönergelerde temel Azure Key Vault bilgisine sahip olduğunuz varsayılır. Daha fazla bilgi için bkz. [Azure Key Vault nedir?](/azure/key-vault/key-vault-whatis) Anahtar kasanızı şu şekilde yapılandırın:

1. Power BI hizmetini anahtar kasası için sarmalama ve sarmalamayı kaldırma izinleriyle bir hizmet sorumlusu olarak ekleyin.

1. Sarmalama ve sarmalamayı kaldırma izinleriyle 4096 bit uzunluğunda bir RSA anahtarı oluşturun (veya bu türde mevcut bir anahtar kullanın).

    > [!IMPORTANT]
    > Power BI KAG, yalnızca 4096 bit uzunluğuna sahip RSA anahtarlarını destekler.

1. Önerilen: Anahtar kasasında _geçici silme_ seçeneğinin etkinleştirildiğinden emin olun.

### <a name="add-the-service-principal"></a>Hizmet sorumlusunu ekleme

1. Azure portalında, anahtar kasanızda **Erişim ilkeleri**'nin altından **Yeni Ekle**'yi seçin.

1. **Sorumlu seç**'in altında Microsoft.Azure.AnalysisServices'i arayın ve seçin.

    > [!NOTE]
    > “Microsoft.Azure.AnalysisServices” öğesini bulamıyorsanız Azure Key Vault’unuz ile ilişkilendirilen aboneliğinizle bir Power BI kaynağının asla ilişkilendirilmemiş olması muhtemeldir. Bunun yerine aşağıdaki dizeyi aramayı deneyin: 00000009-0000-0000-c000-000000000000.

1. **Anahtar izinleri**'nin altında **Anahtar Sarmalamasını Kaldır**'ı ve **Anahtarı Sarmala**'yı seçin.

    ![PBIX dosyası için hizmet sorumlusunu ve şifreleme işlemlerini seçme](media/service-encryption-byok/service-principal.png)

1. **Tamam**'ı, sonra da **Kaydet**'i seçin.

> [!NOTE]
> Gelecekte Power BI'ın verilerinize erişimini iptal etmek için Azure Key Vault'unuzdan bu hizmet sorumlusuna yönelik erişim haklarını kaldırın.

### <a name="create-an-rsa-key"></a>RSA anahtarı oluşturma

1. Anahtar kasanızdaki **Anahtarlar**'ın altında **Oluştur/İçeri Aktar**'ı seçin.

1. **Anahtar Türü** olarak RSA ve **RSA Anahtar Boyutu** olarak 4096 seçin.

    ![Anahtar oluşturma adımı, anahtar türü ve boyutu vurgulanmış](media/service-encryption-byok/create-rsa-key.png)

1. **Oluştur**’u seçin.

1. **Anahtarlar**'ın altında, oluşturduğunuz anahtarı seçin.

1. Anahtarın **Geçerli Sürümü** olarak GUID seçin.

1. Hem **Anahtar Sarmala** hem de **Anahtar Sarmalamasını Kaldır**'ın seçildiğinden emin olun. Power BI'da KAG'yi etkinleştirirken kullanmak üzere **Anahtar Tanımlayıcısı**'nı kopyalayın.

    ![Özellikler, anahtar tanımlayıcısı ve izin verilen işlemler vurgulanmış](media/service-encryption-byok/key-properties.png)

### <a name="soft-delete-option"></a>Geçici silme seçeneği

Anahtarın veya anahtar kasasının yanlışlıkla silinmesi durumunda veri kaybına karşı korunmak için anahtar kasanızda [geçici silme](/azure/key-vault/key-vault-ovw-soft-delete)'yi etkinleştirmenizi öneririz. Anahtar kasasında ["geçici silme" özelliğini etkinleştirmek için PowerShell](/azure/key-vault/key-vault-soft-delete-powershell) kullanmalısınız çünkü bu seçenek henüz Azure portalında sağlanmamaktadır.

Azure Key Vault düzgün yapılandırıldığında kiracınızda KAG'yi etkinleştirmeye hazır olursunuz.

## <a name="enable-byok-on-your-tenant"></a>Kiracınızda KAG'yi etkinleştirme

Oluşturduğunuz ve Azure Key Vault'ta depoladığınız şifreleme anahtarlarını önce Power BI kiracınıza tanıtarak [PowerShell](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt.Admin)'le KAG'yi kiracı düzeyinde etkinleştirirsiniz. Ardından Premium kapasitedeki içeriği şifrelemek için bu şifreleme anahtarlarını bu kapasiteye atarsınız.

### <a name="important-considerations"></a>Önemli noktalar

KAG'yi etkinleştirmeden önce aşağıdaki noktaları aklınızda bulundurun:

- Şu anda, KAG'yi etkinleştirdikten sonra devre dışı bırakamazsınız. `Add-PowerBIEncryptionKey` için parametreleri nasıl belirttiğinize bağlı olarak KAG'yi bir veya birden çok kapasitenizde nasıl kullanacağınızı denetleyebilirsiniz. Öte yandan anahtarların kiracınıza tanıtılmasını geri alamazsınız. Daha fazla bilgi için bkz. [KAG'yi etkinleştirme](#enable-byok).

- KAG kullanan bir çalışma alanını Power BI Premium’daki kapasiteden paylaşılan kapasiteye _doğrudan_ taşıyamazsınız. Çalışma alanını önce KAG’nin etkinleştirilmediği bir kapasiteye taşımanız gerekir.

- KAG kullanan bir çalışma alanını Power BI Premium’daki bir kapasiteden paylaşılan kapasiteye taşırsanız Anahtar ile şifrelendiğinden raporlara ve veri kümelerine erişim sağlayamazsınız. Bu durumla karşılaşmamak için çalışma alanını önce KAG'nin etkinleştirilmediği bir kapasiteye taşımanız gerekir.

### <a name="enable-byok"></a>KAG'yi etkinleştirme

KAG'yi etkinleştirmek için `Connect-PowerBIServiceAccount` cmdlet'ini kullanarak oturum açmış bir Power BI yöneticisi olmanız gerekir. Ardından aşağıdaki örnekte gösterildiği gibi [`Add-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/Add-PowerBIEncryptionKey) kullanarak KAG'yi etkinleştirin:

```powershell
Add-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
```

Birden çok anahtar eklemek için farklı -`-Name` ve `-KeyVaultKeyUri` değerleri ile `Add-PowerBIEncryptionKey` komutunu çalıştırın. 

Cmdlet mevcut ve gelecekteki kapasiteler için şifrelemeyi etkileyen iki anahtar parametresi kabul eder. Varsayılan olarak anahtarların hiçbiri ayarlanmamıştır:

- `-Activate` Bu anahtarın kiracıda henüz şifrelenmemiş tüm mevcut kapasitelerde kullanılacağını gösterir.

- `-Default` Bu anahtarın şimdi kiracının tamamı için varsayılan olduğunu gösterir. Yeni kapasite oluşturduğunuzda, kapasite bu anahtarı devralır.

> [!IMPORTANT]
> `-Default` belirtirseniz, bu noktadan sonra kiracınızda oluşturulan kapasitelerin tümü belirttiğiniz anahtar (veya güncelleştirilmiş bir varsayılan anahtar) kullanılarak şifrelenir. Varsayılan işlemi geri alamazsınız dolayısıyla kiracınızda KAG kullanmayan bir premium kapasite oluşturma olanağını kaybedersiniz.

Kiracınızda KAG’yi etkinleştirdikten sonra bir veya daha fazla Power BI özelliği için şifreleme anahtarını ayarlayın:

1. Sonraki adım için gereken kapasite kimliğini almak üzere [`Get-PowerBICapacity`](/powershell/module/microsoftpowerbimgmt.capacities/get-powerbicapacity) seçeneğini kullanın.

    ```powershell
    Get-PowerBICapacity -Scope Individual
    ```

    Cmdlet aşağıdaki çıktıya benzer bir çıktı döndürür:

    ```
    Id              : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    DisplayName     : Test Capacity
    Admins          : adam@sometestdomain.com
    Sku             : P1
    State           : Active
    UserAccessRight : Admin
    Region          : North Central US
    ```

1. Şifreleme anahtarını ayarlamak için [`Set-PowerBICapacityEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/set-powerbicapacityencryptionkey) kullanın:

    ```powershell
    Set-PowerBICapacityEncryptionKey -CapacityId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -KeyName 'Contoso Sales'
    ```

Kiracınız genelinde KAG'yi nasıl kullandığınızı denetleyebilirsiniz. Örneğin tek bir kapasiteyi şifrelemek için `-Activate` veya `-Default` kullanmadan `Add-PowerBIEncryptionKey` çağrısı yapın. Sonra KAG'yi etkinleştirmek istediğiniz kapasite için `Set-PowerBICapacityEncryptionKey` çağrısı yapın.

## <a name="manage-byok"></a>KAG'yi yönetme

Power BI kiracınızda KAG'nin yönetilmesine yardımcı olmak için ek cmdlet'ler sağlar:

- Bir kapasitenin şu anda kullandığı anahtarı almak için [`Get-PowerBICapacity`](/powershell/module/microsoftpowerbimgmt.capacities/get-powerbicapacity) kullanın:

    ```powershell
    Get-PowerBICapacity -Scope Organization -ShowEncryptionKey
    ```

- Kiracınızın şu anda kullandığı anahtarı almak için [`Get-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/get-powerbiencryptionkey) kullanın:

    ```powershell
    Get-PowerBIEncryptionKey
    ```

- Çalışma alanındaki veri kümelerinin şifrelenip şifrelenmediğini ve şifreleme durumlarının çalışma alanıyla eşitlenmiş olup olmadığını görmek için [`Get-PowerBIWorkspaceEncryptionStatus`](/powershell/module/microsoftpowerbimgmt.admin/get-powerbiworkspaceencryptionstatus) kullanın:

    ```powershell
    Get-PowerBIWorkspaceEncryptionStatus -Name'Contoso Sales'
    ```

    Şifrelemenin kapasite düzeyinde etkinleştirildiğine ama belirtilen çalışma alanı için eşitleme durumunu veri kümesi düzeyinde aldığınıza dikkat edin.

- Şifreleme için kullanılan anahtarın sürümünü değiştirmek için [`Switch-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/switch-powerbiencryptionkey) veya (_döndür_ işlevini) kullanın. Cmdlet yalnızca `-Name` anahtarı için `-KeyVaultKeyUri` değerini güncelleştirir:

    ```powershell
    Switch-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
    ```



## <a name="next-steps"></a>Sonraki adımlar

* [Power BI PowerShell cmdlet modülü](/powershell/power-bi/overview) 

* [Power BI'da çalışmanızı paylaşmanın yolları](../collaborate-share/service-how-to-collaborate-distribute-dashboards-reports.md)

* [URL'de sorgu dizesi parametreleri kullanarak bir raporu filtreleme](../collaborate-share/service-url-filters.md)

* [SharePoint Online'da rapor web bölümüyle ekleme](../collaborate-share/service-embed-report-spo.md)

* [Power BI'dan Web'de yayımlama](../collaborate-share/service-publish-to-web.md)


Power BI, aşağıdaki iyileştirmelerle Power BI Premium deneyimini geliştiren bir önizleme teklifi olarak Power BI Premium 2. Nesil’i kullanıma sundu:
* Performans
* Kullanıcı başına lisanslama
* Daha yüksek ölçek
* İyileştirilmiş ölçümler
* Otomatik ölçeklendirme
* Azaltılmış yönetim yükü

Power BI Premium 2. Nesil hakkında daha fazla bilgi için bkz. [Power BI Premium 2. Nesil (önizleme)](service-premium-what-is.md#power-bi-premium-generation-2-preview).