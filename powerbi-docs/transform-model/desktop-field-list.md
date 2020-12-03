---
title: Power BI Desktop’ta Alan listesini kullanma (önizleme)
description: Power BI Desktop’ta verileri modelleyip raporlar oluşturmak için Alan listesini kullanma
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-transform-model
ms.topic: conceptual
ms.date: 11/11/2020
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 834df274d4cc75af1087ab4fa7d24c2fd7dd4fec
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96416014"
---
# <a name="using-the-field-list-in-power-bi-desktop-preview"></a>Power BI Desktop’ta Alan listesini kullanma (önizleme)

Kasım 2020 güncelleştirmesinden itibaren, Power BI Desktop’taki Model görünümü, Veri görünümü ve Rapor görünümü genelindeki **Alan** listelerini birleştiriyoruz. Bu görünümlerin birleştirilmesi işlevsellik bakımından ve görünümler genelindeki kullanıcı arabiriminde tutarlılık oluşturup müşteri geri bildirimlerini çözümleyecek.

Görünümler genelinde fark edeceğiniz değişiklikler arasında şunlar yer alır:

* İkonografi
* Arama işlevi
* Bağlam menüsü öğeleri
* Benzer sürükle bırak davranışı
* Araç İpuçları
* Erişilebilirlik geliştirmeleri

Amaç, Power BI Desktop’ın kullanılabilirliğini artırmaktır. Değişikliklerin, genel veri iş akışınızda en düşük düzeyde etkisi olması gerekir.

## <a name="enabling-the-new-field-list-preview"></a>Yeni Alan listesini etkinleştirme (önizleme)

Birleştirilmiş Alan listesi **Model** görünümüyle başlayacak ve daha sonra diğer görünümler için de etkinleştirilecek. Birleşik Alan görünümünü etkinleştirmek için Power BI Desktop’ta **Dosya > Seçenekler ve ayarlar > Seçenekler**’e gidip soldaki bölmede **Önizleme özellikleri**’ni seçin. Önizleme özellikleri bölümünde, **Yeni alan listesi**’nin yanındaki onay kutusunu seçin.

![Yeni alan listesini etkinleştirme](media/desktop-field-list/field-list-01.png)

Seçimin etkili olabilmesi için Power BI Desktop’ı yeniden başlatmanız istenir.

## <a name="field-list-changes"></a>Alan listesindeki değişiklikler

Aşağıdaki tablolarda alan listesi güncelleştirmeleri gösterilir: 


|**Özgün alan listesi (Model görünümü)**  | **Yeni alan listesi (Model görünümü)**  |
|:---------:|:---------:|
|**Özgün** |**Yeni** |
|**Simgeler ve kullanıcı arabirimi**       ||
|![özgün alan listesi](media/desktop-field-list/field-list-01a.png)     |![yeni alan listesi](media/desktop-field-list/field-list-01b.png)    |
|**Bağlam menüsü - Alan**       ||
|![Alan için özgün bağlam menüsü](media/desktop-field-list/field-list-02a.png)     |![Alan için yeni bağlam menüsü](media/desktop-field-list/field-list-02b.png)    |
|**Bağlam menüsü - Tablo**       ||
|![Tablo için özgün bağlam menüsü](media/desktop-field-list/field-list-03a.png)     |![Tablo için yeni bağlam menüsü](media/desktop-field-list/field-list-03b.png)    |
|**Araç İpuçları**       ||
|![özgün araç ipucu](media/desktop-field-list/field-list-04a.png)     |![yeni araç ipucu](media/desktop-field-list/field-list-04b.png)    |

Ayrıca, yeni Alan listesi simgeleri de vardır. Aşağıdaki tabloda, özgün simgeler ve yeni karşılıklarının gösterilmesinin yanı sıra, her birine ilişkin kısa bir açıklama sağlanır. 


