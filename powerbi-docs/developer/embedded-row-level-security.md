---
title: "Power BI katıştırılmış içeriğiyle satır düzeyi güvenliği kullanma"
description: "Power BI içeriğini uygulamanıza eklemek için gerçekleştirmeniz gereken işlemler hakkında bilgi edinin."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/21/2017
ms.author: asaxton
ms.openlocfilehash: ffaf4439f48b23dcff8e965b5bea1aeaf19afcc0
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="use-row-level-security-with-power-bi-embedded-content"></a>Power BI katıştırılmış içeriğiyle satır düzeyi güvenliği kullanma
Pano, kutucuk, rapor ve veri kümelerindeki verilere kullanıcı erişimini kısıtlamak için satır düzeyi güvenlik (RLS) kullanılabilir. Birçok farklı kullanıcı, aynı yapıtlarla farklı veriler görerek çalışabilir. Ekleme işlemlerinde RLS desteklenir.

Tipik bir ISV senaryosunda olduğu gibi, Power BI harici kullanıcılar (verilerin sahibinin uygulama olduğu) için ekleme yapıyorsanız bu makale tam size göre! Kullanıcı ve rol için ekleme belirtecini yapılandırmanız gerekir. Bunu nasıl yapacağınızı öğrenmek için okumaya devam edin.

Kuruluşunuzun içindeki Power BI kullanıcıları (verilerin sahibinin kullanıcı olduğu) için ekleme yapıyorsanız RLS, Power BI hizmetinde olduğu gibi çalışır. Uygulamada yapmanız gereken farklı bir işlem yoktur. Daha fazla bilgi için bkz. [Power BI ile satır düzeyi güvenlik (RLS)](../service-admin-rls.md).

![Satır Düzeyi Güvenlik ile ilgili öğeler.](media/embedded-row-level-security/powerbi-embedded-rls-components.png)

RLS'den faydalanmak için üç ana kavramı anlamak önemlidir: Kullanıcılar, Roller ve Kurallar. Şimdi her birine daha yakından bakalım:

**Kullanıcılar**: Yapıtı (pano, kutucuk, rapor veya veri kümesi) görüntüleyen son kullanıcılar. Power BI Embedded'da kullanıcılar bir ekleme belirteci içindeki kullanıcı adı özelliği ile tanımlanır.

**Roller**: Kullanıcılar rollere aittir. Rol, kural kapsayıcısıdır ve *Satış Yöneticisi* veya *Satış Temsilcisi* gibi adlar verilebilir. Rolleri Power BI Desktop uygulamasından oluşturabilirsiniz. Daha fazla bilgi için bkz. [Power BI Desktop ile satır düzeyi güvenlik (RLS)](../desktop-rls.md).

