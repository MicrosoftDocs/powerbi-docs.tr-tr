---
title: "Power BI Desktop'ta Azure Tüketim Öngörüleri verilerine bağlanma (Beta)"
description: "Power BI Desktop'ı kullanarak Azure'a kolayca bağlanın ve hem tüketim hem de kullanım ile ilgili öngörüler edinin"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9127f7b2e19a304c514d5e6449cf1ceb7ecddb13
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-azure-consumption-insights-in-power-bi-desktop-beta"></a>Power BI Desktop'ta Azure Tüketim Öngörüleri'ne bağlanma (Beta)
**Azure Tüketim Öngörüleri** bağlayıcısı ile Azure'a bağlanıp kuruluşunuzun Azure hizmetleri kullanımı hakkında ayrıntılı veri ve bilgi edinmek için **Power BI Desktop** uygulamasını kullanabilirsiniz. Ayrıca, kuruluşunuzun Azure kullanımını raporlamak ve paylaşmak için ölçüler, özel sütunlar ve görseller oluşturabilirsiniz. **Azure Tüketim ve Öngörüleri** bağlayıcısının bu sürümü Beta sürümünde olup değişikliğe tabidir.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01.png)

Bu makalede, **Azure Tüketim Öngörüleri** bağlayıcısını kullanarak bağlanıp ihtiyacınız olan verileri alma ve Azure Kurumsal Bağlayıcısından geçiş yapma hakkında bilgi edinmenin yanı sıra **ACI** (Azure Tüketim Öngörüleri) API'sinde bulunan *kullanım ayrıntıları sütunlarına* ilişkin bir eşleme bulacaksınız.

## <a name="connect-to-azure-consumption-insights"></a>Azure Tüketim Öngörüleri'ne bağlanma
**Azure Tüketim Öngörüleri** bağlayıcısını kullanarak başarıyla bağlanmak için Azure portalında Kurumsal sürümünün özelliklerine erişiminizin olması gerekir.

**Azure Tüketim Öngörüleri** bağlayıcısını kullanarak bağlanmak için **Power BI Desktop**'taki **Giriş** şeridinde **Veri Al**'ı seçin. Soldaki kategorilerden **Çevrimiçi Hizmetler**'i seçtiğinizde **Microsoft Azure Tüketim Öngörüleri (Beta)** seçeneğini görürsünüz. **Bağlan**'ı seçin.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01b.png)

Görüntülenen iletişim kutusuna *Kayıt Numaranızı* girin.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_02.png)

* Kayıt numaranızı, [Azure Enterprise Portal](https://ea.azure.com)'da aşağıdaki görüntüde gösterilen konuma giderek bulabilirsiniz.
  
  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_08.png)
  
  Bağlayıcının bu sürümü, yalnızca https://ea.azure.com sayfasından gelen kurumsal kayıtları destekler. Çin'e ait kayıtlar şu anda desteklenmemektedir.

Bağlanmak için *Erişim anahtarınızı* girin.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_03.png)

* Kayıt için Erişim anahtarınızı [Azure Enterprise Portal](https://ea.azure.com)'da bulabilirsiniz.
  
  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_09.png)

*Erişim anahtarınızı* girip **Bağlan**'ı seçtiğinizde bir **Gezgin** penceresi açılır. Bu pencerede, kullanımınıza sunulan *Summaries*, *UsageDetails*, *PriceSheets* ve *Marketplace* adlı dört tablo gösterilir. Önizlemeyi görmek için herhangi bir tablonun yanındaki onay kutusunu seçebilirsiniz. Tablo adlarının yanlarında bulunan kutuları işaretleyerek bir veya birden fazla tablo seçebilir ve ardından **Yükle** seçeneğini belirleyebilirsiniz.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_04.png)

> [!NOTE]
> *Summaries ve *PriceSheets* tabloları yalnızca kayıt düzeyindeki API Anahtarı için kullanılabilir. Ayrıca, *UsageDetails* ve *PriceSheets* tabloları, varsayılan olarak geçerli aya ilişkin verileri içerir. *Summaries* ve *Marketplace* tabloları, geçerli ay ile sınırlı değildir.
> 
> 

**Yükle**'yi seçtiğinizde veriler, **Power BI Desktop**'a yüklenir.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_05.png)

