---
title: Ağ geçidi performansı izleme (genel Önizleme)
description: Bu makalede, şirket içi veri ağ geçidi etkinlikleri performansını izleme hakkında bilgi sağlar.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 05/08/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 8c5f4170383f31ea465ebb7035aebfb53f551982
ms.sourcegitcommit: af2b2238fe77eaa1b2392a19a143a0250b8665cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2019
ms.locfileid: "65535379"
---
# <a name="gateway-performance-monitoring-public-preview"></a>Ağ geçidi performansı izleme (genel Önizleme)

Performansını izlemek için ağ geçidi yöneticilerinin geleneksel olarak performans sayaçları Windows Performans İzleyicisi aracı üzerinden el ile izleme temel bir işleve bağımlı. Artık ek sorgu günlüğü sunuyoruz ve [ağ geçidi performans PBI şablon dosyası](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) sonuçların görselleştirilmesi için. Bu özellik, ağ geçidi kullanımı hakkında yeni Öngörüler sağlar ve düşük performanslı sorguların gidermenize olanak tanır.

> [!NOTE]
> Bu özellik şu anda yalnızca standart modda şirket içi veri ağ geçidi ve kişisel mod için kullanılabilir.

## <a name="enable-performance-logging"></a>Performans günlüğünü etkinleştirme

Bu özelliği etkinleştirmek için aşağıdaki değişiklikleri *Microsoft.powerbı.datamovement.Pipeline.gatewaycore.dll.config* dosyası "\Program Files\On-şirket içi veri ağ geçidi" klasörü:

1. Güncelleştirme **QueryExecutionReportOn** için _True_ ağ geçidini kullanarak yürütülen sorgular için ek günlük kaydını etkinleştirmek için. Bu seçeneğin etkinleştirilmesi, sorgu yürütme raporu hem sorgu yürütme toplama raporu dosyaları oluşturur.

   ``` xml
   <setting name="QueryExecutionReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. Güncelleştirme **SystemCounterReportOn** için _True_ bellek ve CPU sistem sayaçlar için ek günlük kaydını etkinleştirmek için. Bu seçeneğin etkinleştirilmesi, sistem sayacı toplama rapor dosyası oluşturur.

   ```xml
   <setting name="SystemCounterReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. Gereken şekilde güncelleştiren yapılandırma dosyasında diğer değerleri vardır.

    - **ReportFilePath**: Üç günlük dosyalarının depolandığı yolu belirler. Varsayılan olarak, bu "\Users\PBIEgwService\AppData\Local\Microsoft\On-premises veri gateway\Report" veya "Windows\ServiceProfiles\PBIEgwService\AppData\Local\Microsoft\On şirket içi veri gateway\Report", işletim sistemi sürümüne bağlı olarak yoludur. Bir hizmet hesabı için ağ geçidi dışında kullanıyorsanız _PBIEgwService_, bu yolun bir parçası hizmet hesabı adı ile değiştirin.
    - **ReportFileCount**: Günlük dosyaları korumak için her türde sayısını belirler. Varsayılan değer 10'dur.
    - **ReportFileSizeInBytes**: Korumak için dosya boyutunu belirler. 104857600 varsayılan değerdir.
    - **QuerExecutionAggregationTimeInMinutes**: Sorgu yürütme bilgilerini en iyi duruma toplanır dakika sayısını belirler. Varsayılan değer 5'tir.
    - **SystemCounterAggregationTimeInMinutes**: Sistem sayaçlarını toplanır dakika sayısını belirler. Varsayılan değer 5'tir.

1. Yapılandırma dosyasına değişiklikleri yaptıktan sonra ağ geçidi etkili olması bu yapılandırma değerleri için yeniden başlatın. Şimdi rapor dosyaları için belirttiğiniz konumda oluşturulmasını görmeye başlayacaksınız **ReportFilePath**.

    > [!NOTE]
    > En fazla 10 dakika sürebilir ve süreyi ayarlamak için **QuerExecutionAggregationTimeInMinutes** yapılandırma dosyasında dosyaları klasöründe gösterilmesi kadar.

## <a name="understand-performance-logs"></a>Performans Günlükleri anlama

Bu özellik açtığınızda, üç yeni günlük dosyaları oluşturacağız:

- Sorgu yürütme raporu
- Sorgu yürütme toplama raporu
- Sistem sayacı toplama raporu

Sorgu yürütme rapor ayrıntılı sorgu yürütme bilgilerini içerir. Aşağıdaki öznitelikler yakalayarak kullanabiliriz:

|Öznitelik |Açıklama |
| ---- | ---- |
|**Gatewayobjectıd** |Ağ geçidi için benzersiz tanımlayıcı. |
|**RequestId** |Bir ağ geçidi isteği için benzersiz tanımlayıcı. Birden çok sorgu için aynı olabilir. |
|**Veri kaynağı** |Veri kaynağı türü ve veri kaynağını içerir. |
|**QueryTrackingId** |Bir sorgu için benzersiz tanımlayıcı. |  
|**QueryExecutionEndTimeUTC** |Sorgu yürütme tamamlandığında zaman. |
|**QueryExecutionDuration**(ms) |Bir sorgu yürütme süresi. |
|**QueryType** |Sorgu - örneğin yazın, geçirilen sorgu bir Power BI yenileme/DirectQuery veya PowerApps ve Microsoft Flow sorgularından olabilir. |
|**DataProcessingEndTimeUTC** |Veri işleme biriktirme, veri alma, sıkıştırma, veri işleme ve tamamlanan vb. gibi etkinlikler saati. |
|**DataProcessingDuration**(ms) |Biriktirme, veri alma, sıkıştırma, veri işleme vb. gibi etkinlikler veri işleme süresi. |
|**Başarılı** |Sorgu başarılı veya başarısız olmadığını gösterir. |
|**ErrorMessage** |Sorgu başarısız oldu, hata iletisi gösterir. |
| | |

