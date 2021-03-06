---
title: Raporun tamamını PowerPoint'e aktarma
description: Bir Power BI raporunu PowerPoint'e nasıl aktaracağınızı öğrenin.
author: mihart
ms.author: mihart
ms.reviewer: mihart
ms.custom: contperf-fy20q4
ms.service: powerbi
ms.subservice: pbi-explore
ms.topic: how-to
ms.date: 01/12/2021
LocalizationGroup: Share your work
ms.openlocfilehash: 6001cbd1b503084012b358c4dabf7db27405b9c4
ms.sourcegitcommit: e8c3f327ac0fc73c118874a24d2601733f8f9e45
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2021
ms.locfileid: "98718635"
---
# <a name="export-reports-to-powerpoint"></a>Raporları PowerPoint dosyasına dışarı aktarma

[!INCLUDE[consumer-appliesto-yynn](../includes/consumer-appliesto-yynn.md)]


Power BI hizmetiyle (app.powerbi.com) raporunuzu Microsoft PowerPoint’te yayımlayabilir ve Power BI raporunuzu temel alan bir slayt destesini kolayca oluşturabilirsiniz. PowerPoint’e aktardığınızda aşağıdakiler gerçekleşir:

* Power BI raporundaki her sayfa, PowerPoint’te tek bir slayt olur.
* Power BI raporundaki her sayfa, PowerPoint’te yüksek çözünürlüklü tek bir görüntü olarak dışarı aktarılır.
* Rapora eklediğiniz filtre ve dilimleyici ayarlarını koruyabilirsiniz.
* PowerPoint’te Power BI raporuna yeniden bağlanan bir bağlantı oluşturulur.

**Power BI raporunuzu** **PowerPoint**’e hızla aktarabilirsiniz. Sonraki bölümde açıklanan adımları uygulayın.

Ayrıca isterseniz Power BI hizmetindeki görselleri tek tek kopyalayıp PowerPoint'e (veya yapıştırmayı destekleyen herhangi bir programa) yapıştırabilirsiniz. **Resim olarak kopyala** simgesini seçerek görseli panonuza kopyalayın. Ardından PowerPoint’i açın ve görseli yapıştırın. Daha fazla bilgi için bkz. [Görselleri statik resim olarak kopyalama](../visuals/power-bi-visualization-copy-paste.md).

![Resim olarak kopyala simgesini seçme](media/end-user-powerpoint/power-bi-copy.png)

## <a name="export-your-power-bi-report-to-powerpoint"></a>Power BI raporunuzu PowerPoint’e aktarma
**Power BI hizmetinde**, tuval üzerinde görüntülenecek bir rapor seçin. **Giriş**'ten, **Uygulamalar**’dan veya gezinti bölmesindeki başka bir kapsayıcıdan bir rapor seçebilirsiniz.

PowerPoint’e aktarmak istediğiniz rapor tuvalde görüntülendiğinde menü çubuğundan **Dosya** > **PowerPoint'e aktar**'ı seçin.

![Menü çubuğundan Dışarı Aktar’ı seçme](media/end-user-powerpoint/power-bi-export.png)

Açılan menüde **Geçerli değerler**’i veya **Varsayılan değerler**’i kullanma seçeneği sunulur. **Geçerli değerler** seçeneği, raporu dilimleyici ve filtre değerlerinde yaptığınız etkin değişiklikleri içeren geçerli durumunda dışarı aktarır.  Kullanıcıların çoğu bu seçeneği tercih eder. Ekranı kaydırdıysanız **Geçerli değerler**, görselin kaydırma durumunu kapsamaz ancak verilerin en üstteki bölümü dışarı aktarılır. Alternatif olarak, **Varsayılan değerler** seçildiğinde rapor özgün durumda (*tasarımcının* paylaştığı şekilde) dışarı aktarılır ve özgün durumda yaptığınız değişiklikleri yansıtmaz.

![Neyin Dışarı Aktarılacağını seçme](media/end-user-powerpoint/power-bi-current-values.png)
 
