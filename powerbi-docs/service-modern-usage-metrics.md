---
title: Yeni çalışma alanı deneyiminde kullanım ölçümlerini izleme
description: Power BI panoları ve raporları için yeni çalışma alanı deneyiminde kullanım ölçümlerini görüntüleme, kaydetme ve kullanma.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/22/2020
LocalizationGroup: Dashboards
ms.openlocfilehash: d3f359ad4c968407dff143458b65954844f9a22d
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76829294"
---
# <a name="monitor-usage-metrics-in-the-new-workspace-experience"></a>Yeni çalışma alanı deneyiminde kullanım ölçümlerini izleme

İçeriğinizin nasıl kullanıldığını bilmeniz etkinizi göstermenize ve çalışmalarınızı önceliklendirmenize yardımcı olur. Kullanım ölçümleriniz, raporlarınızdan birinin kuruluşunuzdaki çok sayıda kullanıcı tarafından her gün kullanıldığını, oluşturduğunuz panolardan birinin ise hiç görüntülenmediğini gösterebilir. Bu tür geri bildirimler çalışmalarınızı yönlendirme açısından benzersizdir.

Modern çalışma alanlarında rapor oluşturuyorsanız geliştirilmiş kullanım ölçümleri raporlarına erişebilirsiniz. Bunlar sayesinde kuruluşunuz genelinde bu raporların nasıl ve kimler tarafından kullanıldığını keşfedebilirsiniz. Ayrıca üst düzey performans sorunlarını da belirleyebilirsiniz. Modern Çalışma Alanı deneyimindeki geliştirilmiş kullanım raporları, [Power BI panoları ve raporları için kullanım ölçümlerini izleme](service-usage-metrics.md) başlığı altında belgelenen mevcut kullanım ölçümleri raporlarının yerini alır.

![Yeni Kullanım Ölçümleri raporu](media/service-modern-usage-metrics/power-bi-modern-usage-metrics.png)

> [!NOTE]
> Kullanım ölçümleri raporlarını yalnızca Power BI hizmetinde çalıştırabilirsiniz. Öte yandan kullanım ölçümleri raporunu kaydeder veya bir panoya sabitlerseniz mobil cihazlarda açıp raporla etkileşimli çalışabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

