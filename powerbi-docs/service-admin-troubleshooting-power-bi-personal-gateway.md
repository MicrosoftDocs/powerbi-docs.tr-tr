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
ms.openlocfilehash: bc6eaccc2976266102dcca0d20df73df810fa5f3
ms.sourcegitcommit: bf535771c9ef495f9bb658569403fa5e3dd82e6a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65853559"
---
# <a name="troubleshooting-power-bi-gateway---personal"></a>Power BI Gateway - Personal ile ilgili sorunları giderme
Aşağıdaki bölümlerde, Power BI Gateway-Personal kullanırken gelebilir arasında bazı yaygın olarak karşılaşılabilen sorunlar gidin.

> [!NOTE]
> **Şirket içi veri ağ geçidi (kişisel)** kişisel kullanıma yönelik geçerli ağ geçidi sürümüdür. Söz konusu sürümü kullanmak için yüklemenizi güncelleştirin.
> 
> 

## <a name="update-to-the-latest-version"></a>Son sürüme güncelleştirme
Ağ geçidi sürümü güncel olmadığında birçok sorun ortaya çıkabilir.  En son sürümü kullandığınızdan emin olmak için iyi bir genel uygulama var. Ağ geçidini bir ay veya daha uzun güncelleştirmediyseniz ağ geçidinin en son sürümü yükleyerek göz önünde bulundurun. Ardından, sorunu yeniden bakın.

## <a name="installation"></a>Yükleme
**Kişisel ağ geçidinin 64 bit olan** -makineniz 32 bit ise kişisel ağ geçidini yükleyemezsiniz. İşletim sisteminiz 64-bit sürümünde olması gerekir. Windows 64-bit sürümünü yükleyin veya kişisel ağ geçidinin 64-bit bir makineye yükleyin.

