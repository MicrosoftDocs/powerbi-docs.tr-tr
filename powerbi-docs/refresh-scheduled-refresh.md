---
title: Zamanlanmış yenileme yapılandırma
description: Burada, bir ağ geçidi seçme ve zamanlanmış yenileme özelliklerini ayarlama adımları ele alınır.
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: af8895b90b2f3315fb0cfd71351dbe65c108071e
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="configuring-scheduled-refresh"></a>Zamanlanmış yenileme yapılandırma

>[!NOTE]
>İki ay etkin olunmaması durumunda veri kümenizdeki zamanlanmış yenileme duraklatılır. Daha fazla bilgi için bu makalenin sonraki kısımlarında bulunan [*Yenilemeyi zamanla*](#schedule-refresh) bölümüne bakın.
> 
> 

Veri kümeniz Şimdi Yenile ve Yenilemeyi Zamanla seçenekleri kullanılarak, zamanlanmış yenileme işlemi gerçekleştirilmesini destekliyorsa yenilemenin başarılı olması için dikkat edilmesi gereken birkaç gereksinim ve ayar vardır. Bunlar **Ağ geçidi bağlantısı**, **Veri Kaynağı Kimlik Bilgileri** ve **Yenilemeyi Zamanlama**'dır. Şimdi her birine daha yakından bakalım.

Burada hem [Power BI Gateway – Personal](personal-gateway.md) hem de [şirket içi veri ağ geçidi](service-gateway-onprem.md) için mevcut olan seçenekler açıklanmıştır.

Yenileme zamanlama ekranına gitmek için aşağıdakileri yapabilirsiniz.

1. **Veri Kümeleri** bölümünde bulunan bir veri kümesinin yanındaki **üç nokta (...)** simgesini seçin.
2. **Yenilemeyi Zamanla** seçeneğini belirleyin.
   
    ![](media/refresh-scheduled-refresh/dataset-menu.png)

## <a name="gateway-connection"></a>Ağ geçidi bağlantısı
Karşılaşacağınız seçenekler, çevrimiçi ve kullanılabilir durumda olan ağ geçidinizin türüne (kişisel veya şirket içi) göre değişir.

Kullanılabilir bir ağ geçidi yoksa **Ağ geçidi ayarları**'nın devre dışı olduğunu görürsünüz. Kişisel ağ geçidinin nasıl yükleneceğini gösteren bir iletiyle de karşılaşırsınız.

![](media/refresh-scheduled-refresh/gateway-not-configured.png)

Yapılandırılmış bir kişisel ağ geçidiniz varsa çevrimiçi olması halinde bu ağ geçidini seçebilirsiniz. Kullanılamıyorsa ağ geçidi çevrimdışı olarak görünür.

![](media/refresh-scheduled-refresh/gateway-connection.png)

Erişim iznine sahip olmanız durumunda ilgili kurumsal ağ geçidini de seçebilirsiniz. Yalnızca hesabınızın belirli bir ağ geçidi için yapılandırılmış veri kaynağına ilişkin Kullanıcılar sekmesinde bulunması halinde bir kurumsal ağ geçidi seçeneği sunulur.

## <a name="data-source-credentials"></a>Veri kaynağı kimlik bilgileri
### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
Verileri yenilemek için kişisel ağ geçidi kullanıyorsanız arka uç veri kaynağına bağlanmak için kullanılan kimlik bilgilerini sağlamanız gerekir. Çevrimiçi bir hizmetin içerik paketine bağlıysanız bu bağlantı için girdiğiniz kimlik bilgileri, zamanlanmış yenileme için taşınır.

![](media/refresh-scheduled-refresh/data-source-credentials-pgw.png)

Yalnızca söz konusu veri kümesinde yenileme özelliğini ilk kez kullanırken veri kaynaklarında oturum açmanız gerekir. Girdiğiniz kimlik bilgileri veri kümesinde tutulur.

> [!NOTE]
> Belirli kimlik doğrulama yöntemleri ile bir veri kaynağında oturum açarken kullandığınız parolanın değişmesi veya süresinin dolması halinde, söz konusu parolayı veri kaynağına ilişkin Veri Kaynağı Kimlik Bilgileri bölümünde de değiştirmeniz gerekir.
> 
> 

Olası sorunlar genellikle ya ağ geçidinin Windows'da oturum açamayıp hizmeti başlatamaması nedeniyle çevrimdışı olmasından ya da Power BI'ın güncelleştirilmiş verileri sorgulamak üzere veri kaynaklarında oturum açamamasından meydana gelir. Yenileme başarısız olursa veri kümesinin ayarlarını kontrol edin. Ağ geçidi hizmeti çevrimdışıysa Ağ Geçidi Durumu bölümünde bir hatayla karşılaşırsınız. Power BI'ın veri kaynaklarında oturum açamaması halinde ise hatayla karşılaşacağınız bölüm Veri Kaynağı Kimlik Bilgileri'dir.

### <a name="on-premises-data-gateway"></a>Şirket içi veri ağ geçidi
Verileri yenilemek için şirket içi veri ağ geçidini kullanıyorsanız ağ geçidi yöneticisi tarafından veri kaynağı için tanımlanan kimlik bilgilerini sağlamanız gerekmez.

![](media/refresh-scheduled-refresh/data-source-credentials-egw.png)

> [!NOTE]
> Power BI, veri yenileme amacıyla şirket içi SharePoint veri kaynaklarına bağlanmak için yalnızca *Anonim*, *Temel* ve *Windows (NTLM/Kerberos)* kimlik doğrulama yöntemlerinin kullanılmasını destekler. Power BI, şirket içi SharePoint veri kaynaklarındaki verilerin yenilenmesi için *ADFS* veya *Form Tabanlı Kimlik Doğrulama* yöntemlerini desteklemez.
> 
> 

## <a name="schedule-refresh"></a>Yenilemeyi zamanlama
Zamanlanmış yenileme bölümünde veri kümesini yenileme sıklığını ve zaman aralıklarını tanımlayabilirsiniz. Bazı veri kaynaklarının yapılandırılabilmesi için bir ağ geçidinin mevcut olması gerekmez. Geri kalanlar içinse bu işleme yönelik olarak bir ağ geçidi gerekir.

Ayarları yapılandırmak için **Verilerinizi güncel tutun** kaydırıcısını **Evet** olarak ayarlayın.

> [!NOTE]
> Power BI hizmeti, verilerinizin yenilenmesini, zamanlanmış yenileme saatinizin ilk **15 dakikası** içinde başlatılacak şekilde ayarlar.
> 
> 

![](media/refresh-scheduled-refresh/scheduled-refresh.png)

> [!NOTE]
> İki ay etkin olunmaması durumunda veri kümenizdeki zamanlanmış yenileme duraklatılır. Veri kümesinde bir kullanıcı tarafından ziyaret edilen herhangi bir pano veya rapor bulunmuyorsa veri kümesinin etkin olmadığı varsayılır. Böyle bir durumda, veri kümesi sahibine zamanlanmış yenilemenin duraklatıldığını bildiren bir e-posta gönderilir ve veri kümesine ilişkin yenileme zamanlaması **devre dışı** olarak görüntülenir. Zamanlanmış yenilemeyi sürdürmek için, veri kümesi üzerinde oluşturulmuş herhangi bir panoyu veya raporu yeniden ziyaret etmeniz yeterlidir.
> 
> 

## <a name="whats-supported"></a>Hangi veri kaynakları desteklenir?
Zamanlanmış yenileme için farklı ağ geçitlerinde desteklenen çeşitli veri kümeleri vardır. Kullanabileceğiniz veri kümelerine ilişkin fikir edinmek için aşağıya göz atabilirsiniz.

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
**Power BI Desktop**

* Power BI Desktop'taki Veri Al ve Sorgu Düzenleyicisi bölümlerinde gösterilen tüm çevrimiçi veri kaynakları.
* Hadoop dosyası (HDFS) ve Microsoft Exchange dışında, Power BI Desktop'taki Veri Al ve Sorgu Düzenleyicisi bölümlerinde gösterilen tüm şirket içi veri kaynakları.

**Excel**

> [!NOTE]
> Excel 2016 ve sonraki sürümlerinde, Power Query artık şeridin Veri bölümünde, Al ve Dönüştür altında bulunur.
> 
> 

* Power Query'de gösterilen tüm çevrimiçi veri kaynakları.
* Hadoop dosyası (HDFS) ve Microsoft Exchange dışında, Power Query'de gösterilen tüm şirket içi veri kaynakları.
* Power Pivot'ta gösterilen tüm çevrimiçi veri kaynakları.\*
* Hadoop dosyası (HDFS) ve Microsoft Exchange dışında, Power Pivot'ta gösterilen tüm şirket içi veri kaynakları.

<!-- Refresh Data sources-->
[!INCLUDE [refresh-datasources](./includes/refresh-datasources.md)]

## <a name="troubleshooting"></a>Sorun giderme
Bazen verileri yenileme işlemi beklendiği gibi gitmeyebilir. Bu, genellikle ağ geçidiyle bağlantılı bir sorundan kaynaklanır. Araçlar ve bilinen sorunlara yönelik sorun giderme makalelerine göz atın.

[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)

[Power BI Gateway - Personal ile ilgili sorunları giderme](service-admin-troubleshooting-power-bi-personal-gateway.md)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'da veri yenileme](refresh-data.md)  
[Power BI Gateway - Personal](personal-gateway.md)  
[Şirket içi veri ağ geçidi](service-gateway-onprem.md)  
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
[Power BI Gateway - Personal ile ilgili sorunları giderme](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

