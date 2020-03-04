---
title: Power BI'dan Web'de yayımlama
description: Power BI'daki Web'de yayımla özelliği sayesinde etkileşimli Power BI görselleştirmelerini blog gönderileri, web siteleri, e-postalar veya sosyal medya üzerinden dilediğiniz cihazda görüntülemek üzere çevrimiçi ortamlara ekleyebilirsiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/25/2020
LocalizationGroup: Share your work
ms.openlocfilehash: 34754f413cd6bb8e520ff8d7f2c9d4a28da73ef5
ms.sourcegitcommit: 032a77f2367ca937f45e7e751997d7b7d0e89ee2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609930"
---
# <a name="publish-to-web-from-power-bi"></a>Power BI'dan Web'de yayımlama

Power BI'ın **Web'de yayımla** seçeneği sayesinde etkileşimli Power BI görselleştirmelerini blog gönderileri, web siteleri, e-postalar veya sosyal medya üzerinden dilediğiniz cihazda görüntülemek üzere çevrimiçi ortamlara ekleyebilirsiniz. Ayrıca yayımladığınız görselleri kolayca düzenleyebilir, güncelleştirebilir, yenileyebilir veya yayımlanan görsellerinizin paylaşımını durdurabilirsiniz.

> [!WARNING]
> **Web'de yayımla** seçeneğini kullandığınızda yayımladığınız rapor veya görseller, İnternet üzerindeki herkes tarafından görüntülenebilir. Bunun için kimlik doğrulaması gerekmez ve raporlarınızda toplanan ayrıntı düzeyindeki verileri görüntülemek de dahildir. Raporu yayımlamadan önce verileri ve görselleştirmeleri herkesle paylaşmanızın uygun olduğundan emin olun. Gizli veya özel bilgileri yayımlamayın. Bu konuda şüpheleriniz varsa yayımlamadan önce kuruluşunuzun ilkelerini inceleyin.

