---
title: Power BI Desktop uygulamasını edinme
description: Power BI Desktop uygulamasını indirme ve yükleme
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/10/2019
ms.author: davidi
LocalizationGroup: Get started
ms.openlocfilehash: 7c99b00427ffe742511c0029da79b6ebde02d916
ms.sourcegitcommit: 83e1e162a037f352e542bd5c198a3c98f5db23c7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72511677"
---
# <a name="get-power-bi-desktop"></a>Power BI Desktop uygulamasını edinme
**Power BI Desktop** verileri görselleştiren gelişmiş sorgular, modeller ve raporlar oluşturmanıza olanak sağlar. **Power BI Desktop** ile veri modelleri kurabilir, raporlar oluşturabilir ve Power BI hizmetinde yayımlayarak işinizi paylaşabilirsiniz.  **Power BI Desktop** ücretsiz olarak indirilir.

**Power BI Desktop**'ı aşağıda açıklanan iki yöntemden birini kullanarak edinebilirsiniz:

* Doğrudan **indirme** (bilgisayarınıza indirip yüklediğiniz bir paket)
* **Microsoft Store**’dan bir uygulama olarak yükleme

Her iki yöntemle de bilgisayarınıza **Power BI Desktop**'ın en son sürümünü indirmiş olursunuz ancak dikkat edilmesi gereken ve aşağıda açıklanan birkaç farklılık söz konusudur.

## <a name="download-power-bi-desktop"></a>Power BI Desktop'ı indirme
**Power BI Desktop**'ın en yeni sürümünü indirmek için Power BI hizmetinin sağ üst köşesindeki indirme simgesini seçip **Power BI Desktop** seçeneğini belirleyebilirsiniz.

