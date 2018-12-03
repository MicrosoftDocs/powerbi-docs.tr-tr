---
title: Power BI Desktop'taki Analysis Services Tablo verilerini kullanma
description: Power BI Desktop'taki Analysis Services Tablo verileri
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 102198c4524903098ad0c6b0b9fd7e231c3f1fdc
ms.sourcegitcommit: 05303d3e0454f5627eccaa25721b2e0bad2cc781
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52578302"
---
# <a name="using-analysis-services-tabular-data-in-power-bi-desktop"></a>Power BI Desktop'taki Analysis Services Tablo verilerini kullanma
Power BI Desktop uygulamasında SQL Server Analysis Services Tablo modellerinize bağlanmak ve onlardan veri almak için kullanabileceğiniz iki yöntem vardır: Canlı bağlantı kullanarak keşfetme veya öğeleri seçip Power BI Desktop'a aktarma.

Şimdi bu yöntemlere daha yakından bakalım.

**Canlı bağlantı kullanarak keşfetme**: Canlı bağlantı kullandığınızda Tablo modelinizdeki veya perspektifinizdeki tablolar, sütunlar ve ölçüler gibi öğeler Power BI Desktop uygulamasının Alanlar listesinde görünür. Power BI Desktop'ın gelişmiş görselleştirme ve rapor araçlarını kullanarak Tablo modelinizi yeni ve oldukça etkileşimli şekillerde keşfedebilirsiniz.

Canlı bağlantı sırasında Tablo modelinizdeki veriler Power BI Desktop'a aktarılmaz. Görselleştirmelerle etkileşim kurduğunuzda Power BI Desktop, Tablo modelini sorgular ve gördüğünüz sonuçları hesaplar. Son işleme zamanına göre veya Tablo Modelindeki Doğrudan Sorgu tablolarından her zaman Tablo modelindeki en güncel verilere bakıyor olursunuz. 

Unutmayın, Tablo modelleri oldukça güvenlidir. Power BI Desktop'ta görünen öğeler bağlantı kurduğunuz Tablo modelindeki izinlere göre değişiklik gösterir.

Power BI Desktop'ta oluşturduğunuz dinamik raporları Power BI sitenizde yayımlayarak paylaşabilirsiniz. Tablo modeline canlı bağlantı içeren bir Power BI Desktop dosyasını Power BI sitenizde yayımladığınızda bir yönetici tarafından şirket içi veri ağ geçidi yüklenmesi ve yapılandırılması gerekir. Daha fazla bilgi için bkz. [Şirket içi veri ağ geçidi](service-gateway-onprem.md).

**Öğeleri seçip Power BI Desktop'a aktarma**: Bu seçeneği kullanarak bağlandığınızda Tablo modelinizde veya perspektifinizde bulunan tablo, sütun ve ölçü gibi öğeleri seçerek bir Power BI Desktop modeline yükleyebilirsiniz. İçeriğinizi şekillendirmek için Power BI Desktop'ın gelişmiş Sorgu Düzenleyicisi'ni kullanabilirsiniz. Power BI Desktop'ın modelleme özelliklerini kullanarak verileri modelleyebilirsiniz. Power BI Desktop ile Tablo modeli arasında canlı bağlantı sağlanmaz. Ardından Power BI Desktop modelinizi çevrimdışı keşfedebilir veya Power BI sitenizde yayımlayabilirsiniz.

## <a name="to-connect-to-a-tabular-model"></a>Tablo modeline bağlanmak için
1. Power BI Desktop uygulamasının **Giriş** sekmesinde **Veri Al**'a tıklayın.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata.png)
2. **SQL Server Analysis Services Veritabanı**'na ve ardından **Bağlan**'a tıklayın.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as.png)
3. Sunucu adını girin ve bağlantı modunu seçin. 
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as_server.png)
4. Bu adım seçtiğiniz bağlantı moduna göre değişiklik gösterir:

* Canlı bağlantı kuruyorsanız Gezgin'de bir Tablo modeli veya perspektif seçin.
  
  ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as_live.png)
* Öğeleri seçip veri alma seçeneğini kullanıyorsanız Gezgin'de bir Tablo modeli veya perspektif seçin. Ardından yalnızca yüklenecek tabloları veya sütunları seçebilirsiniz. Yüklemeden önce verilerinizi şekillendirmek için Düzenle'ye tıklayarak Sorgu Düzenleyicisi'ni açın. Hazır olduğunuzda Yükle'ye tıklayarak verileri Power BI Desktop'a aktarın.

  ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_getdata_as_select.png)

## <a name="frequently-asked-questions"></a>Sık Sorulan Sorular
**Soru:** Şirket içi veri ağ geçidine ihtiyacım var mı?