**Kurallar**: Roller kurallara sahiptir ve bu kurallar, verilere uygulanacak gerçek filtrelerdir. Bunlar "Country = USA" gibi basit veya daha dinamik içerikler olabilir.
Bu makalenin kalan bölümünde RLS yazma örneği verecek ve bunu katıştırılmış uygulama içinde kullanacağız. Örneğimizde [Retail Analysis Sample](http://go.microsoft.com/fwlink/?LinkID=780547) PBIX dosyası kullanılmıştır.

![Rapor örneği](media/embedded-row-level-security/powerbi-embedded-report-example.png)

## <a name="adding-roles-with-power-bi-desktop"></a>Power BI Desktop ile rol ekleme
Retail Analysis Sample dosyamızda bir perakende zincirindeki tüm mağazaların satış rakamları gösterilmektedir. RLS kullanılmadığında oturum açıp raporu görüntüleyen tüm bölge yöneticileri aynı verileri görmektedir. Üst yönetim, her bölge yöneticisinin yalnızca kendi yönettiği mağazaların satış rakamlarını görebilmesini talep etmiştir. Bunu yapmak için RLS'den faydalanabiliriz.

RLS, Power BI Desktop uygulamasında gerçekleştirilir. Veri kümesini ve raporu açtığımızda şema görünümüne geçerek şemayı görebiliriz:

![Power BI Desktop'ta şema görünümü](media/embedded-row-level-security/powerbi-embedded-schema.png)

Bu şemada dikkat etmeniz gereken birkaç nokta mevcuttur:

* **Total Sales** gibi tüm ölçüler **Sales** olgu tablosunda depolanmaktadır.
* İlgili dört ek boyut tablosu daha mevcuttur: **Item**, **Time**, **Store** ve **District**.
* İlişki çizgilerindeki oklar, filtrelerin bir tablodan diğerine akış yönünü gösterir. Örneğin **Time[Date]** için bir filtre uygulandığında geçerli şemada yalnızca **Sales** tablosundaki değerler filtrelenecektir. İlişki çizgilerindeki tüm oklar Sales tablosunu işaret ettiği için bu filtreden etkilenecek başka tablo yoktur.
* **District** tablosu, her bölgenin yöneticisini göstermektedir:
  
    ![Disctrict tablosundaki satırlar](media/embedded-row-level-security/powerbi-embedded-district-table.png)

Bu şemaya göre **District** tablosundaki **District Manager** sütununa bir filtre uyguladığımızda ve filtre raporu görüntüleyen kullanıcıyla eşleştiğinde bu filtre **Store** ve **Sales** tablolarını da yalnızca ilgili bölge yöneticisine ait verileri gösterecek şekilde filtreleyecektir.

Aşağıdaki adımları uygulayın:

1. **Modelleme** sekmesinde **Rolleri Yönet**'i seçin.
   
    ![Power BI Desktop'taki Modelleme sekmesi](media/embedded-row-level-security/powerbi-embedded-manage-roles.png)
2. **Manager** adlı yeni bir rol oluşturun.
   
    ![Yeni rol oluşturma](media/embedded-row-level-security/powerbi-embedded-new-role.png)
3. **District** tablosuna aşağıdaki DAX deyimini girin: **[District Manager] = USERNAME()**.
   
    ![RLS kuralı için DAX deyimi](media/embedded-row-level-security/powerbi-embedded-new-role-dax.png)
4. Kuralların çalıştığından emin olmak için **Modelleme** sekmesinde **Rol olarak görüntüle**'yi ve ardından az önce oluşturduğunuz **Manager** rolünü ve **Other user** öğesini seçin. Kullanıcı olarak **Andrew Ma** girin.
   
    ![Rol olarak görüntüle iletişim kutusu](media/embedded-row-level-security/powerbi-embedded-new-role-view.png)
   
    Raporlarda **Andrew Ma** olarak oturum açıldığında görüntülenecek veriler gösterilir.

Buradaki gibi filtreyi uyguladığımızda **District**, **Store** ve **Sales** tablolarındaki tüm kayıtlar filtrelenir. Ancak **Sales** ile **Time**, **Sales** ile **Item** ve **Item** ile **Time** tabloları arasındaki ilişkilerdeki filtre yönü nedeniyle tablolarda filtreleme yapılmaz. İki yönlü çapraz filtreleme hakkında daha fazla bilgi edinmek için [Bidirectional cross-filtering in SQL Server Analysis Services 2016 and Power BI Desktop (SQL Server Analysis Services 2016 ve Power BI Desktop'ta iki yönlü çapraz filtreleme)](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) teknik incelemesini indirin.

## <a name="applying-user-and-role-to-an-embed-token"></a>Ekleme belirtecine kullanıcı ve rol uygulama
Power BI Desktop rollerini yapılandırdınız ancak uygulamanızın rollerden faydalanabilmesi için yapmanız gereken birkaç işlem daha bulunmaktadır.

Kullanıcıların kimlik doğrulaması ve yetkilendirmesi uygulama tarafından gerçekleştirilir ve kullanıcıya belirli bir Power BI Embedded raporuna erişim izni vermek için ekleme belirteçleri kullanılır. Power BI Embedded, kullanıcıyla ilgili belirli bilgilere sahip değildir. RLS'nin çalışması için ekleme belirtecinin bir parçası olarak kimlik biçiminde iletmeniz gereken ek bağlam vardır. Bu işlem [GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx) API'si tarafından gerçekleştirilir.

[GenerateToken](https://msdn.microsoft.com/library/mt784614.aspx) API'si, ilgili veri kümelerini belirten bir kimlik listesini kabul eder. RLS'nin çalışması için aşağıdakileri kimlikle birlikte iletmeniz gerekir.

* **username (zorunlu)**: Bu dize RLS kurallarını uygularken kullanıcının kimliğini belirlemeye yardımcı olmak için kullanılabilir. Yalnızca tek bir kullanıcı listelenebilir.
* **roles (zorunlu)**: Satır Düzeyi Güvenlik kurallarını uygularken seçilecek rolleri içeren dize. Birden fazla rol iletiliyorsa dize dizisi olarak iletilmesi gerekir.
* **dataset (zorunlu)**: Eklediğiniz yapıtla ilgili veri kümesi. 

**GenerateTokenInGroup** yöntemini **PowerBIClient.Reports** üzerinde kullanarak ekleme belirtecini oluşturabilirsiniz. 

Örneğin [PowerBIEmbedded_AppOwnsData](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) örneğini değiştirebilirsiniz. *Home\HomeController.cs satır 76 ve 77* şu değerden:

```
// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync(GroupId, report.Id, generateTokenRequestParameters);
```

şu değere güncelleştirilebilir:

```
var generateTokenRequestParameters = new GenerateTokenRequest("View", null, identities: new List<EffectiveIdentity> { new EffectiveIdentity(username: "username", roles: new List<string> { "roleA", "roleB" }, datasets: new List<string> { "datasetId" }) });

var tokenResponse = await client.Reports.GenerateTokenInGroupAsync("groupId", "reportId", generateTokenRequestParameters);
```

REST API'sini çağırıyorsanız güncelleştirilmiş API artık kullanıcı adı, dize rolleri listesi ve dize veri kümesi listesini içeren **identities** adlı ek bir JSON dizisi kabul etmektedir. Örnek:

```
{
    "accessLevel": "View",
    "identities": [
        {
            "username": "EffectiveIdentity",
            "roles": [ "Role1", "Role2" ],
            "datasets": [ "fe0a1aeb-f6a4-4b27-a2d3-b5df3bb28bdc" ]
        }
    ]
}
```

Tüm parçaları bir araya getirdiniz. Artık bir kullanıcı uygulamanızda oturum açıp bu yapıtı görüntülemek istediğinde, belirlediğiniz satır düzeyi güvenliğe uygun şekilde, yalnızca görme iznine sahip olduğu verileri görebilir.

## <a name="working-with-analysis-services-live-connections"></a>Analysis Services canlı bağlantılarıyla çalışma
Satır düzeyi güvenlik şirket içi sunucular için Analysis Services canlı bağlantılarıyla birlikte kullanılabilir. Bu bağlantı türünü kullanırken anlamanız gereken birkaç belirli kavram vardır.

Kullanıcı adı özelliği için sunulan etkin kimliğin, Analysis Services sunucusunda gerekli izinlere sahip bir Windows kullanıcısı olması gerekir.

**Şirket içi veri ağ geçidi yapılandırması**

Analysis Services canlı bağlantılarıyla çalışırken bir [şirket içi veri ağ geçidi](../service-gateway-onprem.md) kullanılır. Listelenmiş bir kimlikle ekleme belirteci oluştururken ana hesabın ağ geçidinin yöneticisi olarak listelenmesi gerekir. Ana hesap listelenmezse satır düzeyi güvenlik, özelliği verilere uygulamaz. Ağ geçidinde yönetici olmayan bir kullanıcı, rolleri sağlayabilir ancak etkin kimlik için kendi kullanıcı adını belirtmesi gerekir.

**Rollerin kullanılması**

Roller bir ekleme belirteci içinde kimlikle birlikte sağlanabilir. Rol sağlanmazsa ilgili rolleri çözümlemek için sağlanmış olan kullanıcı adı kullanılır.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar
* Power BI hizmetinde kullanıcıların rollere atanması, ekleme belirteci kullanıldığında RLS'yi etkilemez.
* Power BI hizmeti RLS ayarını yöneticilere veya düzenleme izni olan üyelere uygulamaz ancak ekleme belirteciyle ilettiğiniz kimlikler verilere uygulanır.
* Analysis Services canlı bağlantıları şirket içi sunucular için desteklenmektedir.
* Azure Analysis Services canlı bağlantılarında role göre filtreleme özelliği desteklenir ancak kullanıcı adına göre dinamik filtreleme yapılamaz.
* Temel alınan veri kümesi RLS gerektirmiyorsa GenerateToken isteğinin etkin kimlik **içermemesi** gerekir.
* Temel alınan veri kümesi bir bulut modeliyse (önbelleğe alınmış model veya DirectQuery) etkin kimliğin en az bir rol içermesi gerekir. Aksi halde, rol ataması gerçekleşmez.
* Kimlik listesi sayesinde, pano ekleme işlemi için birden çok kimlik belirteci kullanılabilir. Diğer tüm yapıtlar için liste tek bir kimlik içerir.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

