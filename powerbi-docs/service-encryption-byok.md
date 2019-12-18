---
title: Power BI için kendi şifreleme anahtarlarınızı getirme (önizleme)
description: Power BI Premium'da kendi şifreleme anahtarlarınızı kullanmayı öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/24/2019
LocalizationGroup: Premium
ms.openlocfilehash: 4cddf01dd57191b5d3e707589e6d8a78e106259f
ms.sourcegitcommit: 320d83ab392ded71bfda42c5491acab3d9d357b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74958483"
---
# <a name="bring-your-own-encryption-keys-for-power-bi-preview"></a>Power BI için kendi şifreleme anahtarlarınızı getirme (önizleme)

Power BI _bekleyen_ ve _işlenmekte olan_ verileri şifreler. Varsayılan olarak Power BI verilerinizi şifrelemek için Microsoft tarafından yönetilen anahtarları kullanır. Power BI Premium'da veri kümesinde içeri aktarılan ve bekleyen veriler için de kendi anahtarlarınızı kullanabilirsiniz (daha fazla bilgi için bkz. [Veri kaynağı ve depolama konusunda dikkat edilmesi gerekenler](#data-source-and-storage-considerations)). Bu yaklaşım genellikle _kendi anahtarını getir_ (KAG) olarak tanımlanır.

## <a name="why-use-byok"></a>Neden KAG kullanılmalı?

KAG bulut hizmeti sağlayıcısıyla (bu durumda Microsoft) anahtar düzenlemelerini belirleyen uyumluluk gereksinimlerini karşılamayı kolaylaştırır. KAG ile bekleyen Power BI verileriniz için şifreleme anahtarlarını uygulama düzeyinde siz sağlar ve denetlersiniz. Sonuç olarak, denetim sizde olur ve hizmette çıkmaya karar verirseniz kuruluşunuzun anahtarlarını iptal edebilirsiniz. Anahtarlar iptal edildiğinde veriler hizmet tarafından okunamaz.

## <a name="data-source-and-storage-considerations"></a>Veri kaynağı ve depolama konusunda dikkat edilmesi gerekenler

KAG kullanmak için verileri bir Power BI Desktop (PBIX) dosyasından Power BI hizmetine yüklemeniz gerekir. Aşağıdaki senaryolarda KAG kullanamazsınız:

- Analysis Services Canlı Bağlantısı
- Excel çalışma kitapları (veriler önce Power BI Desktop'a içeri aktarılmadıysa)
- [Gönderme veri kümeleri](/rest/api/power-bi/pushdatasets)
- [Akış veri kümeleri](service-real-time-streaming.md#set-up-your-real-time-streaming-dataset-in-power-bi)
- [Büyük modeller](service-premium-large-models.md)

KAG, kutucuk ve görsellerin sorgu sonuçlarından ziyade sadece PBIX dosyasıyla ilişkilendirilen veri kümesi için geçerlidir.

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

    ![PBIX dosyası bileşenleri](media/service-encryption-byok/service-principal.png)

1. **Tamam**'ı, sonra da **Kaydet**'i seçin.

> [!NOTE]
> Gelecekte Power BI'ın verilerinize erişimini iptal etmek için Azure Key Vault'unuzdan bu hizmet sorumlusuna yönelik erişim haklarını kaldırın.

### <a name="create-an-rsa-key"></a>RSA anahtarı oluşturma

1. Anahtar kasanızdaki **Anahtarlar**'ın altında **Oluştur/İçeri Aktar**'ı seçin.

1. **Anahtar Türü** olarak RSA ve **RSA Anahtar Boyutu** olarak 4096 seçin.

    ![PBIX dosyası bileşenleri](media/service-encryption-byok/create-rsa-key.png)

1. **Oluştur**'u seçin.

1. **Anahtarlar**'ın altında, oluşturduğunuz anahtarı seçin.

1. Anahtarın **Geçerli Sürümü** olarak GUID seçin.

1. Hem **Anahtar Sarmala** hem de **Anahtar Sarmalamasını Kaldır**'ın seçildiğinden emin olun. Power BI'da KAG'yi etkinleştirirken kullanmak üzere **Anahtar Tanımlayıcısı**'nı kopyalayın.

    ![PBIX dosyası bileşenleri](media/service-encryption-byok/key-properties.png)

### <a name="soft-delete-option"></a>Geçici silme seçeneği

Anahtarın veya anahtar kasasının yanlışlıkla silinmesi durumunda veri kaybına karşı korunmak için anahtar kasanızda [geçici silme](/azure/key-vault/key-vault-ovw-soft-delete)'yi etkinleştirmenizi öneririz. Anahtar kasasında ["geçici silme" özelliğini etkinleştirmek için PowerShell](/azure/key-vault/key-vault-soft-delete-powershell) kullanmalısınız çünkü bu seçenek henüz Azure portalında sağlanmamaktadır.

Azure Key Vault düzgün yapılandırıldığında kiracınızda KAG'yi etkinleştirmeye hazır olursunuz.

## <a name="enable-byok-on-your-tenant"></a>Kiracınızda KAG'yi etkinleştirme

Oluşturduğunuz ve Azure Key Vault'ta depoladığınız şifreleme anahtarlarını önce Power BI kiracınıza tanıtarak [PowerShell](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt.Admin)'le KAG'yi kiracı düzeyinde etkinleştirirsiniz. Ardından Premium kapasitedeki içeriği şifrelemek için bu şifreleme anahtarlarını bu kapasiteye atarsınız.

### <a name="important-considerations"></a>Önemli noktalar

KAG'yi etkinleştirmeden önce aşağıdaki noktaları aklınızda bulundurun:

- Şu anda, KAG'yi etkinleştirdikten sonra devre dışı bırakamazsınız. `Add-PowerBIEncryptionKey` için parametreleri nasıl belirttiğinize bağlı olarak KAG'yi bir veya birden çok kapasitenizde nasıl kullanacağınızı denetleyebilirsiniz. Öte yandan anahtarların kiracınıza tanıtılmasını geri alamazsınız. Daha fazla bilgi için bkz. [KAG'yi etkinleştirme](#enable-byok).

- KAG kullanan bir çalışma alanını Power BI Premium'daki ayrılmış kapasiteden paylaşılan kapasiteye _doğrudan_ taşıyamazsınız. Çalışma alanını önce KAG'nin etkinleştirilmediği bir ayrılmış kapasiteye taşımanız gerekir.

### <a name="enable-byok"></a>KAG'yi etkinleştirme

KAG'yi etkinleştirmek için Power BI hizmetinin `Connect-PowerBIServiceAccount` cmdlet'ini kullanarak oturum açmış bir kiracı yöneticisi olmalısınız. Ardından aşağıdaki örnekte gösterildiği gibi [`Add-PowerBIEncryptionKey`](/powershell/module/microsoftpowerbimgmt.admin/Add-PowerBIEncryptionKey) kullanarak KAG'yi etkinleştirin:

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
    Set-PowerBICapacityEncryptionKey-CapacityId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -KeyName 'Contoso Sales'
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