**Cevap:** Duruma göre değişir. Power BI Desktop ile bir Tablo modeline canlı bağlantı kuruyorsanız ancak bunu Power BI sitenizde yayımlama planınız yoksa ağ geçidine ihtiyacınız yoktur. Diğer taraftan Power BI sitenizde yayımlamayı düşünüyorsanız Power BI hizmetiyle şirket içi Analysis Services sunucunuz arasında güvenli bağlantı kurulması için veri ağ geçidine ihtiyacınız vardır. Veri ağ geçidi yüklemeden önce Analysis Services sunucunuzun yöneticisiyle iletişime geçmeyi unutmayın.

Öğeleri seçip veri alma seçeneğini kullanıyorsanız Tablo modeli verilerini doğrudan Power BI Desktop dosyanıza aktarmış olursunuz ve ağ geçidi kullanmanız gerekmez.

**Soru:** Power BI hizmetinden bir Tablo modeline canlı bağlantı kurmayla Power BI Desktop'tan canlı bağlantı kurma arasındaki fark nedir?

**Cevap:** Power BI hizmetindeki sitenizde bulunan bir Tablo modelinden kuruluşunuzda şirket içi Analysis Services veritabanına canlı bağlantı kurduğunuzda bu iki nokta arasındaki iletişimin güvenliğini sağlamak için şirket içi ağ geçidine ihtiyaç duyulur. Power BI Desktop'tan bir Tablo modeline canlı bağlantı kurduğunuzda hem Power BI Desktop hem de bağlandığınız Analysis Services sunucusu şirket içi ortamda çalıştığından ağ geçidine ihtiyaç yoktur. Ancak Power BI Desktop dosyanızı Power BI sitenizde yayımlamak için bir ağ geçidi kullanmanız gerekir.

**Soru:** Canlı bağlantı oluşturduktan sonra aynı Power BI Desktop dosyasındaki başka bir veri kaynağına bağlanabilir miyim?

**Cevap:** Hayır. Verileri canlı keşfederken aynı dosyadaki başka türde veri kaynağına bağlanamazsınız. Önceden verileri içeri aktardıysanız veya Power BI Desktop dosyasında farklı bir veri kaynağına bağlandıysanız canlı keşfetme için yeni bir dosya oluşturmanız gerekir.

**Soru:** Canlı bağlantı oluşturduktan sonra Power BI Desktop'ta modeli düzenleyebilir veya sorgulayabilir miyim?

**Cevap:** Power BI Desktop'ta rapor düzeyinde ölçüler oluşturabilirsiniz ancak canlı verileri keşfederken diğer tüm sorgulama ve modelleme özellikleri devre dışı bırakılır.

**Soru:** Oluşturduğum canlı bağlantı güvenli mi?

**Cevap:** Evet. Analysis Services sunucusuna bağlanmak için geçerli Windows kimlik bilgileriniz kullanılır. Canlı keşfetme sırasında Power BI hizmetinde veya Power BI Desktop uygulamasında Temel ya da kayıtlı kimlik bilgileri kullanamazsınız.

**Soru:** Gezgin'de bir model ve bir perspektif görüyorum. Aralarındaki fark nedir?

**Cevap:** Perspektif, bir Tablo modelinin belirli bir görünümüdür. Veri analiz ihtiyaçlarına göre yalnızca belirli tabloları, sütunları veya ölçüleri kapsıyor olabilir. Tablo modelinde her zaman en az bir perspektif bulunabilir ve bu modeldeki her şeyi içerebilir. Hangisini seçeceğinizden emin değilseniz yöneticinizle iletişime geçmeniz gerekir.

## <a name="to-change-the-server-name-after-initial-connection"></a>İlk bağlantının ardından sunucu adını değiştirme
Canlı keşfetme bağlantısıyla bir Power BI Desktop dosyası oluşturduktan sonra bağlantıyı farklı bir sunucuya almak isteyebileceğiniz durumlar söz konusu olabilir. Örneğin Power BI Desktop dosyasını geliştirme sunucusuna bağlıyken oluşturduysanız Power BI hizmetinde yayımlamadan önce bağlantıyı üretim sunucusuna geçirmek isteyebilirsiniz.

1. Şeritten **Sorguları Düzenle**'yi seçin.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_chname_editquery.png)
2. Yeni sunucu adını girin.
   
   ![](media/desktop-analysis-services-tabular-data/pbid_sqlas_chname_dialog.png)
   
   
## <a name="troubleshooting"></a>Sorun giderme 
Aşağıdaki listede SQL Server Analysis Services (SSAS) veya Azure Analysis Services’a bağlanma sırasında yaşandığı bilinen tüm sorunlar açıklanmıştır. 

* **Hata: Model şeması yüklenemedi** - Bu hata genellikle Analysis Services’a bağlanan kullanıcının veritabanına/modele erişimi olmadığında gerçekleşir.