>[!Note]
>İçeriğinizi dahili bir portala veya web sitesine güvenle eklemek için [Ekle](service-embed-secure.md) veya [SharePoint Online'da Ekle](service-embed-report-spo.md) seçeneğini kullanın. Bu seçenekler, kullanıcılarınız dahili verilerinizi görüntülerken tüm izinlerin ve güvenliğin zorunlu tutulmasını sağlar.

## <a name="how-to-use-publish-to-web"></a>Web'de yayımla özelliğini kullanma

**Web'de yayımla** özelliğini, kişisel veya grup çalışma alanlarında düzenleyebildiğiniz raporlarda kullanabilirsiniz.  Sizinle paylaşılan raporlarda veya verileri korumak için satır düzeyi güvenliğe dayanan raporlarda kullanılamaz. **Web'de yayımla** özelliğinin desteklenmediği tüm durumların listesi için aşağıdaki [**Sınırlamalar**](#limitations) bölümüne bakın. **Web'de yayımla** özelliğini kullanmadan önce bu makalenin üst kısmındaki **Uyarı** bölümünü inceleyin.

Aşağıdaki kısa video bu özelliğin nasıl çalıştığını gösterir. Aşağıdaki adımları izleyerek kendiniz de deneyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UF9QtqE7s4Y" frameborder="0" allowfullscreen></iframe>

Aşağıdaki adımlar **Web'de yayımla** özelliğinin nasıl kullanılacağını açıklamaktadır.

1. Çalışma alanınızda, düzenleme yetkisine sahip olduğunuz bir rapor açın ve **Dosya > Web'de yayımla**'yı seçin.

   ![PtW1](media/service-publish-to-web/publish_to_web1.png)
   
2. Ekleme kodları oluşturmanıza izin verilmediyse [Power BI yöneticinize](service-admin-role.md) başvurun

   ![PtW1](media/service-publish-to-web/publish_to_web_admin_prompt.png)
   
   Kuruluşunuzda Web’de yayımla özelliğini etkinleştirebilecek birini bulmaya ilişkin yardım almak için [bu ipuçlarına bakın](#how-to-find-your-power-bi-administrator).

3. İletişim kutusunun içeriğini inceleyin ve **Ekleme kodu oluştur**’u seçin.

   ![PtW2](media/service-publish-to-web/publish_to_web2_ga.png)

4. Burada gösterildiği gibi uyarıyı gözden geçirin ve verilerin genel bir web sitesine eklenmeye uygun olduğunu onaylayın. Uygunsa **Yayımla**'yı seçin.

   ![PtW3](media/service-publish-to-web/publish_to_web3_ga.png)

5. İletişim kutusuyla birlikte bir bağlantı görüntülenir. Bu bağlantıyı e-posta yoluyla gönderebilir, iFrame gibi bir koda ekleyebilir veya web sayfasına ya da bloga doğrudan yapıştırabilirsiniz.

   ![PtW4](media/service-publish-to-web/publish_to_web4.png)

6. Daha önce rapor için bir ekleme kodu oluşturduysanız ve **Web'de yayımla**’yı seçerseniz 2-4 arası adımlardaki iletişim kutusunu görmezsiniz. Bunun yerine **Ekleme kodu** iletişim kutusu açılır:

   ![PtW5](media/service-publish-to-web/publish_to_web5.png)

   Her rapor için yalnızca bir ekleme kodu oluşturabilirsiniz.


## <a name="tips-and-tricks-for-view-modes"></a>Görüntüleme modlarına ilişkin ipuçları ve püf noktaları

İçeriği bir blog gönderisine eklediğinizde genelde belirli bir ekran boyutuna sığdırmanız gerekir.  iFrame etiketinde yükseklik ve genişliği gerektiği şekilde ayarlayabilirsiniz. Ancak raporunuzun sağlanan iFrame alanına sığdığından emin olmalısınız, bu nedenle raporu düzenlerken uygun Görünüm Modunu da ayarlamanız gerekir.

Aşağıdaki tabloda Görünüm Modu ve raporun eklendiği zaman nasıl görüneceği hakkında bilgiler verilmiştir.

| Görünüm Modu | Eklendiğinde nasıl görüneceği |
| --- | --- |
| ![PtW6b](media/service-publish-to-web/publish_to_web6b.png) |**Sayfaya sığdır** ayarı, raporunuzun sayfasının yükseklik ve genişliğini dikkate alır. Sayfanızı 16:9 veya 4:3 gibi *dinamik* oranlara ayarladıysanız içeriğiniz iFrame içine sığacak şekilde ölçeklendirilir. **Sayfaya sığdır** ayarını kullanan raporlar bir iFrame'e eklendiğinde *sinemaskop* etkisine maruz kalabilir. Bu durumda içerik iFrame içine sığacak şekilde ölçeklendirildikten sonra iFrame alanında gri renkli arka plan gösterilir. Bu etkiyi en aza indirmek için iFrame’in yükseklik ve genişlik ayarını uygun şekilde değiştirin. |
| ![PtW6d](media/service-publish-to-web/publish_to_web6d.png) |**Gerçek boyut**, raporunuzun rapor sayfasındaki boyutunu korumasını sağlar. Bunun sonucunda iFrame içinde kaydırma çubukları görüntülenebilir. Kaydırma çubuklarının gösterilmemesi için iFrame yükseklik ve genişlik ayarını değiştirin. |
| ![PtW6c](media/service-publish-to-web/publish_to_web6c.png) |**Genişliğe uydur** ayarı, içeriğin iFrame’in yatay alanını doldurmasını sağlar. Kenarlık gösterilmeye devam eder ancak içerik yatay boşluğun tamamını kullanacak şekilde ölçeklendirilir. |

## <a name="tips-and-tricks-for-iframe-height-and-width"></a>iFrame yükseklik ve genişlik ayarlarıyla ilgili ipuçları ve püf noktaları

**Web'de yayımla** ekleme kodu aşağıdaki örnekte gösterildiği gibi görünür:

![PtW7](media/service-publish-to-web/publish_to_web7.png)
 
Genişlik ve yükseklik değerlerini el ile değiştirerek, eklediğiniz sayfada nasıl görüneceğini tam olarak belirleyebilirsiniz.

Daha iyi bir yerleşim sağlamak için iFrame’in yükseklik değerine 56 piksel ekleyerek alt çubuğun geçerli boyutunu hesaba katabilirsiniz. Rapor sayfanızda dinamik boyut kullanılıyorsa aşağıdaki tabloda verilen değerleri kullanarak sinemaskop etkisine maruz kalmadan düzgün bir yerleşim sağlayabilirsiniz.

| Oran | Boyut | Boyut (Genişlik x Yükseklik) |
| --- | --- | --- |
| 16:9 |Küçük |640 x 416 piksel |
| 16:9 |Orta |800 x 506 piksel |
| 16:9 |Büyük |960 x 596 piksel |
| 4:3 |Küçük |640 x 536 piksel |
| 4:3 |Orta |800 x 656 piksel |
| 4:3 |Büyük |960 x 776 piksel |

## <a name="manage-embed-codes"></a>Ekleme kodlarını yönet

**Web'de yayımla** ekleme kodunu oluşturduktan sonra kodlarınızı Power BI'ın **Ayarlar** menüsünden yönetebilirsiniz. Ekleme kodlarını yöneterek belirli bir kodun içindeki hedef görseli veya raporu kaldırabilir (ekleme kodunu geçersiz kılabilir) veya ekleme kodunu alabilirsiniz.

1. **Web'de yayımla** özelliğiyle oluşturduğunuz ekleme kodlarını yönetmek için **Ayarlar** menüsünü açıp **Ekleme kodlarını yönet**'i seçin.

   ![PtW8](media/service-publish-to-web/publish_to_web8.png)

2. Ekleme kodlarınız görüntülenir.

   ![PtW9](media/service-publish-to-web/publish_to_web9.png)

3. Ekleme kodunu alabilir veya silebilirsiniz. Sildiğinizde, o rapor veya görsele giden tüm bağlantılar devre dışı kalır.

   ![PtW10](media/service-publish-to-web/publish_to_web10.png)

4. **Sil**’i seçerseniz onaylamanız istenir.

   ![PtW11](media/service-publish-to-web/publish_to_web11.png)

## <a name="updates-to-reports-and-data-refresh"></a>Raporları güncelleştirme ve veri yenileme

**Web'de yayımla** ekleme kodunuzu oluşturup paylaştıktan sonra yaptığınız değişiklikler rapora yansıtılır ve ekleme kodu bağlantısı anında etkinleştirilir. Bağlantıyı açan herkes bunu görüntüleyebilir. Bununla birlikte ilk eylemden sonra raporlar veya görsellerdeki güncelleştirmelerin kullanıcılarınıza gösterilmesi iki veya üç saat sürebilir. Daha fazla bilgi edinmek için bu makalenin devamındaki [**Nasıl çalışır?** ](#howitworks) bölümünü inceleyin. 

## <a name="data-refresh"></a>Veri yenileme

Veri yenileme işlemleri eklediğiniz raporlara veya görsellere otomatik olarak yansıtılır. Yenilenen verilerin ekleme kodlarından görünür hale gelmesi yaklaşık bir saat sürebilir. Otomatik yenilemeyi devre dışı bırakmak için raporun kullandığı veri kümesinin zamanlamasındaki **yenileme** seçeneğini kullanın.  

## <a name="custom-visuals"></a>Özel görseller

Özel görseller **Web'de yayımla** işlevinde desteklenmektedir. **Web'de yayımla** özelliğini kullandığınızda yayımladığınız görseli paylaştığınız kullanıcıların raporu görüntülemek için özel görselleri etkinleştirmesine gerek yoktur.

## <a name="limitations"></a>Sınırlamalar

**Web’de yayımla** özelliği Power BI hizmetindeki veri kaynaklarının ve raporların çoğu için desteklenir ama aşağıdaki öğeler şu anda **Web’de yayımla** işlevinde desteklenmez ve kullanılamaz:

- Satır düzeyi güvenlik kullanan raporlar.
- Azure Analysis Services, Analysis Services - Çok Boyutlu ve şirket içi ortamda barındırılan Analysis Services - Tablo da dahil olmak üzere herhangi bir Canlı Bağlantı veri kaynağını kullanan raporlar.
- Doğrudan veya bir kuruluş içerik paketi aracılığıyla sizinle paylaşılmış olan raporlar.
- Düzenleme yetkisine sahip bir üye olmadığınız gruplardaki raporlar.
- "R" Görselleri şu an için raporları **Web'de yayımla** özelliği tarafından desteklenmemektedir.
- Web’de yayımlanan bir rapordaki görsellerden Verileri dışarı aktarma.
- ArcGIS Maps for Power BI görselleri.
- Rapor düzeyi DAX ölçüleri içeren raporlar.
- Çoklu oturum açma veri sorgulama modelleri.
- Gizli veya özel bilgilerin güvenliğini sağlama.
- [Paylaşılan ve sertifikalı veri kümeleri](service-datasets-share.md).
- **Ekle** seçeneğiyle birlikte sağlanan otomatik kimlik doğrulama özelliği Power BI JavaScript API’si ile çalışmaz. Power BI JavaScript API'sinde, ekleme için [verilerin kullanıcıya ait olması](developer/embed-sample-for-your-organization.md) yaklaşımını kullanın.

## <a name="tenant-setting"></a>Kiracı ayarı

**Web’de yayımla** ayarı kullanıcıların ekleme kodları oluşturabileceği seçenekler getirir.

![Web’de yayımla ayarı](media/service-admin-portal/powerbi-admin-publish-to-web-setting.png)

**Ekleme kodlarının nasıl çalışacağını seçin** seçeneği **Yalnızca mevcut ekleme kodlarına izin ver** olarak ayarlandıysa ve **Web’de yayımla** ayarı **Etkin** durumdaysa, ekleme kodu oluşturmak için Power BI yöneticinize başvurmanız istenir.

![Web'de yayımla istemi](media/service-publish-to-web/publish_to_web_admin_prompt.png)

Power BI yöneticileri **Web'de yayımla** özelliğini etkinleştirebilir veya devre dışı bırakabilir. Belirli gruplara erişimi de kısıtlayabilirler ve bu ekleme kodu oluşturma becerinizi etkiler. **Web’de yayımla** ayarına göre kullanıcı arabiriminde farklı seçeneklerle karşılaşırsınız.

|Öne çıkan özelliği |Tüm kuruluş için etkindir |Tüm kuruluş için devre dışıdır |Belirli güvenlik grupları   |
|---------|---------|---------|---------|
|Raporun **Dosya** menüsündeki **Web'de yayımla** seçeneği|Tüm kullanıcılar için etkindir|Herkes için görünmez|Yalnızca yetkili kullanıcılar veya gruplar için görünür.|
|**Ayarlar** bölümündeki **Ekleme kodlarını yönet** seçeneği|Tüm kullanıcılar için etkindir|Tüm kullanıcılar için etkindir|Tüm kullanıcılar için etkindir.<br><br>* **Sil** seçeneği yalnızca yetkili kullanıcılar veya gruplar için görünür.<br>* **Kod al** seçeneği tüm kullanıcılar için etkindir.|
|Yönetici portalındaki **Ekleme kodları** seçeneği|Durum olarak aşağıdakilerden biri görüntülenir:<br>* Etkin<br>* Desteklenmiyor<br>* Engellendi|Durum olarak **Devre dışı** görüntülenir|Durum olarak aşağıdakilerden biri görüntülenir:<br>* Etkin<br>* Desteklenmiyor<br>* Engellendi<br><br>Bir kullanıcı, kiracı ayarına göre yetkilendirilmemişse durum, **İhlal edildi** olarak görüntülenir.|
|Mevcut yayımlanmış raporlar|Tümü etkindir|Tümü devre dışıdır|Raporlar tüm kullanıcılar için görünür olmaya devam eder.|

## <a name="understanding-the-embed-code-status-column"></a>Ekleme kodu durum sütununu anlama

>[!Note]
>Yayımladığınız ekleme kodlarını düzenli aralıklarla gözden geçirmeli ve artık genel kullanıma sunulması gerekmeyenleri kaldırmalısınız. 

**Ekleme kodlarını yönet** sayfası bir durum sütunu içerir. Varsayılan olarak ekleme kodları **Etkin** durumdadır ama aşağıda listelenen durumlarda da olabilirler.

| Durum | Açıklama |
| --- | --- |
| **Etkin** |Rapor İnternet kullanıcıları tarafından görüntülenebilir ve raporla etkileşim kurulabilir. |
| **Engellendi** |Rapor içeriği [Power BI Hizmet Kullanım Koşulları](https://powerbi.microsoft.com/terms-of-service)'nı ihlal ediyor. Microsoft tarafından engellendi. İçeriğin bir hata sonucu engellendiğini düşünüyorsanız desteğe başvurun. |
| **Desteklenmiyor** |Raporun veri kümesi satır düzeyi güvenlik veya desteklenmeyen başka bir yapılandırma kullanıyor. Listenin tamamı için [**Sınırlamalar**](#limitations) bölümüne bakın. |
| **İhlal edildi** |Ekleme kodu, tanımlanmış kiracı ilkesi kapsamının dışındadır. Bu durum genellikle, bir ekleme kodu oluşturulduktan sonra kiracıdaki **Web'de yayımla** ayarının, ekleme koduna sahip kullanıcı dışlanacak şekilde değiştirilmesiyle ortaya çıkar. Kiracı ayarı devre dışıysa veya kullanıcının artık ekleme kodu oluşturmasına izin verilmiyorsa mevcut ekleme kodları **İhlal edildi** durumunda görüntülenir. |

## <a name="how-to-report-a-concern-with-publish-to-web-content"></a>Web'de yayımla içeriğiyle ilgili sorunları bildirme

Bir web sitesine eklenmiş olan **Web'de yayımla** içeriğiyle ilgili bir sorunu bildirmek için aşağıdaki resimde gösterilen şekilde alt çubuktaki **Bayrak** simgesini kullanın. Microsoft'a sorununuzu açıklayan bir e-posta göndermeniz istenir. Microsoft, içeriği Power BI Hizmeti Kullanım Koşulları çerçevesinde değerlendirerek gerekli eylemi gerçekleştirecektir.

Sorun bildirmek için gördüğünüz **Web'de yayımla** raporunun alt çubuğundaki **bayrak** simgesini seçin.

![PtW12](media/service-publish-to-web/publish_to_web12_ga.png)

## <a name="licensing-and-pricing"></a>Lisanslama ve Fiyatlandırma

**Web'de yayımla** özelliğini kullanabilmek için Microsoft Power BI kullanıcısı olmanız gerekir. Raporunuzu görüntüleyen kişilerin Power BI kullanıcısı olması gerekmez.

<a name="howitworks"></a>
## <a name="how-it-works-technical-details"></a>Nasıl çalışır? (teknik bilgiler)

**Web'de yayımla** özelliğini kullanarak bir ekleme kodu oluşturduğunuzda rapor, İnternet kullanıcılarına açık hale gelir. Rapor herkese açık olduğundan görüntüleyenler, ilerleyen zamanlarda sosyal medya üzerinden kolayca paylaşabilir. Kullanıcılar genel URL'yi doğrudan açarak veya bir web sayfasında ya da blogda eklenmiş biçimde raporu görüntüledikçe Power BI, rapor tanımını ve raporu görüntülemek için gerekli olan sorguların sonuçlarını önbelleğe alır. Bu, binlerce kullanıcının performansı etkilemeden eş zamanlı olarak raporu görüntüleyebilmesini sağlar.

Önbellek uzun ömürlü olduğundan rapor tanımını güncelleştirmeniz (Görünüm modunu değiştirme gibi) durumunda veya rapor verilerini yenilediğinizde değişikliklerin, raporun kullanıcılarınızın görüntülediği sürümüne uygulanması yaklaşık bir saat sürebilir. Bu nedenle çalışmanızı önceden planlayıp **Web'de yayımla** ekleme kodunu ancak gerekli ayarları tamamladıktan sonra oluşturmanız önerilir.

## <a name="how-to-find-your-power-bi-administrator"></a>Power BI yöneticinizi bulma

[Web’de yayımla kiracı ayarlarını](#tenant-setting) değiştirmek için kuruluşunuzun [Power BI yöneticisiyle](service-admin-role.md) çalışmanız gerekir.

Power BI’a kaydolan kişilerin veya küçük kuruluşların henüz Power BI yöneticisi olmayabilir. [Kiracı yöneticisi devralma sürecimizi](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover) izlemeniz gerekir. Power BI yöneticiniz varsa, yöneticiniz sizin için ekleme kodu oluşturmayı etkinleştirebilir.

Büyük kuruluşlar genelde bir Power BI yöneticisine sahip olur. Aşağıdaki rollerden herhangi birine sahip olan kişiler Power BI yöneticisi olarak görev yapabilir:

- Office 365 yöneticileri
- Azure Active Directory yöneticileri
- Azure Active Directory’de Power BI hizmet yöneticisi rolüne sahip olan kullanıcılar

Ayarı güncelleştirmeleri için kuruluşunuzda [bu kişilerden birini](https://docs.microsoft.com/office365/admin/admin-overview/admin-overview#who-has-admin-permissions-in-my-business) bulmanız gerekir.


## <a name="next-steps"></a>Sonraki adımlar

- [SharePoint Online rapor web bölümü](service-embed-report-spo.md) 

- [Raporu güvenli bir portala veya web sitesine ekleme](service-embed-secure.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
