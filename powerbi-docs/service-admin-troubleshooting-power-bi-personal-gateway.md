---
title: Power BI Gateway - Personal ile ilgili sorunları giderme
description: Power BI Gateway - Personal ile ilgili sorunları giderme
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 5/06/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 7827ce359022eccfb75798b08da164b7504c84df
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271823"
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Power BI Gateway - Personal ile ilgili sorunları giderme

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Aşağıdaki bölümlerde, Power BI Gateway - Personal'ı kullanırken yaygın olarak karşılaşılabilen sorunlar ele alınmıştır.

## <a name="update-to-the-latest-version"></a>Son sürüme güncelleştirme

**Şirket içi veri ağ geçidi (kişisel)** kişisel kullanıma yönelik geçerli ağ geçidi sürümüdür. Söz konusu sürümü kullanmak için yüklemenizi güncelleştirin.

Ağ geçidi sürümü güncel olmadığında birçok sorun ortaya çıkabilir.  En son sürümü kullandığınızdan emin olmak her zaman için iyi bir yöntemdir. Ağ geçidini bir ay veya daha uzun süredir güncelleştirmediyseniz ağ geçidinin en son sürümünü yüklemeyi göz önünde bulundurabilirsiniz. Ardından sorunu yeniden oluşturup oluşturamayacağınıza bakın.

## <a name="installation"></a>Yükleme
**Kişisel ağ geçidi 64 bit** - Makineniz 32 bitse kişisel ağ geçidini yükleyemezsiniz. İşletim sisteminizin sürümü 64 bit olmalıdır. Bir Windows 64 bit sürümü yükleyin veya kişisel ağ geçidini 64 bit olan bir makineye yükleyin.