|Özgün simge  |Yeni simge  |Description  |
|:---------:|:---------:|:---------|
|![özgün klasör simgesi](media/desktop-field-list/field-list-05a.png)     |![yeni klasör simgesi](media/desktop-field-list/field-list-05b.png)           |Alanlar listesinde klasör         |
|![özgün sayısal alan simgesi](media/desktop-field-list/field-list-06a.png)     |![yeni sayısal alan simgesi](media/desktop-field-list/field-list-06b.png)         |Sayısal alan: Sayısal alanlar, örneğin toplamı veya ortalaması alınabilecek toplamlardır. Toplamlar, verilerle birlikte içeri aktarılır ve raporunuzun temel aldığı veri modelinde tanımlanır. Daha fazla bilgi için bkz. [Power BI raporlarındaki toplamlar](../create-reports/service-aggregates.md).         |
|![özgün hesaplanmış sütun simgesi](media/desktop-field-list/field-list-07a.png)     |![yeni hesaplanmış sütun simgesi](media/desktop-field-list/field-list-07b.png)         |Sayısal olmayan veri türündeki hesaplanmış sütun: Veri Çözümleme İfadeleri (DAX) formülüyle oluşturduğunuz ve sütunun değerlerini tanımlayan yeni, sayısal olmayan sütun. [Hesaplanmış sütunlar](desktop-calculated-columns.md) hakkındaki diğer bilgileri okuyun.        |
|![özgün sayısal hesaplanmış sütun simgesi](media/desktop-field-list/field-list-08a.png)     |![yeni sayısal hesaplanmış sütun simgesi](media/desktop-field-list/field-list-08b.png)          |Sayısal hesaplanmış sütun: Veri Çözümleme İfadeleri (DAX) formülüyle oluşturduğunuz ve sütunun değerlerini tanımlayan yeni sütun. [Hesaplanmış sütunlar](desktop-calculated-columns.md) hakkındaki diğer bilgileri okuyun.         |
|![özgün ölçü simgesi](media/desktop-field-list/field-list-09a.png)     |![yeni ölçü simgesi](media/desktop-field-list/field-list-09b.png)          |Ölçü: Her ölçünün kendi sabit kodlanmış formülü vardır. Rapor görüntüleyicileri hesaplama türünü değiştiremez. Örneğin, tür toplam olarak ayarlanmışsa bu şekilde olarak kalır. Değerler bir sütunda depolanmaz. Yalnızca görseldeki konumlarına bağlı olarak bunlar anında hesaplanır. Daha fazla bilgi için bkz. [Ölçüleri anlama](desktop-measures.md).         |
|![özgün ölçü grubu simgesi](media/desktop-field-list/field-list-10a.png)     |![yeni ölçü grubu simgesi](media/desktop-field-list/field-list-10b.png)         |Ölçü grubu.         |
|![özgün kpi simgesi](media/desktop-field-list/field-list-11a.png)     |![yeni kpi simgesi](media/desktop-field-list/field-list-11b.png)         |KPI: Ölçülebilen bir hedefe doğru ilerleme durumunu gösteren görsel bir ipucu. [Ana Performans Göstergesi (KPI)](../visuals/power-bi-visualization-kpi.md) görselleri hakkındaki diğer bilgileri okuyun.         |
|![özgün alanlar hiyerarşisi simgesi](media/desktop-field-list/field-list-12a.png)     |![yeni alanlar hiyerarşisi simgesi](media/desktop-field-list/field-list-12b.png)           |Alanların hiyerarşisi: Hiyerarşiyi oluşturan alanları görmek için oku seçin. Daha fazla bilgi için YouTube'da [Hiyerarşileri oluşturma ve bunlarla çalışma](https://www.youtube.com/watch?v=q8WDUAiTGeU) hakkındaki bu Power BI videosunu izleyin.         |
|![özgün coğrafi veriler simgesi](media/desktop-field-list/field-list-13a.png)     |![yeni coğrafi veriler simgesi](media/desktop-field-list/field-list-13b.png)         |Coğrafi veriler: Bu konum alanları kullanılarak harita görselleştirmeleri oluşturulabilir.         |
|![özgün kimlik alanı simgesi](media/desktop-field-list/field-list-14a.png)     |![yeni kimlik alanı simgesi](media/desktop-field-list/field-list-14b.png)          |Kimlik alanı: Bu simgeye sahip alanlar, yinelenen değerlere sahip olsalar bile tüm değerleri gösterecek şekilde ayarlanmış benzersiz alanlardır. Örneğin, verilerinizde adları "Can Kaya" olan iki farklı kişinin kaydı olabilir ve bunların her biri benzersiz olarak kabul edilir. Bunlar toplanmaz.         |
|![özgün parametre simgesi](media/desktop-field-list/field-list-15a.png)     |![yeni parametre simgesi](media/desktop-field-list/field-list-15b.png)          |Parametre: Raporlarınızın ve veri modellerinizin bazı bölümlerini (sorgu filtresi, veri kaynağı başvurusu, ölçü tanımı vb.) bir veya birden çok parametre değerine bağımlı yapmak için parametreler ayarlayın. Daha fazla bilgi için [sorgu parametreleri](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) hakkındaki bu Power BI blog gönderisine bakın.         |
|![özgün takvim tarihi alanı simgesi](media/desktop-field-list/field-list-16a.png)     |![yeni takvim tarihi alanı simgesi](media/desktop-field-list/field-list-16b.png)         |Yerleşik tarih tablosu içeren bir takvim tarihi alanı.         |
|![özgün hesaplanmış tablo simgesi](media/desktop-field-list/field-list-17a.png)     |![yeni hesaplanmış tablo simgesi](media/desktop-field-list/field-list-17b.png)          |Hesaplanmış tablo: Zaten modele yüklenmiş olan verilerin temel alındığı, Veri Çözümleme İfadeleri (DAX) formülüyle oluşturulan bir tablo. Bunlar ara hesaplamalar için en iyi seçenektir ve modelin parçası olarak depolamanız yararlı olabilir.         |
|![özgün uyarı simgesi](media/desktop-field-list/field-list-18a.png)     |![yeni uyarı simgesi](media/desktop-field-list/field-list-18b.png)         |Uyarı: Hata içeren bir hesaplanmış alan. Örneğin, DAX ifadesinin söz dizimi yanlış olabilir.         |
|![özgün grup simgesi](media/desktop-field-list/field-list-19a.png)     |![yeni grup simgesi](media/desktop-field-list/field-list-19b.png)         |Grup: Bu sütundaki değerler için, gruplar ve bölmeler özelliği kullanılarak başka bir sütundaki gruplandırma değerleri temel alınır. [Gruplandırma ve bölmeyi nasıl kullanacağınızı](../create-reports/desktop-grouping-and-binning.md) okuyabilirsiniz.         |
| özgün simge yok    |![yeni değişiklik algılama ölçüsü simgesi](media/desktop-field-list/field-list-20b.png)          |Değişiklik algılama ölçüsü: Otomatik sayfa yenileme için bir sayfayı yapılandırdığınızda, sayfanın geri kalanındaki görsellerin güncelleştirilip güncelleştirilmemesi gerektiğini belirlemek üzere sorgulanan bir [değişiklik algılama ölçüsü](../create-reports/desktop-grouping-and-binning.md) yapılandırabilirsiniz.         |


## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makaleler de ilginizi çekebilir:

* [Power BI Desktop'taki hesaplanmış sütunlar oluşturma](desktop-calculated-columns.md)
* [Power BI Desktop'ta gruplandırmayı ve gruplamayı kullanma](../create-reports/desktop-grouping-and-binning.md)
* [Power BI Desktop raporlarında kılavuz çizgilerini ve kılavuza yaslama işlevini kullanma](../create-reports/desktop-gridlines-snap-to-grid.md)