Sorgu yürütme toplama raporu için bir zaman aralığına göre toplanmış sorgu bilgileri içeren **Gatewayobjectıd**, **DataSource**, **başarı**ve **QueryType**. Varsayılan değer 5 dakikadır, ancak aşağıda açıklandığı şekilde ayarlayabilirsiniz. Aşağıdaki öznitelikler yakalayarak kullanabiliriz:

|Öznitelik |Açıklama |
| ---- | ---- |
|**Gatewayobjectıd** |Ağ geçidi için benzersiz tanımlayıcı. |
|**AggregationStartTimeUTC** |Kendisi için sorgu öznitelikleri toplanmış zaman penceresi başlangıcı. |
|**AggregationEndTimeUTC** |Öznitelikler için hangi sorgu toplanmış zaman penceresini sonu. |
|**Veri kaynağı** |Veri kaynağı türü ve veri kaynağını içerir. |
|**Başarılı** |Sorgu başarılı veya başarısız olmadığını gösterir. |
|**AverageQueryExecutionDuration**(ms) |Sorgu yürütme süresi toplama zaman penceresi için ortalama. |
|**MaxQueryExecutionDuration**(ms) |Toplama zaman penceresi için en yüksek sorgu yürütme süresi. |
|**MinQueryExecutionDuration**(ms) |Toplama zaman penceresi için en az bir sorgu yürütme süresi. |
|**QueryType** |Sorgu - örneğin yazın, geçirilen sorgu bir Power BI yenileme/DirectQuery veya PowerApps ve Microsoft Flow sorgularından olabilir. |
|**AverageDataProcessingDuration**(ms) |Toplama zaman penceresi vb. için ortalama süre gibi biriktirme, veri alma, sıkıştırma, veri işleme, veri işleme etkinlikler. |
|**MaxDataProcessingDuration**(ms) |Toplama zaman penceresi için en uzun süre biriktirme, veri alma, sıkıştırma, veri işleme vb. gibi veri işleme etkinlikler. |
|**MinDataProcessingDuration**(ms) |Toplama zaman penceresi için minimum süre biriktirme, veri alma, sıkıştırma, veri işleme vb. gibi veri işleme etkinlikler. |
|**Sayısı** |Sorgu sayısı. |
| | |

Sistem sayacı toplama raporu için bir zaman aralığında toplanan sistem sayacı değerlerini içerir. Varsayılan değer 5 dakikadır, ancak aşağıda açıklandığı şekilde ayarlayabilirsiniz. Aşağıdaki öznitelikler yakalayarak kullanabiliriz:

|Öznitelik |Açıklama |
| ---- | ---- |
|**Gatewayobjectıd** |Ağ geçidi için benzersiz tanımlayıcı. |
|**AggregationStartTimeUTC** |Sistem sayaçlarını toplanmış zaman penceresi başlangıcı. |
|**AggregationEndTimeUTC** |İçin hangi sistem sayaçları toplanmış zaman penceresini sonu. |
|**CounterName** |Ağ Geçidi tarafından karma, bellek ve CPU kullanımı dahil olmak üzere ve genel makine ağ geçidini barındıran sistemi sayaçları. |
|**En fazla** |Sistem sayacı toplama zaman penceresi için en büyük değer. |
|**Min** |Sistem sayacı toplama zaman penceresi için en küçük değer. |
|**Ortalama** |Toplama zaman penceresi için sistem sayacı için ortalama değeri. |
| | |

## <a name="visualize-gateway-performance"></a>Ağ geçidi performansı görselleştirin

Şimdi, günlük dosyalarında verileri görselleştirebilirsiniz.

1. İndirme [ağ geçidi performans PBI şablon](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) ve Power BI desktop'ı kullanarak açın.

1. Açılan iletişim kutusunda, klasör yolu değerle eşleşip eşleşmediğini kontrol **ReportFilePath**.

    ![Klasör yolu için açılan menüsü](media/service-gateway-performance-monitoring/gateway-folder-path-pop-up.png)

1. Seçin **yük**, ve şablon dosyasını başlatır, günlük dosyalarından veri yükleniyor. Raporlarda veri kullanarak daha sonra bu tüm görsellerin doldurulması gerekir.

1. İsteğe bağlı bir PBIX bu dosyayı kaydedin ve hizmetiniz için otomatik yenilemeler için yayımlayın.

Ayrıca, bu şablon dosyası, gereksinimlerinize uyacak şekilde özelleştirebilirsiniz. Power BI şablonları hakkında daha fazla bilgi için bkz. Bu [Microsoft Power BI Blog Gönderisi](https://powerbi.microsoft.com/en-us/blog/deep-dive-into-query-parameters-and-power-bi-templates/).