![Power BI Desktop'ın en son sürümünü indirme](media/desktop-get-the-desktop/getpbid_downloads.png)

Power BI Desktop'ın en son sürümünü şu indirme sayfasından da indirebilirsiniz:

* [**Power BI Desktop indirme** (32 bit ve 64 bit sürümleri)](https://powerbi.microsoft.com/desktop).
  
  [![Power BI Desktop’ın en son sürümünü indirme](media/service-admin-power-bi-security/PBI_Security_01.png)](https://powerbi.microsoft.com/desktop)

Seçtiğiniz indirme yönteminden bağımsız olarak, **Power BI Desktop**'ı indirdiğinizde yükleme dosyasını çalıştırmanız istenir:

![Power BI Desktop yükleme dosyasını çalıştırma](media/desktop-get-the-desktop/download-desktop-exe.png)

Haziran 2019 yayınından itibaren, **Power BI Desktop** desteklenen tüm dilleri içeren tek bir .exe yükleme paketi olarak gönderilmektedir. 32 bit ve 64 bit sürümler için ayrı .exe dosyaları vardır. .msi paketleri Eylül 2019 sürümünden itibaren kullanımdan kaldırılmıştır; bu nedenle yükleme için .exe yürütülebilir dosyası gereklidir. Bu yaklaşım dağıtım, güncelleştirme ve yüklemeyi (özellikle Yöneticiler için) çok daha kolay ve daha kullanışlı hale getirir. Ayrıca, bu makalenin ilerleyen kısımlarındaki [yükleme sırasında komut satırı seçeneklerini kullanma](#using-command-line-options-during-installation) bölümünde açıklandığı gibi, komut satırı parametrelerini kullanarak yükleme işlemini özelleştirebilirsiniz.

Yükleme paketini başlattıktan sonra **Power BI Desktop** bir uygulama olarak yüklenir ve masaüstünüzde çalışır.

![Power BI Desktop uygulaması masaüstünüzde çalışır](media/desktop-get-the-desktop/designer_gsg_install.png)

> [!NOTE]
> **Power BI Desktop**’ın indirilen (MSI) sürümünü ve **Microsoft Store** sürümünü aynı bilgisayara yükleme işlemi (bazı durumlarda *yan yana* yükleme olarak adlandırılır) desteklenmemektedir.
> 
> 

## <a name="install-as-an-app-from-the-microsoft-store"></a>Microsoft Store’dan bir uygulama olarak yükleme
**Power BI Desktop**’ı, şu bağlantıyı kullanarak Microsoft Store’dan da edinebilirsiniz:

* [**Microsoft Store**’dan **Power BI Desktop**’ı yükleme](http://aka.ms/pbidesktopstore)

  ![Microsoft Store’dan Power BI Desktop'ı edinin](media/desktop-get-the-desktop/getpbid_04.png)

**Power BI Desktop**’ı Microsoft Store’dan edinmenin bazı avantajları vardır:

* **Otomatik güncelleştirmeler**: Windows, en son sürümü, kullanılabilir olduğunda arka planda otomatik olarak indirir. Böylece, sürümünüz her zaman güncel kalır.
* **Daha küçük indirmeler**: **Microsoft Store** yalnızca her güncelleştirmede değiştirilen bileşenlerin makinenize indirilmesini sağlar, bu da her güncelleştirme için daha küçük boyutta indirmeler gerçekleştirileceği anlamına gelir.
* **Yönetici ayrıcalığı gerekmez**: Paketi doğrudan indirip yüklediğinizde yüklemenin başarıyla tamamlanması için yönetici olmanız gerekir. **Power BI Desktop**’ı Microsoft Store’dan alırsanız yönetici ayrıcalığı gerekli *değildir*.
* **BT tarafından kullanıma sunulabilir**: **Microsoft Store** sürümü, kuruluşunuzdaki herkese kolayca dağıtılabilir veya kolaylıkla *kullanıma sunulabilir*; bunun yanı sıra **Power BI Desktop**’a **İş için Microsoft Store** aracılığıyla da ulaşılabilir.
* **Dil algılama**: **Microsoft Store** sürümü, desteklenen tüm dilleri içerir ve her başlatıldığında bilgisayarda kullanılan dilleri denetler. Bu durum, **Power BI Desktop**'ta oluşturulan modellerin yerelleştirmesini de etkiler; örneğin, yerleşik tarih hiyerarşileri, **Power BI Desktop**'ın .pbix dosyası oluşturulurken kullandığı dil ile eşleşir.

**Power BI Desktop**’ı Microsoft Store’dan yükleme konusunda aşağıda verilen bazı önemli noktalar ve sınırlamalar söz konusudur:

* SAP bağlayıcısını kullanıyorsanız SAP sürücü dosyalarınızı *Windows\System32* klasörüne taşımanız gerekir.
* **Power BI Desktop**, Microsoft Store’dan yüklendiğinde, .exe sürümünden kullanıcı ayarları kopyalanmaz. Yeni veri kaynaklarınıza yeniden bağlanmanız ve veri kaynağı kimlik bilgilerinizi yeniden girmeniz gerekebilir. 

> [!NOTE]
> **Power BI Desktop**’ın indirilen (MSI) sürümünü ve **Microsoft Store** sürümünü aynı bilgisayara yükleme işlemi (bazı durumlarda *yan yana* yükleme olarak adlandırılır) desteklenmemektedir. **Power BI Desktop**’ı **Microsoft Store**’dan indirmeden önce el ile kaldırmanız gerekir
> 
> [!NOTE]
> **Power BI Desktop**'ın Power BI Rapor Sunucusu sürümü için bu makalede ele alınan sürümlerden ayrı ve farklı bir yükleme gereklidir. **Power BI Desktop**'ın Power BI Rapor Sunucusu sürümü hakkında daha fazla bilgi için bkz. [Power BI Rapor Sunucusu için Power BI raporu oluşturma](report-server/quickstart-create-powerbi-report.md).
> 
> 

## <a name="using-power-bi-desktop"></a>Power BI Desktop'ı kullanma
**Power BI Desktop**'ı başlattığınızda *Hoş Geldiniz* ekranı görüntülenir.

![Power BI Desktop Hoş Geldiniz ekranı](media/desktop-get-the-desktop/getpbid_05.png)

**Power BI Desktop**'ı ilk kez kullanacaksanız (yükleme bir yükseltme değilse) devam edebilmek için önce birkaç soruluk bir form doldurmanız veya **Power BI hizmetinde** oturum açmanız istenir.

Buradan veri modelleri veya raporlar oluşturmaya başlayabilir ve ardından bu raporları, Power BI hizmetinde başkalarıyla paylaşabilirsiniz. **Power BI Desktop**'ı kullanmaya başlama konusunda yardımcı olabilecek kılavuzlara ilişkin bağlantılar için bu makalenin sonundaki **Daha fazla bilgi** bağlantılarına başvurun.

## <a name="minimum-requirements"></a>Minimum gereksinimler
**Power BI Desktop**'ı çalıştırmaya yönelik minimum gereksinimler aşağıdaki listede verilmiştir:

* Windows 7/Windows Server 2008 R2 veya sonraki sürümler
* .NET 4.5
* Internet Explorer 10 veya sonraki sürümler
* **Bellek (RAM):** En az 1 GB kullanılabilir bellek. (1,5 GB veya daha fazla bellek önerilir.)
* **Ekran:** En az 1440x900 veya 1600x900 (16:9) ekran önerilir. Belirli denetimler (başlangıç ekranını kapatma gibi) bu çözünürlükleri aşacağı için 1024x768 veya 1280x800 gibi daha düşük çözünürlükler önerilmez.
* **Windows Görüntü ayarları:** Görüntü ayarlarınız metin, uygulama ve diğer öğelerin boyutunu %100'den fazla değiştirecek şekilde belirlendiyse **Power BI Desktop**'ı kullanmaya devam etmek için kapatılması veya yanıt verilmesi gereken bazı iletişim kutularını göremeyebilirsiniz. Bu sorunla karşılaşırsanız Windows'da **Ayarlar > Sistem > Görüntü** yolunu izleyerek **Görüntü ayarları**'nı denetleyin ve kaydırıcıyı kullanarak görüntü ayarlarını %100'e döndürün.
* **CPU:** 1 gigahertz (GHz) veya daha hızlı x86 veya x64 bit işlemci önerilir.

## <a name="considerations-and-limitations"></a>Önemli Noktalar ve Sınırlamalar

Power BI Desktop ile her zaman harika bir deneyim yaşamanızı istiyoruz. Power BI Desktop'ta sorunlarla karşılaştığınız noktalar olabilir. Bu bölümde ortaya çıkabilecek sorunlarla ilgili çözümlere veya önerilere yer verilmiştir. 

### <a name="using-command-line-options-during-installation"></a>Yükleme sırasında komut satırı seçeneklerini kullanma 

Power BI Desktop yüklerken komut satırı geçişleriyle özellikleri ve seçenekleri ayarlayabilirsiniz. Bu seçenek özellikle kuruluş genelinde Power BI Desktop yüklemesini yöneten veya kolaylaştıran Yöneticiler için yararlıdır. Bu seçenekler .msi ve .exe yüklemeleri için geçerlidir. 


|Komut satırı araçları  |Davranış  |
|---------|---------|
|-q, -quiet, -s, -silent     |sessiz yükleme         |
|-passive     |yalnızca yükleme sırasında ilerleme çubuğunu göster         |
|-norestart     |bilgisayar yeniden başlatma gereksinimini gösterme         |
|-forcerestart     |yüklemeden sonra bilgisayarı sormadan yeniden başlat         |
|-promptrestart     |bilgisayarın yeniden başlatılması gerekiyorsa kullanıcıya sor (varsayılan)         |
|-l<>, -log<>     |yüklemeyi <> içinde belirtilen dosyayla belirli bir dosyaya kaydet         |
|-uninstall     |Power BI Desktop’u kaldır         |
|-repair     |yüklemeyi onar (veya şu anda yüklü değilse yükle)         |
|-package, -update     |Power BI Desktop’ı yükle (varsayılan olarak, -uninstall veya -repair belirtilmediğinde)         |

Ayrıca, bir "PROPERTY=VALUE" söz dizimi ile belirtilen aşağıdaki **söz dizimi parametrelerini** kullanabilirsiniz:

|Parametre  |Anlamı  |
|---------|---------|
|ACCEPT_EULA     |EULA belgesini otomatik olarak kabul etmek için 1 değeri gerektirir         |
|ENABLECXP     |1 değeri, ürün kullanımına ilişkin telemetri yakalayan müşteri deneyimi programına kaydolur         |
|INSTALLDESKTOPSHORTCUT     |1 değeri, Masaüstüne bir kısayol ekler         |
|INSTALLLOCATION     |Yüklenmesini istediğiniz dosya yolu         |
|LANGUAGE     |Uygulamanın varsayılan dilini uygulamak için, yerel ayar kodu (örneğin, en-US, de-DE, PR-BR). Dil belirtilmemişse, Power BI Desktop Windows işletim sistemi dilini görüntüler. Bu ayar, Seçenekler iletişim kutusundan kullanıcı tarafından değiştirilebilir.         |
|REG_SHOWLEADGENDIALOG     |0 değeri, Power BI Desktop’ta oturum açmadan önce görüntülenen iletişim kutusunu göstermeyi devre dışı bırakır         |

Örneğin, Almanca dilini kullanarak herhangi bir kullanıcı arabirimi olmadan yüklemek için aşağıdaki söz dizimi ile çalıştırabilirsiniz: 

```“-quiet LANG=de-DE ACCEPT_EULA=1”```

### <a name="installing-power-bi-desktop-on-remote-machines"></a>Uzak makinelere Power BI Desktop yükleme

Kullanıcılarınıza Windows Installer dosyası (.msi dosyası) gerektiren bir araçla Power BI Desktop dağıtıyorsanız, .msi dosyasını Power BI Desktop installer .exe dosyasından ayıklayabilirsiniz. Bunu gerçekleştirmek için WiX Toolset gibi üçüncü taraf araçları kullanabilirsiniz.

> [!NOTE]
> Üçüncü taraf ürün olarak WiX Toolset seçenekleri bildirimde bulunulmadan değişebilir. Lütfen en güncel bilgiler için belgelerini kontrol edin ve yardım almak için kullanıcı posta listesine başvurun.

* Power BI Desktop yükleyicisini indirdiğiniz bilgisayarda, https://wixtoolset.org/ adresindeki Wix Web sitesinden WiX Toolset’in en son sürümünü indirip yükleyin.
* Yönetici olarak bir komut satırı penceresi açın ve WiX Toolset’i yüklediğiniz klasöre gidin.
* Aşağıdaki komutu çalıştırın: 
    
    ```Dark.exe <path to Power BI Desktop installer> -x <output folder>```

    Örneğin, şunu çalıştırın:

    ``` Dark.exe C:\PBIDesktop_x64.exe -x C:\output```

* Çıktı klasöründe .msi dosyalarını içeren *AttachedContainer* adlı bir klasör bulunur.


### <a name="issues-when-using-previous-releases-of-power-bi-desktop"></a>Power BI Desktop'ın önceki sürümlerini kullanırken ortaya çıkan sorunlar

Bazı kullanıcılar, **Power BI Desktop**’ın eski bir sürümü kullanıldığında aşağıdakine benzer bir hata ile karşılaşır: 

    "We weren't able to restore the saved database to the model" 

Power BI Desktop’ın geçerli sürümüne güncelleştirme yapıldığında sorun genellikle çözülür.

### <a name="disabling-notifications"></a>Bildirimleri devre dışı bırakma
Özellik, performans, kararlılık alanlarındaki ve diğer konulardaki gelişmelerden faydalanabilmeniz için Power BI Desktop'ı en son sürümüne güncelleştirmenizi öneririz. Bazı kuruluşlar kullanıcıların yeni bir sürüm çıktığında güncelleştirme yapmasını istemeyebilir. Aşağıdaki adımları izleyerek kayıt defterinde yapacağınız bir değişiklikle bildirimleri devre dışı bırakabilirsiniz:

1. Kayıt Defteri Düzenleyicisi'ni kullanarak şu konuma gidin: *HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft Power BI Desktop*
2. Orada aşağıdaki ayarlarla yeni girdi oluşturun: *REG_DWORD : DisableUpdateNotification*
3. Yeni girişin değerini **1** olarak belirleyin.

Değişikliğin etkili olabilmesi için bilgisayarınızı yeniden başlatmanız gerekir.

### <a name="power-bi-desktop-loads-with-a-partial-screen"></a>Power BI Desktop ekranı tam olarak yüklenmiyor

Belirli ekran çözünürlüğü yapılandırmalarında bazı kullanıcılar Power BI Desktop'ta büyük siyah alanların görüntülendiğini görebilir. Bu durum genellikle doğrudan Power BI Desktop'ın içerik sunmasıyla ilgili değil yapılan son işletim sistemi güncelleştirmelerinin öğelerin işlenme şeklini etkilemesiyle ilgilidir. Nedeni her ne olursa olsun büyük siyah alanların göze hoş görünmediğini biliyoruz. Bu sorunu gidermek için aşağıdaki adımları izleyebilirsiniz:

1. Başlat tuşuna basın ve açılan arama çubuğuna *bulanık* yazın.
2. Açılan iletişim kutusunda şu seçeneği belirtin: *Bulanık uygulamaları Windows'un düzeltmesine izin ver.*
3. Power BI Desktop'ı yeniden başlatın.

Bu sorun sonraki Windows güncelleştirmeleriyle birlikte giderilebilir. 
 

## <a name="next-steps"></a>Sonraki adımlar
**Power BI Desktop** uygulamasını yükledikten sonra aşağıdaki makaleler hızlı bir şekilde çalışmaya başlamanızı sağlayabilir:

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop ile Sorgulara Genel Bakış](desktop-query-overview.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'taki Verilere Bağlanma](desktop-connect-to-data.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)   