Belirlediğiniz veriler yüklendikten sonra, seçtiğiniz tabloları ve alanları **Alanlar** bölmesinde görebilirsiniz.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_06.png)

## <a name="using-azure-consumption-insights"></a>Azure Tüketim Öngörüleri'ni kullanma
**Azure Tüketim Öngörüleri** bağlayıcısını kullanabilmek için Azure portalında Kurumsal özelliklerine erişiminizin olması gerekir.

**Azure Tüketim Öngörüleri** bağlayıcısı aracılığıyla verileri başarıyla yüklediğinizde, **Sorgu Düzenleyicisi**'ni kullanarak kendi özel ölçülerinizi ve sütunlarınızı oluşturabilir; **Power BI hizmetinde** paylaşabileceğiniz görseller, raporlar ve panolar elde edebilirsiniz.

Azure'da boş bir sorgu kullanarak alabileceğiniz bir dizi örnek özel sorgu da mevcuttur. Bunun için **Power BI Desktop**'ın **Giriş** şeridindeki **Veri Al** düğmesinde bulunan açılan menü okunu ve ardından **Boş Sorgu**'yu seçin. Ayrıca bu işlemi **Sorgu Düzenleyicisi**'nin sol tarafındaki **Sorgular** bölmesinde sağ tıklayıp görünen menüde **Yeni Sorgu > Boş Sorgu** seçeneğini belirleyerek de yapabilirsiniz.

**Formül çubuğuna** aşağıdakileri yazın:

    = MicrosoftAzureConsumptionInsights.Contents

Aşağıdaki görüntüde olduğu gibi bir dizi örnek görünür.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_07.png)

Raporlarla çalışırken ve sorgu oluştururken aşağıdakileri kullanın:

* Geçerli tarihten itibaren ay sayısını tanımlamak için *noOfMonths* parametresini kullanın
  * Geçerli tarihten itibaren kaç aya ilişkin verileri içeri aktarmak istediğinizi belirtmek için 1 ile 36 arasında bir değer kullanın. İçeri aktarma kısıtlamalarıyla karşılaşmamak ve Power BI'da sorgular için izin verilen veri hacmi eşiğini aşmamak için en fazla 12 aya ait verileri almanızı öneririz.
* Tarihteki bir ay aralığını tanımlamak için *startBillingDataWindow* ve *endBillingDataWindow* parametrelerini kullanın
* *noOfMonths* parametresini, *startBillingDataWindow* veya *endBillingDataWindow* parametreleri ile birlikte *kullanmayın*

## <a name="migrating-from-the-azure-enterprise-connector"></a>Azure Kurumsal Bağlayıcısı'ndan geçiş yapma
Bazı müşterilerin, kullanımdan kaldırılarak **Azure Tüketim Öngörüleri** bağlayıcısı ile değiştirilecek olan *Azure Kurumsal Bağlayıcısı (Beta)* aracılığıyla oluşturduğu görseller vardır. **Azure Tüketim Öngörüleri** bağlayıcısı, aşağıdakilerin de dahil olduğu bazı özellikler ve iyileştirmeler içerir:

* *Bakiye Özeti* ve *Market Alışverişleri* için kullanılabilen ek veri kaynakları
* *startBillingDataWindow* ve *endBillingDataWindow* gibi yeni ve gelişmiş parametreler
* Daha iyi performans ve yanıtlama hızı

Müşterilerin yeni **Azure Tüketim Öngörüleri** bağlayıcısına geçiş yapmalarına yardımcı olmak ve özel panolar veya raporlar oluşturarak ortaya koydukları çalışmaları korumak için aşağıdaki adımlarda, yeni bağlayıcıya nasıl geçiş yapılacağı gösterilmektedir.

### <a name="step-1-connect-to-azure-using-the-new-connector"></a>1. Adım: Yeni bağlayıcıyı kullanarak Azure'a bağlanma
İlk adım, **Azure Tüketim Öngörüleri** bağlayıcısını kullanarak Azure'a bağlanmaktır. Bu işlemi nasıl gerçekleştireceğiniz, makalenin önceki kısımlarında ayrıntılı olarak açıklanmıştır. Bu adımda **Power BI Desktop**'taki **Giriş** şeridinde **Veri Al > Boş Sorgu** seçeneğini belirleyin.