Ayrıca, raporun gizli sekmelerinin dışarı aktarılıp aktarılmayacağını seçebileceğiniz bir onay kutusu vardır. Yalnızca tarayıcınızda görebildiğiniz rapor sekmelerini dışarı aktarmak isterseniz bu onay kutusunu seçin. Dışarı aktarma işlemine tüm gizli sekmelerin de alınmasını tercih ederseniz bu kutuyu işaretlemeden bırakın. Onay kutusu soluk görüntüleniyorsa raporda gizli sekme yoktur. Gizli sekmeye örnek olarak bir araç ipucu sekmesi verilebilir. [Özel araç ipuçları](../create-reports/desktop-tooltips.md) rapor *tasarımcıları* tarafından oluşturulur ve Power BI hizmetinde *iş kullanıcıları* için rapor sekmeleri olarak görüntülenmez. 

Ayrıca **Yalnızca geçerli sayfayı dışarı aktar** seçeneğini işaretleyerek raporun yalnızca görüntülemekte olduğunuz sayfasını dışarı aktarabilirsiniz.  Bu seçenek varsayılan olarak işaretlenmemiş durumdadır ve raporun tüm sayfaları dışarı aktarılır.

Seçimlerinizi yaptıktan sonra devam etmek için **Dışarı Aktar**’ı seçin. Power BI hizmeti tarayıcı penceresinin sağ üst köşesinde, raporun PowerPoint’e aktarıldığını belirten bir bildirim başlığı görürsünüz. 



![PowerPoint’e aktarma devam ediyor bildirimi](media/end-user-powerpoint/power-bi-export-progress.png)

Dışarı aktarma işlemi birkaç dakika sürebilir. Raporun yapısı ve Power BI hizmeti üzerindeki geçerli yük gibi etmenler gereken zamanı etkileyebilir. Rapor dışarı aktarılırken Power BI’da çalışmaya devam edebilirsiniz.

Power BI hizmeti dışarı aktarma işlemini tamamladıktan sonra bildirim başlığı bunu bildirecek şekilde değişir. Dosyanız artık, tarayıcınızın indirilen dosyaları görüntülediği konumda kullanılabilir. Aşağıdaki görüntüde, tarayıcı pencerenizin alt kısmında bulunan bir indirme başlığı olarak gösterilmektedir.

![Ekranın en altındaki tarayıcı bildirimi](media/end-user-powerpoint/power-bi-browsers.png)

İşte bu kadar kolay. Dosyayı indirebilir, PowerPoint ile açabilir ve ardından herhangi bir PowerPoint destesi ile aynı şekilde dosyayı değiştirebilir veya geliştirebilirsiniz.

## <a name="open-the-powerpoint-file"></a>PowerPoint dosyasını açın
Power BI'dan aktarılan PowerPoint dosyasını açtığınızda, ilgi çekici ve kullanışlı birkaç öğeyle karşılaşırsınız. Aşağıdaki görüntüye bir göz atın ve bu ilgi çekici özelliklerden bazılarının açıklandığı numaralı maddeleri inceleyin. PowerPoint sayfaları, Power BI raporundaki özgün sayfa büyüklüklerinden veya boyutlarından bağımsız olarak her zaman standart 9:16 boyutunda oluşturulur.

![PowerPoint açılıyor](media/end-user-powerpoint/power-bi-powerpoint-numbered.png)

1. Slayt destesinin ilk sayfasında raporunuzun adı ve ayrıca slayt destesi için temel alınan raporu **Power BI’da Görüntülemenizi** sağlayan bir bağlantı bulunur.
2. Raporla ilgili bazı yararlı bilgiler de bulabilirsiniz. **Son veri yenileme**, dışarı aktarılan raporun temel aldığı tarih ve saati gösterir. **İndirme zamanı**, Power BI raporunun bir PowerPoint dosyasına aktarıldığı tarih ve saati gösterir. **İndirme zamanı**, dışarı aktarma sırasında bilgisayarınızın saat dilimine göre belirlenir.


