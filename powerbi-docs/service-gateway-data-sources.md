---
title: Veri kaynaklarını yönetme
description: Power BI’da veri kaynaklarını yönetmeyi öğrenin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Gateways
ms.openlocfilehash: 254c0033dfc64b3a0f44bcda2289fedccf2e9eda
ms.sourcegitcommit: 4222ebad1a3a32d8040f6a615a0b7f173d7869d0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71164532"
---
# <a name="manage-data-sources"></a>Veri kaynaklarını yönetme

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Power BI, her biri kendi gereksinimlerine sahip olan birçok veri kaynağını destekler. Bir ağ geçidi tek bir veri kaynağı ya da birden çok veri kaynağı için kullanılabilir. Bu örnekte veri kaynağı olarak SQL Server'ın nasıl ekleneceğini gösteriyoruz. Adımlar diğer veri kaynaklarında da benzerdir.

Veri kaynağı yönetimi işlemlerinin çoğu API’ler kullanılarak da gerçekleştirilebilir. Daha fazla bilgi için bkz. [REST API’ler (Ağ Geçitleri)](/rest/api/power-bi/gateways).

## <a name="add-a-data-source"></a>Veri kaynağı ekleme

1. Power BI hizmetinin sağ üst köşesinde ![Ayarlar dişli simgesi](media/service-gateway-data-sources/icon-gear.png) > **Ağ geçitlerini yönet** öğesini seçin.

    ![Ağ geçitlerini yönet](media/service-gateway-data-sources/manage-gateways.png)

2. Bir ağ geçidi seçin ve sonra da **Veri kaynağı ekle**'yi seçin. İsterseniz **Ağ Geçitleri** > **Veri kaynağı ekle**'ye gidin.

    ![Veri kaynağı ekleme](media/service-gateway-data-sources/add-data-source.png)

3. **Veri Kaynağı Türü**’nü seçin.

    ![SQL Server’ı seçin](media/service-gateway-data-sources/select-sql-server.png)

4. Veri kaynağı bilgilerini girin. Bu örnekte **Sunucu**, **Veritabanı** ve diğer bilgiler gereklidir. 

    ![Veri kaynağı ayarları](media/service-gateway-data-sources/data-source-settings.png)

5. SQL Server için **Kimlik Doğrulama Yöntemi** olarak **Windows** veya **Temel**  (SQL Kimlik Doğrulaması) seçeneğini belirtirsiniz. **Temel**’i seçerseniz veri kaynağınızın kimlik bilgilerini girin.

6. **Gelişmiş ayarlar** bölümünde, isteğe bağlı olarak veri kaynağınızın [gizlilik düzeyini](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540) yapılandırın ([DirectQuery](desktop-directquery-about.md) için geçerli değildir).

    ![Gelişmiş ayarlar](media/service-gateway-data-sources/advanced-settings.png)

7. **Ekle**'yi seçin. İşlem başarılı olursa *Bağlantı Başarılı* ifadesini görürsünüz.

    ![Bağlantı başarılı](media/service-gateway-data-sources/connection-successful.png)

Şimdi bu veri kaynağını kullanarak SQL Server verilerinizi Power BI pano ve raporlarına ekleyebilirsiniz.

## <a name="remove-a-data-source"></a>Veri kaynaklarını kaldırma

Artık kullanmıyorsanız veri kaynağını kaldırabilirsiniz. Bir veri kaynağını kaldırmak, o veri kaynağını kullanan panoların ve raporların çalışmamasına yol açar.

Veri kaynağını kaldırmak için veri kaynağına gidin ve **Kaldır**’ı seçin.

![Veri kaynaklarını kaldırma](media/service-gateway-data-sources/remove-data-source.png)

## <a name="use-the-data-source-for-scheduled-refresh-or-directquery"></a>Veri kaynağını zamanlanmış yenileme veya DirectQuery için kullanma

Veri kaynağı, oluşturulduktan sonra DirectQuery bağlantılarıyla veya zamanlanmış yenileme yoluyla kullanılabilir.

> [!NOTE]
>Şirket içi veri ağ geçidinde bulunan veri kaynağındaki ve Power BI Desktop’taki sunucu ve veritabanı adları eşleşmelidir.

