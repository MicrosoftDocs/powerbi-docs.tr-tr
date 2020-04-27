---
title: Zamanlanmış yenileme yapılandırma
description: Burada, bir ağ geçidi seçme ve zamanlanmış yenileme özelliklerini ayarlama adımları ele alınır.
author: davidiseminger
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/06/2019
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: cc0527d093118fdb585800d0038f824223098119
ms.sourcegitcommit: 1f768dfef27cd8887318671f91427f72d02370c6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81675688"
---
# <a name="configure-scheduled-refresh"></a>Zamanlanmış yenileme yapılandırma

>[!NOTE]
>İki ay etkin olunmaması durumunda veri kümenizdeki zamanlanmış yenileme duraklatılır. Daha fazla bilgi için bu makalenin devamındaki [*Zamanlanmış yenileme*](#scheduled-refresh) bölümüne bakın.

Bu makalede [Şirket içi veri ağ geçidi (kişisel mod)](service-gateway-personal-mode.md) hem de [Şirket içi veri ağ geçidi](service-gateway-onprem.md) için zamanlanmış yenilemeye yönelik olarak sağlanan seçenekler açıklanır. Yenileme seçeneklerini Power BI hizmetinin şu alanlarında belirtirsiniz: **Ağ geçidi bağlantısı**, **Veri kaynağı kimlik bilgileri** ve **Zamanlanmış yenileme**. Her birini sırayla gözden geçireceğiz. Yenileme zamanlamalarıyla ilgili sınırlamalar da dahil olmak üzere veri yenileme hakkında daha fazla bilgi için bkz. [Veri yenileme](refresh-data.md#data-refresh).

**Zamanlanmış yenileme** ekranına gitmek için:

1. Gezinti bölmesindeki **Veri Kümeleri**'nin altında, listelenen bir veri kümesinin yanındaki **Diğer seçenekler** (...) simgesini seçin.
2. **Yenilemeyi Zamanla** seçeneğini belirleyin.

    ![Yenileme Zamanlama](media/refresh-scheduled-refresh/dataset-menu.png)

## <a name="gateway-connection"></a>Ağ geçidi bağlantısı

Burada gördüğünüz seçenekler, çevrimiçi ve kullanılabilir durumda olan ağ geçidinizin kişisel veya kurumsal olmasına göre değişir.

Kullanılabilir bir ağ geçidi yoksa **Ağ geçidi bağlantısı**'nın devre dışı olduğunu görürsünüz. Kişisel ağ geçidinin nasıl yükleneceğini gösteren bir ileti de görürsünüz.

![Ağ geçidi yapılandırılmamış](media/refresh-scheduled-refresh/gateway-not-configured.png)

Yapılandırılmış bir kişisel ağ geçidiniz varsa, çevrimiçi olması halinde bu ağ geçidini seçebilirsiniz. Kullanılabilir değilse çevrimdışı olduğunu gösterir.

![Ağ geçidi bağlantısı](media/refresh-scheduled-refresh/gateway-connection.png)

Erişim iznine sahip olmanız durumunda ilgili kurumsal ağ geçidini de seçebilirsiniz. Yalnızca hesabınızın belirli bir ağ geçidi için yapılandırılmış veri kaynağının **Kullanıcılar** sekmesinde listelenmesi halinde bir kurumsal ağ geçidinin kullanılabilir olduğunu görürsünüz.

## <a name="data-source-credentials"></a>Veri kaynağı kimlik bilgileri

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal

Verileri yenilemek için kişisel ağ geçidi kullanıyorsanız arka uç veri kaynağına bağlanmak için kimlik bilgilerini sağlamanız gerekir. Çevrimiçi bir hizmetin içerik paketine bağlıysanız bu bağlantı için girdiğiniz kimlik bilgileri, zamanlanmış yenileme için taşınır.

![Veri kaynağı kimlik bilgileri](media/refresh-scheduled-refresh/data-source-credentials-pgw.png)

Yalnızca söz konusu veri kümesinde yenileme özelliğini ilk kez kullanırken veri kaynağında oturum açmanız gerekir. Girdiğiniz kimlik bilgileri veri kümesinde tutulur.

> [!NOTE]
> Bazı kimlik doğrulaması yöntemleri için, bir veri kaynağında oturum açarken kullandığınız parolanın süresinin dolması veya değişmesi halinde, söz konusu parolayı **Veri kaynağı kimlik bilgileri** bölümündeki veri kaynağı için de değiştirmeniz gerekir.

Olası sorunlar genellikle ya ağ geçidinin Windows'da oturum açamayıp hizmeti başlatamaması nedeniyle çevrimdışı olmasından ya da Power BI'ın güncelleştirilmiş verileri sorgulamak üzere veri kaynaklarında oturum açamamasından meydana gelir. Yenileme başarısız olursa, veri kümesinin ayarlarını kontrol edin. Ağ geçidi hizmeti çevrimdışıysa, **Durum** bölümünde bir hatayla karşılaşırsınız. Power BI'ın veri kaynaklarında oturum açamaması halinde ise hatayla karşılaşacağınız bölüm Veri Kaynağı Kimlik Bilgileri'dir.

### <a name="on-premises-data-gateway"></a>Şirket içi veri ağ geçidi

Verileri yenilemek için şirket içi veri ağ geçidini kullanıyorsanız ağ geçidi yöneticisi tarafından veri kaynağı için tanımlanan kimlik bilgilerini sağlamanız gerekmez.

![Yenileme Zamanla komutu](media/refresh-scheduled-refresh/data-source-credentials-egw.png)

> [!NOTE]
> Power BI, veri yenileme amacıyla şirket içi SharePoint veri kaynaklarına bağlanmak için yalnızca *Anonim*, *Temel* ve *Windows (NTLM/Kerberos)* kimlik doğrulama yöntemlerinin kullanılmasını destekler. Power BI, şirket içi SharePoint veri kaynaklarındaki verilerin yenilenmesi için *ADFS* veya *Form Tabanlı Kimlik Doğrulama* yöntemlerini desteklemez.

## <a name="scheduled-refresh"></a>Zamanlanmış yenileme

**Zamanlanmış yenileme** bölümünde veri kümesini yenileme sıklığını ve zaman aralıklarını tanımlayabilirsiniz. Bazı veri kaynaklarında yenileme için yapılandırılabilecek bir ağ geçidi gerekmez; diğer veri kaynakları ise ağ geçidi gerektirir.

Ayarları yapılandırmak için **Verilerinizi güncel tutun** kaydırıcısını **Açık** olarak ayarlayın.

> [!NOTE]
> Hedef, yenilemeyi zamanlanan zaman aralığının 15 dakika içerisinde başlatmaktır. Ancak, hizmet gerekli kaynakları daha erken ayıramazsa, bir saati bulabilen gecikmeler ortaya çıkabilir.

![Zamanlanmış yenileme iletişim kutusu](media/refresh-scheduled-refresh/scheduled-refresh.png)

> [!NOTE]
> İki ay etkin olunmaması durumunda veri kümenizdeki zamanlanmış yenileme duraklatılır. Veri kümesinde bir kullanıcı tarafından ziyaret edilen herhangi bir pano veya rapor bulunmuyorsa veri kümesinin etkin olmadığı varsayılır. Bu sırada veri kümesi sahibine zamanlanmış yenilemenin duraklatıldığını belirten bir e-posta gönderilir. Veri kümesinin yenileme zamanlaması **devre dışı** olarak görüntülenir. Zamanlanmış yenilemeyi sürdürmek için, veri kümesi üzerinde oluşturulmuş herhangi bir panoyu veya raporu yeniden ziyaret etmeniz yeterlidir.

## <a name="whats-supported"></a>Neler desteklenir?


> [!NOTE]
> Zamanlanan yenileme de, art arda dört hatadan sonra otomatik olarak devre dışı bırakılır.

Zamanlanmış yenileme için farklı ağ geçitlerinde desteklenen çeşitli veri kümeleri vardır. Kullanabileceğiniz veri kümelerine ilişkin fikir edinmek için aşağıya göz atabilirsiniz.

### <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal

**Power BI Desktop**

* Power BI Desktop'taki **Veri Al** ve Sorgu Düzenleyicisi bölümlerinde gösterilen tüm çevrimiçi veri kaynakları.
* Hadoop Dosyası (HDFS) ve Microsoft Exchange dışında, Power BI Desktop'taki **Veri Al** ve Sorgu Düzenleyicisi bölümlerinde gösterilen tüm şirket içi veri kaynakları.

**Excel**

* Power Query'de gösterilen tüm çevrimiçi veri kaynakları.
* Hadoop dosyası (HDFS) ve Microsoft Exchange dışında, Power Query'de gösterilen tüm şirket içi veri kaynakları.
* Power Pivot'ta gösterilen tüm çevrimiçi veri kaynakları.
* Hadoop dosyası (HDFS) ve Microsoft Exchange dışında, Power Pivot'ta gösterilen tüm şirket içi veri kaynakları.

> [!NOTE]
> Excel 2016 ve sonraki sürümlerinde, Power Query şeridin **Veri** bölümünde, **Verileri Al ve Dönüştür**'ün altında bulunur.

### <a name="power-bi-gateway"></a>Power BI Ağ Geçidi

Desteklenen veri kaynakları hakkında bilgi için bkz. [Power BI veri kaynakları](power-bi-data-sources.md).

## <a name="troubleshooting"></a>Sorun giderme
Bazen verileri yenileme işlemi beklendiği gibi gitmeyebilir. Bu, genellikle ağ geçidiyle bağlantılı bir sorundan kaynaklanır. Araçlar ve bilinen sorunlara yönelik sorun giderme makalelerine göz atın.

- [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)
- [Power BI Gateway - Personal ile ilgili sorunları giderme](service-admin-troubleshooting-power-bi-personal-gateway.md)

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI'da veri yenileme](refresh-data.md)  
- [Power BI Gateway - Personal](service-gateway-personal-mode.md)  
- [Şirket içi veri ağ geçidi (kişisel mod)](service-gateway-onprem.md)  
- [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
- [Power BI Gateway - Personal ile ilgili sorunları giderme](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)