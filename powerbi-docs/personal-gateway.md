---
title: Power BI Gateway - Personal
description: Power BI Gateway - Personal
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
LocalizationGroup: Gateways
ms.openlocfilehash: 8d047e814eaa7c84ee7e1be20d1f4722c6cb1e56
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="power-bi-gateway---personal"></a>Power BI Gateway - Personal
> [!NOTE]
> Power BI için kişisel ağ geçidinin **şirket içi veri ağ geçidi (kişisel mod)** adlı yeni bir sürümü vardır. Aşağıdaki makalede **Power BI Gateway - Personal** adlı eski sürüm açıklanmaktadır. Bu sürüm, 31 Temmuz 2017 tarihinden sonra kullanımdan kaldırılacak ve artık çalışmayacaktır. Nasıl yükleyeceğiniz de dahil olmak üzere, kişisel ağ geçidinin yeni sürümü hakkında bilgi için [**Şirket içi veri ağ geçidi (kişisel mod)** başlıklı makaleye bakın](service-gateway-personal-mode.md).
> 
> 

Bir köprü işlevi gören **Power BI Gateway - Personal**, Power BI hizmeti ve [yenileme](refresh-data.md) özelliğini destekleyen şirket içi veri kaynakları arasında hızlı ve güvenli veri aktarımı sağlar. Bu makalenin amacı, ağ geçidinin nasıl çalıştığını ve bir ağ geçidine ihtiyacınız olup olmadığını anlamanızı sağlayacak ayrıntılı bir açıklama sunmaktır. Ayrıca, kişisel ağ geçidi hakkında bu [yararlı videoyu](https://www.youtube.com/watch?v=de58vROLqZI) da hazırladık. 

Ağ geçidi, bilgisayarınızda bir hizmet olarak yüklenip çalıştırılır. Bir hizmet olarak, yapılandırma sırasında belirttiğiniz Windows hesabı kullanılarak çalıştırılır. Bazı durumlarda Ağ Geçidi bir uygulama olarak çalıştırılır. Sonraki kısımlarda bu konuyu daha ayrıntılı olarak ele alacağız.

Power BI bir şirket içi veri kaynağındaki verileri yenilediğinde ağ geçidi, Power BI hesabınızın kaynağa bağlanmak ve kaynaktan veri sorgulamak için doğru izinlere sahip olmasını sağlar.

Power BI ile ağ geçidi arasındaki veri aktarımının güvenliği [Azure Service Bus](http://azure.microsoft.com/documentation/services/service-bus/) tarafından sağlanır. Service Bus, Power BI hizmeti ile bilgisayarınız arasında güvenli bir kanal oluşturur. Ağ geçidi bu güvenli bağlantıyı sağladığından, genellikle güvenlik duvarınızda bir bağlantı noktası açmanıza gerek yoktur.

Ağ geçidiyle ilgili ayrıntılara geçmeden önce Power BI'da kullanılan bazı terimleri inceleyelim:

*Veri kümesi*, bir çevrimiçi veya şirket içi veri kaynağından Power BI'a yüklenen verilerdir. Bağlanıp karşıya veri yüklemek için Veri Al özelliğini kullandığınızda bir veri kümesi oluşturursunuz. Veri kümeleri, tarayıcınızdaki Power BI Çalışma Alanınızın Çalışma Alanım bölmesinde görünür. Rapor oluşturup panonuza kutucuk sabitlediğinizde veri kümenizdeki verileri görürsünüz.

*Veri kaynağı*, bir veri kümesine yüklediğiniz verilerin asıl kaynağıdır. Veri kaynağı bir veri tabanı, Excel çalışma sayfası, web hizmeti vb. olabilir. Excel çalışma kitaplarını kullanarak veri satırları içeren basit bir çalışma sayfası oluşturabilirsiniz. Oluşturduğunuz bu çalışma sayfası bir veri kaynağı olarak kabul edilir. Excel'de bulunan Power Query veya Power Pivot eklentisini kullanarak hem çevrimiçi hem de şirket içi veri kaynaklarına bağlanıp bu kaynaklardan veri sorgulayabilirsiniz. Üstelik bu işlemlerin tamamını aynı çalışma kitabında gerçekleştirirsiniz. Power BI Desktop ile hem çevrimiçi hem de şirket içi veri kaynaklarına bağlanıp bu kaynaklardan veri sorgulamak için Veri Al seçeneğini kullanabilirsiniz.

Kişisel ağ geçidi, şirket içi veri ağ geçidi aracılığıyla yüklenir. Kişisel ağ geçidini [Power BI Gateway sayfasından](https://powerbi.microsoft.com/gateway/) indirebilirsiniz.

## <a name="do-i-need-a-gateway"></a>Bir ağ geçidine ihtiyacım var mı?
Bir ağ geçidi yüklemeden önce ağ geçidine gerçekten ihtiyacınız olup olmadığını bilmeniz önemlidir. Bu, aslında veri kaynaklarınıza bağlıdır:

### <a name="on-premises-data-sources"></a>Şirket içi veri kaynakları
Kişisel ağ geçidi, kuruluşunuzdaki desteklenen şirket içi veri kaynağından veri alan veri kümelerinin yenilenmesi için *gereklidir*.

ŞİMDİ YENİLE ve YENİLEMEYİ ZAMANLA özellikleri, aşağıdaki kaynaklardan yüklenen veri kümeleri için bir ağ geçidiyle birlikte desteklenir:

* Desteklenen bir şirket içi veri kaynağına bağlanmak ve bu kaynaktan veri sorgulamak için Power Query veya Power Pivot eklentilerinin kullanıldığı Microsoft Excel 2013 (veya sonraki bir sürümü) çalışma kitapları. Power Query veya Power Pivot sekmesindeki Dış Veri Al bölümünde gösterilen tüm şirket içi veri kaynakları (Hadoop dosyası (HDFS) ve Microsoft Exchange dışında) yenileme özelliğini destekler.
* Desteklenen şirket içi veri kaynağına bağlanmak ve bu kaynaktan veri sorgulamak için Veri Al özelliğinin kullanıldığı Microsoft Power BI Desktop dosyaları. Hadoop dosyası (HDFS) ve Microsoft Exchange dışında, Veri Al sayfasında gösterilen tüm şirket içi veri kaynakları yenileme özelliğini destekler.

### <a name="online-data-sources"></a>Çevrimiçi veri kaynakları
Ağ geçidi *yalnızca* [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx) işlevini kullanmanız halinde gereklidir. Yalnızca çevrimiçi veri kaynaklarından veri alan veri kümelerini yenilemek için ağ geçidi gerekli *değildir*.

> [!NOTE]
> [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx) işlevini kullanıyorsanız yalnızca, veri kümesini veya raporunuzu 18 Kasım 2016 tarihinden sonra yeniden yayımlamış olmanız halinde bir ağ geçidi gereklidir.
> 
> 

ŞİMDİ YENİLE ve YENİLEMEYİ ZAMANLA özellikleri, aşağıdaki kaynaklardan yüklenen veri kümeleri için bir ağ geçidi olmadan desteklenir:

* Çevrimiçi veri kaynaklarından alınan ait içerik paketleri (içerik paketleri\\hizmetler). İçerik paketlerinden alınan veri kümeleri, varsayılan ayara göre günde bir kez otomatik olarak güncelleştirilir ancak yenileme işlemini elle de gerçekleştirebilir veya bir yenileme zamanlaması oluşturabilirsiniz.
* Çevrimiçi bir veri kaynağına bağlanmak ve bu kaynaktan veri sorgulamak için Power Query veya Power Pivot eklentilerinin kullanıldığı Microsoft Excel 2013 (veya sonraki bir sürümü) çalışma kitapları.
* Çevrimiçi bir veri kaynağına bağlanmak ve bu kaynaktan veri sorgulamak için Veri Al seçeneğinin kullanıldığı Microsoft Power BI Desktop dosyaları.

**Soru:** Excel çalışma kitabım veya Power BI Desktop dosyam hem çevrimiçi hem de şirket içi veri kaynaklarından veri alırsa ne olur?

**Yanıt:** Bir ağ geçidi *gereklidir*. Şirket içi veri kaynaklarınızdaki verileri yenilemek için bir ağ geçidi yükleyip yapılandırmanız gerekir.

**Soru:** Excel çalışma kitabımda yalnızca benim yazmış olduğum veri satırları varsa ne olur?**

**Yanıt:** Bir ağ geçidi gerekli *değildir*. Bir ağ geçidi yükleyip yapılandırmanız gereken tek senaryo; çalışma kitabınızda, desteklenen bir çevrimiçi veri kaynağından veri sorgulamak ve veri modeline veri yüklemek için Power Query veya Power Pivot eklentilerinin kullanılmasıdır

## <a name="setting-up-a-gateway-for-the-first-time"></a>İlk kez bir ağ geçidi ayarlama
İlk kez bir ağ geçidi ayarlarken aşağıdaki üç adımı uygularsınız:

1. Bir ağ geçidi indirme ve yükleme
2. Ağ geçidini yapılandırma
3. Power BI'daki veri kaynaklarında oturum açma

Her bir adımı ayrıntılı olarak ele alalım.

### <a name="download-and-install-a-gateway"></a>Bir ağ geçidi indirme ve yükleme
> [!NOTE]
> Power BI için kişisel ağ geçidinin **şirket içi veri ağ geçidi (kişisel mod)** adlı yeni bir sürümü vardır. Bu makalede **Power BI Gateway - Personal** adlı eski sürüm açıklanmaktadır. Bu sürüm, 31 Temmuz 2017 tarihinden sonra kullanımdan kaldırılacak ve artık çalışmayacaktır. Nasıl yükleyeceğiniz de dahil olmak üzere, kişisel ağ geçidinin yeni sürümü hakkında bilgi için [**Şirket içi veri ağ geçidi (kişisel mod)** başlıklı makaleye bakın](service-gateway-personal-mode.md).
> 
> 

Desteklenen bir veri kümesi için ŞİMDİ YENİLE veya YENİLEMEYİ ZAMANLA seçeneğine ilk kez tıkladığınızda bir ağ geçidi yüklemeniz istenir. Alternatif olarak, ağ geçidini yüklemek için İndir menüsünde **Data Gateway**'i seçebilirsiniz. [Şirket içi veri ağ geçidini](http://go.microsoft.com/fwlink/?LinkID=820925) indirin.

Kendinize ait bir ağ geçidine sahip olmak için **Şirket içi veri ağ geçidi** yerine **Personal Gateway**'i tercih etmeniz gerekir.

Bir ağ geçidi yüklemek gerçekten de çok kolaydır. Ağ geçidini yüklemek için bir konum seçtikten sonra diğer uygulamalarda olduğu gibi lisans sözleşmesini okuyup kabul etmeniz yeterlidir. Bununla birlikte, bilmeniz gereken bazı önemli noktalar da vardır. Özellikle, ağ geçidini yüklediğiniz bilgisayar türünü ve bu bilgisayarda Windows'da oturum açtığınız hesabın türünü bilmeniz gerekir.

> [!NOTE]
> Ağ geçidinin, veri kaynağına erişimi olması gerekir. Kişisel makineniz veri kaynağına bağlanamıyorsa, veri kaynağına erişimi olan bir makineye [şirket içi veri ağ geçidi](service-gateway-onprem.md) yüklemeyi deneyebilirsiniz. Azure'da barındırılan bir sanal makineye (VM) yüklenmiş olan SQL Server, buna örnek olarak gösterilebilir. Kişisel makinenizin VM'ye erişimi olmayabilir. Bunun yerine, şirket içi veri ağ geçidini VM’ye yükleyip Power BI hizmetinde bir veri kaynağı yapılandırabilirsiniz.
> 
> 

### <a name="computer-type"></a>Bilgisayar türü
Ağ geçidini yüklediğiniz bilgisayarın türü önemlidir.

> [!NOTE]
> Kişisel ağ geçidi, yalnızca 64 bit Windows işletim sistemlerinde desteklenir.
> 
> 

Dizüstü bilgisayarda: Zamanlanmış bir yenilemenin gerçekleşebilmesi için ağ geçidinin çalışır durumda olması gerekir. Dizüstü bilgisayarlar genellikle kapalıdır veya çalıştırıldığından daha çok uyku modundadır. Ağ geçidinizi bir dizüstü bilgisayara yüklerseniz zamanlanmış yenileme saatlerini dizüstü bilgisayarın çalıştırıldığı saatlere göre ayarladığınızdan emin olun. Bu şekilde ayarlama yapmazsanız yenileme işlemi, bir sonraki zamanlanmış yenileme saatine kadar yeniden denenmez.

Masaüstü bilgisayarlarda: Burada çok sorun yaşanmaz. Bilgisayarın ve ağ geçidinin zamanladığınız yenileme saatlerinde çalıştırıldığından emin olmanız yeterlidir. Pek çok masaüstü bilgisayar uyku moduna geçer ve bilgisayar uyku modundayken yenileme işlemi gerçekleştirilemez.

Bir ağ geçidi yükledikten sonra başka bir ağ geçidi yüklemenize gerek yoktur. Desteklenen tüm veri kümeleri için aynı ağ geçidini kullanabilirsiniz. Ayrıca, çalışma kitabınızı ve Power BI Desktop dosyalarınızı karşıya yüklediğiniz bilgisayarda ağ geçidini yüklemenize gerek yoktur. Örnek senaryo: Kuruluşunuzdaki bir SQL Server veri kaynağına bağlanan bir Excel çalışma kitabınız olduğunu düşünelim. Çalışma kitabını dizüstü bilgisayarınızdan yüklemek için Power BI'da Veri Al seçeneğini kullandınız. Ayrıca, sürekli açık bıraktığınız bir masaüstü bir bilgisayarınız var ve bu bilgisayarda bir ağ geçidi yükleyip yapılandırdınız. Power BI'da, veri kaynaklarınızda oturum açtınız ve veri kümesi için bir yenileme zamanlaması ayarladınız.  Zamanlanmış yenileme saati geldiğinde Power BI, masaüstü bilgisayarınızda yüklü olan ağ geçidiyle güvenli bir bağlantı kurar. Ardından, güncelleştirmeleri almak için veri kaynaklarına güvenli bir şekilde bağlanır. Yenileme işlemi için, dizüstü bilgisayarınızdan yüklediğiniz ilk çalışma kitabıyla iletişim kurulmaz.

> [!NOTE]
> Kişisel ve kurumsal ağ geçitlerini aynı bilgisayara yükleyebilirsiniz.
> 
> 

### <a name="windows-account"></a>Windows hesabı
Ağ geçidini yüklediğinizde Windows hesabınızı kullanarak bilgisayarınızda oturum açarsınız. Windows hesabınızın sahip olduğu izinlerin türü, ağ geçidinin Windows'da nasıl yükleneceğini ve çalıştırılacağını etkiler.

Windows'da oturum açtığınız hesap:

|  | Yönetici izinlerine sahipse | Yönetici izinlerine sahip değilse |
| --- | --- | --- |
| **Power BI Gateway - Personal** |Hizmet olarak çalıştırılır |Uygulama olarak çalıştırılır |
| **Zamanlanmış Yenileme** |Bilgisayarınız ve ağ geçidi hizmeti çalıştırıldığı sürece, zamanlanmış yenileme saatinde oturum açmış olmanız gerekmez. |Zamanlanmış yenileme saatinde bilgisayarınızda oturum açmış olmanız gerekir. |
| **Windows hesabının parolasını değiştirme** |Ağ geçidi hizmetinde Parolanızı değiştirmeniz gerekir. Ağ geçidi tarafından kullanılan hesap parolası artık geçerli değilse yenileme başarısız olur. |Ağ geçidi her zaman, oturum açmış olduğunuz hesap ve parola kullanılarak çalıştırılır. Windows oturumunuz açık değilse ağ geçidi çalıştırılmaz ve yenileme başarısız olur. |

### <a name="configure-the-gateway"></a>Ağ geçidini yapılandırma
Yükleme Sihirbazı sonlandığında Yapılandırma Sihirbazı'nı başlatmanız istenir. Bir ağ geçidini yapılandırmak için çok fazla işlem gerçekleştirmenize gerek yoktur. Sihirbaz üzerinden Power BI'da oturum açmanız gerekir. Bu işlem Sihirbazın, Power BI hizmetindeki Power BI hesabınızla bağlantı kurabilmesi için gereklidir.

Windows'da Yönetici izinleriyle oturum açtığınızda Windows hesabınıza ilişkin kimlik bilgilerinizi girmeniz istenir. Farklı bir Windows hesabı belirtebilirsiniz ancak söz konusu izinlerin, ağ geçidinin çalıştırılma şeklini belirlediğini unutmayın. Ağ geçidi hizmeti, bu hesap kullanılarak çalıştırılır.

### <a name="sign-in-to-data-sources"></a>Veri kaynaklarında oturum açma
Yapılandırma Sihirbazı sonlandığında ağ geçidiniz çalışır durumdaysa bir Kimlik Doğrulaması türü belirtip veri kümenizin veri kaynaklarının her birinde oturum açmanız gerekir. Bu adımı Power BI'da gerçekleştirirsiniz.

![](media/personal-gateway/pg_dataset_settings_signin.png)

Yalnızca bir kimlik doğrulaması türü belirtip her veri kaynağında bir kez oturum açmanız yeterlidir. Veri kümesinin Ayarlar ekranındaki **Veri Kaynaklarını Yönet** bölümünde oturum açarsınız. Birden fazla veri kaynağınız varsa her bir veri kaynağında oturum açmanız gerekir. Ağ geçidi, varsayılan Kimlik Doğrulaması türünü veri kaynağına göre belirler. Çoğu durumda Windows kimlik doğrulaması kullanılır ancak veri kaynağınız için farklı bir kimlik doğrulaması türü gerekli olabilir. Emin değilseniz veri kaynağı yöneticinize danışın.

## <a name="up-and-running"></a>Çalışır durumda!
Ağ geçidiniz çalışır durumdaysa bir veri kümesi için YENİLEMEYİ ZAMANLA'ya tıklayabilirsiniz. Açılan ekranda veri kümenize ilişkin Ayarlar sayfasını görürsünüz.

![](media/personal-gateway/pg_awintsales_settings.png)

Bu sayfada şunlar görüntülenir:

1. Yenileme durumu: Yenilemenin başarılı olup olmadığını ve bir sonraki zamanlanmış yenileme saatini gösterir.
2. **Ağ Geçidi**: Bir ağ geçidinin yüklü ve çevrimiçi olup olmadığını gösterir. Bir ağ geçidi yüklü ancak çevrimiçi değilse Veri Kaynaklarını Yönet ve Yenilemeyi Zamanla ayarları devre dışı bırakılır.
3. **Veri Kaynaklarını Yönet**: Veri kümesinin bağlandığı veri kaynaklarını gösterir. Oturum açabilir veya kimlik doğrulaması türünü değiştirebilirsiniz. Her veri kaynağı için yalnızca bir kez oturum açmanız gerekir.
4. **Yenilemeyi Zamanla**: Burada, yenileme zamanlama ayarlarını yapılandırabilirsiniz. Ağ geçidi çevrimiçi değilse bu ayarlar devre dışı bırakılır.
5. Yenileme hatası bildirimleri: Varsayılan olarak belirlenen bu seçenek, zamanlanmış bir yenileme başarısız olduğunda size e-posta gönderilmesini sağlar.

## <a name="updating-your-windows-account-password"></a>Windows hesabınızın parolasını güncelleştirme
Ağ geçidinizi yüklediğiniz sırada bilgisayarınızda yönetici ayrıcalıkları olan bir Windows hesabı ile oturum açtıysanız ağ geçidi, Yapılandırma Sihirbazı'nda belirttiğiniz Windows hesabını kullanan bir hizmet olarak çalışır. Genellikle bu hesap, bilgisayarınızda oturum açmak için kullandığınız Windows hesabıdır. Windows hesabınızın parolasını değiştirdiğinizde bu parolayı ağ geçidinde de değiştirmeniz gerekir; aksi halde, hizmet çalıştırılamayabilir ve yenileme başarısız olur. Windows hesabınızın parolasını ağ geçidi için de değiştirmek üzere Windows Masaüstü Görev Çubuğunuzda veya Uygulamalar'da kişisel ağ geçidi simgesini seçin.

![](media/personal-gateway/pg_programicon.png)

Burada parolanızı güncelleştirebilir ve ağ geçidinizin bağlantı durumunu kontrol edebilirsiniz.

![](media/personal-gateway/pg_credentials.png)

## <a name="ports"></a>Bağlantı Noktaları
Ağ geçidi, şu giden bağlantı noktaları üzerinden iletişim kurar: TCP 443 (varsayılan), 5671, 5672, 9350 ila 9354.  Ağ geçidi için gelen bağlantı noktaları gerekli değildir.

| Etki alanı adları | Giden bağlantı noktaları | Açıklama |
| --- | --- | --- |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Gelişmiş İleti Sıraya Alma Protokolü (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |TCP üzerinden Service Bus Geçişi'ndeki dinleyiciler (Erişim Denetimi belirtecinin alınması için 443 gerekir) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| login.windows.net |443 |HTTPS |

Etki alanları yerine IP adreslerini beyaz listeye almanız gerekirse Microsoft Azure Datacenter IP aralıkları listesini indirip kullanabilirsiniz. [İndirin](https://www.microsoft.com/download/details.aspx?id=41653)

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidi (kişisel mod): Kişisel ağ geçidinin yeni sürümü](service-gateway-personal-mode.md)
[Power BI Ağ Geçitleri için ara sunucu ayarlarını yapılandırma](service-gateway-proxy.md)  
[Power BI Premium](service-premium.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

