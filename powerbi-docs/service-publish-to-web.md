---
title: Power BI'dan Web'de yayımlama
description: Power BI'daki Web'de yayımla özelliği sayesinde etkileşimli Power BI görselleştirmelerini blog gönderileri, web siteleri, e-postalar veya sosyal medya üzerinden dilediğiniz cihazda görüntülemek üzere çevrimiçi ortamlara ekleyebilirsiniz.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/16/2019
LocalizationGroup: Share your work
ms.openlocfilehash: 1b5dfc0b05595e96c9a297a5be3700e71cdbe229
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051574"
---
# <a name="publish-to-web-from-power-bi"></a>Power BI'dan Web'de yayımlama

Power BI'ın ile **Web'de Yayımla** seçeneği, çevrimiçi, olduğu gibi etkileşimli Power BI Görselleştirmelerini kolayca katıştırabilir blog gönderileri, Web siteleri, e-postalar veya sosyal medya, herhangi bir CİHAZDAN. Ayrıca yayımladığınız görselleri kolayca düzenleyebilir, güncelleştirebilir, yenileyebilir veya paylaşımdan kaldırabilirsiniz.

> [!WARNING]
> Kullanırken **Web'de Yayımla**, Internet'teki herkes yayımlanan rapor veya görselin görüntüleyebilirsiniz. Bu kimlik doğrulaması gerektirmez ve raporlarınızı toplama ayrıntı düzeyindeki verileri görüntüleme içerir. Bir raporu yayımlamadan önce verileri ve görselleştirmeleri herkese açık şekilde paylaşma Tamam olduğundan emin olun. Gizli veya özel bilgileri yayımlamayın. Bu konuda şüpheleriniz varsa yayımlamadan önce kuruluşunuzun ilkelerini inceleyin.

