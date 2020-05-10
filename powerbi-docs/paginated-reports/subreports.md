---
title: Power BI sayfalandırılmış raporlarındaki alt raporlar
description: Bu makalede Power BI hizmetindeki sayfalandırılmış raporlar için desteklenen veri kaynaklarını ve Azure SQL Veritabanı veri kaynaklarına nasıl bağlanacağınızı öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 04/29/2020
ms.openlocfilehash: 65d1401a66f8e670df1af3097f0e99fb6b647022
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82615715"
---
# <a name="subreports-in-power-bi-paginated-reports"></a>Power BI sayfalandırılmış raporlarındaki alt raporlar

*Alt rapor*, ana sayfalandırılmış raporun gövdesi içinde başka bir sayfalandırılmış rapor görüntüleyen bir sayfalandırılmış rapor öğesidir. Kavramsal olarak bir raporun içindeki alt rapor, Web sayfasındaki çerçeveye benzer. Bunu, raporun içine rapor eklemek için kullanırsınız. Her raporu alt rapor olarak kullanabilirsiniz. Alt rapor olarak görüntülenen raporu, ana raporla aynı Premium çalışma alanında depolarsınız. Ana raporu, parametreleri alt rapora geçirecek şekilde tasarlayabilirsiniz. Alt rapor veri bölgeleri içinde yinelenebilir ve bir parametre kullanılarak alt raporun her örneğindeki veriler filtrelenebilir.  
  
 ![Sayfalandırılmış rapordaki alt rapor](media/subreports/paginated-report-subreport.png "Sayfalandırılmış rapor alt raporu")  
  
 Bu çizimde ana Sales Order (Satış Siparişi) raporunda görüntülenen kişi bilgileri asında Contacts (Kişiler) alt raporundan gelir.  
  
