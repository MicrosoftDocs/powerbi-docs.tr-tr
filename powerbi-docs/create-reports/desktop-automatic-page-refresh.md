---
title: Power BI Desktop’ta otomatik sayfa yenileme
description: Bu makalede, Power BI Desktop’ta DirectQuery kaynakları için sayfaları otomatik olarak yenileme işlemi gösterilmektedir.
author: davidiseminger
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 06/10/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9a1e42b4901e8659bb5d999294f29a80a0389280
ms.sourcegitcommit: 10c5b6cd5e7070f96de8a9f1d9b95f3d242ac7f2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86557245"
---
# <a name="automatic-page-refresh-in-power-bi-desktop"></a>Power BI Desktop’ta otomatik sayfa yenileme 

Kritik olayları izlerken, kaynak veriler güncelleştirildiği anda verilerin yenilenmesi önemlidir. Örneğin, üretim sektöründe bir makinenin hatalı çalıştığını veya hatalı çalışmak üzere olduğunu bilmeniz kritik önem taşır.

Power BI’daki otomatik sayfa yenileme özelliği, etkin rapor sayfanızın [DirectQuery kaynakları](https://docs.microsoft.com/power-bi/desktop-directquery-about) için önceden tanımlanmış bir tempoda yeni verileri sorgulamasını sağlar.

## <a name="using-automatic-page-refresh"></a>Otomatik sayfa yenilemeyi kullanma

Otomatik sayfa yenileme yalnızca DirectQuery veri kaynakları için kullanılabilir.

Otomatik sayfa yenilemeyi kullanmak için, yenilemeyi etkinleştirmek istediğiniz rapor sayfasını seçin. **Görsel Öğeler** bölmesinde **Biçimlendirme** düğmesini (boya rulosu) seçin ve bölmenin alt kısmından **Sayfa yenileme**’yi bulun. 

![Sayfa yenileme konumu](media/desktop-automatic-page-refresh/automatic-page-refresh-01.png)

Aşağıdaki görüntüde **Sayfa yenileme** kartı gösterilmektedir. Numaralandırılmış öğeler resimden sonra açıklanmaktadır.

![Sayfa yenileme kartı](media/desktop-automatic-page-refresh/automatic-page-refresh-02.png)

1.    Sayfa yenilemeyi açar veya kapatır
2.    Sayfa yenileme aralığına ilişkin sayı değeri
3.    Sayfa yenileme aralığı birimi

Bu kartta sayfa yenilemeyi açabilir ve yenileme süresini seçebilirsiniz. Varsayılan değer 30 dakikadır. (En az yenileme aralığı bir saniyedir.) Raporunuz, belirlediğiniz aralıkta yenilemeye başlar. 

## <a name="determining-the-page-refresh-interval"></a>Sayfa yenileme aralığını belirleme

Otomatik sayfa yenileme etkinleştirildiğinde Power BI Desktop, DirectQuery kaynağınıza sürekli olarak sorgu gönderir. Sorgunun gönderilmesi ile verilerin döndürülmesi arasında bir gecikme olur. Bu nedenle kısa yenileme aralıkları için sorguların sorgulanan verileri yapılandırılan aralık içinde başarıyla döndürdüğünü onaylamanız gerekir. Veriler aralık içinde döndürülmezse görseller yapılandırılandan daha az sıklıkta güncelleştirilir.

En iyi uygulama olarak yenileme aralığı en azından beklenen yeni veri alım hızıyla eşleşmelidir:

* Yeni veriler her 20 dakikada bir kaynağa ulaşırsa yenileme aralığınız 20 dakikadan kısa olamaz. 

* Her saniye yeni veriler alınıyorsa aralığı bir saniye olarak ayarlayın. 

Bir saniye gibi düşük yenileme aralıkları için aşağıdakiler gibi faktörleri göz önünde bulundurun:
- DirectQuery veri kaynağının türü
- Sorgularınızın üzerinde oluşturduğu yük
- Rapor görüntüleyicilerinizin kapasitenin veri merkezine uzaklığı 

Power BI Desktop’ta Performans Analizi’ni kullanarak döndürme sürelerini tahmin edebilirsiniz. Performans Analizi, her görsel sorgunun kaynaktan sonuçlarla dönmek için yeterli süresi olup olmadığını denetlemenize olanak verir. Ayrıca, zamanın harcandığı yeri belirlemenizi sağlar. Performans Analizi’nin sonuçlarına göre, veri kaynağını ayarlayabilir veya raporunuzdaki diğer görseller ve ölçülerle deneme yapabilirsiniz.

Aşağıdaki resimde, Performans Analizi’ndeki DirectQuery sonuçları gösterilmektedir:

![Performans Analizi sonuçları](media/desktop-automatic-page-refresh/automatic-page-refresh-03.png)

Bu veri kaynağıyla ilgili bazı diğer özellikleri ele alalım: 

-    Veriler 2 saniyelik hızla ulaşır. 
-    Performans Analizi, yaklaşık 4,9 saniyelik (4,688 milisaniyelik) maksimum sorgu + görüntüleme süresini gösterir. 
-    Veri kaynağı, saniyede yaklaşık 1,000 eşzamanlı sorguyu işleyecek şekilde yapılandırılmıştır. 
-    Yaklaşık 10 kullanıcının raporu eşzamanlı olarak görüntülemesini beklersiniz.

Böylece aşağıdaki denklemdekiler oluşur:

**5 görsel x 10 kullanıcı = yaklaşık 50 sorgu**

Bu hesaplamanın sonucu, veri kaynağının destekleyebileceğinden çok daha fazla yüke sahip olduğunu gösterir. Veriler iki saniyelik hızla ulaşır ve bu da sizin yenileme hızınız olmalıdır. Ancak sorgunun tamamlanması yaklaşık beş saniye sürdüğünden bunu beş saniyeden uzun bir süreye ayarlamanız gerekir. 

Ayrıca, raporunuzu hizmette yayımladığınızda bu sürenin değişebileceğini unutmayın. Rapor, bulutta barındırılan Azure Analysis Services örneğini kullandığı için bu fark oluşur. Yenileme hızınızı uygun şekilde ayarlamanız faydalı olabilir. 

Sorguları ve yenileme zamanlamasını hesaba katmak için Power BI yalnızca kalan tüm yenileme sorguları tamamlandığında bir sonraki yenileme sorgusunu çalıştırır. Bu nedenle, yenileme aralığınız, sorgularınızın işlenme süresinden kısa olursa Power BI yalnızca kalan sorgular tamamlandıktan sonra tekrar yenileme yapar. 

Şimdi de kapasite yöneticisi olarak performans sorunlarını nasıl algılayıp tanılayabileceğinize bakalım. Daha sonra bu makalenin ilerleyen bölümünde, performans ve sorun giderme ile ilgili diğer sorular ve yanıtlar için [Sık sorulan sorular](#frequently-asked-questions) bölümüne de göz atabilirsiniz.

## <a name="automatic-page-refresh-in-the-power-bi-service"></a>Power BI hizmetinde otomatik sayfa yenileme

Ayrıca, Power BI Desktop’ta yazılmış ve Power BI hizmetinde yayımlanmış olan raporlar için de otomatik sayfa yenilemeyi ayarlayabilirsiniz. 

Power BI hizmetindeki raporlar için otomatik sayfa yenilemeyi yapılandırmak için, Power BI Desktop’takine benzer adımları kullanırsınız. Power BI hizmetinde yapılandırıldığında, otomatik sayfa yenileme [eklenmiş Power BI](../developer/embedded/embedding.md) içeriğini de destekler. Bu resimde, Power BI hizmeti için **Sayfa yenileme** yapılandırması gösterilmektedir:

![Power BI hizmetinde otomatik sayfa yenileme](media/desktop-automatic-page-refresh/automatic-page-refresh-04.png)

Bu açıklamalar, numaralandırılmış öğelere karşılık gelir: 

1.    Sayfa yenilemeyi açar veya kapatır.
2.    Sayfa yenileme aralığına ilişkin sayı değeri. Bir tamsayı olmalıdır.
3.    Sayfa yenileme aralığı birimi.

### <a name="page-refresh-intervals"></a>Sayfa yenileme aralıkları

Power BI hizmetinde izin verilen sayfa yenileme aralıkları, raporun çalışma alanı türünden etkilenir. Bu raporlar için geçerlidir:

* Otomatik sayfa yenileme özelliği etkin olan bir çalışma alanında rapor yayımlama
* Bir çalışma alanında zaten bulunan bir sayfa yenileme aralığını düzenleme
* Doğrudan hizmette rapor oluşturma

Power BI Desktop’ta yenileme aralıklarına yönelik bir kısıtlama yoktur. Yenileme aralığı her saniye gibi bir sıklıkta olabilir. Ancak raporlar Power BI hizmetinde yayımlandığında, belirli kısıtlamalar uygulanır. Bu kısıtlamalar aşağıdaki bölümlerde açıklanmıştır.

### <a name="restrictions-on-refresh-intervals"></a>Yenileme aralıklarındaki kısıtlamalar

Power BI hizmetinde, otomatik sayfa yenilemeye çalışma alanı gibi faktörler ve Premium hizmetleri kullanıp kullanmadığınız temel alınarak kısıtlamalar uygulanır.

Bu kısıtlamaların nasıl çalıştığını netleştirmek için kapasiteler ve çalışma alanıyla ilgili bazı arka plan bilgileriyle başlayalım.

*Kapasiteler*, Power BI’daki önemli kavramlardan biridir. Power BI içeriğini barındırmak ve sunmak için kullanılan bir dizi kaynağı (depolama, işlemci ve bellek) temsil eder. Kapasiteler paylaşımlı veya ayrılmıştır. *Paylaşılan kapasite* diğer Microsoft müşterileri ile paylaşılır. *Ayrılmış kapasite*, tamamen tek bir müşteriye ayrılır. Ayrılmış kapasitelere giriş için bkz. [Premium kapasiteleri yönetme](../admin/service-premium-capacity-manage.md).

Paylaşılan kapasitede iş yükleri, diğer müşterilerle paylaşılan hesaplama kaynaklarında çalışır. Kapasitenin kaynakları paylaşması gerektiğinden, *tarafsızlığı* sağlamak için maksimum model boyutu (1 GB) ve maksimum günlük yenileme sıklığı (günde sekiz defa) ayarlama gibi sınırlamalar uygulanır.

Power BI *çalışma alanları* kapasitelerin içinde yer alır. Bunlar güvenlik, işbirliği ve dağıtım kapsayıcılarını temsil eder. Her Power BI kullanıcısının **Çalışma Alanım** olarak bilinen kendi kişisel çalışma alanı vardır. İşbirliğine ve dağıtıma olanak sağlamak için ek çalışma alanları oluşturulabilir. Bunlar *çalışma alanları* olarak bilinir. Kişisel çalışma alanları da dahil olmak üzere çalışma alanları varsayılan olarak paylaşılan kapasitede oluşturulur.

Burada, iki çalışma alanı senaryosu için bazı ayrıntılara yer verilmiştir:

**Paylaşılan çalışma alanları**. Düzenli çalışma alanları (Premium kapasitenin parçası olmayan çalışma alanları) için otomatik sayfa yenileme minimum 30 dakikalık aralığa (izin verilen en düşük aralık) sahip olur.

**Premium çalışma alanları**. Premium çalışma alanlarındaki otomatik sayfa yenileme kullanılabilirliği, Premium yöneticinizin Power BI Premium kapasitesi için ayarladığı iş yükü ayarlarına bağlı olur. Otomatik sayfa yenilemeyi ayarlama yeteneğinizi etkileyebilecek iki değişken vardır:

 - **Özellik açık/kapalı**. Kapasite yöneticiniz özelliği devre dışı bıraktıysa yayımlanmış raporunuzda herhangi bir sayfa yenileme türü ayarlayamazsınız.

 - **Minimum yenileme aralığı**. Özellik etkinleştirilirken, kapasite yöneticinizin bir minimum yenileme aralığı ayarlaması gerekir. Zaman aralığınız minimumdan düşükse Power BI hizmeti, kapasite yöneticiniz tarafından ayarlanan minimum aralığa göre aralığınızı geçersiz kılar. Bu geçersiz kılma işlemi, aşağıdaki tabloda “Kapasite yönetimini geçersiz kılma” olarak adlandırılmıştır. 

Bu tabloda, bu özelliğin nerede kullanılabildiğine dair daha fazla ayrıntı ve her bir kapasite türü ve [depolama moduna](../connect-data/service-dataset-modes-understand.md) ilişkin sınırlar açıklanmaktadır:

| Depolama modu | Ayrılmış kapasite | Paylaşılan kapasite |
| --- | --- | --- |
| DirectQuery | **Desteklenen**: Evet <br>**Minimum yenileme aralığı**: 1 saniye <br>**Kapasite yönetimini geçersiz kılma**: Evet | **Desteklenen**: Evet <br>**Minimum yenileme aralığı**: 30 dakika <br>**Kapasite yönetimini geçersiz kılma**: Hayır |
| İçeri Aktar | **Desteklenen**: Hayır <br>**Minimum yenileme aralığı**: YOK <br>**Kapasite yönetimini geçersiz kılma**: YOK | **Desteklenen**: Hayır <br>**Minimum yenileme aralığı**: YOK <br>**Kapasite yönetimini geçersiz kılma**: YOK |
| Karma mod (DirectQuery ve diğer veri kaynakları) | **Desteklenen**: Evet <br>**Minimum yenileme aralığı**: 1 saniye <br>**Kapasite yönetimini geçersiz kılma**: Evet | **Desteklenen**: Evet <br>**Minimum yenileme aralığı**: 30 dakika <br>**Kapasite yönetimini geçersiz kılma**: Hayır |
| Live connect AS | **Desteklenen**: Hayır <br>**Minimum yenileme aralığı**: YOK <br>**Kapasite yönetimini geçersiz kılma**: YOK | **Desteklenen**: Hayır <br>**Minimum yenileme aralığı**: YOK <br>**Kapasite yönetimini geçersiz kılma**: YOK |
| Live connect PBI | **Desteklenen**: Hayır <br>**Minimum yenileme aralığı**: YOK <br>**Kapasite yönetimini geçersiz kılma**: YOK | **Desteklenen**: Hayır <br>**Minimum yenileme aralığı**: YOK <br>**Kapasite yönetimini geçersiz kılma**: YOK |

> [!NOTE]
> Power BI Desktop’tan otomatik sayfa yenileme özelliği etkin raporunuzu hizmette yayımlarken, veri kümesi ayarları menüsünde DirectQuery veri kaynağı için kimlik bilgilerini sağlamanız gerekir.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Power BI Desktop veya Power BI hizmetinde otomatik sayfa yenilemeyi kullanırken göz önünde bulundurulması gereken birkaç nokta vardır:

* İçeri Aktarma, LiveConnect ve Push depolama modları, otomatik sayfa yenileme için desteklenmez.  
* En az bir DirectQuery veri kaynağı olan bileşik modeller desteklenir.
* Power BI Desktop’ta yenileme aralıklarına yönelik bir kısıtlama yoktur. Aralık her saniye gibi bir sıklıkta olabilir. Raporlar Power BI hizmetinde yayımlandığında, bu makalenin [önceki](#restrictions-on-refresh-intervals) kısmında açıklandığı gibi belirli kısıtlamalar uygulanır.
* SharePoint Online ekleme seçeneği, otomatik sayfa yenileme özelliğini desteklemez.

### <a name="performance-diagnostics"></a>Performans tanılamaları

Otomatik sayfa yenileme, senaryoları izlemek ve hızla değişen verileri keşfetmek için kullanışlıdır. Ancak bazen bu, kapasite veya veri kaynağı üzerinde gereksiz yük oluşturabilir.

Veri kaynaklarında gereksiz yük oluşmasını engellemek için Power BI şu korumaları içerir:

- Tüm otomatik sayfa yenileme sorguları, etkileşimli sorguların (sayfa yükleme ve görselleri çapraz filtreleme gibi) öncelikli olmasını sağlamak için daha düşük öncelikle çalıştırılır.
- Bir sonraki yenileme döngüsü geldiğinde sorgu tamamlanmadıysa Power BI, önceki sorgu tamamlanıncaya kadar yeni yenileme sorguları düzenlemez. Örneğin, bir saniyelik yenileme aralığınız varsa ve sorgularınız ortalama dört saniye sürüyorsa Power BI yalnızca dört saniyede bir etkili şekilde bir sorgu düzenler.

Performans sorunları yaşamaya devam edebileceğiniz iki yer vardır:

1. **Kapasite**. Sorgu ilk olarak Premium kapasiteye gelir; burada, rapor görselleştirmelerinden oluşturulan DAX sorgusu katlanır ve kaynak sorgulara değerlendirilir.
2. **DirectQuery veri kaynağı**. Önceki adımda yer alan çevrilmiş sorgular, kaynağa karşı çalıştırılır. Kaynak SQL Server örnekleriniz, SAP Hana kaynaklarınız vb. olabilir.

Yöneticilerin kullanımına sunulan [Premium Capacity Metrics uygulamasını](../admin/service-admin-premium-monitor-capacity.md) kullanarak, düşük öncelikli sorgular tarafından kapasitenin ne kadarının kullanılmakta olduğunu görselleştirebilirsiniz.

Düşük öncelikli sorgular, otomatik sayfa yenileme sorgularından ve model yenileme sorgularından oluşur. Şu anda, otomatik sayfa yenileme ve model yenileme sorgularından gelen yükü ayırt etmenin bir yolu yoktur.

Kapasitenizin düşük öncelikli sorgularla aşırı yüklendiğini fark ederseniz uygulayabileceğiniz birkaç eylem vardır:

- Daha büyük bir premium SKU isteyin.
- Rapor sahibinden yenileme aralığını azaltmasını isteme.
- Kapasite yönetici portalında şunları yapabilirsiniz:
   - Bu kapasite için otomatik sayfa yenilemeyi kapatma.
   - Minimum yenileme aralığını yükseltebilirsiniz; bu, söz konusu kapasitedeki tüm raporları etkiler.


### <a name="frequently-asked-questions"></a>Sık sorulan sorular

**Ben bir rapor yazarıyım. Rapor yenileme aralığını Power BI Desktop’ta bir saniye olacak şekilde tanımladım, ancak yayımlandıktan sonra raporum hizmette yenilenmiyor.**

* Sayfa için otomatik sayfa yenilemenin açık olduğundan emin olun. Bu ayar sayfa başına olduğundan, raporda yenilemek istediğiniz her bir sayfa için bunun açık olduğundan emin olmanız gerekir.
* Ekli Premium kapasiteye sahip bir çalışma alanına yükleyip yüklemediğinizi kontrol edin. Yapmadıysanız yenileme aralığınız 30 dakikada kilitlenir.
* Raporunuz bir Premium çalışma alanındaysa bu özelliğin ekli kapasite için etkin olup olmadığını yöneticinize sorun. Ayrıca, kapasite için minimum yenileme aralığının raporunuzla aynı veya raporunuzdan daha düşük olduğundan da emin olun.

**Ben bir kapasite yöneticisiyim. Otomatik sayfa yenileme aralığım için ayarları değiştirdim, ancak değişiklikler yansıtılmadı. Başka bir deyişle, raporlar halen olmaması gereken bir hızda yenileniyor veya otomatik sayfa yenileme ayarını açtığım halde yenilenmiyor.**

* Kapasite yöneticisi kullanıcı arabiriminde yapılan otomatik sayfa yenileme ayarı değişikliklerinin raporlara yayılması 5 dakika kadar sürebilir.
* Otomatik sayfa yenileme özelliğini hem kapasite için açmanız hem de bir raporun bunu etkinleştirmek istediğiniz sayfaları için açmanız gerekir.

**Raporum karma modda çalışıyor. (Karma mod, raporun hem DirectQuery bağlantısına hem de İçeri aktarma veri kaynağına sahip olduğu anlamına gelir.) Bazı görseller yenilenmiyor.**

- Görselleriniz İçeri Aktarma tablolarına başvuruyorsa bu davranış, beklenen bir durumdur. İçeri Aktarma için otomatik sayfa yenileme desteklenmez.
- Bu bölümdeki ilk soruya bakın.

**Raporum hizmette düzgün şekilde yenileniyordu, ancak daha sonra aniden durdu.**

* Sorunun kendi kendine çözülüp çözülmediğini görmek için sayfayı yenilemeyi deneyin.
* Kapasite yöneticinizle görüşün. Yönetici, özelliği kapatmış veya en düşük yenileme aralığını artırmış olabilir. (Bu bölümdeki ikinci soruya bakın.)

**Ben bir rapor yazarıyım. Görsellerim, belirttiğim tempoda yenilenmiyor. Daha yavaş hızda yenileniyor.**

* Sorgularınızın çalışması daha uzun sürüyorsa yenileme aralığı gecikir. Otomatik sayfa yenileme, yeni sorgular çalıştırmadan önce tüm sorguların sona ermesini bekler.
* Kapasite yöneticiniz, raporunuzda ayarlamış olduğunuzdan daha yüksek bir minimum yenileme aralığı ayarlamış olabilir. Kapasite yöneticinizden en düşük yenileme aralığını azaltmasını isteyin.

**Otomatik sayfa yenileme sorguları, önbellekten sunulur mu?**

* Hayır. Tüm otomatik sayfa yenileme sorguları, önbelleğe alınmış verileri atlar.


## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için şu makalelere bakın:

* [Power BI'da DirectQuery kullanma](../connect-data/desktop-directquery-about.md)
* [Power BI Desktop’ta bileşik modeller kullanma](../transform-model/desktop-composite-models.md)
* [Rapor öğesi performansını incelemek için Performans Analizi’ni kullanma](desktop-performance-analyzer.md)
* [Power BI Premium kapasitelerini dağıtma ve yönetme](../guidance/whitepaper-powerbi-premium-deployment.md)
* [Power BI Desktop'ta veri kaynakları](../connect-data/desktop-data-sources.md)
* [Power BI Desktop'ta verileri şekillendirme ve birleştirme](../connect-data/desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](../connect-data/desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](../connect-data/desktop-enter-data-directly-into-desktop.md)   