>[!Note]
>İçeriğinizi dahili bir portala veya web sitesine güvenle eklemek için [Ekle](service-embed-secure.md) veya [SharePoint Online'da Ekle](service-embed-report-spo.md) seçeneğini kullanın. Bu seçenekler, kullanıcılarınız dahili verilerinizi görüntülerken tüm izinlerin ve güvenliğin zorunlu tutulmasını sağlar.

## <a name="how-to-use-publish-to-web"></a>Web'de yayımla özelliğini kullanma

**Web'de Yayımla** raporları düzenleyebilirsiniz, kişisel veya grup çalışma alanlarında kullanılabilir.  Siz veya satır düzeyi güvenlik bağlı olanları ile verilerin güvenliğini sağlamak için paylaşılan raporlar için kullanılamaz. Bkz: [ **sınırlamaları** ](#limitations) bölümünde çalışmaları tam bir listesi için burada **Web'de Yayımla** desteklenmiyor. Gözden geçirme **uyarı** kullanmadan önce bu makalenin önceki **Web'de Yayımla**.

Aşağıdaki *kısa video* bu özelliğin nasıl çalıştığı gösterilmektedir. Daha sonra kendiniz aşağıdaki adımları deneyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UF9QtqE7s4Y" frameborder="0" allowfullscreen></iframe>

Aşağıdaki adımlar **Web'de yayımla** özelliğinin nasıl kullanılacağını açıklamaktadır.

1. Düzenle ve seçin, çalışma alanınızda bir rapor açın **Dosya > Web'de Yayımla**.

   ![PtW1](media/service-publish-to-web/publish_to_web1.png)

2. İçerik ve Seç iletişim kutusu gözden **ekleme kodu oluştur**.

   ![PtW2](media/service-publish-to-web/publish_to_web2_ga.png)

3. Burada gösterildiği gibi uyarıyı gözden geçirin ve verilerin genel bir Web sitesine eklenmeye olduğunu onaylayın. İse, seçin **Yayımla**.

   ![PtW3](media/service-publish-to-web/publish_to_web3_ga.png)

4. Bir iletişim kutusu ile bir bağlantı görüntülenir. Bu bağlantıyı bir e-postayla gönderin, kod gibi bir iFrame katıştırma veya doğrudan bir web sayfası ya da blog sayfanıza yapıştırın.

   ![PtW4](media/service-publish-to-web/publish_to_web4.png)

5. Bir rapor için bir ekleme kodu daha önce oluşturduğunuz ve seçtiğiniz **Web'de Yayımla**, 2-4 arası adımları iletişim kutularında görmezsiniz. Bunun yerine, **ekleme kodu** iletişim kutusu görüntülenir:

   ![PtW5](media/service-publish-to-web/publish_to_web5.png)

   Her rapor için yalnızca bir ekleme kodu oluşturabilirsiniz.


## <a name="tips-and-tricks-for-view-modes"></a>Görüntüleme modlarına ilişkin ipuçları

İçeriği bir blog gönderisine eklediğinizde, genellikle bir özel ekran boyutuna sığdırmanız gerekir.  Yükseklik ve genişlik iFrame etiketindeki gerektiği şekilde ayarlayabilirsiniz. Ancak, bu nedenle raporu düzenlerken uygun görünüm modunu ayarlayın gerekir raporunuzu verilen iFrame alanı içinde emin olmanız gerekir.

Aşağıdaki tabloda Görünüm Modu ve raporun eklendiği zaman nasıl görüneceği hakkında bilgiler verilmiştir.

| Görünüm Modu | Eklendiğinde nasıl görüneceği |
| --- | --- |
| ![PtW6b](media/service-publish-to-web/publish_to_web6b.png) |**Sayfaya Sığdır** raporunuzun sayfa yüksekliğini ve genişliğini dikkate alır. Sayfanızı "Dinamik" oranlara 16:9 veya 4:3 olarak ayarlamak, içerik iFrame içine sığacak şekilde ölçeklendirilir. Bir iFrame içine katıştırılan kullanarak **Sayfaya Sığdır** sonuçlanabilir **sinemaskop**, burada gri renkli bir arka plan iFrame alanlarda koddan sonra ölçeği iFrame içine sığacak şekilde gösterilir. Sinemaskop en aza indirmek için iFrame's yükseklik ve genişlik uygun şekilde ayarlayın. |
| ![PtW6d](media/service-publish-to-web/publish_to_web6d.png) |**Gerçek Boyut** rapor kümesi rapor sayfasındaki boyutunu korumasını sağlar. Bu görünen iFrame içinde kaydırma çubukları neden olabilir. İFrame yükseklik ve genişlik kaydırma çubuklarını önlemek için ayarlayın. |
| ![PtW6c](media/service-publish-to-web/publish_to_web6c.png) |**Genişliğe Uydur** içeriği IFRAME yatay alana sığdırır sağlar. Kenarlık gösterilmeye, ancak tüm yatay boşluk kullanmak için içeriği ölçeklendirir. |

## <a name="tips-and-tricks-for-iframe-height-and-width"></a>iFrame yükseklik ve genişlik ayarlarıyla ilgili ipuçları ve püf noktaları

A **Web'de Yayımla** ekleme kodu aşağıdaki aşağıdaki gibi görünür:

![PtW7](media/service-publish-to-web/publish_to_web7.png)
 
El ile tam olarak nerede ekleme yapıyorsanız sayfasında uyacak şekilde nasıl istediğinizi olduğundan emin olun, height ve width düzenleyebilirsiniz.

Daha kusursuz bir çözüm elde etmek için alt çubuğun geçerli boyutunu alacak şekilde IFRAME yüksekliği 56 piksel ekleme deneyebilirsiniz. Rapor sayfanızda Dinamik boyut kullanılıyorsa aşağıdaki tabloda verilen değerleri kullanarak sinemaskop etkisine maruz kalmadan düzgün bir yerleşim sağlayabilirsiniz.

| Oran | Boyut | Boyut (Genişlik x Yükseklik) |
| --- | --- | --- |
| 16:9 |Küçük |640 x 416 piksel |
| 16:9 |Orta |800 x 506 piksel |
| 16:9 |Büyük |960 x 596 piksel |
| 4:3 |Küçük |640 x 536 piksel |
| 4:3 |Orta |800 x 656 piksel |
| 4:3 |Büyük |960 x 776 piksel |

## <a name="manage-embed-codes"></a>Ekleme kodlarını yönet

Oluşturduktan sonra bir **Web'de Yayımla** ekleme kodu, kendi kodlarını yönetebileceğiniz **ayarları** Power BI menü. Ekleme kodlarını yöneterek içindeki hedef görseli veya raporu (ekleme kodunu geçersiz kılabilir) bir kod, kaldırabilir veya ekleme kodunu alma.

1. **Web'de yayımla** özelliğiyle oluşturduğunuz ekleme kodlarını yönetmek için **Ayarlar** menüsünü açıp **Ekleme kodlarını yönet**'i seçin.

   ![PtW8](media/service-publish-to-web/publish_to_web8.png)

2. Ekleme kodlarını görünür.

   ![PtW9](media/service-publish-to-web/publish_to_web9.png)

3. Almak veya bir ekleme kodu silin. Bu rapor veya görselin giden bağlantıları silmeden devre dışı bırakır.

   ![PtW10](media/service-publish-to-web/publish_to_web10.png)

4. Seçerseniz **Sil**, bir onay sorulur.

   ![PtW11](media/service-publish-to-web/publish_to_web11.png)

## <a name="updates-to-reports-and-data-refresh"></a>Raporları güncelleştirme ve veri yenileme

Oluşturduktan sonra **Web'de Yayımla** ekleme kodunu ve paylaşımı, rapor değişikliklerle güncelleştirildiğinde yaptığınız ekleme kodu bağlantısı hemen etkin hale gelir ve bağlantıyı açan herkes görüntüleyebilir. İlk bu eylemi gerçekleştirdikten sonra ancak güncelleştirmeleri rapor veya görseller kullanıcılarınıza görünür olma önce yaklaşık bir saat sürebilir. Güncelleştirmelerin hemen kullanılabilir hale gelmesini istiyorsanız ekleme kodunu silip yeni bir kod oluşturabilirsiniz. Daha fazla bilgi için bkz. [ **nasıl çalıştığını** ](#howitworks) bu makalenin devamındaki bölümü. 

## <a name="data-refresh"></a>Veri yenileme

Veri yenileme işlemleri eklediğiniz raporlara veya görsellere otomatik olarak yansıtılır. Yenilenen verilerin ekleme kodlarından görünür hale gelmesi yaklaşık 1 saat sürebilir. Otomatik yenilemeyi devre dışı bırakmak için seçebileceğiniz **yenilenmez** zamanlamaya veri kümesinin raporunu kullanır.  

## <a name="custom-visuals"></a>Özel görseller

Özel görseller **Web'de yayımla** işlevinde desteklenmektedir. Kullanırken **Web'de Yayımla**, yayımladığınız görseli paylaştığınız kullanıcıların raporu görüntülemek için özel görselleri etkinleştirmesine gerekmez.

## <a name="limitations"></a>Sınırlamalar

**Web'de Yayımla** çoğunluğu veri kaynakları ve Power BI hizmetinde, ancak aşağıdaki öğeler raporlar için desteklenen **şu anda desteklenen veya kullanılabilir** ile **Web'de Yayımla** :

- Satır düzeyi güvenlik kullanan raporlar.
- Azure Analysis Services, Analysis Services - Çok Boyutlu ve şirket içi ortamda barındırılan Analysis Services - Tablo da dahil olmak üzere herhangi bir Canlı Bağlantı veri kaynağını kullanan raporlar.
- Doğrudan veya bir kuruluş içerik paketi aracılığıyla sizinle paylaşılmış olan raporlar.
- Düzenleme yetkisine sahip bir üye olmadığınız gruplardaki raporlar.
- "R" görselleri şu anda desteklenmez **Web'de Yayımla** raporlar.
- Bir rapordaki görsellerden verileri dışarı aktarma, hangi web yayımlandı.
- ArcGIS Maps for Power BI görselleri.
- Rapor düzeyi DAX ölçüler içeren raporlar.
- Çoklu oturum açma veri modelleri sorgulayın.
- [Gizli veya özel bilgilerin güvenliğini](#publish-to-web-from-power-bi).
- **Ekle** seçeneğiyle birlikte sağlanan otomatik kimlik doğrulama özelliği Power BI JavaScript API’si ile çalışmaz. Power BI JavaScript API'sinde, ekleme için [verilerin kullanıcıya ait olması](developer/embed-sample-for-your-organization.md) yaklaşımını kullanın. [Verilerin kullanıcıya ait olması](developer/embed-sample-for-your-organization.md) hakkında daha fazla bilgi edinin.

## <a name="tenant-setting"></a>Kiracı ayarı

Power BI yöneticileri etkinleştirmek veya devre dışı **Web'de Yayımla** özelliği. Bunlar ayrıca bir ekleme kodu oluşturup oluşturamayacağınız etkileyebilir belirli gruplara erişimi kısıtlayabilirsiniz.

|Öne çıkan özelliği |Tüm kuruluş için etkindir |Tüm kuruluş için devre dışıdır |Belirli güvenlik grupları   |
|---------|---------|---------|---------|
|**Web'de Yayımla** rapora ilişkin **dosya** menüsü|Tüm kullanıcılar için etkindir|Herkes için görünmez|Yalnızca yetkili kullanıcılar veya gruplar için görünür.|
|**Ayarlar** bölümündeki **Ekleme kodlarını yönet** seçeneği|Tüm kullanıcılar için etkindir|Tüm kullanıcılar için etkindir|Tüm kullanıcılar için etkindir.<br><br>* **Sil** seçeneği yalnızca yetkili kullanıcılar veya gruplar için görünür.<br>* **Kod al** seçeneği tüm kullanıcılar için etkindir.|
|Yönetici portalındaki **Ekleme kodları** seçeneği|Durum olarak şunlardan biri görüntülenir:<br>* Etkin<br>* Desteklenmiyor<br>* Engellendi|Durum olarak **Devre dışı** görüntülenir|Durum olarak şunlardan biri görüntülenir:<br>* Etkin<br>* Desteklenmiyor<br>* Engellendi<br><br>Bir kullanıcı, kiracı ayarına göre yetkilendirilmemişse durum, **İhlal edildi** olarak görüntülenir.|
|Mevcut yayımlanmış raporlar|Tümü etkindir|Tümü devre dışıdır|Raporlar tüm kullanıcılar için görünür olmaya devam eder.|

## <a name="understanding-the-embed-code-status-column"></a>Ekleme kodu durum sütununu anlama

**Ekleme kodlarını Yönet** sayfası, bir durum sütunu içerir. Varsayılan olarak, ekleme kodları olan **etkin**, aşağıda listelenen durumlardan biri de olabilir ancak.

| Durum | Açıklama |
| --- | --- |
| **Etkin** |Rapor İnternet kullanıcıları tarafından görüntülenebilir ve raporla etkileşim kurulabilir. |
| **Engellendi** |Rapor içeriği ihlal [Power BI hizmet kullanım koşulları](https://powerbi.microsoft.com/terms-of-service). Microsoft, engelledi. İçeriğin bir hata sonucu engellendiğini düşünüyorsanız desteğe başvurun. |
| **Desteklenmiyor** |Raporun veri kümesi satır düzeyi güvenlik veya desteklenmeyen başka bir yapılandırma kullanıyor. Bkz: [ **sınırlamaları** ](#limitations) tam listesi için bölüm. |
| **İhlal edildi** |Ekleme kodunu dışında tanımlanmış Kiracı ilkesi var. Bu genellikle bir ekleme kodu oluşturduğunuzda oluşur ve ardından **Web'de Yayımla** Kiracı ayarı ekleme kodunu sahip kullanıcı dışlanacak şekilde değiştirildi. Kiracı ayarı devre dışı bırakılır veya kullanıcı, artık oluşturma izni ekleme kodları, mevcut ekleme Kodları Göster bir **ihlal edildi** durumu. |

## <a name="how-to-report-a-concern-with-publish-to-web-content"></a>Web'de yayımla içeriğiyle ilgili sorunları bildirme

Bir içeriğiyle ilgili rapor **Web'de Yayımla** kullanmak, eklenmiş bir Web sitesi veya blog **bayrağı** aşağıdaki görüntüde gösterildiği şekilde alt çubuktaki simgesi. Size bir e-posta Microsoft'a gönderilecek endişelerinizi göndermeniz istenir. Microsoft Power BI hizmet kullanım koşulları üzerinde temel içerik değerlendirilemedi ve uygun eylemi gerçekleştirin.

Bir sorun bildirmek için seçin **bayrağı** simge alt çubuğundaki **Web'de Yayımla** raporu görürsünüz.

![PtW12](media/service-publish-to-web/publish_to_web12_ga.png)

## <a name="licensing-and-pricing"></a>Lisanslama ve Fiyatlandırma

**Web'de yayımla** özelliğini kullanabilmek için Microsoft Power BI kullanıcısı olmanız gerekir. Raporunuzun görüntüleyiciler Power BI kullanıcısı olması gerekmez.

<a name="howitworks"></a>
## <a name="how-it-works-technical-details"></a>Nasıl çalışır? (teknik bilgiler)

Kullanarak bir ekleme kodu oluşturduğunuzda **Web'de Yayımla**, rapor Internet kullanıcıları için görünür hale gelir. Raporun sosyal medya üzerinden kolayca gelecekte paylaşmak için görüntüleyenler genel olarak kullanılabilir. Kullanıcılar genel URL'yi doğrudan açarak veya bir web sayfasında ya da blogda eklenmiş biçimde raporu görüntüledikçe Power BI, rapor tanımını ve raporu görüntülemek için gerekli olan sorguların sonuçlarını önbelleğe alır. Bu, performansı etkilemeden binlerce eş zamanlı kullanıcının rapor görüntüleyebilirsiniz sağlar.

Önbellek uzun ömürlü olduğundan rapor tanımını (örneğin, görünüm modunu değiştirme) güncelleştirmek ya da rapor verilerini yenilediğinizde, kullanıcılarınızın görüntülemek rapor sürümünde değişiklikler yansıtılır önce yaklaşık bir saat sürebilir. Bu nedenle çalışmanızı önceden planlayıp **Web'de yayımla** ekleme kodunu ancak gerekli ayarları tamamladıktan sonra oluşturmanız önerilir.

## <a name="next-steps"></a>Sonraki adımlar

- [SharePoint Online rapor web bölümü](service-embed-report-spo.md) 

- [Raporu güvenli bir portala veya web sitesine ekleme](service-embed-secure.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
