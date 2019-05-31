---
title: Kuruluşunuzda denetim özelliğini kullanma
description: Gerçekleştirilen eylemleri izlemek ve araştırmak için Power BI ile birlikte denetim özelliklerini nasıl kullanabileceğinizi öğrenin. Güvenlik ve Uyumluluk Merkezi'ni veya PowerShell'i kullanabilirsiniz.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 559ff45974274420e2545228720000359d5fe971
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906886"
---
# <a name="use-auditing-within-your-organization"></a>Kuruluşunuzda denetim özelliğini kullanma

Kimin hangi Power BI öğeler üzerinde yaptığını bilmek, Kiracı, kuruluşunuzun Mevzuata uygunluk ve kayıt yönetimi gibi kendi gereksinimlerini karşılayacak yardımcı kritik olabilir. Power BI'ın "Raporu görüntüle" ve "Panoyu görüntüle" gibi bir kullanıcı tarafından gerçekleştirilen eylemler denetim için denetleme kullanabilir. Denetim izinlerini denetlemek için kullanamazsınız.

Denetim görevlerini Office 365 Güvenlik ve Uyumluluk Merkezi'nden gerçekleştirebilir veya bunun için PowerShell'i kullanabilirsiniz. Denetim, Power BI'ı desteklemek için otomatik olarak sağlanan Exchange Online'ın işlevselliğine dayanır.

Denetim verilerini tarih aralığını, kullanıcı, Pano, rapor, veri kümesi ve etkinlik türüne göre filtre uygulayabilirsiniz. Etkinlikler, çevrimdışı analiz için bir csv (virgülle ayrılmış değer) dosyası da indirebilirsiniz.

## <a name="requirements"></a>Gereksinimler

Denetim günlüklerine erişmek için şu gereksinimleri karşılamanız gerekir:

