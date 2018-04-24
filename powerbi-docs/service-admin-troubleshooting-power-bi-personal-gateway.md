---
title: Power BI Gateway - Personal ile ilgili sorunları giderme
description: Power BI Gateway - Personal ile ilgili sorunları giderme
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: d321d70fe201af500feb35ef4e5ea1df6cc558f0
ms.sourcegitcommit: 312390f18b99de1123bf7a7674c6dffa8088529f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Power BI Gateway - Personal ile ilgili sorunları giderme
Aşağıda, Power BI Gateway - Personal'ı kullanırken yaygın olarak karşılaşılabilen sorunlar ele alınmıştır.

> [!NOTE]
> **Şirket içi veri ağ geçidi (kişisel)** kişisel kullanıma yönelik geçerli ağ geçidi sürümüdür. Söz konusu sürümü kullanmak için yüklemenizi güncelleştirin.
> 
> 

## <a name="update-to-the-latest-version"></a>Son sürüme güncelleştirme
Ağ geçidi sürümü güncel olmadığında birçok sorun ortaya çıkabilir.  En son sürümü kullandığınızdan emin olmak, her zaman için iyi bir uygulamadır.  Ağ geçidini bir ay veya daha uzun süredir güncelleştirmediyseniz ağ geçidinin en son sürümünü yükleyerek, sorunu yeniden oluşturup oluşturamadığınızı görmenizde yarar vardır.

## <a name="installation"></a>Yükleme
**Kişisel ağ geçidinin 64 bit olması**: Makineniz 32 bit ise kişisel ağ geçidini yükleyemezsiniz. İşletim sisteminiz 64 bit olmalıdır. Bir Windows 64 bit sürümü yüklemeniz veya kişisel ağ geçidini 64 bit olan bir makineye yüklemeniz gerekir.