3. Gezinti bölmesinde gösterildiği gibi her rapor sayfası ayrı bir slayttır. 
4. Yayımlanan raporunuz, varsa ilgili Power BI ayarlarınıza, yoksa tarayıcınızın yerel ayarına göre seçilen dilde gösterilir. Tarayıcınızda dil tercihinizi görmek veya ayarlamak için dişli simgesini seçin ve ![Dişli simgesi](media/end-user-powerpoint/power-bi-settings-icon.png) > **Ayarlar** > **Genel** > **Dil** seçeneğini belirtin. Yerel ayar bilgileri için bkz. [Power BI için desteklenen diller ve ülkeler veya bölgeler](../fundamentals/supported-languages-countries-regions.md).


Tek bir slaytı görüntülediğinizde her rapor sayfasının bağımsız bir görüntü olduğunu görürsünüz. PowerPoint'te her slayt statik bir resim olduğundan kaydırma kullanılamaz.

![Her görseli ayrı bir görüntü olarak gösteren ekran](media/end-user-powerpoint/power-bi-images.png)

Buradan sonra PowerPoint destenizle veya yüksek çözünürlüklü görüntülerden biriyle ne yapacağınız size kalmıştır.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
**PowerPoint’e Aktar** özelliği ile çalışırken dikkat edilmesi gereken bazı önemli noktalar ve sınırlamalar vardır.
 

* **Dışarı aktarma** seçeneğini görmüyorsanız, bir raporu (Pano değil) görüntülediğinizden emin olun.

* Şu anda dışarı aktarma için **Geçerli Değerler**’i seçtiğinizde [URL filtreleri](../collaborate-share/service-url-filters.md) dikkate alınmaz.

* PowerPoint'e aktarma sırasında raporda kullanılan özel yazı tipleri, varsayılan yazı tipiyle değiştirilir.

* Aşağıdaki görsel türleri desteklenmez ve PowerPoint'e aktarılmaz:
   - [Sertifikalanmamış özel görseller](../developer/visuals/power-bi-custom-visuals-certified.md) desteklenmez. 
   - [ESRI ArcGIS görseli](../visuals/power-bi-visualizations-arcgis.md) desteklenmiyor
   - R ve Python görselleri desteklenmez.
   - Arka plan görüntüleri grafiğin sınırlayıcı alanına göre kırpılır. Raporu PowerPoint’e aktarmadan önce arka plan görüntülerini kaldırmanızı öneririz.

* Bazı raporlar dışarı aktarılamaz. Bu modüller şunlardır:
    - Bir panoyu kuruluşunuzun dışındaki biriyle (yani Power BI kiracınızda bulunmayan bir kullanıcıyla) paylaştığınızda bu kullanıcı, paylaşılan panonun ilişkili raporlarını PowerPoint’e aktaramaz. Örneğin, siz aaron@contoso.com iseniz david@cohowinery.com ile paylaşımda bulunabilirsiniz. Ancak david@cohowinery.com, ilişkili raporları PowerPoint’e aktaramaz.
    - 50'den fazla rapor sayfası olan raporlar. Sayfalandırılmış raporlarda bu sınırlama yoktur. Ayrıntılar için bkz. [sayfalandırılmış rapor yazdırma](end-user-paginated-report.md#interact-with-a-paginated-report) .
    - Dışarı aktarıldığında boyutu 500 MB ve üzeri olan raporlar. 
    - PowerPoint'in eski sürümlerine aktarılan raporlar.
    - İşlenmesi bir saatten uzun süren raporlar. 
    - Yüklenmesi 6 dakikadan uzun süren rapor sayfaları. 

* Power BI hizmetinde **PowerPoint’e Aktar** menü öğesi kullanılamıyorsa bunun nedeni büyük olasılıkla Power BI yöneticisinin veya rapor sahibinin özelliği devre dışı bırakmış olmasıdır. Ayrıntılar için yöneticinize veya rapor sahibine başvurun.
* Power BI hizmeti, PowerPoint dışa aktarma dili olarak Power BI dil ayarınızı kullanır. Tarayıcınızda dil tercihinizi görmek veya ayarlamak için dişli simgesini seçin ve ![Dişli simgesi](media/end-user-powerpoint/power-bi-settings-icon.png) > **Ayarlar** > **Genel** > **Dil** seçeneğini belirtin.



## <a name="next-steps"></a>Sonraki adımlar
[Görselleri statik resim olarak kopyalama](../visuals/power-bi-visualization-copy-paste.md)    
[Rapor yazdırma](end-user-print.md)