* Denetim günlükleri veya yalnızca görüntülenen denetim günlükleri Exchange Online Denetim günlüğüne erişmek için atanması veya bir genel yönetici ya da olmalıdır. Varsayılan olarak, bu rolleri üzerinde atanmış uyumluluk yönetimi ve kuruluş yönetim rolü grupları gelir **izinleri** Exchange Yönetim merkezinde sayfası.

    Yönetici olmayan hesaplar Denetim günlüğüne erişmesini sağlamak için kullanıcı rolü bu gruplardan birine üye eklemeniz gerekir. Bunu yapmanın istiyorsanız başka bir deyişle, Exchange Yönetim merkezinde bir özel rol grubu oluşturabilir, bu gruba denetim günlükleri veya yalnızca görüntülenen denetim günlükleri rolüne atayın ve ardından yönetici olmayan hesapta yeni rol grubuna ekleyin. Daha fazla bilgi için bkz. [Exchange Online'da rol gruplarını yönetme](/Exchange/permissions-exo/role-groups).

    Microsoft 365 yönetim merkezinden Exchange yönetim merkezine erişemiyorsanız, https://outlook.office365.com/ecp adresine gidin ve kimlik bilgilerinizi kullanarak oturum açın.

* Denetim günlüğüne erişebilir, ancak bir genel yönetici veya Power BI hizmeti yöneticisi değilseniz Power BI Yönetici portalına erişemezsiniz. Bu durumda doğrudan [Office 365 Güvenlik ve Uyumluluk Merkezi](https://sip.protection.office.com/#/unifiedauditlog) bağlantısını kullanmanız gerekir.

## <a name="access-your-audit-logs"></a>Denetim günlüklerinize erişme

Günlüklerine erişmek için öncelikle Power BI'da günlüğe kaydetmeyi etkinleştirmek emin olun. Daha fazla bilgi için yönetici portalı belgelerinin [Denetim günlükleri](service-admin-portal.md#audit-logs) bölümüne bakın. Denetimi etkinleştirme zamanı arasında bir 48 saatlik gecikme kadar olabilir ve ne zaman denetim verilerini görüntüleyebilir. Verileri hemen göremiyorsanız denetim günlüklerini daha sonra denetleyin. Denetim günlüklerini görüntüleme izni alma ile günlüklere erişebilme arasında da benzer bir gecikme olabilir.

Power BI denetim günlüklerine doğrudan [Office 365 Güvenlik ve Uyumluluk Merkezi](https://sip.protection.office.com/#/unifiedauditlog)'nden erişebilirsiniz. Power BI Yönetici portalı'ndan bir bağlantısı vardır:

1. Power BI'da seçin **dişli simgesini** seçip sağ üst köşedeki **Yönetici portalı**.

   ![Çağrılan Yönetici portalı seçeneğiyle dişli açılan menüsünün ekran görüntüsü.](media/service-admin-auditing/powerbi-admin.png)

1. **Denetim günlükleri**'ni seçin.

1. **O365 Yönetim Merkezi'ne git** seçeneğini belirleyin.

   ![Yönetim Portalı'nın ekran görüntüsü ile denetim seçeneği ve Git çekilerek Microsoft O365 Yönetim Merkezi'ne seçenekleri kaydeder.](media/service-admin-auditing/audit-log-o365-admin-center.png)

## <a name="search-only-power-bi-activities"></a>Yalnızca Power BI etkinliklerinde arama yapma

Aşağıdaki adımları izleyerek sonuçları yalnızca Power BI etkinlikleriyle sınırlayabilirsiniz. Etkinlik listesi için bu makalenin devamındaki [Power BI tarafından denetlenen etkinlikler](#activities-audited-by-power-bi) listesine bakın.

1. Üzerinde **denetim günlük araması** sayfasındaki **arama**, seçmek için açılan **etkinlikleri**.

2. **Power BI etkinlikleri**'ni seçin.

   ![Power BI etkinlikleriyle çekilerek ekran görüntüsü, denetim günlük araması.](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. Dışındaki herhangi bir alanı seçerek seçim kutusunu kapatın.

Aramalarınız yalnızca Power BI etkinlikleri döndürür.

## <a name="search-the-audit-logs-by-date"></a>Denetim günlüklerinde tarihe göre arama yapma

**Başlangıç tarihi** ve **Bitiş tarihi** alanlarını kullanarak günlüklerde tarihe göre arama yapabilirsiniz. Son yedi gün varsayılan seçimdir. Görüntü tarih ve saati Eşgüdümlü Evrensel Saat (UTC) biçiminde sunar. Belirtebileceğiniz maksimum tarih aralığı 90 gündür. 

Seçili tarih aralığı 90 günden fazlaysa hata alırsınız. 90 gün olan maksimum tarih aralığını kullanıyorsanız **Başlangıç tarihi** için içinde bulunduğunuz saati seçin. Bunu yapmamanız halinde başlangıç tarihinin bitiş tarihinden daha erken olduğunu belirten bir hata alırsınız. Denetimi son 90 gün içinde etkinleştirdiyseniz tarih aralığının başlangıç tarihi, denetimin etkinleştirildiği tarihten önceki bir gün olamaz.

![Başlangıç tarihi ve bitiş tarihi seçeneklerini, bahsedilen ile ekran görüntüsü, denetim günlük araması.](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>Denetim günlüklerinde kullanıcılara göre arama yapma

Denetim günlüğü girişlerinde belirli kullanıcılar tarafından gerçekleştirilen etkinlikler için arama yapabilirsiniz. Bir veya daha fazla kullanıcı adlarını girin **kullanıcılar** alan. Kullanıcı adı, bir e-posta adresi gibi görünüyor. Kullanıcılar, Power bı'da oturum hesabıdır. Kuruluşunuzdaki tüm kullanıcılara (ve hizmet hesaplarına) ait girişleri döndürmek için bu kutuyu boş bırakın.

![Kullanıcılara göre arama](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="view-search-results"></a>Arama sonuçlarını görüntüleme

Seçtikten sonra **arama**, arama sonuçları yükleyin. Birkaç dakika sonra altında görüntülenmesini **sonuçları**. Arama tamamlandığında bulunan sonuç sayısı gösterir. **Denetim günlük araması** en fazla 1000 olay görüntülenir. 1000'den fazla olayları arama ölçütlerini karşılıyorsanız, uygulamanın en yeni 1000 olayları görüntüler.

### <a name="view-the-main-results"></a>Ana sonuçları görüntüleme

**Sonuçları** alan arama tarafından döndürülen her olay için aşağıdaki bilgiler bulunur. Sonuçları sıralamak için **Sonuçlar** bölümündeki sütun başlıklarından birini seçin.

| **Sütun** | **Tanım** |
| --- | --- |
| Tarih |Olayın gerçekleştiği tarih ve saat (UTC biçiminde). |
| IP adresi |Oturum etkinliği için kullanılan cihazın IP adresi. Uygulamanın IP adresini bir IPv4 veya IPv6 adresi biçiminde görüntüler. |
| Kullanıcı |Olayı tetikleyen eylemi gerçekleştiren kullanıcı (veya hizmet hesabı). |
| Etkinlik |Kullanıcı tarafından gerçekleştirilen etkinlik. Bu değer, **Etkinlikler** açılan listesinde seçtiğiniz etkinliklere karşılık gelir. Exchange yönetimi denetim günlüğünden bir olay için bu sütundaki değer Exchange cmdlet olur. |
| Öğe |Nesne, oluşturulan veya karşılık gelen bir etkinliği nedeniyle değiştirilemiyor. Örneğin, görüntülenen veya değiştirilen dosya veya güncelleştirilmiş kullanıcı hesabı. Etkinliklerin hepsi için bu sütunda değer görüntülenmez. |
| Ayrıntı |Bir etkinlikle ilgili ayrıntılı bilgiler. Tekrar tüm etkinlikleri bir değere sahip. |

### <a name="view-the-details-for-an-event"></a>Olay ayrıntılarını görüntüleme

Bir olay hakkında daha fazla ayrıntı görüntülemek için arama sonuçları listesinde olay kaydı'nı seçin. A **ayrıntıları** olay kaydının ayrıntılı özelliklerini içeren sayfası açılır. **Ayrıntıları** sayfası özellikler olayın gerçekleştiği Office 365 hizmete bağlı olarak görüntüler.

Bu bilgileri görüntülemek için **Daha fazla bilgi**'yi seçin. Tüm Power BI girişlerinin RecordType özelliği 20 değerine sahiptir. Diğer özellikler hakkında bilgi için bkz. [Denetim günlüğündeki ayrıntılı özellikler](/office365/securitycompliance/detailed-properties-in-the-office-365-audit-log/).

   ![Bahsedilen daha fazla bilgi seçeneği içeren denetim Ayrıntıları iletişim kutusunun ekran görüntüsü.](media/service-admin-auditing/audit-details.png)

## <a name="export-search-results"></a>Arama sonuçlarını dışarı aktarma

Power BI denetim günlüğünü CSV dosyasına dışarı aktarmak için aşağıdaki adımları izleyin.

1. **Sonuçları dışarı aktar**'ı seçin.

1. **Yüklenen sonuçları kaydet**'i veya **Tüm sonuçları indir**'i seçin.

    ![Ekran görüntüsü dışarı aktarma seçeneği sonuçlanır.](media/service-admin-auditing/export-auditing-results.png)

## <a name="use-powershell-to-search-audit-logs"></a>Denetim günlüklerinde arama yapmak için PowerShell'i kullanma

Oturum açma bilgilerinize göre denetim günlüklerine erişmek için PowerShell'i de kullanabilirsiniz. Aşağıdaki örnekte Exchange Online PowerShell'e nasıl bağlanılacağı ve Power BI denetim günlüğü girdilerini çekmek için [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/) komutunun nasıl kullanılacağı gösterilir. Betiği çalıştırmak için bir yönetici, uygun izinleri açıklandığı atamanız gerekir [gereksinimleri](#requirements) bölümü.

```powershell
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2018 -EndDate 9/15/2018 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

Exchange Online'a bağlanma hakkında daha fazla bilgi için bkz. [Connect to Exchange Online PowerShell (Exchange Online PowerShell'e bağlanma)](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell/). Denetim günlükleriyle PowerShell kullanımı üzerine başka bir örnek için bkz. [Power BI Pro lisanslarını atamak için Power BI denetim günlüğünü ve PowerShell'i kullanma](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/).

## <a name="activities-audited-by-power-bi"></a>Power BI tarafından denetlenen etkinlikler

Aşağıdaki etkinlikleri, Power BI tarafından denetlenir:

| Kolay ad                                     | İşlem adı                              | Notlar                                  |
|---------------------------------------------------|---------------------------------------------|------------------------------------------|
| Power BI ağ geçidine veri kaynağı eklendi             | AddDatasourceToGateway                      |                                          |
| Power BI klasörüne erişim eklendi                      | AddFolderAccess                             | Şu anda kullanılmıyor                       |
| Power BI grup üyeleri eklendi                      | AddGroupMembers                             |                                          |
| Yönetici, veri akışı depolama hesabını kiracıya ekledi | AdminAttachedDataflowStorageAccountToTenant | Şu anda kullanılmıyor                       |
| Power BI veri kümesi çözümleme                         | AnalyzedByExternalApplication               |                                          |
| Power BI raporu analiz edildi                          | AnalyzeInExcel                              |                                          |
| Ağ geçidine bağlanmış Power BI veri kümesi                | BindToGateway                               |                                          |
| Kapasite durumu değiştirildi                            | ChangeCapacityState                         |                                          |
| Kapasite kullanıcı ataması değiştirildi                  | UpdateCapacityUsersAssignment               |                                          |
| Power BI veri kümesi bağlantıları değiştirildi              | SetAllConnections                           |                                          |
| Power BI ağ geçidi yöneticilerinin değiştirilmesi                   | ChangeGatewayAdministrators                 |                                          |
| Değiştirilen Power BI ağ geçidi veri kaynağı kullanıcıları        | ChangeGatewayDatasourceUsers                |                                          |
| Kurumsal Power BI içerik paketi oluşturuldu      | CreateOrgApp                                |                                          |
| Power BI uygulaması oluşturuldu                              | CreateApp                                   |                                          |
| Power BI panosu oluşturuldu                        | CreateDashboard                             |                                          |
| Power BI veri akışı oluşturuldu                         | CreateDataflow                              |                                          |
| Power BI veri kümesi oluşturuldu                          | CreateDataset                               |                                          |
| Power BI e-posta aboneliği oluşturuldu               | CreateEmailSubscription                     |                                          |
| Power BI klasörü oluşturuldu                           | CreateFolder                                |                                          |
| Power BI ağ geçidi oluşturma                          | CreateGateway                               |                                          |
| Power BI grubu oluşturuldu                            | CreateGroup                                 |                                          |
| Power BI raporu oluşturuldu                           | CreateReport                                |                                          |
| Veri akışı dış depolama hesabına geçirildi     | DataflowMigratedToExternalStorageAccount    | Şu anda kullanılmıyor                       |
| Veri akışı izinleri eklendi                        | DataflowPermissionsAdded                    | Şu anda kullanılmıyor                       |
| Veri akışı izinleri kaldırıldı                      | DataflowPermissionsRemoved                  | Şu anda kullanılmıyor                       |
| Kurumsal Power BI içerik paketi silindi      | DeleteOrgApp                                |                                          |
| Power BI açıklaması silindi                          | DeleteComment                               |                                          |
| Power BI panosu silindi                        | DeleteDashboard                             | Şu anda kullanılmıyor                       |
| Power BI veri akışı silindi                         | DeleteDataflow                              | Şu anda kullanılmıyor                       |
| Power BI veri kümesi silindi                          | DeleteDataset                               |                                          |
| Power BI e-posta aboneliği silindi               | DeleteEmailSubscription                     |                                          |
| Power BI klasörü silindi                           | DeleteFolder                                |                                          |
| Power BI klasörüne erişim silindi                    | DeleteFolderAccess                          | Şu anda kullanılmıyor                       |
| Power BI ağ geçidi silme                          | DeleteGateway                               |                                          |
| Power BI grubu silindi                            | DeleteGroup                                 |                                          |
| Power BI raporu silindi                           | DeleteReport                                |                                          |
| Power BI veri kümesi veri kaynakları keşfedildi          | GetDatasources                              |                                          |
| Power BI raporu indirme                        | DownloadReport                              |                                          |
| Power BI sertifika izni düzenlendi          | EditCertificationPermission                 | Şu anda kullanılmıyor                       |
| Power BI panosu düzenlendi                         | EditDashboard                               | Şu anda kullanılmıyor                       |
| Power BI veri kümesi düzenlendi                           | EditDataset                                 |                                          |
| Power BI veri kümesi özellikleri düzenlendi                | EditDatasetProperties                       | Şu anda kullanılmıyor                       |
| Power BI raporu düzenlendi                            | EditReport                                  |                                          |
| Power BI veri akışı dışarı aktarıldı                        | ExportDataflow                              |                                          |
| Power BI raporu görsel verileri dışarı aktarıldı              | ExportReport                                |                                          |
| Power BI kutucuk verileri dışarı aktarıldı                       | ExportTile                                  |                                          |
| Veri akışı izinleri eklenemedi                | FailedToAddDataflowPermissions              | Şu anda kullanılmıyor                       |
| Veri akışı izinleri kaldırılamadı             | FailedToRemoveDataflowPermissions           | Şu anda kullanılmıyor                       |
| Power BI veri akışı SAS belirteci oluşturuldu             | GenerateDataflowSasToken                    |                                          |
| Power BI Ekleme Belirteci oluşturuldu                    | GenerateEmbedToken                          |                                          |
| Dosya Power BI'a aktarıldı                         | İçeri Aktar                                      |                                          |
| Power BI uygulaması yüklendi                            | InstallApp                                  |                                          |
| Çalışma alanı bir kapasiteye geçirildi                  | MigrateWorkspaceIntoCapacity                |                                          |
| Power BI açıklaması gönderildi                           | PostComment                                 |                                          |
| Power BI panosu yazdırıldı                        | PrintDashboard                              |                                          |
| Power BI rapor sayfası yazdırıldı                      | PrintReport                                 |                                          |
| Power BI raporu web'de yayımlandı                  | PublishToWebReport                          |                                          |
| Key Vault'tan Power BI veri akışı gizli dizisi alındı  | ReceiveDataflowSecretFromKeyVault           | Şu anda kullanılmıyor                       |
| Veri kaynağını Power BI ağ geçidinden kaldırma         | RemoveDatasourceFromGateway                 |                                          |
| Power BI grup üyeleri kaldırıldı                    | DeleteGroupMembers                          |                                          |
| Çalışma alanı kapasiteden kaldırıldı                 | RemoveWorkspacesFromCapacity                |                                          |
| Power BI panosu yeniden adlandırıldı                        | RenameDashboard                             |                                          |
| Power BI veri akışı yenileme isteği gönderildi               | RequestDataflowRefresh                      | Şu anda kullanılmıyor                       |
| Power BI veri kümesi yenileme isteği gönderildi                | RefreshDataset                              |                                          |
| Power BI çalışma alanları alındı                     | GetWorkspaces                               |                                          |
| Power BI veri akışı üzerinde zamanlanmış yenileme ayarlandı        | SetScheduledRefreshOnDataflow               |                                          |
| Power BI veri kümesi üzerinde zamanlanmış yenileme ayarlandı         | SetScheduledRefresh                         |                                          |
| Power BI panosu paylaşıldı                         | ShareDashboard                              |                                          |
| Power BI raporu paylaşıldı                            | ShareReport                                 |                                          |
| Power BI uzatılmış deneme sürümünü başlatma                   | OptInForExtendedProTrial                    | Şu anda kullanılmıyor                       |
| Power BI deneme sürümü başlatıldı                            | OptInForProTrial                            |                                          |
| Power BI veri kaynağı devralındı                   | TakeOverDatasource                          |                                          |
| Power BI veri kümesi devralındı                        | TakeOverDataset                             |                                          |
| Power BI uygulaması yayımdan kaldırıldı                          | UnpublishApp                                |                                          |
| Kapasite kaynağı idare ayarları güncelleştirildi      | UpdateCapacityResourceGovernanceSettings    | Şu anda Microsoft 365 yönetim merkezinde değil |
| Kapasite yöneticisi güncelleştirildi                            | UpdateCapacityAdmins                        |                                          |
| Kapasitenin görünen adı güncelleştirildi                     | UpdateCapacityDisplayName                   |                                          |
| Kuruluşun Power BI ayarları güncelleştirildi          | UpdatedAdminFeatureSwitch                   |                                          |
| Power BI uygulaması güncelleştirildi                              | UpdateApp                                   |                                          |
| Power BI veri akışı güncelleştirildi                         | UpdateDataflow                              |                                          |
| Power BI veri kümesi veri kaynakları güncelleştirildi             | UpdateDatasources                           |                                          |
| Power BI veri kümesi parametreleri güncelleştirildi               | UpdateDatasetParameters                     |                                          |
| Power BI e-posta aboneliği güncelleştirildi               | UpdateEmailSubscription                     |                                          |
| Power BI klasörü güncelleştirildi                           | UpdateFolder                                |                                          |
| Power BI klasörüne erişim güncelleştirildi                    | UpdateFolderAccess                          |                                          |
| Power BI ağ geçidi veri kaynağı kimlik bilgileri güncelleştirildi  | UpdateDatasourceCredentials                 |                                          |
| Power BI panosu görüntülendi                         | ViewDashboard                               |                                          |
| Power BI veri akışı görüntülendi                          | ViewDataflow                                |                                          |
| Power BI raporu görüntülendi                            | ViewReport                                  |                                          |
| Power BI kutucuğu görüntülendi                              | ViewTile                                    |                                          |
| Power BI kullanım ölçümleri görüntülendi                     | ViewUsageMetrics                            |                                          |
|                                                   |                                             |                                          |

## <a name="next-steps"></a>Sonraki adımlar

[Power BI yönetimi nedir?](service-admin-administering-power-bi-in-your-organization.md)  

[Power BI Yönetici Portalı](service-admin-portal.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