Ağ geçidindeki veri kaynağı ve veri kümeniz arasındaki bağlantı, sunucu ve veritabanı adınızı temel alır. Bu adların eşleşmesi gerekir. Örneğin, Power BI Desktop'ta sunucu adı için bir IP Adresi sağlarsanız bu IP adresini ağ geçidi yapılandırmasındaki veri kaynağında da kullanmanız gerekir. Power BI Desktop'ta *SUNUCU\ÖRNEK* yapılandırmasını kullanırsanız ağ geçidi için yapılandırılan veri kaynağında da aynısını kullanmanız gerekir.

Ağ geçidinde yapılandırılan veri kaynağının **Kullanıcılar** sekmesinde listeleniyorsanız ve sunucu ile veritabanı adı eşleşiyorsa ağ geçidini zamanlanmış yenileme ile kullanılabilen bir seçenek olarak görürsünüz.

![Ağ geçidi bağlantısı](media/service-gateway-data-sources/gateway-connection.png)

> [!WARNING]
> Veri kümeniz birden çok veri kaynağı içeriyorsa her bir veri kaynağı, ağ geçidine eklenmelidir. Ağ geçidine bir veya daha fazla veri kaynağı eklenmezse ağ geçidini zamanlanmış yenileme için kullanılabilir olarak göremezsiniz.

### <a name="limitations"></a>Sınırlamalar

OAuth, yalnızca şirket içi veri ağ geçidine sahip özel bağlayıcılara yönelik bir desteklenen kimlik doğrulamasıdır. OAuth kimlik doğrulamasını gerekli kılan diğer veri kaynaklarını ekleyemezsiniz. Veri kümeniz OAuth kimlik doğrulaması gerektiren bir veri kaynağı içeriyorsa ve bu veri kaynağı bir özel bağlayıcı değilse, ağ geçidini zamanlanmış yenileme için kullanamazsınız.

## <a name="manage-users"></a>Kullanıcıları yönetme

Bir ağ geçidine veri kaynağı ekledikten sonra, kullanıcılara ve e-posta özellikli güvenlik gruplarına ilgili veri kaynağı (tüm ağ geçidi değil) için erişim verirsiniz. Veri kaynağı kullanıcı listesi yalnızca veri kaynağından verileri içeren raporları yayımlamasına izin verilen kullanıcıları denetler. Rapor sahipleri panolar, içerik paketleri ve uygulamalar oluşturabilir ve sonra bu öğeleri diğer kullanıcılarla paylaşabilir.

Ayrıca, kullanıcılara ve güvenlik gruplarına ağ geçidi için yönetim erişimi verebilirsiniz.

### <a name="add-users-to-a-data-source"></a>Veri kaynağına kullanıcı ekleme

1. Power BI hizmetinin sağ üst köşesinde ![Ayarlar dişli simgesi](media/service-gateway-data-sources/icon-gear.png) > **Ağ geçitlerini yönet** öğesini seçin.

2. Kullanıcıları eklemek istediğiniz veri kaynağını seçin.

3. **Kullanıcılar**’ı seçin ve kuruluşunuzda seçili veri kaynağına erişim vermek istediğiniz kullanıcıyı girin. Örneğin, aşağıdaki ekranda Maggie ve Adam'ı ekliyorsunuz.

    ![Kullanıcılar sekmesi](media/service-gateway-data-sources/users-tab.png)

4. **Ekle**’yi seçtiğinizde kutuda eklenen üyenin adı gösterilir.

    ![Kullanıcı ekleme](media/service-gateway-data-sources/add-user.png)

Kullanıcıları, erişim izni vermek istediğiniz her bir veri kaynağına eklemeniz gerektiğini unutmayın. Her veri kaynağının ayrı kullanıcı listesi vardır. Kullanıcıları her veri kaynağına ayrı ayrı ekleyin.

### <a name="remove-users-from-a-data-source"></a>Veri kaynağından kullanıcıları kaldırma

Veri kaynağının **Kullanıcılar** sekmesinde, bu veri kaynağını kullanan kullanıcıları ve güvenlik gruplarını kaldırabilirsiniz.

![Kullanıcı kaldırma](media/service-gateway-data-sources/remove-user.png)

## <a name="store-encrypted-credentials-in-the-cloud"></a>Şifrelenmiş kimlik bilgilerini bulutta depolama