### <a name="step-2-use-the-advanced-editor-to-create-a-query"></a>2. Adım: Gelişmiş Düzenleyici'yi kullanarak bir sorgu oluşturma
**Sorgu Düzenleyicisi**'ndeki **Giriş** şeridinin **Sorgu** bölümünde **Gelişmiş Düzenleyici**'yi seçin. Açılan **Gelişmiş Düzenleyici** penceresine aşağıdaki sorguyu girin.

    let    
        enrollmentNumber = "100",
        optionalParameters = [ numberOfMonth = 6, dataType="DetailCharges" ],
        data = MicrosoftAzureConsumptionInsights.Contents(enrollmentNumber, optionalParameters)   
    in     
        data

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_10.png)

*enrollmentNumber* değerini kendi kayıt numaranızla değiştirmeniz gerektiğini unutmayın. Bu numaraya [Azure Enterprise Portal](https://ea.azure.com)'dan ulaşabilirsiniz. *numberOfMonth* parametresi, güncel verilerden itibaren kaç ay öncesine ait verileri almak istediğinizi belirtir. Geçerli ay için sıfır (0) değerini kullanın.

**Gelişmiş Düzenleyici** penceresinde **Bitti**'yi seçtiğinizde önizleme yenilenir ve tabloda, belirtilen ay aralığına ilişkin verileri görürsünüz. **Kapat & Uygula**'yı seçip geri dönün.

### <a name="step-3-move-measures-and-custom-columns-to-the-new-report"></a>3. Adım: Ölçüleri ve özel sütunları yeni rapora taşıma
Bu adımda, oluşturduğunuz özel sütunları veya ölçüleri yeni ayrıntılar tablosuna taşımanız gerekir. Uygulamanız gereken adımlar:

1. Not Defteri'ni (veya başka bir metin düzenleyiciyi) açın.
2. Taşımak istediğiniz ölçüyü seçin ve *Formül* alanındaki metni kopyalayıp Not Defteri'ne yerleştirin.
   
   ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_11.png)
3. İlk ayrıntılar tablosunu *Query1* olarak yeniden adlandırın.
4. Tablonuza sağ tıklayıp **Yeni Ölçü**'yü seçerek yeni ölçüler ve özel sütunlar oluşturduktan sonra, tamamı bitene kadar mağaza ölçülerinizi ve sütunlarınızı kesip yapıştırın.

### <a name="step-4-re-link-tables-that-had-relationships"></a>4. Adım: İlişkili tabloları yeniden bağlantılı hale getirme
Pek çok panoda, arama veya filtreleme için kullanılan ek tablolar (tarih tabloları veya özel projeler için kullanılan tablolar gibi) bulunur. Bu ilişkiler yeniden oluşturulduğunda, kalan sorunların büyük kısmı çözülmüş olur. Bunun nasıl yapılacağı aşağıda açıklanmaktadır.

- **Power BI Desktop**'taki **Modelleme** sekmesinde **İlişkileri Yönet**'i seçtiğinizde, söz konusu modeldeki ilişkileri yönetmenize olanak sağlayan bir pencere açılır. Tablolarınızı gereken şekilde yeniden bağlantılı hale getirin.
   
    ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_12.png)

### <a name="step-5-verify-your-visuals-and-adjust-field-formatting-as-needed"></a>5. Adım: Görsellerinizi doğrulama ve alan biçimlendirmesini gereken şekilde ayarlama
Bu aşamaya kadar geldiğinize göre görselleriniz, tablolarınız ve detaylandırma özelliklerinizin çoğu beklendiği şekilde çalışır. Ancak, her şeyin istediğiniz gibi görünmesini sağlamak üzere biçimlendirme için bazı ince ayarlar yapmanız gerekebilir. Her bir panonuzu ve görselinizi hızlıca inceleyerek istediğiniz gibi göründüğünden emin olun.