**Kişisel ağ geçidi başarısız bir bilgisayarın yerel Yöneticisi olmanıza rağmen bir hizmet olarak yüklemek** -kullanıcı bilgisayarın yerel yönetici grubundaysa ancak Grup İlkesi olarak oturum açmak kullanıcı adına izin vermez, yükleme başarısız olabilir bir hizmeti. Şu anda Grup İlkesi sağlayan bir hizmet olarak oturum açma emin olun. Bu soruna ilişkin bir düzeltme üzerinde çalışıyoruz. [Daha fazla bilgi](https://technet.microsoft.com/library/cc739424.aspx)

**İşlem zaman aşımına uğradı** -kişisel ağ geçidi yükleme bilgisayarın (fiziksel makine veya VM) tek çekirdekli işlemci varsa bu iletiyi yaygındır. Tüm uygulamaları kapatın ve gerekli olmayan işlemleri devre dışı bırakıp yüklemeyi tekrar gerçekleştirmeyi deneyin.

**Kişisel ağ geçidi ile aynı bilgisayarda veri yönetimi ağ geçidi veya Analysis Services Connector yüklenemez** - zaten sahip olduğunuz bir Analysis Services Connector veya veri yönetimi ağ geçidi yüklü, bağlayıcı kaldırmalısınız veya ağ geçidi. Kişisel ağ geçidini yükledikten sonra deneyin.

> [!NOTE]
> Yükleme sırasında bir sorunla karşılaşırsanız Kurulum günlükleri sorunu gidermenize yardımcı olacak bilgiler sağlar. Daha fazla bilgi için [Kurulum günlükleri](#SetupLogs).
> 
> 

 **Proxy Yapılandırması** ortamınızı bir ara sunucu kullanılması gerekiyorsa kişisel ağ geçidini yapılandırma sorunlarını görebilirsiniz. Ara sunucu yapılandırması hakkında daha fazla bilgi edinmek için bkz. [Power BI Gateway'ler için ara sunucu ayarlarını yapılandırma](service-gateway-proxy.md)

## <a name="schedule-refresh"></a>Yenileme zamanlama
**Hata: Bulutta depolanan kimlik bilgileri eksik.**

Ayarlarda bu hatayı alabilirsiniz \<veri kümesi\> zamanlanmış yenileme varsa ve kaldırılmış ve kişisel ağ geçidinin yeniden. Kişisel ağ geçidi kaldırdığınızda, yenileme için yapılandırılmış bir veri kümesi için veri kaynağı kimlik bilgileri Power BI hizmetinden kaldırılır.

**Çözüm:** Power BI'da bir veri kümesinin yenileme ayarlarına gidin. Bir hata ile herhangi bir veri kaynağı için veri kaynaklarını yönet seçin **kimlik bilgilerini Düzenle** ve yeniden oturum açın veri kaynağına.

**Hata: Veri kümesi için sağlanan kimlik bilgileri geçerli değil. Devam etmek için lütfen sayfayı yenileyerek veya Veri Kaynağı Ayarları iletişim kutusunda kimlik bilgilerini güncelleştirin.**

**Çözüm**: Kimlik bilgileri ile ilgili bir ileti alıyorsanız bu aşağıdaki anlamlara gelebilir:

* Kullanıcı adları ve parolalar veri kaynaklarında oturum açmak, güncel olduğundan emin olun. Power BI'da ilgili veri kümesinin yenileme ayarlarına gidin. Veri kaynaklarını yönet seçin **kimlik bilgilerini Düzenle** veri kaynağı için kimlik bilgilerini güncelleştirmek için.
* Kaynaklardan biri kimlik doğrulaması için OAuth kullanıyorsa, kişisel ağ geçidi'ni yenilemek bulut kaynağı ile tek bir sorguda bir şirket içi kaynak arasındaki karmalar başarısız. Bu sorunu CRM Online ile yerel bir SQL Server arasındaki bir karma örneğidir. CRM Online için OAuth gerektiğinden mashup başarısız olur.
  
  Bu hata bilinen bir sorundur ve onu araştırılmaktadır. Bu soruna geçici bir çözüm bulut kaynağı ile şirket içi kaynak için ayrı bir sorgu gerekir. Ardından, bir birleştirme kullanın veya bunları birleştirmek üzere sorgusu.

**Hata: Desteklenmeyen veri kaynağı.**

**Çözüm:** Yenilemeyi Zamanla ayarlarında desteklenmeyen veri kaynağı iletisi alırsanız bu aşağıdaki anlamlara gelebilir: 

* Veri kaynağı, Power bı'da yenileme için şu anda desteklenmemektedir. 
* Excel çalışma kitabını bir veri modeli, yalnızca çalışma sayfası verilerini içermiyor. Power BI şu anda yalnızca, karşıya yüklenen Excel çalışma kitabının bir veri modeli içermesi halinde yenilemeyi destekler. Verileri Excel'deki Power Query ile içeri aktarıyorsanız veri modeline veri Yükle seçeneğini belirlediğinizden emin olun. Bu seçenek verileri veri modeline aktarılır. 

**Hata: [veriler birleştirilemiyor oluşturulamıyor] &lt;sorgu parçası&gt;/&lt;... &gt; / &lt;... &gt; birlikte kullanılamayan gizlilik düzeylerine sahip veri kaynaklarına erişiyor. Lütfen bu veri birleşimini yeniden oluşturun.**

**Çözüm**: Bu gizlilik düzeyi sınırlamalarıdır ve kullanmakta olduğunuz veri kaynaklarının türleri nedeniyle hatasıdır.

**Hata: Veri kaynağı hatası: "\[Table\]"değerini Table türüne dönüştüremiyoruz.**

**Çözüm**: Bu gizlilik düzeyi sınırlamalarıdır ve kullanmakta olduğunuz veri kaynaklarının türleri nedeniyle hatasıdır.

**Hata: Bu satır için yeterli alan yok.**

Boyutu 4 MB'tan büyük tek bir satır varsa, bu hata oluşur. Veri kaynağınızdaki satırını bulun ve filtrelemeniz veya satır boyutunu azaltmak çalışır.

## <a name="data-sources"></a>Veri kaynakları
**Eksik veri sağlayıcısı** – kişisel ağ geçidi yalnızca 64 bit sürümü olan. Kişisel ağ geçidinin yüklendiği bilgisayarda veri sağlayıcılarının 64 bit sürümünün yüklü olması gerekir. Örneğin, veri kümesindeki veri kaynağı Microsoft Access ise kişisel ağ geçidini yüklediğiniz bilgisayara 64 bit ACE sağlayıcısını yüklemeniz gerekir.  

>[!NOTE]
>Excel 32 bit sürümü varsa, aynı bilgisayara 64 bit sürümü ACE sağlayıcısı yükleyemezsiniz.

**Access veritabanı için Windows kimlik doğrulamasının desteklenmemesi**: Power BI, Access veritabanı için şu anda yalnızca anonim kimlik doğrulamasını destekliyor. Access veritabanı için Windows kimlik doğrulamasını etkinleştirmeye çalışıyoruz.

**Bir veri kaynağı için kimlik bilgileri girerken hata oturum** -veri kaynağı için Windows kimlik bilgileri girerken bunun gibi bir hata alırsanız kişisel ağ geçidinin daha eski bir sürümünü yine de olabilir. [Power BI Gateway - Personal'ın en son sürümünü yükleyin](https://powerbi.microsoft.com/gateway/).

  ![](media/service-admin-troubleshooting-power-bi-personal-gateway/pbi_pg_credentialserror.jpg.png)

**Hata: ACE OLEDB kullanılan bir veri kaynağı için Windows kimlik doğrulaması seçildiğinde karşılaşılan oturum açma hatası**: ACE OLEDB sağlayıcısı kullanılan bir veri kaynağı için veri kaynağı kimlik bilgilerini girdiğinizde bu hatayı alırsanız:

![](media/service-admin-troubleshooting-power-bi-personal-gateway/aceoledberror.png)

Power BI, şu anda ACE OLEDB Sağlayıcısı kullanılan bir veri kaynağı için Windows kimlik doğrulamasını desteklememektedir.

**Çözüm:** Bu hatayı çözmek için seçebileceğiniz **anonim kimlik doğrulaması**. Eski ACE OLEDB Sağlayıcısı için anonim kimlik bilgileri için Windows kimlik bilgileri eşit.

## <a name="tile-refresh"></a>Kutucuk yenileme
Pano kutucuklarını yenileme ile ilgili bir hata sonucu aldığınızı, aşağıdaki makaleye bakın.

[Kutucuk hatalarıyla ilgili sorunları giderme](refresh-troubleshooting-tile-errors.md)

## <a name="tools-for-troubleshooting"></a>Sorun giderme araçları
### <a name="refresh-history"></a>Yenileme Geçmişi
**Yenileme geçmişi** hangi hata oluştu. görmenize yardımcı olur ve bir destek isteği oluşturmak ihtiyacınız varsa yararlı verileri sağlar. Hem zamanlanmış ve isteğe bağlı yenilemeleri görüntüleyebilirsiniz. İşte için nereden **yenileme geçmişi**.

1. Power BI gezinti bölmesindeki **Veri Kümeleri** bölümünde bir veri kümesi seçin ve ardından&gt; Menüyü Aç &gt; **Yenilemeyi Zamanla** seçeneğini belirleyin.
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh.png)
1. İçinde **ayarları...** seçin **yenileme geçmişi**.  
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/scheduled-refresh-2.png)
   
   ![](media/service-admin-troubleshooting-power-bi-personal-gateway/refresh-history.png)

### <a name="event-logs"></a>Olay günlükleri
Çeşitli olay günlükleri, bilgi sağlayabilir. İlk iki **veri yönetimi ağ geçidi** ve **Powerbıgateway**, makinede yönetici olduğunuz halinde sunulur.  Yönetici değilseniz ve Personal Gateway kullanıyorsanız günlük girişlerini içinde görürsünüz **uygulama** günlük.

**Veri Yönetimi Ağ Geçidi** ve **PowerBIGateway** günlükleri **Uygulama ve Hizmet Günlükleri** altındadır.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/event-logs.png)

### <a name="fiddler-trace"></a>Fiddler ile izleme
[Fiddler](http://www.telerik.com/fiddler), Telerik tarafından kullanıma sunulup HTTP trafiğini izleyen ücretsiz bir araçtır. İstemci makinesinden Power BI hizmeti ile iletişimi görebilirsiniz. Bu iletişim, hataları ve diğer ilgili bilgileri gösterebilir.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/fiddler.png)

<a name="SetupLogs"></a>

### <a name="setup-logs"></a>Kurulum Günlükleri
Varsa **kişisel ağ geçidinin**, yüklenemiyorsa Kurulum günlüğünü görüntülemeye yönelik bir bağlantı görürsünüz. Kurulum günlüğüne hatasıyla ilgili ayrıntı gösterebilirsiniz. Bu günlüklerin Windows yükleme günlükleri, MSI günlükleri olarak da bilinir. Oldukça karmaşık olabilen bu günlükleri okumakta zorlanabilirsiniz. Genellikle, altındaki sonuç hatadır, ancak hatanın nedenini belirlemek basit değildir. Bu, farklı bir günlükteki hataların sonucu olabileceği gibi günlükte daha üst kısımlarda belirtilen bir hatadan da kaynaklanıyor olabilir.

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-log.png)

Ya da gidebilirsiniz, **Temp klasörü** (% temp %) ile başlayan dosyaları arayın **güç\_BI\_**.

> [!NOTE]
> %temp% klasörüne gitmek, sizi geçici klasörün bir alt klasöre götürebilir. **Güç\_BI\_**  geçici dizin kökündeki dosyalarıdır.  Bir veya iki düzey üstteki klasöre erişmeniz gerekebilir.
> 
> 

![](media/service-admin-troubleshooting-power-bi-personal-gateway/setup-logs2.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Gateway'ler için ara sunucu ayarlarını yapılandırma](service-gateway-proxy.md)  
[Veri Yenileme](refresh-data.md)  
[Power BI Gateway - Personal](service-gateway-personal-mode.md)  
[Kutucuk hatalarıyla ilgili sorunları giderme](refresh-troubleshooting-tile-errors.md)  
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