Ağ geçidine bir veri kaynağı eklediğinizde bu veri kaynağına yönelik kimlik bilgilerini sağlamanız gerekir. Veri kaynağına yönelik tüm sorgular bu kimlik bilgileri kullanılarak çalıştırılır. Kimlik bilgileri güvenli bir şekilde şifrelenir. Bunlar bulutta depolanmadan önce simetrik şifrelemeyle şifrelenir. Böylece bulutta şifrelerinin çözülmesi önlenir. Kimlik bilgileri, şirket içinde ağ geçidini çalıştıran, veri kaynaklarına erişildiği zaman şifrelerinin çözüldüğü makineye gönderilir.

## <a name="list-of-available-data-source-types"></a>Kullanılabilir veri kaynağı türlerinin listesi

Şirket içi veri ağ geçidi, Power BI için aşağıdaki veri kaynaklarını destekler. Şirket içi veri kaynaklarının yanı sıra, bir güvenlik duvarının arkasındaki kaynaklar, VPN’ler veya sanal ağlar için de bir veri ağ geçidi gerekebilir.

| **Veri kaynağı** | **Canlı/DirectQuery** | **El ile veya zamanlanmış yenileme (kullanıcı tarafından yapılandırılmış)** |
| --- | --- | --- |
| Amazon Redshift |Evet |Evet |
| Analysis Services |Evet |Evet |
| AtScale küpleri |Evet |Evet |
| Azure Active Directory |Hayır |Evet |
| Azure Blob depolama |Hayır |Evet |
| Azure DevOps Server |Hayır |Evet |
| Azure Tablo depolama |Hayır |Evet |
| BI Bağlayıcısı |Evet |Evet |
| Denodo |Evet |Evet |
| Dremio |Evet |Evet |
| EmigoDataSourceConnector |Hayır |Evet |
| Essbase |Evet |Evet |
| Exasol |Evet |Evet |
| Dosya |Hayır |Evet |
| Klasör |Hayır |Evet |
| Paxata |Hayır |Evet |
| IBM DB2 |Evet |Evet |
| IBM Informix Veritabanı |Hayır |Evet |
| IBM Netezza |Evet |Evet |
| Impala |Evet |Evet |
| Jethro ODBC |Evet |Evet |
| Kyligence Enterprise |Evet |Evet |
| MarkLogic ODBC |Evet |Evet |
| Microsoft Graph Güvenliği |Hayır |Evet |
| MySQL |Hayır |Evet |
| ODBC |Hayır |Evet |
| OData |Hayır |Evet |
| OLE DB |Hayır |Evet |
| Oracle |Evet |Evet |
| PostgreSQL |Hayır |Evet |
| QubolePresto |Evet |Evet |
| Quick Base Bağlayıcısı |Hayır |Evet |
| SAP Business Warehouse İleti Sunucusu |Evet |Evet |
| SAP Business Warehouse Sunucusu |Evet |Evet |
| SAP HANA |Evet |Evet |
| SQL Server |Evet |Evet |
| SharePoint |Hayır |Evet |
| Snowflake |Evet |Evet |
| Spark |Evet |Evet |
| SurveyMonkey |Hayır |Evet |
| Sybase |Hayır |Evet |
| TeamDesk.Database |Hayır |Evet |
| Teradata |Evet |Evet |
| Vertica |Evet |Evet |
| Web |Hayır |Evet |
| Workforce Dimensions |Hayır |Evet |

## <a name="next-steps"></a>Sonraki adımlar

* [Veri kaynağınızı yönetme - Analysis Services](service-gateway-enterprise-manage-ssas.md)
* [Veri kaynağınızı yönetme - SAP HANA](service-gateway-enterprise-manage-sap.md)
* [Veri kaynağınızı yönetme - SQL Server](service-gateway-enterprise-manage-sql.md)
* [Veri kaynağınızı yönetme - Oracle](service-gateway-onprem-manage-oracle.md)
* [Veri kaynağınızı yönetme - İçeri aktarma/zamanlanmış yenileme](service-gateway-enterprise-manage-scheduled-refresh.md)
* [Veri ağ geçidi dağıtmaya ilişkin yönergeler](service-gateway-deployment-guidance.md)

Başka bir sorunuz mu var? [Power BI Topluluğu](http://community.powerbi.com/)'nu deneyin.
