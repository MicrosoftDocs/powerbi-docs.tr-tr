---
title: Power BI'da SQL Server Analysis Services canlı verileri
description: Power BI'da SQL Server Analysis Services canlı verileri. Bu işlem, kurumsal ağ geçidi için yapılandırılmış olan veri kaynağı aracılığıyla gerçekleştirilir.
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: Minewiskan
ms.author: owend
ms.reviewer: ''
ms.custom: ''
ms.date: 08/10/2017
LocalizationGroup: Data from databases
ms.openlocfilehash: 00b7c98236f37505fbb0ddec81a45b65bf3e3ee6
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "73871187"
---
# <a name="sql-server-analysis-services-live-data-in-power-bi"></a>Power BI'da SQL Server Analysis Services canlı verileri

Power BI'da canlı SQL Server Analysis Services sunucusuna bağlanmak için kullanabileceğiniz iki yöntem vardır. **Veri al** ekranından SQL Server Analysis Services sunucusuna bağlanabilir veya Analysis Services sunucusuna bağlı bir [Power BI Desktop dosyası](service-desktop-files.md) veya [Excel çalışma kitabı](service-excel-workbook-files.md) ile bağlantı kurabilirsiniz. En iyi deneyim için Microsoft, zengin araç setine ve Power BI Desktop dosyasının yedek bir kopyasını yerel olarak saklama olanağına sahip olan Power BI Desktop’u kullanmanızı önerir.

>[!IMPORTANT]
> * Canlı bir Analysis Services sunucusuna bağlanmak için yönetici tarafından yüklenmiş ve yapılandırılmış bir Şirket içi veri ağ geçidi olması gerekir. Daha fazla bilgi için bkz. [Şirket içi veri ağ geçidi](service-gateway-onprem.md).
> * Ağ geçidi kullandığınızda veriler şirket içinde kalır.  Oluşturduğunuz raporlar, Power BI hizmetine kaydettiğiniz verileri kullanır. 
> * [Soru-Cevap doğal dilde sorgu özelliği](service-q-and-a-direct-query.md), Analysis Services canlı bağlantıları için önizleme sürümdedir.

## <a name="to-connect-to-a-model-from-get-data"></a>Veri al ekranından bir modele bağlanmak için

1. **Çalışma Alanım**'da **Veri al**'ı seçin. Varsa grup çalışma alanı da kullanabilirsiniz.

   ![Veri al düğmesine bağlanma](media/sql-server-analysis-services-tabular-data/connecttoas_getdatabutton.png)

2. **Veritabanları ve Daha Fazlası**'nı seçin.

   ![Veri al 1 düğmesine bağlanma](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_1.png)

3. **SQL Server Analysis Services** > **Bağlan**'ı seçin.

   ![Veri al 2 düğmesine bağlanma](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_2.png)

4. Bir sunucu seçin. Bu adımda hiç sunucu görmüyorsanız ağ geçidi veya veri kaynağı yapılandırılmamış veya hesabınız ağ geçidinde veri kaynağının **Kullanıcılar** sekmesine eklenmemiş olabilir. Yöneticinize başvurun.

5. Bağlanmak istediğiniz modeli seçin. Bu, Tablolu veya Çok Boyutlu olabilir.

Bağlandığınız model, Power BI sitesinin **Çalışma Alanım/Veri Kümeleri** sayfasında görünür. Grup çalışma alanına geçtiyseniz veri kümesi grup içinde görünür.

![Veri kümesine bağlanma](media/sql-server-analysis-services-tabular-data/connecttoas_dataset_5.png)

## <a name="dashboard-tiles"></a>Pano kutucukları

Bir rapordan panoya sabitlediğiniz görsellere ait kutucuklar 10 dakikada bir otomatik olarak yenilenir. Şirket içi Analysis Services sunucunuzdaki veriler güncelleştirilirse kutucuklar, 10 dakika sonra otomatik olarak güncelleştirilir.

## <a name="common-issues"></a>Sık Karşılaşılan Sorunlar

* Model şeması yüklenemiyor hatası - Bu hata, SSAS’ye bağlanan kullanıcının SSAS veritabanına, küpüne ve modeline erişimi olmadığında meydana gelir.

## <a name="next-steps"></a>Sonraki adımlar

* [On-premises data gateway (Şirket içi veri ağ geçidi)](service-gateway-onprem.md)  
* [Analysis Services veri kaynaklarını yönetme](service-gateway-enterprise-manage-ssas.md)  
* [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)