**Bilgisayarın yerel yöneticisi olmanıza rağmen kişisel ağ geçidinin yüklenememesi**: Kullanıcı, bilgisayarın yerel Yönetici grubundaysa ancak grup ilkesi söz konusu kullanıcı adının bir hizmet olarak oturum açmasına izin vermiyorsa yükleme başarısız olabilir. Şimdilik yapmanız gereken, grup ilkesinin bir kullanıcının hizmet olarak oturum açmasına izin verdiğinden emin olmaktır. Bu soruna ilişkin bir düzeltme üzerinde çalışıyoruz. [Daha fazla bilgi](https://technet.microsoft.com/library/cc739424.aspx)

**İşlem zaman aşımına uğradı**: Bu ileti, kişisel ağ geçidinin yüklendiği bilgisayarın (fiziksel makine veya VM) tek çekirdekli bir işlemciye sahip olduğu durumlarda sık karşılaşılan bir sorundur. Tüm uygulamaları kapatın ve gerekli olmayan işlemleri devre dışı bırakıp yüklemeyi tekrar gerçekleştirmeyi deneyin.

**Veri Yönetimi Ağ Geçidi'nin veya Analysis Services Connector'ın kişisel ağ geçidi ile aynı bilgisayara yüklenememesi**: Analysis Services Connector veya Veri Yönetimi Ağ Geçidi zaten yüklüyse önce Connector'ı veya ağ geçidini kaldırmanız gerekir. Ardından kişisel ağ geçidini yüklemeyi deneyin.

> [!NOTE]
> Yükleme sırasında bir sorunla karşılaşırsanız kurulum günlükleri, sorunu gidermenize yardımcı olacak bilgiler sağlayabilir. Daha fazla bilgi için bkz. [Kurulum Günlükleri](#SetupLogs).
> 
> 

 **Ara sunucu yapılandırması**: Ortamınız için bir ara sunucu kullanılması gerekiyorsa kişisel ağ geçidini yapılandırma ile ilgili sorunlar görebilirsiniz. Ara sunucuyu yapılandırma hakkında daha fazla bilgi edinmek için bkz. [Şirket içi veri ağ geçidi için ara sunucu ayarlarını yapılandırma](/data-integration/gateway/service-gateway-proxy).

## <a name="schedule-refresh"></a>Yenileme zamanlama
**Hata: Bulutta depolanan kimlik bilgileri eksik.**

Bir yenileme zamanladıktan sonra kişisel ağ geçidini kaldırıp yeniden yüklediyseniz \<veri kümesi\> için Ayarlar bölümünde bu hatayla karşılaşabilirsiniz. Bir kişisel ağ geçidini kaldırdığınızda, yenileme için yapılandırılmış bir veri kümesine ilişkin veri kaynağı kimlik bilgileri de Power BI hizmetinden kaldırılır.

**Çözüm:** Power BI'da bir veri kümesinin yenileme ayarlarına gidin. Veri Kaynaklarını Yönet bölümünde, hata veren herhangi bir veri kaynağı için **Kimlik bilgilerini düzenle**'yi seçin ve veri kaynağında tekrar oturum açın.

**Hata: Veri kümesi için sağlanan kimlik bilgileri geçerli değil. Devam etmek için lütfen sayfayı yenileyerek veya Veri Kaynağı Ayarları iletişim kutusunda kimlik bilgilerini güncelleştirin.**

**Çözüm**: Kimlik bilgileri ile ilgili bir ileti alıyorsanız bu aşağıdaki anlamlara gelebilir:

* Veri kaynaklarında oturum açmak için kullanılan kullanıcı adları ve parolaların güncel olduğundan emin olun. Power BI'da ilgili veri kümesinin yenileme ayarlarına gidin. Veri kaynağı kimlik bilgilerini güncelleştirmek için Veri Kaynaklarını Yönet bölümündeki **Kimlik bilgilerini düzenle**'yi seçin.
* Kaynaklardan birinde kimlik doğrulaması için OAuth kullanılıyorsa tek bir sorguda yer alan, bulut kaynağı ile şirket içi kaynak arasındaki karmalar, kişisel ağ geçidinde yenilenemez. CRM Online ile yerel SQL Server arasındaki bir karma bu soruna örnek olarak verilebilir. CRM Online için OAuth gerektiğinden karma başarısız olur.
  
  Bu hata bilinen bir sorundur ve araştırılmaktadır. Soruna yönelik geçici çözüm olarak bulut kaynağı ile şirket içi kaynak için ayrı bir sorgu bulundurun. Bunları birleştirmek için birleştirme veya ekleme sorgusu kullanın.

**Hata: Desteklenmeyen veri kaynağı.**

**Çözüm:** Yenilemeyi Zamanla ayarlarında desteklenmeyen veri kaynağı iletisi alırsanız bu aşağıdaki anlamlara gelebilir: 

* Power BI'da veri kaynağı yenileme işlemi o anda desteklenmiyordur. 
* Excel çalışma kitabı veri modelini değil yalnızca çalışma sayfası verilerini içeriyordur. Power BI şu anda yalnızca, karşıya yüklenen Excel çalışma kitabının bir veri modeli içermesi halinde yenilemeyi destekler. Verileri Excel'deki Power Query ile içeri aktarıyorsanız veri modeline veri Yükle seçeneğini belirlediğinizden emin olun. Bu seçenek verilerin bir veri modeline aktarılmasını güvence altına alır. 

**Hata: [Veriler birleştirilemiyor] &lt;sorgu parçası&gt;/&lt;…&gt;/&lt;…&gt;, birlikte kullanılamayan gizlilik düzeylerine sahip veri kaynaklarına erişiyor. Lütfen bu veri birleşimini yeniden oluşturun.**

**Çözüm**: Bu hatanın nedeni kullandığınız veri kaynaklarının türleri ve gizlilik düzeyi sınırlamalarıdır.

**Hata: Veri kaynağı hatası: "\[Table\]"değerini Table türüne dönüştüremiyoruz.**

**Çözüm**: Bu hatanın nedeni kullandığınız veri kaynaklarının türleri ve gizlilik düzeyi sınırlamalarıdır.

**Hata: Bu satır için yeterli alan yok.**

Satırlarınızdan birinin boyutu 4 MB'tan fazlaysa bu hatayla karşılaşırsınız. Veri kaynağınızda söz konusu satırı bulup filtrelemeyi veya satırın boyutunu azaltmayı deneyin.

## <a name="data-sources"></a>Veri kaynakları
**Eksik veri sağlayıcısı**: Kişisel ağ geçidi yalnızca 64 bit sürümlerde kullanılabilir. Kişisel ağ geçidinin yüklendiği bilgisayarda veri sağlayıcılarının 64 bit sürümünün yüklü olması gerekir. Örneğin, veri kümesindeki veri kaynağı Microsoft Access ise kişisel ağ geçidini yüklediğiniz bilgisayara 64 bit ACE sağlayıcısını yüklemeniz gerekir.  

>[!NOTE]
>Excel'in 32 bit sürümüne sahipseniz aynı bilgisayara sürümü 64 bit olan bir ACE sağlayıcısı yükleyemezsiniz.

**Access veritabanı için Windows kimlik doğrulamasının desteklenmemesi**: Power BI, Access veritabanı için şu anda yalnızca anonim kimlik doğrulamasını destekliyor. Access veritabanı için Windows kimlik doğrulamasını etkinleştirmeye çalışıyoruz.

**Bir veri kaynağı için kimlik bilgileri girildiğinde karşılaşılan oturum açma hatası**: Bir veri kaynağı için Windows kimlik bilgilerini girdiğinizde buna benzer bir hata alırsanız kişisel ağ geçidinin daha eski bir sürümünü kullanıyor olabilirsiniz. [Power BI Gateway - Personal'ın en son sürümünü yükleyin](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**Hata: ACE OLEDB kullanılan bir veri kaynağı için Windows kimlik doğrulaması seçildiğinde karşılaşılan oturum açma hatası**: ACE OLEDB sağlayıcısı kullanılan bir veri kaynağı için veri kaynağı kimlik bilgilerini girdiğinizde bu hatayı alırsanız:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Power BI şu anda ACE OLEDB sağlayıcısını kullanan veri kaynakları için Windows kimlik doğrulamasını desteklememektedir.

**Çözüm:** Geçici çözüm olarak, **Anonim kimlik doğrulaması** seçebilirsiniz. Eski ACE OLEDB sağlayıcısı için Anonim kimlik bilgileri, Windows kimlik bilgilerine eşittir.

## <a name="tile-refresh"></a>Kutucuk yenileme
Pano kutucuklarını yenileme ile ilgili bir hata alırsanız aşağıdaki makaleye bakın.

[Kutucuk hatalarıyla ilgili sorunları giderme](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>Sorun giderme araçları
### <a name="refresh-history"></a>Yenileme Geçmişi
**Yenileme Geçmişi**, oluşan hataları görmenize yardımcı olur ve destek isteği oluşturmanız gerektiğinde size faydalı veriler sağlar. Hem zamanlanmış yenilemeleri hem de isteğe bağlı yenilemeleri görüntüleyebilirsiniz. **Yenileme Geçmişi**'ne aşağıda gösterildiği gibi ulaşırsınız.

1. Power BI gezinti bölmesindeki **Veri Kümeleri** bölümünde bir veri kümesi seçin ve ardından&gt; Menüyü Aç &gt; **Yenilemeyi Zamanla** seçeneğini belirleyin.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
1. **Ayarlar:** için **Yenileme Geçmişi**'ni seçin.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>Olay günlükleri
Çeşitli olay günlükleri bilgi sağlayabilir. İlk ikisi, **Veri Yönetimi Ağ Geçidi** ile **PowerBIGateway**'dir ve bunlar, makinede yönetici olmanız durumunda sunulur.  Yönetici değilseniz ve Personal Gateway kullanıyorsanız günlük girdilerini **Uygulama** günlüğü içinde görürsünüz.

**Veri Yönetimi Ağ Geçidi** ve **PowerBIGateway** günlükleri **Uygulama ve Hizmet Günlükleri** altındadır.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler ile izleme
[Fiddler](http://www.telerik.com/fiddler), Telerik tarafından kullanıma sunulup HTTP trafiğini izleyen ücretsiz bir araçtır. İstemci makinesinden Power BI hizmetiyle iletişimi görebilirsiniz. Bu iletişim hataları ve diğer ilgili bilgileri gösterebilir.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>Kurulum Günlükleri
**Personal Gateway** yüklenemiyorsa kurulum günlüğünü görüntülemeye yönelik bir bağlantı görürsünüz. Kurulum günlüğü hatayla ilgili ayrıntıları gösterebilir. Bu günlükler aynı zamanda MSI günlükleri olarak da bilinen Windows Yüklemesi günlükleridir. Oldukça karmaşık olabilen bu günlükleri okumakta zorlanabilirsiniz. Oluşan hata genellikle altta verilir ancak hatanın nedenini belirlemek basit değildir. Bu, farklı bir günlükteki hataların sonucu olabileceği gibi günlükte daha üst kısımlarda belirtilen bir hatadan da kaynaklanıyor olabilir.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

**Geçici klasörünüze** (%temp%) gidebilir ve **Power\_BI\_** ile başlayan dosyaları arayabilirsiniz.

> [!NOTE]
> %temp% klasörüne gitmek, sizi geçici klasörün bir alt klasöre götürebilir. **Power\_BI\_** dosyaları, geçici klasör dizininin kökündedir.  Bir veya iki düzey üstteki klasöre erişmeniz gerekebilir.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidi için proxy ayarlarını yapılandırma](/data-integration/gateway/service-gateway-proxy)  
[Veri Yenileme](refresh-data.md)  
[Power BI Gateway - Personal](service-gateway-personal-mode.md)  
[Kutucuk hatalarıyla ilgili sorunları giderme](refresh-troubleshooting-tile-errors.md)  
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