**Bilgisayarın yerel yöneticisi olmanıza rağmen kişisel ağ geçidinin yüklenememesi**: Kullanıcı, bilgisayarın yerel Yönetici grubundaysa ancak grup ilkesi söz konusu kullanıcı adının bir hizmet olarak oturum açmasına izin vermiyorsa yükleme başarısız olabilir.  Şimdilik yapmanız gereken, grup ilkesinin bir kullanıcının hizmet olarak oturum açmasına izin verdiğinden emin olmaktır. Bu soruna ilişkin bir düzeltme üzerinde çalışıyoruz. [Daha fazla bilgi](https://technet.microsoft.com/library/cc739424.aspx)

**İşlemin zaman aşımına uğraması**: Bu, kişisel ağ geçidinin yüklendiği bilgisayarın (fiziksel makine veya VM) tek çekirdekli bir işlemciye sahip olduğu durumlarda sık karşılaşılan bir sorundur. Tüm uygulamaları kapatın ve gerekli olmayan işlemleri devre dışı bırakıp yüklemeyi tekrar gerçekleştirmeyi deneyin.

**Veri Yönetimi Ağ Geçidi'nin veya Analysis Services Connector'ın kişisel ağ geçidi ile aynı bilgisayara yüklenememesi**: Analysis Services Connector veya Veri Yönetimi Ağ Geçidi zaten yüklüyse önce Connector'ı veya ağ geçidini kaldırmanız, ardından kişisel ağ geçidini yüklemeyi denemeniz gerekir.

> [!NOTE]
> Yükleme sırasında bir sorunla karşılaşırsanız kurulum günlükleri, sorunu gidermenize yardımcı olacak bilgiler sağlayabilir. Daha fazla bilgi için [Kurulum Günlükleri](#SetupLogs) bölümüne bakın.
> 
> 

 **Ara sunucu yapılandırması**: Ortamınız için bir ara sunucu kullanılması gerekiyorsa kişisel ağ geçidini yapılandırma ile ilgili sorunlarla karşılaşabilirsiniz. Ara sunucu yapılandırması hakkında daha fazla bilgi edinmek için bkz. [Power BI Gateway'ler için ara sunucu ayarlarını yapılandırma](service-gateway-proxy.md)

## <a name="schedule-refresh"></a>Yenileme zamanlama
**Hata: The credential stored in the cloud is missing.** (Bulutta depolanan kimlik bilgileri eksik.)

Bir yenileme zamanladıktan sonra kişisel ağ geçidini kaldırıp yeniden yüklediyseniz \<veri kümesi\> için Ayarlar bölümünde bu hatayla karşılaşabilirsiniz. Bir kişisel ağ geçidini kaldırdığınızda, yenileme için yapılandırılmış bir veri kümesine ilişkin veri kaynağı kimlik bilgileri de Power BI hizmetinden kaldırılır.

**Çözüm:** Power BI'da bir veri kümesinin yenileme ayarlarına gidin. Veri Kaynaklarını Yönet bölümünde, hata veren herhangi bir veri kaynağı için Kimlik bilgilerini düzenle'ye tıklayın ve veri kaynağında tekrar oturum açın.

**Hata: Veri kümesi için sağlanan kimlik bilgileri geçerli değil. Devam etmek için lütfen sayfayı yenileyerek veya Veri Kaynağı Ayarları iletişim kutusunda kimlik bilgilerini güncelleştirin.**

**Çözüm**: Kimlik bilgileri ile ilgili bir ileti alıyorsanız bu, aşağıdaki anlamlara gelebilir:

* Veri kaynaklarında oturum açmak için kullanılan kullanıcı adları ve parolaların güncel olduğundan emin olun. Power BI'da ilgili veri kümesinin yenileme ayarlarına gidin. Veri kaynağı kimlik bilgilerini güncelleştirmek için Veri Kaynaklarını Yönet bölümündeki Kimlik bilgilerini düzenle seçeneğine tıklayın.
* Kaynaklardan birinde kimlik doğrulaması için OAuth kullanılıyorsa tek bir sorguda yer alan, bulut kaynağı ile şirket içi kaynak arasındaki karmalar, kişisel ağ geçidinde yenilenemez. CRM Online ile yerel SQL Server arasındaki bir karma bu duruma örnek olarak verilebilir. CRM Online için OAuth gerektiğinden yenileme başarısız olur.
  
  Bu bilinen bir sorundur ve araştırılmaktadır. Soruna yönelik geçici çözüm olarak bulut kaynağı ile şirket içi kaynak için ayrı bir sorgu bulundurun ve bunları birleştirmek üzere birleştirme veya ekleme sorgusu kullanın.

**Hata: Unsupported data source.** (Desteklenmeyen veri kaynağı.)

**Çözüm:** Yenilemeyi Zamanla ayarlarında bir desteklenmeyen veri kaynağı iletisi alırsanız bu, aşağıdaki anlamlara gelebilir: 

* Power BI'da veri kaynağı yenileme işlemi o anda desteklenmiyordur. 
* Excel çalışma kitabı bir veri modelini değil, yalnızca çalışma sayfası verilerini içeriyordur. Power BI şu anda yalnızca, karşıya yüklenen Excel çalışma kitabının bir veri modeli içermesi halinde yenilemeyi destekler. Verileri Excel'deki Power Query ile içeri aktarıyorsanız veri modeline veri Yükle seçeneğini belirlediğinizden emin olun. Böylece veriler bir veri modeline aktarılır. 

**Hata: [Veriler birleştirilemiyor] &lt;sorgu parçası&gt;/&lt;…&gt;/&lt;…&gt;, birlikte kullanılamayan gizlilik düzeylerine sahip veri kaynaklarına erişiyor. Lütfen bu veri birleşimini yeniden oluşturun.**

**Çözüm**: Bu hatanın nedeni, kullandığınız veri kaynaklarının türleri ve gizlilik düzeyi sınırlamalarıdır. [Daha fazla bilgi](refresh-enable-fast-combine.md)

**Hata: Veri kaynağı hatası: "\[Table\]"değerini Table türüne dönüştüremiyoruz.**

**Çözüm**: Bu hatanın nedeni, kullandığınız veri kaynaklarının türleri ve gizlilik düzeyi sınırlamalarıdır. [Daha fazla bilgi](refresh-enable-fast-combine.md)

**Hata: There is not enough space for this row.** (Bu satır için yeterli alan yok.)

Boyut olarak 4 MB'tan büyük tek bir satırınız varsa bu hatayı alırsınız. Veri kaynağınızdan hangi satır olduğunu belirlemeniz ve bu satırı filtrelemeyi ya da satırın boyutunu azaltmayı denemeniz gerekir.

## <a name="data-sources"></a>Veri kaynakları
**Eksik veri sağlayıcısı**: Kişisel ağ geçidi yalnızca 64 bit sürümlerde kullanılabilir. Kişisel ağ geçidinin yüklendiği bilgisayarda veri sağlayıcılarının 64 bit sürümünün yüklü olması gerekir. Örneğin, veri kümesindeki veri kaynağı Microsoft Access ise kişisel ağ geçidini yüklediğiniz bilgisayara 64 bit ACE sağlayıcısını yüklemeniz gerekir.  

>[!NOTE]
>Excel 32 bit sürümüne sahipseniz aynı bilgisayara 64 bit bir ACE sağlayıcısı yükleyemezsiniz.

**Access veritabanı için Windows kimlik doğrulamasının desteklenmemesi**: Power BI, Access veritabanı için şu anda yalnızca anonim kimlik doğrulamasını destekliyor. Access veritabanı için Windows kimlik doğrulamasını etkinleştirmeye çalışıyoruz.

**Bir veri kaynağı için kimlik bilgileri girildiğinde karşılaşılan oturum açma hatası**: Bir veri kaynağı için Windows kimlik bilgilerini girdiğinizde buna benzer bir hata alırsanız kişisel ağ geçidinin daha eski bir sürümünü kullanıyor olabilirsiniz. [Power BI Gateway - Personal'ın en son sürümünü yükleyin](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**ACE OLEDB kullanılan bir veri kaynağı için Windows kimlik doğrulaması seçildiğinde meydana gelen oturum açma hatası**: ACE OLEDB sağlayıcısı kullanılan bir veri kaynağı için veri kaynağı kimlik bilgilerini girdiğinizde bu hatayı alırsanız:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Power BI şu anda ACE OLEDB sağlayıcısı kullanılan veri kaynakları için Windows kimlik doğrulamasını desteklememektedir.

**Çözüm:** Geçici çözüm olarak, Anonim kimlik doğrulamasını seçebilirsiniz. Eski ACE OLEDB sağlayıcısı için Anonim kimlik bilgileri, Windows kimlik bilgileri ile eşdeğerdir.

## <a name="tile-refresh"></a>Kutucuk yenileme
Pano kutucuklarını yenileme ile ilgili bir hata alırsanız lütfen aşağıdaki makaleye başvurun.

[Kutucuk hatalarıyla ilgili sorunları giderme](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>Sorun giderme araçları
### <a name="refresh-history"></a>Geçmişi Yenile
**Geçmişi yenile**, meydana gelen hataları görmenizi sağlamanın yanı sıra bir destek isteği oluşturmanız gerektiğinde de size faydalı veriler sunabilir. Hem zamanlanmış yenilemeleri hem de isteğe bağlı yenilemeleri görüntüleyebilirsiniz. **Yenileme Geçmişi**'ne ulaşmak için aşağıdaki adımları uygulayın.

1. Power BI gezinti bölmesindeki **Veri Kümeleri** bölümünde bir veri kümesi seçin ve ardından&gt; Menüyü Aç &gt; **Yenilemeyi Zamanla** seçeneğini belirleyin.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
2. **Ayarlar: ...** &gt; **Yenilemeyi Zamanla** bölümündeki **Geçmişi yenile** seçeneğini belirleyin.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>Olay günlükleri
Bilgi sağlayabilecek çeşitli olay günlükleri vardır. İlk ikisi, **Veri Yönetimi Ağ Geçidi** ile **PowerBIGateway**'dir ve bunlar, makinede yönetici rolünde olmanız halinde sunulur.  Yönetici değilseniz ve Personal Gateway kullanıyorsanız günlük girişlerini **Uygulama** günlüğü içinde görürsünüz.

**Veri Yönetimi Ağ Geçidi** ve **PowerBIGateway** günlükleri **Uygulama ve Hizmet Günlükleri** altındadır.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler ile izleme
[Fiddler](http://www.telerik.com/fiddler), Telerik tarafından kullanıma sunulup HTTP trafiğini izlemeyi sağlayan ücretsiz bir araçtır.  İstemci makinesinden Power BI hizmetindeki gelen ve giden trafiği görebilirsiniz. Bu sayede hataları ve diğer ilgili bilgileri görüntüleyebilirsiniz.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>Kurulum Günlükleri
**Personal Gateway** yüklenemiyorsa kurulum günlüğünü görüntülemeye yönelik bir bağlantı görürsünüz. Hata ile ilgili ayrıntılar bu bağlantıda gösterilebilir. Bunlar, aynı zamanda MSI günlükleri olarak da bilinen Windows Yüklemesi günlükleridir. Oldukça karmaşık olabilen bu günlükleri okumakta zorlanabilirsiniz. Oluşan hata genellikle altta verilir ancak hatanın nedenini belirlemek basit değildir. Bu, farklı bir günlükteki hataların sonucu olabileceği gibi günlükte daha üst kısımlarda belirtilen bir hatadan da kaynaklanıyor olabilir.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

Alternatif olarak, **Geçici klasör** (%temp%) yolunuza gidip **Power\_BI\_** ile başlayan dosyaları arayabilirsiniz.

> [!NOTE]
> %temp% klasörüne gitmek, sizi geçici klasörün bir alt klasöre götürebilir.  **Power\_BI\_** dosyaları, geçici klasör dizininin kökündedir.  Bir veya iki düzey üstteki klasöre erişmeniz gerekebilir.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Gateway'ler için ara sunucu ayarlarını yapılandırma](service-gateway-proxy.md)  
[Veri Yenileme](refresh-data.md)  
[Power BI Gateway - Personal](personal-gateway.md)  
[Kutucuk hatalarıyla ilgili sorunları giderme](refresh-troubleshooting-tile-errors.md)  
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