## <a name="using-the-azure-consumption-and-insights-aci-api-to-get-consumption-data"></a>Kullanım verilerini almak için Azure Tüketim Öngörüleri (ACI) API'sini kullanma
Azure tarafından sağlanan bir [**Azure Tüketim Öngörüleri (ACI) API**](https://azure.microsoft.com/blog/announcing-general-availability-of-consumption-and-charge-apis-for-enterprise-azure-customers/)'si de mevcuttur. ACI API'sini kulla6narak Azure kullanım bilgilerini toplama, raporlama ve görselleştirmeye yönelik kendi özel çözümlerinizi oluşturabilirsiniz.

### <a name="mapping-names-and-usage-details-between-the-portal-the-connector-and-the-api"></a>Adları ve kullanım ayrıntılarını portal, bağlayıcı ve API arasında eşleme
Azure Portal'daki ayrıntı sütunları ve adları API ve bağlayıcıda benzerdir ancak her zaman aynı değildir. Daha açıklayıcı olması açısından aşağıdaki tabloda API, bağlayıcı ve Azure Portal'da gördüğünüz sütunlar arasında eşleme yapılmıştır. Ayrıca, ilgili sütunun kullanımdan kaldırılıp kaldırılmadığı da belirtilmiştir. Daha fazla bilgi ve bu terimlerin tanımları için [Azure faturalama veri sözlüğüne](https://docs.microsoft.com/azure/billing/billing-enterprise-api-usage-detail) göz atın.

| ACI Bağlayıcısı/İçerik Paketi Sütun Adı | ACI API'si Sütun Adı | EA Sütun Adı | Kullanımdan kalktı/Geriye dönük uyumluluk için mevcut |
| --- | --- | --- | --- |
| AccountName |accountName |Hesap Adı |Hayır |
| AccountId |accountId | |Evet |
| AccountOwnerId |accountOwnerEmail |AccountOwnerId |Hayır |
| AdditionalInfo |additionalInfo |AdditionalInfo |Hayır |
| AdditionalInfold | | |Evet |
| Tüketilen Miktar |consumedQuantity |Tüketilen Miktar |Hayır |
| Tüketim Hizmeti |consumedService |Tüketim Hizmeti |Hayır |
| ConsumedServiceId |consumedServiceId | |Evet |
| Maliyet |cost |ExtendedCost |Hayır |
| Maliyet Merkezi |costCenter |Maliyet Merkezi |Hayır |
| Tarih |date |Tarih |Hayır |
| Gün | |Gün |Hayır |
| DepartmentName |departmentName |Bölüm Adı |Hayır |
| DepartmentID |departmentId | |Evet |
| Örnek Kimliği | | |Evet |
| InstanceId |instanceId |Örnek Kimliği |Hayır |
| Konum | | |Evet |
| Sayaç Kategorisi |meterCategory |Sayaç Kategorisi |Hayır |
| Ölçüm kimliği | | |Evet |
| Sayaç Adı |meterName |Sayaç Adı |Hayır |
| Tarife Bölgesi |meterRegion |Tarife Bölgesi |Hayır |
| Sayaç Alt Kategorisi |meterSubCategory |Sayaç Alt Kategorisi |Hayır |
| MeterId |meterId |Ölçüm kimliği |Hayır |
| Ay | |Ay |Hayır |
| Ürün |product |Ürün |Hayır |
| ProductId |productId | |Evet |
| Kaynak Grubu |resourceGroup |Kaynak Grubu |Hayır |
| Kaynak Konumu |resourceLocation |Kaynak Konumu |Hayır |
| ResourceGroupId | | |Evet |
| ResourceLocationId |resourceLocationId | |Evet |
| ResourceRate |resourceRate |ResourceRate |Hayır |
| ServiceAdministratorId |serviceAdministratorId |ServiceAdministratorId |Hayır |
| ServiceInfo1 |serviceInfo1 |ServiceInfo1 |Hayır |
| ServiceInfo1Id | | |Evet |
| ServiceInfo2 |serviceInfo2 |ServiceInfo2 |Hayır |
| ServiceInfo2Id | | |Evet |
| Depolama Hizmeti Tanımlayıcısı |storeServiceIdentifier |Depolama Hizmeti Tanımlayıcısı |Hayır |
| StoreServiceIdentifierId | | |Evet |
| Abonelik Adı |subscriptionName |Abonelik Adı |Hayır |
| Etiketler |tags |Etiketler |Hayır |
| TagsId | | |Evet |
| Ölçü Birimi |unitOfMeasure |Ölçü Birimi |Hayır |
| Yıl | |Yıl |Hayır |
| SubscriptionId |subscriptionId |SubscriptionId |Evet |
| SubscriptionGuid |subscriptionGuid |SubscriptionGuid |Hayır |

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md)
* [Power BI Desktop'taki veri kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   