Sayfalandırılmış rapor tanımı (.rdl) dosyalarını Power BI Report Builder’da oluşturur ve değiştirirsiniz. SQL Server Reporting Services’te depolanan alt raporları Power BI hizmetindeki bir Premium çalışma alanına yükleyebilirsiniz. Ana raporlarla alt raporların aynı çalışma alanında yayımlanması gerekir. [Power BI Report Builder](https://go.microsoft.com/fwlink/?linkid=2086513)’ı yükleyin.
  
## <a name="work-with-report-builder-and-the-power-bi-service"></a>Report Builder ve Power BI hizmetiyle çalışma

Power BI Report Builder bilgisayarınızdaki sayfalandırılmış raporlarla (yerel raporlar olarak bilinir) veya Power BI hizmetindeki raporlarla çalışabilir.  Report Builder’ı ilk kez açtığınızda Power BI hesabınızda oturum açmanız istenir. Oturum açmadıysanız, sağ üst köşede **Oturum aç**'ı seçin.

:::image type="content" source="media/subreports/report-builder-sign-in.png" alt-text="Power BI’da oturum açma":::

Oturum açtıktan sonra Power BI Report Builder’da **Dosya** menüsünün **Aç** ve **Farklı Kaydet** seçenekleri için **Power BI Hizmeti** değerini görürsünüz. Dosyaya kaydederken **Power BI Hizmeti**’ni seçerseniz, Power BI Report Builder ile Power BI hizmeti arasında bir canlı bağlantı oluşturursunuz. 

:::image type="content" source="media/subreports/report-builder-subreport-open-service.png" alt-text="Power BI hizmetinden açma":::

## <a name="save-a-local-report-to-the-power-bi-service"></a>Power BI hizmetinde yerel raporu kaydetme

Ana rapora bir alt rapor ekleyebilmek için önce iki rapor oluşturun ve bunları aynı Power BI Premium çalışma alanına kaydedin. 

1. Mevcut yerel raporu açmak için **Dosya** menüsünde **Aç** > **Bu bilgisayar**’ı ve sonra da .rdl dosyasını seçin.  

2. **Dosya** menüsünde **Farklı Kaydet** > **Power BI Hizmeti**'ni seçin.  Ayrıntılar için bkz. [Power BI hizmetinde sayfalandırılmış rapor yayımlama](paginated-reports-save-to-power-bi-service.md).

    > [!NOTE]
    > Ayrıca Power BI hizmetinden başlayarak da raporu karşıya yükleyebilirsiniz. Aynı [Power BI hizmetinde sayfalandırılmış rapor yayımlama](paginated-reports-save-to-power-bi-service.md) makalesinde ayrıntıları bulabilirsiniz.

3. **Farklı Kaydet** iletişim kutusunda, sayfalandırılmış raporlarınızı depolayabileceğiniz bir Power BI Premium çalışma alanı seçin.  Premium çalışma alanlarının adının yanında ![Premium elmas simgesi](media/subreports/report-builder-premium-diamond.png) bulunur.

    :::image type="content" source="media/subreports/report-builder-subreport-save-as-service.png" alt-text="Power BI hizmetine farklı kaydetme":::

4. **Kaydet**'i seçin.

## <a name="add-a-subreport-to-a-report"></a>Rapora bir alt rapor ekleme

Artık her iki raporu da aynı Premium çalışma alanına kaydettiğinize göre, raporlardan birini diğerine alt rapor olarak ekleyebilirsiniz. Alt rapor eklemenin iki yolu vardır. 

1. **Ekle** şeridinde **Alt Rapor** düğmesini seçin veya rapor tuvaline sağ tıklayın ve **Ekle** > **Alt Rapor**’u seçin.

    :::image type="content" source="media/subreports/report-builder-insert-subreport.png" alt-text="Rapora bir alt rapor ekleme":::

    **Alt Rapor Özellikleri** iletişim kutusu açılır.  

2. **Gözat** düğmesini seçin > alt rapor olarak kullanmak istediğiniz rapora gidin > **Ad** metin kutusunda alt raporun adını belirtin.

3. Gereken diğer özellikleri, örneğin [parametreleri](#use-parameters-in-subreports) yapılandırın.

## <a name="use-parameters-in-subreports"></a>Alt raporlarda parametre kullanma  
 Parametreleri üst rapordan alt rapora geçirmek için, alt rapor olarak kullandığınız raporda bir rapor parametresi tanımlayın. Alt raporu üst rapora yerleştirirken rapor parametresini ve üst rapordan alt rapordaki rapor parametresine geçirilecek değeri seçebilirsiniz.  
  
> [!NOTE]  
> Alt rapordan seçtiğiniz parametre bir *rapor* parametresidir; *sorgu* parametresi değildir.  
  
 Alt raporu, raporun ana gövdesine veya bir veri bölgesine yerleştirebilirsiniz. Alt raporu bir veri bölgesine yerleştirirseniz, alt rapor veri bölgesindeki grubun veya satırın her örneğinde yinelenir. Gruptan veya satırdan bir değeri alt rapora geçirebilirsiniz. Alt rapor değeri özelliğinde, alt rapor parametresine geçirmek istediğiniz değeri içeren alan için bir alan ifadesi kullanın.  
  
 Parametreler ve alt raporlarla çalışma hakkında daha fazla bilgi için, SQL Server Reporting Services belgelerinin [Alt rapor ve parametreler ekleme](https://docs.microsoft.com/sql/reporting-services/report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) bölümüne bakın.  

## <a name="preview-paginated-reports-in-report-builder"></a>Report Builder’da sayfalandırılmış raporları önizleme

Report Builder’da raporlarınızın önizlemesini görüntüleyebilirsiniz.

- **Giriş** şeridinde **Çalıştır**'ı seçin. 

Report Builder bir tasarım aracı olduğundan, raporun önizlemesi raporu Power BI hizmetinde işlemekten farklı görünebilir.

### <a name="notes-about-previewing"></a>Önizleme hakkında notlar

- Report Builder raporlarda kullanılan veri kaynaklarının kimlik bilgilerini depolamaz.  Report Builder önizleme sırasında sizden her kimlik bilgisi kümesini ister.  
- Raporun veri kaynakları şirket içindeyse raporu Power BI çalışma alanına kaydettikten sonra ağ geçidini yapılandırmanız gerekir.
- Report Builder önizleme sırasında hatayla karşılaşırsa genel bir ileti döndürür.  Hatayı ayıklamak zor olursa, raporu Power BI hizmetinde işlemeyi göz önünde bulundurun.  

## <a name="considerations"></a>Önemli noktalar

### <a name="maintaining-the-connection"></a>Bağlantıyı koruma

Dosyayı kapattığınızda Report Builder Power BI bağlantısını korumaz.  Alt raporların Power BI çalışma alanında depolandığı bir yerel ana raporla çalışmanız mümkündür. Raporu kapatmadan önce ana raporu Power BI çalışma alanına kaydettiğinizden emin olun.  Kaydetmezseniz önizleme sırasında ‘bulunamadı’ iletisi alabilirsiniz çünkü Power BI hizmetine canlı bağlantı yoktur.  Böyle bir durumda alt rapora gidin ve özelliklerini seçin.  Power BI hizmetinden alt raporu yeniden açın.  Bu işlem bağlantının yeniden kurulmasını sağlar ve tüm diğer alt raporlar sorunsuz çalışır.

### <a name="renaming-a-subreport"></a>Alt raporu yeniden adlandırma

Çalışma alanında bir alt raporu yeniden adlandırırsanız, ana rapordaki ad başvurusunu düzeltmeniz gerekir. Aksi takdirde alt rapor işlenmez. Ana rapor yine alt rapor öğesinin içinde bir hata iletisiyle işlenir.

## <a name="migrate-large-reports"></a>Büyük raporları geçirme

Büyük raporları Power BI’a geçiriyorsanız [RdlMigration aracını](../guidance/migrate-ssrs-reports-to-power-bi.md) kullanmayı göz önünde bulundurun.  RdlMigration aracı yinelenen alt rapor adlarını işleyecek şekilde güncelleştirilmiştir.  Bir veya birden fazla rapor aynı adı paylaştığında ama farklı alt dizinlerde yer aldığında yinelenen alt rapor adları söz konusu olabilir.  Adlar benzersiz bir şekilde çözümlenmezse yalnızca ilk alt rapor tanınır.

Büyük raporları geçirirken Report Builder’ı kullanmak istiyorsanız önce alt raporlarla çalışmanızı öneririz. Yinelenen rapor adlarını önlemek için her alt raporu Power BI çalışma alanına kaydedin.

## <a name="share-reports-with-subreports"></a>Alt raporları olan raporları paylaşma

Daha önce belirttiğimiz gibi ana rapor ile alt raporların aynı çalışma alanında yer alması gerekir. Aksi takdirde alt rapor işlenmez. Ana raporu paylaşırken alt raporları da paylaşmanız gerekir. Ana raporu bir uygulamada paylaşırsanız, bu uygulamaya alt raporları da eklediğinizden emin olun. Ana raporu doğrudan kullanıcılarla veya kullanıcı gruplarıyla paylaşıyorsanız aynı kullanıcılarla veya kullanıcı gruplarıyla alt raporu da paylaştığınızdan emin olun.
  
## <a name="next-steps"></a>Sonraki adımlar

[Power BI sayfalandırılmış raporlarındaki alt raporların sorunlarını giderme](subreports-troubleshoot.md)

[Power BI hizmetinde sayfalandırılmış rapor görüntüleme](../consumer/paginated-reports-view-power-bi-service.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
