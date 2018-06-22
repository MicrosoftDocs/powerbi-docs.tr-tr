---
title: Power BI Desktop'ta R Betikleri Çalıştırma
description: Power BI Desktop'ta R Betikleri Çalıştırma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: acadd84fbd8d0cf7f44b23362474d08608107f24
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34286463"
---
# <a name="run-r-scripts-in-power-bi-desktop"></a>Power BI Desktop'ta R betikleri çalıştırın
**Power BI Desktop**'ta R betiklerini doğrudan çalıştırabilir ve elde edilen veri kümelerini bir Power BI Desktop veri modeline aktarabilirsiniz.

## <a name="install-r"></a>R yükleme
Power BI Desktop'ta R betikleri çalıştırabilmek için yerel makinenize **R** yüklemeniz gerekir. **R** programlama dilini, [Revolution Open indirme sayfası](https://mran.revolutionanalytics.com/download/) ve [CRAN Repository](https://cran.r-project.org/bin/windows/base/) de dahil olmak üzere pek çok konumdan ücretsiz olarak indirip yükleyebilirsiniz. R betiklerinin Power BI Desktop'taki güncel sürümü, yükleme yolunda Unicode karakterlerin yanı sıra boşlukların (boş karakterler) olmasını da destekler.

## <a name="run-r-scripts"></a>R betiklerini çalıştırma
Power BI Desktop’ta yalnızca birkaç basit adım uygulayarak R betikleri çalıştırabilir ve bir veri modeli oluşturabilirsiniz. Bu modeli kullanarak raporlar oluşturabilir ve raporları Power BI hizmetinde paylaşabilirsiniz. Power BI Desktop'taki R betikleri artık, ondalık (.) ve virgül (,) içeren sayı biçimlerini de destekliyor.

### <a name="prepare-an-r-script"></a>R betiği hazırlama
Power BI Desktop'ta bir R betiği çalıştırmak için yerel R geliştirme ortamınızda betiği oluşturun ve başarıyla çalıştığından emin olun.

Betiği Power BI Desktop'ta çalıştırmak için, söz konusu betiğin yeni ve değiştirilmemiş bir çalışma alanında başarıyla çalıştığından emin olun. Bu, tüm paket ve bağımlılıkların açık bir şekilde yüklenmesi ve çalıştırılması gerektiği anlamına gelir. Bağımlı betikler çalıştırmak için *source()* öğesini kullanabilirsiniz.

Power BI Desktop'ta bir R betiğini hazırlamaya ve çalıştırmaya ilişkin bazı sınırlamalar vardır:

* Yalnızca veri çerçeveleri içeri aktarıldığından, Power BI'a aktarmak istediğiniz verilerin bir veri çerçevesinde gösterildiğinden emin olun
* Karmaşık ve Vektör olarak yazılan sütunlar içeri aktarılmaz ve oluşturulan tablodaki hata değerleri ile değiştirilir
* Yok değerleri, Power BI Desktop'ta NULL değerlere dönüştürülür
* 30 dakikadan uzun süren herhangi bir R betiği çalıştırma işlemi zaman aşımına uğrar
* R betiğindeki etkileşimli çağrılar (kullanıcı girişinin beklenmesi gibi) betik yürütme işlemini durdurur
* R betiğindeki çalışma dizinini ayarlarken çalışma dizinine yönelik bir tam yol (göreli yol yerine) tanımlamanız *gerekir*

### <a name="run-your-r-script-and-import-data"></a>R betiğinizi çalıştırma ve verileri içeri aktarma
1. Power BI Desktop'ta R Betiği veri bağlayıcısını **Veri Al** penceresinde bulabilirsiniz. R Betiğinizi çalıştırmak için, aşağıda gösterilen şekilde **Veri Al&gt; Diğer...** seçeneğini belirleyin ve ardından **Diğer &gt; R betiği**’ni seçin:
   
   ![](media/desktop-r-scripts/r-scripts-1.png)
2. Yerel makinenizde R yüklüyse R altyapınız olarak en son yüklenen sürüm seçilir. Betiğinizi kopyalayıp betik penceresine yapıştırmanız ve **Tamam**'ı seçmeniz yeterlidir.
   
   ![](media/desktop-r-scripts/r-scripts-2.png)
3. R yüklü değilse, tanımlanmamışsa veya yerel makinenizde birden fazla yükleme mevcutsa; yükleme seçeneklerini görüntülemek ya da R betiğini çalıştırmak istediğiniz yüklemeyi seçmek için **R Yükleme Ayarları** menüsünü genişletin.
   
   ![](media/desktop-r-scripts/r-scripts-3.png)
   
   R yüklüyse ancak tanımlanmamışsa, **R Yükleme Ayarları** menüsünü genişlettiğinizde görünen metin kutusuna betiğin konumunu açık bir şekilde girebilirsiniz. Yukarıdaki görüntüde *C:\Program Files\R\R-3.2.0* yolu, metin kutusuna açık bir şekilde girilmiştir.
   
   R yükleme ayarları, Seçenekler iletişim kutusunun R Betiği Oluşturma bölümünde bulunur. R yükleme ayarlarınızı belirtmek için **Dosya > Seçenekler ve ayarlar**’ı seçin, sonra da **Seçenekler > R betiği oluşturma** seçeneğini belirleyin. Birden fazla R yüklemesi varsa, kullanacağınız yüklemeyi seçmenize olanak sağlayan bir açılan menü görüntülenir.
   
   ![](media/desktop-r-scripts/r-scripts-4.png)
4. R Betiğini çalıştırmak için **Tamam**'ı seçin. Betik başarıyla çalıştırıldığında, oluşturulan veri çerçevelerini seçip Power BI modeline ekleyebilirsiniz.

### <a name="refresh"></a>Yenileme
Power BI Desktop'ta bir R betiğini yenileyebilirsiniz. Bir R betiğini yenilediğinizde Power BI Desktop, R betiğini Power BI Desktop ortamında yeniden çalıştırır.

## <a name="next-steps"></a>Sonraki adımlar
Power BI'daki R hakkında daha fazla bilgi edinmek için aşağıdaki ek kaynaklara göz atın.

* [Power BI Desktop'ta R görselleri oluşturma](desktop-r-visuals.md)
* [Power BI ile harici bir R IDE kullanma](desktop-r-ide.md)