- Kullanım ölçümleri verilerini çalıştırmak ve bu verilere erişmek için Power BI Pro lisansı gerekir. Öte yandan kullanım ölçümleri özelliği, atanan lisanslarından bağımsız olarak tüm kullanıcılara ilişkin kullanım bilgilerini toplar.
- Raporda geliştirilmiş kullanım ölçümlerine erişmek için, rapor bir modern çalışma alanında bulunmalı ve söz konusu rapor üzerinde düzenleme erişiminiz olmalıdır.
- Power BI yöneticinizin içerik oluşturucuları için kullanım ölçümlerini etkinleştirmiş olması gerekir. Power BI yöneticiniz kullanım ölçümlerinde kullanıcı başına veri toplanmasını da etkinleştirmiş olabilir. [Yönetim portalında bu seçenekleri etkinleştirmeyi](service-admin-portal.md#control-usage-metrics) öğrenin.

## <a name="create--view-an-improved-usage-metrics-report"></a>Geliştirilmiş kullanım ölçümleri raporunu oluşturma ve görüntüleme

Yalnızca yönetici, üye veya katkıda bulunan izinlerine sahip kullanıcılar geliştirilmiş kullanım ölçümleri raporunu görüntüleyebilir. Görüntüleyici izinleri yeterli değildir. Raporunuzun durduğu modern çalışma alanında en azından katkıda bulunan izinlerine sahipseniz, aşağıdaki yordamı kullanarak geliştirilmiş kullanım ölçümlerini görüntüleyebilirsiniz:

1. Kullanım ölçümlerini analiz etmek istediğiniz raporun bulunduğu çalışma alanını açın.
2. Çalışma alanı içerik listelerinin birinden raporun bağlam menüsünü açın ve **Kullanım ölçümleri raporunu görüntüle**’yi seçin. Alternatif olarak raporu açın, sonra komut çubuğunda bağlam menüsünü açın ve ardından **Kullanım ölçümleri**’ni seçin.

    ![Kullanım Ölçümlerini seçme](media/service-modern-usage-metrics/power-bi-modern-view-usage-metrics.png)

1. Bunu ilk kez yaptığınızda Power BI, kullanım ölçümleri raporunu oluşturur ve hazır olduğunda sizi bilgilendirir.

    ![Kullanım ölçümleri raporu hazır](media/service-modern-usage-metrics/power-bi-modern-usage-metrics-ready.png)

1. Sonuçları görmek için **Kullanım ölçümlerini görüntüle**'yi seçin.
2. Bunu ilk kez yapıyorsanız Power BI eski kullanım ölçümleri raporunu açabilir. Geliştirilmiş kullanım ölçümleri raporunu görüntülemek için, sağ üst köşede Yeni kullanım raporu kapalı anahtarını **Açık** konuma getirin.

    ![Modern Kullanım Ölçümleri raporuna geçme](media/service-modern-usage-metrics/power-bi-modern-usage-metrics-on.png)

    > [!NOTE]
    > Yeni kullanım raporu anahtarının görüntülenmesi için raporunuzun bir modern çalışma alanında bulunuyor olması gerekir. Eski çalışma alanlarında geliştirilmiş kullanım ölçümleri raporları sağlanmaz.

## <a name="about-the-improved-usage-metrics-report"></a>Geliştirilmiş kullanım ölçümleri raporu hakkında

Yukarıdaki yordamı izleyerek geliştirilmiş kullanım ölçümleri raporunu görüntülediğinizde, Power BI bu içeriğin son 30 güne ait kullanım ölçümlerinin yer aldığı, önceden oluşturulmuş bir rapor oluşturur. Rapor zaten aşina olduğunuz Power BI raporlarına benzer. Son kullanıcılarınızın web üzerinden mi yoksa mobil uygulamadan mı erişim sağladığını görebilir, bu bilgiye göre filtreleme yapabilirsiniz. Raporlarınız geliştikçe kullanım ölçümleri raporları da yeni verilerle güncelleştirilecektir.

> [!NOTE]
> Kullanım ölçümleri raporları Son Görüntülenen, Çalışma Alanı, Sık Kullanılanlar veya diğer içerik listelerinde gösterilmez. Bu raporlar uygulamaya eklenemez. Kullanım ölçümleri raporundaki kutucuklardan birini bir panoya sabitlerseniz bu panoyu uygulamaya ekleyemezsiniz.

### <a name="usage-metrics-report-dataset"></a>Kullanım ölçümleri raporu veri kümesi

Geliştirilmiş kullanım ölçümleri raporu Kullanım Ölçümleri Raporu veri kümesine dayanır. Bu veri kümesi, geliştirilmiş kullanım ölçümleri raporunu ilk kez başlattığınızda Power BI’ın otomatik olarak oluşturduğu veri kümesidir. Ardından Power BI bu veri kümesini her gün yeniler. Yenileme zamanlamasını değiştiremezsiniz ama Power BI’ın kullanım ölçümleri verilerini yenilemek için kullandığı kimlik bilgilerini güncelleştirebilirsiniz. Kimlik bilgilerinin süresi dolduysa veya veri kümesinin bulunduğu çalışma alanından kullanım ölçümleri raporunu ilk kez başlatan kullanıcıyı kaldırdıysanız, zamanlanmış yenilemeyi sürdürmek için bu gerekli olabilir.

### <a name="usage-metrics-report-pages"></a>Kullanım ölçümleri raporu sayfaları

Geliştirilmiş kullanım ölçümleri raporu aşağıdaki rapor sayfalarını içerir:

- **Rapor kullanımı**    Rapor görünümleri ve rapor görüntüleyicileri hakkında tarihe göre kaç kullanıcının görüntülediği gibi bilgiler sağlar.
- **Rapor performansı**    Tipik rapor açılış sürelerini tüketim yöntemine ve tarayıcı türlerine göre ayrılmış olarak gösterir.
- **SSS**     Sık sorulan "Görüntüleyici" nedir ve "Görünüm" nedir gibi soruların yanıtlarını sağlar.

### <a name="which-metrics-are-reported"></a>Hangi ölçümler raporda yer alır?

| **Sayfa** | **Ölçüm** | **Açıklama** |
| --- | --- | --- |
| Kullanım bildirme | Rapor görünümleri | Birisi raporu her açtığında bir rapor görünümü kaydedilir. Görünüm tanımının önceki kullanım ölçümleri raporlarından farklı olduğuna dikkat edin. Rapor sayfalarının değiştirilmesi artık ek bir görünüm olarak kabul edilmez. |
| Kullanım bildirme | Benzersiz görüntüleyiciler | Görüntüleyici, zaman aralığı içinde raporu en az bir kez açmış olan kişidir (AAD kullanıcı hesabı temelinde). |
| Kullanım bildirme | Görünüm eğilimi | Görünüm eğilimi zaman içindeki görünüm sayısı değişikliklerini yansıtır. Seçilen zaman aralığının ilk yarısını ikinci yarısıyla karşılaştırır. |
| Kullanım bildirme | Tarih dilimleyici | Rapor kullanım sayfasında zaman aralığını değiştirebilir, örneğin haftalık veya iki haftalık eğilimleri hesaplayabilirsiniz. Rapor kullanımı sayfasının sol alt köşesinde, seçili rapor için kullanım verilerinin sağlandığı en erken ve en geç tarihi belirleyebilirsiniz. |
| Kullanım bildirme | Derece | Sınıflandırma, kuruluştaki diğer tüm raporlarla karşılaştırıldığında, görünüm sayısı temelinde raporun popülerliğini gösterir.   |
| Kullanım bildirme | Günlük rapor görünümü sayısı | Günlük toplam görünüm sayısı. |
| Kullanım bildirme | Günlük rapor görüntüleyici sayısı | Raporu görüntüleyen farklı kullanıcıların toplam sayısı (AAD kullanıcı hesabına göre). |
| Kullanım bildirme | Dağıtım yöntemi | Kullanıcıların rapora nasıl eriştiği; örneğin çalışma alanının üyeleri olarak, raporun onlarla paylaşılması yoluyla veya uygulamayı yükleyerek. |
| Kullanım bildirme | Platform dilimleyici | Rapora Power BI hizmetinden (powerbi.com) veya Power BI Embedded üzerinden mi yoksa mobil cihazdan mı erişim sağlandığı. |
| Kullanım bildirme | Rapor görünümleri olan kullanıcılar | Raporu açan kullanıcıların görünüm sayısına göre sıralanmış listesini gösterir. |
| Kullanım bildirme | Sayfalar | Raporda 1'den fazla sayfa varsa raporu görüntülenen sayfalara göre dilimleyebilirsiniz. Listede "Boş" seçeneğinin bulunması, bir rapor sayfasının yeni eklendiğini (yeni sayfanın gerçek adının dilimleyici listesine eklenmesi 24 saat kadar sürebilir) ve/veya rapor sayfalarının silindiğini gösterir. Bu gibi durumlarda "Boş" seçeneği görüntülenir. |
| Rapor performansı | Tipik açılış süresi | Tipik rapor açılış süresi, raporu açma işleminin süresinin yüzde birlik bölümünün 50’ncisine karşılık gelir. Diğer bir deyişle, rapor açma eylemlerinin %50’sinin tamamlanma süresinin altında kalan süredir. Rapor performansı sayfası da tipik rapor açılış süresini tüketim yöntemine ve tarayıcı türüne göre ayırır.   |
| Rapor performansı | Açılış süresi eğilimi | Açılış süresi eğilimi, rapor açma performansının zaman içindeki değişikliklerini yansıtır. Bu, raporun seçilen zaman aralığının ilk yarısındaki açılış sürelerini ikinci yarısındaki sürelerle karşılaştırır. |
| Rapor performansı | Tarih dilimleyici | Rapor performansı sayfasında zaman aralığını değiştirebilir, örneğin haftalık veya iki haftalık eğilimleri hesaplayabilirsiniz. Rapor performansı sayfasının sol alt köşesinde, seçili rapor için kullanım verilerinin sağlandığı en erken ve en geç tarihi belirleyebilirsiniz. |
| Rapor performansı | Günlük performans | Tek tek her gün için hesaplanan rapor açma eylemlerinin %10’unun, %50’sinin ve %90’ının performansı. |
| Rapor performansı | 7 günlük performans | Her tarih için son 7 gün boyunca hesaplanan rapor açma eylemlerinin %10’unun, %50’sinin ve %90’ının performansı. |
| Rapor performansı | Tüketim yöntemi | Kullanıcıların raporu nasıl açtığı; örneğin Power BI hizmeti (powerbi.com), Power BI Embedded veya mobil cihaz yoluyla. |
| Rapor performansı | Browsers (Tarayıcılar) | Kullanıcıların raporu açmak için kullandıkları tarayıcı; örneğin Firefox, Edge ve Chrome. |

## <a name="update-usage-metrics-report-credentials"></a>Kullanım ölçümleri raporu kimlik bilgilerini güncelleştirme

Kullanım Ölçümleri Raporu veri kümesini devralmak ve kimlik bilgilerini güncelleştirmek için aşağıdaki yordamı kullanın.

1. Kullanım Ölçümleri Raporu veri kümesini güncelleştirmek istediğiniz raporun bulunduğu çalışma alanını açın.
2. Üst kısımdaki siyah üst bilgi çubuğunda **Ayarlar** simgesini, sonra da **Ayarlar**’ı seçin.

    ![Ayarlar'ı seçin](media/service-modern-usage-metrics/power-bi-settings-settings.png)

3. **Veri Kümeleri** sekmesine geçin.

1. Kullanım Ölçümleri Raporu veri kümesini seçin. 

    ![Kullanım Ölçümleri veri kümesini seçme](media/service-modern-usage-metrics/power-bi-select-usage-metrics.png)
    
    Geçerli veri kümesi sahibi siz değilseniz, veri kaynağı kimlik bilgilerini güncelleştirebilmek için önce sahipliği devralmanız gerekir. 
    
5. **Devral** düğmesini seçin, sonra **Veri kümesi ayarlarını devral** iletişim kutusunda **Devral**’ı yeniden seçin.

1. **Veri kaynağı kimlik bilgileri**’nin altında **Kimlik bilgilerini düzenle**’yi seçin.

    ![Kimlik bilgilerini düzenle](media/service-modern-usage-metrics/power-bi-usage-metrics-edit-credentials.png)

2. **Kullanım Ölçümleri Raporunu Yapılandır** iletişim kutusunda **Oturum aç**’ı seçin.

    ![Oturum aç'ı seçme](media/service-modern-usage-metrics/power-bi-modern-usage-metrics-configure.png)

1. Oturum açma dizisini tamamlayın ve veri kaynağının başarıyla güncelleştirildiğine ilişkin bildirime dikkat edin.

    > [!NOTE]
    > Kullanım Ölçümleri Raporu veri kümesi son 30 günün kullanım verilerini içerir. Yeni kullanım verilerinin içeri aktarılması 24 saat kadar sürebilir. Power BI kullanıcı arabirimini kullanarak el ile yenileme tetikleyemezsiniz.


## <a name="disable-usage-metrics-reports"></a>Kullanım ölçümleri raporunu devre dışı bırakma

Kullanım ölçümleri raporları, Power BI veya Office 365 yöneticileri tarafından etkinleştirilip devre dışı bırakılabilecek bir özelliktir. Yöneticiler kullanım ölçümlerine erişim sahibi olan kullanıcılar üzerinde ayrıntılı denetime sahiptir. Varsayılan olarak bu özellik, kuruluştaki tüm kullanıcılar için Etkin durumdadır. Bu ayarlarla ilgili ayrıntılar için Yönetim portalı makalesinde [Kullanım ölçümlerini denetleme](service-admin-portal.md#control-usage-metrics) konusuna bakın.

> [!NOTE]
> Yalnızca Power BI kiracısının yöneticileri Yönetim portalını ve düzenleme ayarlarını görebilir.

## <a name="exclude-user-information-from-usage-metrics-reports"></a>Kullanım ölçümleri raporundan kullanıcı bilgilerini dışlama

Varsayılan olarak, kullanım ölçümleri için kullanıcı başına veriler etkinleştirilir ve içerik tüketicisinin hesap bilgileri ölçüm raporuna eklenir. Yöneticiler kullanıcıların bir bölümü veya tümü için bu bilgilerin ortaya konmasını istemiyorsa, belirli güvenlik grupları veya kuruluşun tamamı için Power BI yönetici portalı kiracı ayarlarında İçerik oluşturucuları için kullanım ölçümlerinde kullanıcı başına veriler seçeneğini devre dışı bırakarak kullanıcı bilgilerini kullanım raporunuzun dışında tutabilir.

1. Yönetici portalının **Kiracı ayarları** sekmesindeki **Denetim ve kullanım ayarları**’nın altında **İçerik oluşturucuları için kullanım ölçümlerinde kullanıcı başına veriler**’i genişletin ve **Devre Dışı**’nı seçin.

2. **Geçerli kullanım ölçümleri içeriğindeki tüm kullanıcıya özgü verileri silinip silinmeyeceğine** karar verin ve **Uygula**’yı seçin.

    ![Kullanıcı başına ölçümleri devre dışı bırakma](media/service-modern-usage-metrics/power-bi-admin-disable-per-user-metrics.png)

Kullanıcı bilgileri dışlandıysa, kullanım raporunda bu kullanıcılara Adsız kullanıcılar olarak başvurulur.

Yöneticiler kullanım ölçümlerini kuruluşun tamamı için devre dışı bırakırken Tüm mevcut kullanım ölçümleri içeriğini silin seçeneğini kullanarak kullanım ölçümleri raporları kullanılarak oluşturulmuş olan mevcut tüm raporları ve pano kutucuklarını silebilir. Bu seçenek, kullanmakta olanlar dahil olmak üzere kuruluştaki tüm kullanıcılar için kullanım ölçümlerine yönelik erişimi kaldırır. Kullanım ölçümleri içeriğini silme işlemi geri alınamaz.

> [!NOTE]
> Yalnızca Power BI kiracısının yöneticileri Yönetici portalını görebilir ve İçerik oluşturucuları için kullanım ölçümlerinde kullanıcı başına veriler ayarını yapılandırabilir.

## <a name="customize-the-usage-metrics-report"></a>Kullanım ölçümleri raporunu özelleştirme

Rapor verilerini yakından incelemek veya temel veri kümesiyle kendi raporlarınızı oluşturmak için birkaç seçeneğiniz vardır:

- **Power BI hizmetinde [raporun bir kopyasını oluşturma.](#create-a-copy-of-the-usage-report)**   Kullanım ölçümleri raporunun kendi gereksinimlerinize göre özelleştirebileceğiniz ayrı bir örneğini oluşturmak için **Kopyasını kaydet**’i kullanın.
- **Yeni bir raporla [veri kümesine bağlanın](#create-a-new-usage-report-in-power-bi-desktop).**   Her çalışma alanı için, daha önce [Kullanım ölçümleri raporu veri kümesi](#usage-metrics-report-dataset) bölümünde açıklandığı gibi veri kümesinin adı "Kullanım Ölçümleri Raporu" olur. Power BI Desktop'ı kullanarak temel veri kümesine dayanan özel kullanım ölçümleri raporları da oluşturabilirsiniz.
- **[Excel’de Çözümle’yi kullanın](#analyze-usage-data-in-excel).**   Ayrıca Power BI kullanım verilerini analiz etmek için Microsoft Excel 2010 SP1 veya sonraki sürümlerinin PivotTable, grafik ve dilimleyici özelliklerinden de yararlanabilirsiniz. [Excel’de Çözümle](service-analyze-in-excel.md) özelliği hakkında daha fazla bilgi edinin.

### <a name="create-a-copy-of-the-usage-report"></a>Kullanım raporunun kopyasını oluşturma

Önceden hazırlanmış salt okunur bir kullanım raporunun kopyasını oluşturduğunuzda, Power BI raporun düzenlenebilir bir örneğini oluşturur. İlk bakışta iki rapor aynı görünür. Ama artık raporu Düzenleme görünümünde açabilir; yeni görselleştirme, filtre ve sayfa ekleyebilir, var olan görselleştirmeleri değiştirebilir veya silebilir ve başka işlemler yapabilirsiniz. Power BI yeni raporu geçerli çalışma alanına kaydeder.

1. Yeni kullanım ölçümleri raporunda **Diğer seçenekler** menüsünü (...) ve sonra da **Kopyasını kaydet**’i seçin.

    ![Raporun kopyasını kaydetme](media/service-modern-usage-metrics/power-bi-modern-usage-metrics-save.png)

2. **Raporunuzu kaydedin** iletişim kutusunda bir ad girin ve **Kaydet**’i seçin.

    Power BI düzenlenebilir bir Power BI raporu oluşturur, bunu geçerli çalışma alanına kaydeder ve raporun kopyasını açar. 

3. **Diğer seçenekler** menüsünü (…) seçin ve sonra da **Düzenle**’yi seçerek Düzenleme görünümüne geçin. 

    Örneğin filtreleri değiştirebilir, yeni sayfalar ekleyebilir, yeni görselleştirmeler oluşturabilir, yazı tiplerini ve renklerini biçimlendirebilirsiniz.

1. Yeni rapor geçerli çalışma alanında Raporlar sekmesine kaydedilir ve Son görüntülenen içerik listesine eklenir.

    ![Raporlar sekmesinde yeni rapor](media/service-modern-usage-metrics/power-bi-modern-usage-metrics-new-report.png)

### <a name="create-a-new-usage-report-in-power-bi-desktop"></a>Power BI Desktop'ta yeni kullanım raporu oluşturma

Power BI Desktop’ta Kullanım Ölçümleri Raporu veri kümesini temel alan yeni bir kullanım raporu oluşturabilirsiniz. Kullanım Ölçümleri Raporu veri kümesiyle bağlantı kurmak ve kendi raporunuzu oluşturmak için, Power BI Desktop’ta Power BI hizmeti oturumu açmanız gerekir. 

1. Power BI Desktop'ı açın.

2. Power BI hizmetinde oturum açmadıysanız **Dosya** menüsünde **Oturum aç**’ı seçin.

1. Kullanım Ölçümleri Raporu veri kümesine bağlanmak için **Giriş** şeridinde **Veri Al**’ı seçin.

4. Sol bölmede **Power Platform**’u seçin, sonra da **Power BI veri kümeleri** > **Bağlan**’ı seçin.

    ![Veri al > Power Platform](media/service-modern-usage-metrics/power-bi-desktop-get-data.png)

1. Ekranı kaydırarak istenen veri kümesine gelin veya arama kutusuna *Kullanım Ölçümleri Raporu* yazın. 

6. Çalışma Alanı sütununda doğru veri kümesini seçtiğinizi onaylayın, ardından **Oluştur**’u seçin. 

    ![Kullanım Ölçümleri Raporu veri kümesini seçme](media/service-modern-usage-metrics/power-bi-desktop-select-usage-metrics.png)

7. Power BI Desktop’ta, seçilen veri kümesindeki tablolara, sütunlara ve ölçülere erişmenizi sağlayan Alanlar listesini gözden geçirin.

    ![Kullanım Ölçümleri Raporu alanlar listesini görüntüleme](media/service-modern-usage-metrics/power-bi-desktop-fields-list.png)

1. Artık tümüyle aynı Kullanım Ölçümleri Raporu veri kümesinden özel kullanım raporları oluşturabilir ve bunları paylaşabilirsiniz.

### <a name="analyze-usage-data-in-excel"></a>Excel’de kullanım verilerini analiz etme

Excel’de kullanım verilerine bağlandığınızda, önceden tanımlanmış ölçüleri kullanan PivotTable’lar oluşturabilirsiniz. Excel PivotTable'larının Power BI veri kümesine bağlanırken sayısal alanların sürükle ve bırak ile toplama özelliğini desteklemediğini aklınızda bulundurun.

1. İlk olarak, henüz yapmadıysanız [kullanım ölçümleri raporunun kopyasını oluşturun](#create-a-copy-of-the-usage-report). 

2. Yeni kullanım ölçümleri raporunu açın, **Diğer seçenekler** menüsünü (…) ve sonra da **Excel’de Çözümle**’yi seçin.

    ![Excel’de Analiz Et](media/service-modern-usage-metrics/power-bi-export-excel.png)

1. **Öncelikle bazı Excel güncelleştirmeleri yapmanız gerekiyor** iletişim kutusunu görüyorsanız **İndir**’i seçin ve Power BI bağlantısı için en son güncelleştirmeleri yükleyin veya **Bu güncelleştirmeleri zaten yükledim** öğesini seçin.

    ![Excel güncelleştirmeleri](media/service-modern-usage-metrics/power-bi-excel-updates.png)

    > [!NOTE]
    > Bazı kuruluşların Grup İlkesi kuralları, Excel'e gerekli olan Excel'de Çözümle güncelleştirmelerinin yüklenmesini engelleyebilir. Güncelleştirmeleri yükleyemiyorsanız yöneticinizle görüşün.

1. Kullanım Ölçümleri raporu.odc dosyasıyla ne yapmak istediğinizi soran tarayıcı iletişim kutusunda **Aç**’ı seçin.

    ![.odc dosyasını açma](media/service-modern-usage-metrics/power-bi-open-odc-file.png)

1. Power BI Excel’i başlatır. .odc dosyasının dosya adını ve yolunu doğrulayın, sonra da **Etkinleştir**’i seçin.

    ![Excel güvenlik bildirimi](media/service-modern-usage-metrics/power-bi-excel-security-notice.png)

1. Artık Excel açıldığı ve boş bir PivotTable’ınız olduğuna göre, alanları Satırlar, Sütunlar, Filtreler ve Değerler kutularına sürükleyebilir, ardından kullanım verilerinizde özel görünümler oluşturabilirsiniz.

    ![Excel'de PivotTable](media/service-modern-usage-metrics/power-bi-pivottable-excel.png)

## <a name="usage-metrics-in-national-clouds"></a>Ulusal bulutlarda kullanım ölçümleri

Power BI, ayrı ayrı ulusal bulutlarda kullanılabilir. Bu bulutlar hizmet teslimi, veri dayanıklılığı, erişim ve denetimle ilgili yerel yasal düzenlemelere yönelik benzersiz bir modelle birlikte, Power BI'ın küresel sürümüyle aynı güvenlik, gizlilik, uyumluluk ve saydamlık düzeyleri sunar. Yerel yasal düzenlemelere yönelik bu benzersiz modelden dolayı, ulusal bulutlarda kullanım ölçümleri sağlanmaz. Daha fazla bilgi için [ulusal bulutlar](https://powerbi.microsoft.com/clouds/) konusuna bakın.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Geliştirilmiş kullanım ölçümleri raporuyla bu raporun öncülünü karşılaştırırken farklılıklar olabileceğini ve bunların nedenlerini anlamak önemlidir. Özellikle rapor kullanım ölçümleri şimdi Power BI hizmetinden toplanan etkinlik verilerini temel almaktadır. Kullanım ölçümleri raporunun önceki sürümleri, hizmetten toplanan kullanım ölçümleriyle her zaman eşleşmeyen istemci telemetrisine dayanıyordu. Üstelik geliştirilmiş kullanım ölçümleri raporunda farklı bir “Görünüm” tanımı kullanılır. Görünüm, birisi raporu her açtığında hizmette kaydedildiği şekliyle bir rapor açma olayıdır. Rapor sayfalarının değiştirilmesi artık ek bir görünüm olarak kabul edilmez.

> [!NOTE]
> Geliştirilmiş kullanım ölçümleri raporu Power BI hizmetinden toplanan etkinlik verilerine dayandığından, kullanım ölçümleri artık denetim günlüklerinin ve etkinlik günlüklerinin toplam sayılarıyla eşleşir. Tutarsız ağ bağlantıları, reklam engelleyiciler veya istemci tarafı sorunlarından dolayı etkinliklerin eksik veya fazla sayılması artık görüntüleyici veya görünüm sayılarını çarpıtmaz.

Önceki kullanım ölçümleri raporlarıyla geliştirilmiş raporlar arasında yukarıda belirtilen farklara ek olarak, önceki sürüm için aşağıdaki sınırlamalara da dikkat edin:

- Pano kullanım ölçümleri hala kullanım ölçümleri raporlarının önceki sürümüne dayanıyor.
- Geliştirilmiş kullanım ölçümleri raporları yalnızca modern çalışma alanlarındaki raporlarda kullanılabiliyor. Eski çalışma alanlarındaki raporlar yalnızca kullanım ölçümleri raporlarının önceki sürümünü destekler.
- Rapor performans ölçümleri istemci telemetrisine dayanır. Bazı görünüm türleri performans ölçümlerine dahil edilmez. Örneğin kullanıcı e-posta iletisinde bir raporun bağlantısını seçtiğinde, görünüm rapor kullanımında hesaba katılır ama performans ölçümlerinde olay yoktur.
- Sayfalandırılmış Raporlar için rapor performansı ölçümleri kullanılamaz. Bu tür raporlar için ne Rapor kullanımı sayfasındaki Sayfalar sekmesi ne de Rapor performansı sayfasındaki grafikler veri gösterir.
- İç içe gruplar kullanıldığında kullanıcı maskeleme beklendiği gibi çalışmaz. Kuruluşunuz Power BI yönetici portalı kiracı ayarlarında İçerik oluşturucuları için kullanım ölçümlerinde kullanıcıya özgü veriler ayarını devre dışı bıraktıysa yalnızca en üst düzeydeki üyeler maskelenir. Alt grupların üyeleri hala görünür durumdadır.
- Kullanım Ölçümleri Raporu veri kümesini başlatmak birkaç dakika sürebilir ve sonuçta boş bir kullanım ölçümleri raporu gösterilebilir, çünkü Power BI kullanıcı arabirimi yenileme işleminin bitmesini beklemez. Yenileme işleminin başarılı olduğunu doğrulamak için Kullanım Ölçümleri Raporu veri kümesi ayarlarında yenileme geçmişini denetleyin.
- Kullanım Ölçümleri Raporu veri kümesini başlatma işlemi, yenileme sırasında karşılaşılan zaman aşımından dolayı başarısız olabilir. Bu sorunu çözmek için aşağıdaki Sorun Giderme bölümüne bakın.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

Yukarıda anlatılan önemli noktalar ve sınırlamalara ek olarak, kullanım ölçümleriyle ilgili aşağıdaki soru ve yanıtlar kullanıcılara ve yöneticilere yardımcı olabilir:

**S:** Raporda kullanım ölçümlerini çalıştıramıyorum.

**Y:** Kullanım ölçümlerimi yalnızca sahip olduğunuz veya düzenleme izniniz olan raporlarda görebilirsiniz.

**S:** Mevcut kullanım ölçümleri raporumun sağ üst köşesinde Yeni kullanım raporu açık düğmesini neden göremiyorum?

**Y:** Geliştirilmiş kullanım ölçümleri raporu yalnızca modern çalışma alanlarındaki raporlarda kullanılabilir.

**S:** Rapor hangi zaman aralığını kapsar?

**Y:** Kullanım raporu, geçerli günün etkinlikleri hariç son 30 günün etkinlik verilerini temel alır. Rapor kullanım sayfasındaki Tarih dilimleyicisini kullanarak zaman aralığını daraltabilir, örneğin yalnızca son haftanın verilerini analiz edebilirsiniz.

**S:** En son etkinlik verilerini ne zaman göreceğim?

**Y:** Kullanım raporu UTC saat dilimine göre son tamamlanmış güne kadar olan etkinlik verilerini içerir. Raporda gösterilen veriler, veri kümesinin yenileme zamanına da bağlıdır. Power BI veri kümesini günde bir kez yeniler.

**S:** Veriler güncel değil gibi görünüyor.

**Y:** Yeni etkinlik verilerinin kullanım raporunda görüntülenmesinin 24 saat kadar sürebileceğini unutmayın.

**S:** Kullanım verilerinin veri kaynağı nedir?

**Y:** Kullanım Ölçümleri Raporu veri kümesi özel Kullanım Ölçümleri Veri Bağlayıcısı’nı kullanarak verilerini Power BI’ın dahili bir kullanım ölçümleri deposundan içeri aktarır. Kullanım Ölçümleri Veri Bağlayıcısı’nın kimlik bilgilerini Kullanım Ölçümleri Raporu veri kümesinin ayarlar sayfasında güncelleştirebilirsiniz.

**S:** Verilere nasıl bağlanabilirim? Veya varsayılan raporu nasıl değiştirebilirim?

**Y:** Salt okunur, önceden oluşturulmuş kullanım raporunun bir kopyasını oluşturabilirsiniz. Raporun kopyası aynı Kullanım Ölçümleri Raporu veri kümesine bağlanır ve rapor ayrıntılarını düzenlemenize olanak tanır.

**S:** "Görüntüleyici" ve "Görünüm" nedir?

**Y:** Görüntüleyici, zaman aralığı içinde raporu en az bir kez açmış olan kişidir. Görünüm, bir rapor açma olayıdır. Birisi raporu her açtığında bir rapor görünümü kaydedilir.

Görünüm tanımının önceki kullanım ölçümleri raporlarından farklı olduğuna dikkat edin. Rapor sayfalarının değiştirilmesi artık ek bir görünüm olarak kabul edilmez.

**S:** "Görünüm eğilimi" nasıl hesaplanır?

**Y:** Görünüm eğilimi zaman içindeki görünüm sayısı değişikliklerini yansıtır. Seçilen zaman aralığının ilk yarısını ikinci yarısıyla karşılaştırır. Rapor kullanım sayfasındaki Tarih dilimleyicisini kullanarak zaman aralığını değiştirebilir, haftalık veya iki haftalık eğilimleri hesaplayabilirsiniz.

**S:** "Dağıtım" ve "Platform" ne anlama gelir?

**Y:** Dağıtım, görüntüleyicilerin rapora nasıl erişim elde ettiğini gösterir: doğrudan paylaşılan, çalışma alanı erişimi yoluyla veya uygulama aracılığıyla.

Platform, görüntüleyicinin raporu açmak için kullandığı teknolojiyi gösterir: PowerBI.com, Mobile veya Embedded yoluyla.

**S:** Rapor sınıflandırması nasıl çalışır?

**Y:** Sınıflandırma, kuruluştaki diğer tüm raporlarla karşılaştırıldığında, görünüm sayısı temelinde raporun popülerliğini gösterir.

**S:** "Adsız Kullanıcılar" kimdir?

**Y:** Kuruluşunuz kullanıcı bilgilerini kullanım raporunuzdan dışlamaya karar verebilir. Kullanım raporunda dışlanan kullanıcılara Adsız kullanıcılar olarak başvurulur.

**S:** "Tipik rapor açılış süresi" nedir?

**Y:** Tipik rapor açılış süresi, raporu açma işleminin süresinin yüzde birlik bölümünün 50’ncisine karşılık gelir. Diğer bir deyişle, rapor açma eylemlerinin %50’sinin tamamlanma süresinin altında kalan süredir. Rapor performansı sayfası da tipik rapor açılış süresini tüketim yöntemine ve tarayıcı türüne göre ayırır.

**S:** "Açılış süresi eğilimi" nasıl hesaplanır?

**Y:** Açılış süresi eğilimi, rapor açma performansının zaman içindeki değişikliklerini yansıtır. Bu, raporun seçilen zaman aralığının ilk yarısındaki açılış sürelerini ikinci yarısındaki sürelerle karşılaştırır. Rapor performansı sayfasındaki Tarih dilimleyicisini kullanarak zaman aralığını değiştirebilir, örneğin haftalık veya iki haftalık eğilimleri hesaplayabilirsiniz.

**S:**  Kullanım ölçümleri raporunun önceki sürümünde dört rapor vardı ama geliştirilmiş sürümde yalnızca üç rapor görüntüleniyor.

**Y:**  Geliştirilmiş kullanım ölçümleri raporu yalnızca son 30 gün içinde açılmış olan raporları içeriyor; oysa önceki sürüm son 90 günün raporlarını kapsıyordu. Bir rapor geliştirilmiş kullanım ölçümleri raporunda yer almıyorsa büyük olasılıkla kullanılmasının üzerinden 30 günden fazla bir süre geçmiştir.

## <a name="troubleshoot-delete-the-dataset"></a>Sorun giderme: Veri kümesini silme

Veri tutarlılığı veya yenileme sorunlarından kuşkulanıyorsanız, mevcut Kullanım Ölçümleri Raporu veri kümesini silmek anlamlı olabilir. Ardından Kullanım Ölçümlerini Görüntüle işlemini yeniden çalıştırıp ilişkili geliştirilmiş kullanım ölçümleri raporlarıyla yeni bir veri kümesi oluşturabilirsiniz. Şu adımları izleyin.

### <a name="delete-the-dataset"></a>Veri kümesini silme

1. Kullanım Ölçümleri Raporu veri kümesini sıfırlamak istediğiniz raporun bulunduğu çalışma alanını açın.

2. Üst kısımdaki siyah üst bilgi çubuğunda **Ayarlar** simgesini, sonra da **Ayarlar**’ı seçin.

    ![Ayarlar'ı seçin](media/service-modern-usage-metrics/power-bi-settings-settings.png)

3. **Veri Kümeleri** sekmesine geçin ve Kullanım Ölçümleri Raporu veri kümesini seçin. 

    ![Kullanım ölçümleri veri kümesi](media/service-modern-usage-metrics/power-bi-settings-usage-report-dataset.png)

5. Tarayıcınızın adres çubuğunda görüntülenen URL’den çalışma alanı ve veri kümesi kimliklerini kopyalayın.

    ![Kullanım ölçümleri veri kümesi URL’si](media/service-modern-usage-metrics/power-bi-usage-metrics-url.png)

1. Tarayıcınızda [https://docs.microsoft.com/rest/api/power-bi/datasets/deletedatasetingroup](https://docs.microsoft.com/rest/api/power-bi/datasets/deletedatasetingroup) adresine gidin ve **Dene** düğmesini seçin.

    ![Veri kümesini silme Dene düğmesi](media/service-modern-usage-metrics/power-bi-delete-dataset-try-it.png)

1. Power BI’da oturum açın, Çalışma Alanı kimliğini **groupId** metin kutusuna ve veri kümesi kimliğini **datasetId** metin kutusuna yapıştırın, sonra da **Çalıştır**’ı seçin. 

    ![REST API’yi deneme](media/service-modern-usage-metrics/power-bi-rest-api-try-it.png)

1. **Çalıştır** düğmesinin altında, hizmetin **200** Yanıt Kodunu döndürdüğünü doğrulayın. Bu kod, veri kümesinin ve onunla ilişkilendirilmiş kullanım ölçümleri raporlarının başarıyla silindiğini gösterir.

    ![Yanıt kodu 200](media/service-modern-usage-metrics/power-bi-response-code-200.png)

### <a name="create-a-fresh-usage-metrics-report"></a>Yeni bir kullanım ölçümleri raporu oluşturma

1. Power BI hizmetine döndüğünüzde veri kümesinin gittiğini görürsünüz.

    ![Kullanım ölçümleri raporu yok](media/service-modern-usage-metrics/power-bi-no-usage-metrics-dataset.png)

2. Kullanım Ölçümleri raporunu Raporlar listesinde görmeye devam ediyorsanız tarayıcınızı yenileyin.

3. [Yeni bir kullanım ölçümleri raporu oluşturun](#create--view-an-improved-usage-metrics-report).

## <a name="next-steps"></a>Sonraki adımlar

[Yönetim portalında Power BI’ı yönetme](service-admin-portal.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
