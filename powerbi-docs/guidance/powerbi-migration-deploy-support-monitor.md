---
title: Power BI'a dağıtma
description: Power BI’a geçiş yaparken dağıtma, destekleme ve izlemeye ilişkin rehberlik.
author: peter-myers
ms.author: kfollis
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 08/20/2020
ms.openlocfilehash: 65520d7126b0bce422d018ed973f2b63b217bde9
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99086913"
---
# <a name="deploy-to-power-bi"></a>Power BI'a dağıtma

Bu makalede, Power BI’a geçiş yaparken içerik dağıtmayı ve bunu destekleyip izlemeyi ele alan **5. aşamaya** ilişkin bilgiler sunulur.

:::image type="content" source="media/powerbi-migration-deploy-support-monitor/migrate-to-powerbi-stage-5.png" alt-text="Bir Power BI geçişinin aşamalarını gösteren görüntü. Bu makalede 5. aşama vurgulanır.":::

> [!NOTE]
> Yukarıdaki grafiğin kapsamlı açıklaması için bkz. [Power BI geçişine genel bakış](powerbi-migration-overview.md).

5\. aşama, yeni Power BI çözümünün üretime dağıtılmasına odaklanır.

Bu aşamada çıkış olarak işletme tarafından kullanılmaya hazır olan bir üretim çözümü elde edilir. Çevik bir yöntemle çalışırken, gelecekteki bir yinelemeyle sunulacak bazı planlı geliştirmelerin olması kabul edilebilir. Bu aşamada, destek ve izleme de önemlidir ve bunların sürekli olarak gerçekleştirilmesi gerekir.

> [!TIP]
> Paralel çalışma ve eski raporların kullanımdan çıkarılması (aşağıda ele alınır) haricinde bu makalede ele alınan konular, standart Power BI uygulama projeleri için de geçerlidir.

## <a name="deploy-to-test-environment"></a>Test ortamına dağıtma

Genelde, IT tarafından yönetilen veya iş üretkenliği açısından kritik olan çözümlerin test ortamı bulunur. Tüm Power BI çözümleri için gerekli olmayan test ortamları, geliştirme ve üretimin arasında yer alır. Test çalışma alanı, üretime sunma öncesinde kullanıcı kabul testi (UAT) gerçekleştirilmesi için geliştirmeden ayrılmış sabit bir konum olarak görev yapabilir.

İçeriğiniz Premium kapasiteli bir çalışma alanında yayımlandıysa, [dağıtım işlem hatlarını](../create-reports/deployment-pipelines-overview.md) kullanarak geliştirme, test ve üretim çalışma alanlarına dağıtma işlemini basitleştirebilirsiniz. Ya da, bunları el ile veya [PowerShell betiklerini](https://powerbi.microsoft.com/blog/duplicating-workspaces-by-using-power-bi-cmdlets/) kullanarak yayımlayabilirsiniz.

### <a name="deploy-to-test-workspace"></a>Test çalışma alanına dağıtma

Test çalışma alanına dağıtma işlemlerinde genelde şu önemli etkinlikler gerçekleştirilir:

- **Bağlantı dizeleri ve parametreleri:** Geliştirme ve test ortamı farklı veri kaynaklarını kullanıyorsa veri kümesi bağlantı dizelerini ayarlayın. Bağlantı dizelerini etkin şekilde yönetmek için [parametreleme](../connect-data/service-parameters.md) kullanılabilir.
- **Çalışma alanı içeriği:** Veri kümelerini ve raporları test çalışma alanında yayımlayın ve pano oluşturun.
- **Uygulama.** UAT işleminin bir parçasıysa, test çalışma alanındaki içeriği kullanarak bir [uygulama](../consumer/end-user-apps.md) yayımlayın. Genellikle, uygulama izinleri UAT ile ilişkili olan az sayıda kişiyle sınırlıdır.
- **Veri yenileme:** UAT’nin etkin olarak gerçekleştiği dönem için tüm İçeri aktarma veri kümelerine yönelik [veri kümesi yenileme işlemi](../connect-data/refresh-scheduled-refresh.md) zamanlayın.
- **Güvenlik:** [Çalışma alanı rollerini](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) güncelleştirin veya doğrulayın. Çalışma alanı erişimine ilişkin testi işlemi, UAT ile ilişkili olan az sayıda kişiyi içerir.

> [!NOTE]
> Geliştirme, test ve üretime dağıtıma yönelik seçenekler hakkında daha fazla bilgi edinmek için [Power BI kuruluş dağıtımı planlama teknik incelemesinin](https://aka.ms/PBIEnterpriseDeploymentWP) 9 bölümüne bakın.

### <a name="conduct-user-acceptance-testing"></a>Kullanıcı kabul testi gerçekleştirme

UAT, genelde konu uzmanı olan iş kullanıcılarıyla gerçekleştirilir. Konu uzmanları, doğrulamanın ardından yeni içeriğin doğru olduğuna, gereksinimleri karşıladığına ve daha geniş kapsamlı kullanım için dağıtılabileceğine onay verir.

Yazılı onaylar da dahil olmak üzere bu UAT işleminin resmiyet düzeyi, değişiklik yönetimi uygulamalarınıza göre farklılık gösterir.

## <a name="deploy-to-production-environment"></a>Üretim ortamına dağıtma

Üretim ortamına dağıtmayla ilişkili bazı önemli noktalar bulunur.

### <a name="conduct-a-staged-deployment"></a>Aşamalı dağıtım gerçekleştirme

Riski ve kullanıcılar için hizmet kesintisini en aza indirmeye çalışıyorsanız veya farklı endişeleriniz varsa, aşamalı dağıtım gerçekleştirebilirsiniz. İlk üretime dağıtım küçük bir pilot kullanıcı grubuyla yapılabilir. Böylece, pilot kullanıcılardan etkin olarak geri bildirim istenebilir.

Tüm hedef kullanıcılar yeni Power BI çözümüne erişim iznine sahip olana kadar üretim çalışma alanındaki veya uygulamadaki izinleri genişletin.

> [!TIP]
> Yeni Power BI çözümünün tüketiciler tarafından nasıl benimsendiğini ve kullanıldığını öğrenmek için [Power BI etkinlik günlüğünü](../admin/service-admin-auditing.md) kullanın.

### <a name="handle-additional-components"></a>Ek bileşenleri işleme

Dağıtım işlemi boyunca, aşağıda belirtilenler gibi tüm çözümün desteklenmesi için gereken diğer gereksinimlerin karşılanması için Power BI yöneticilerinizle çalışmanız gerekebilir:

- **Ağ geçidi bakımı:** Veri ağ geçidinde [yeni bir veri kaynağını](../connect-data/service-gateway-data-sources.md) kaydetmeniz gerekebilir.
- **Ağ geçidi sürücüleri ve bağlayıcılar:** Yeni bir özel veri kaynağının kullanılması, ağ geçidi kümesinde yeni bir sürücünün veya özel bağlayıcının kullanılmasını gerektirebilir.
- **Yeni bir Premium kapasite oluşturma:** Mevcut bir [Premium kapasiteyi](../admin/service-premium-capacity-manage.md) kullanabilirsiniz. Ya da, yeni bir Premium kapasitenin kullanılmasını gerektiren durumlar oluşabilir. Departmana ilişkin bir iş yükünü ayırmak istediğinizde bu durum yaşanabilir.
- **Power BI veri akışı ayarlama:** Veri hazırlama etkinlikleri, Power Query Online kullanılarak her [Power BI veri akışında](../transform-model/dataflows/dataflows-introduction-self-service.md) bir kez ayarlanabilir. Bu, veri hazırlama işlemlerinin birçok Power BI Desktop dosyasında yinelenmesine yönelik gereksinimini ortadan kaldırır.
- **Yeni bir kuruluş görseli kaydetme:** AppSource’ta bulunmayan özel görsellere yönelik [kuruluş görseli](../developer/visuals/power-bi-custom-visuals-organization.md) kaydı yönetici portalından yapılabilir.
- **Öne çıkan içerik ayarlama:** Power BI hizmeti giriş sayfasında kimlerin [içeriği öne çıkarabileceğini](https://powerbi.microsoft.com/blog/promote-your-reports-dashboards-and-apps-on-power-bi-home/) denetleyen bir kiracı ayarı bulunur.
- **Duyarlılık etiketleri ayarlama:** Tüm [duyarlılık etiketleri](../admin/service-security-data-protection-overview.md) Microsoft Information Protection ile tümleşiktir.

### <a name="deploy-to-production-workspace"></a>Üretim çalışma alanına dağıtma

Üretim çalışma alanına dağıtma işlemlerinde genelde şu önemli etkinlikler gerçekleştirilir:

- **Değişiklik yönetimi:** Gerekirse dağıtım izni edinin ve standart değişiklik yönetimi uygulamalarınızı kullanarak dağıtımı kullanıcılara bildirin. Üretim dağıtımlarına izin verilen onaylı bir değişiklik yönetimi aralığı olabilir. Genelde BT tarafından yönetilen içeriklere uygulanan bu özellik self servis içeriğe çok nadir uygulanır.
- **Geri alma planı:** Geçiş işlemlerinde, yeni bir çözümün ilk kez geçirilmesine yönelik bir beklenti oluşur. İçerik zaten mevcutsa, gerekli olması durumunda önceki sürüme geri dönme planı bulundurmak mantıklıdır. SharePoint ve OneDrive sürüm oluşturma özelliğini kullanarak Power BI Desktop dosyalarının önceki sürümlerini bulundurma bu amaç için uygundur.
- **Bağlantı dizeleri ve parametreleri:** Test ve üretim ortamı farklı veri kaynaklarını kullanıyorsa veri kümesi bağlantı dizelerini ayarlayın. [Parametreleme](../connect-data/service-parameters.md), bu amaç için etkili şekilde kullanılabilir.
- **Veri yenileme:** İçeri aktarılan veri kümeleri için [veri kümesi yenilemesini zamanlayın](../connect-data/refresh-scheduled-refresh.md).
- **Çalışma alanı içeriği:** Veri kümelerini ve raporları üretim çalışma alanında yayımlayın ve pano oluşturun. İçeriğiniz Premium kapasiteli çalışma alanlarında yayımlandıysa, [Dağıtım işlem hatları](../create-reports/deployment-pipelines-overview.md) ile geliştirme, test ve üretim çalışma alanlarına yönelik dağıtım işlemini basitleştirebilirsiniz.
- **Uygulama:** İçerik dağıtım stratejiniz uygulamaları içeriyorsa, üretim çalışma alanınızda bulunan içeriği kullanarak bir [uygulama](../consumer/end-user-apps.md) yayımlayın.
- **Güvenlik:** İçerik dağıtımı ve işbirliği stratejinizi temel alarak [çalışma alanı rollerini](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) güncelleştirin ve doğrulayın.
- **Veri kümesi ayarları:** Her veri kümesi için şu ayarları güncelleştirin ve doğrulayın:
  - [Destekleme](../collaborate-share/service-endorse-content.md) (sertifikalı veya yükseltilen gibi)
  - Ağ geçidi bağlantısı veya veri kaynağı kimlik bilgileri
  - Zamanlanmış yenileme
  - [Öne çıkan Soru-Cevap soruları](../create-reports/service-q-and-a-create-featured-questions.md)
- **Rapor ve pano ayarları:** Her rapor ve panoya yönelik ayarları güncelleştirin ve doğrulayın. En önemli ayarlar şunlardır:
  - Açıklama
  - İlgili kişi veya grup
  - [Duyarlılık etiketi](../admin/service-security-apply-data-sensitivity-labels.md)
  - [Öne çıkan içerik](https://powerbi.microsoft.com/blog/promote-your-reports-dashboards-and-apps-on-power-bi-home/)
- **Abonelikler:** Gerekirse rapor abonelikleri ayarlayın.

> [!IMPORTANT]
> Bu noktada önemli bir kilometre taşına ulaştınız. Geçiş tamamlandığında başarınızı kutlayabilirsiniz.

### <a name="communicate-with-users"></a>Kullanıcılarla iletişim kurma

Yeni çözümü tüketicilere duyurun. İçeriği, ilgili belgeleri, sık sorulan soruları ve öğreticileri nerede bulabileceklerini onlara bildirin. Yeni içeriği tanıtmak için öğle yemeği tarzında etkinlikler düzenleyebilir veya isteğe bağlı videolar hazırlayabilirsiniz.

Yardım isteme ve geri bildirimde bulunmaya ilişkin yönergeler sağladığınızdan emin olun.

### <a name="conduct-a-retrospective"></a>Geçmişe dönük değerlendirme gerçekleştirme

Geçişin başarılı yönlerini incelemek ve sonraki geçiş işleminde nelerin daha iyi yapılabileceğini anlamak için bir geçmişe dönük değerlendirme gerçekleştirebilirsiniz.

## <a name="run-in-parallel"></a>Paralel çalıştırma

Çoğu durumda, yeni çözüm önceden belirlenen bir süre boyunca eski çözüm ile paralel çalışır. Paralel çalıştırma şu avantajları sunar:

- Özellikle raporların görev açısından kritik olduğu durumlarda riskin azalması.
- Kullanıcıların yeni Power BI çözümüne alışması için onlara süre tanır.
- Power BI’da sunulan bilgilerle eski raporlar arasında çapraz başvuru yapılmasına olanak tanır.

## <a name="decommission-the-legacy-report"></a>Eski raporu kullanımdan çıkarma

Bir noktada, Power BI’a geçirilen raporların eski iş zekası platformunda devre dışı bırakılması gerekir. Eski raporlar şu durumlarda kullanımdan çıkarılabilir:

- Kullanıcı topluluğuna iletilen önceden belirlenmiş paralel çalıştırma süresinin dolması. Bu süre genelde 30-90 gündür.
- Tüm eski sistem kullanıcılarının artık yeni Power BI çözümüne erişebilmesi.
- Eski raporda artık önemli bir etkinliğin gerçekleşmemesi.
- Yeni Power BI çözümünde kullanıcı üretkenliğini etkileyen sorunların oluşmaması.

## <a name="monitor-the-solution"></a>Çözümü izleme

[Power BI etkinlik günlüğündeki](../admin/service-admin-auditing.md) (veya Power BI Rapor Sunucusu’na dağıtılan içeriğe yönelik [yürütme günlüğü](/sql/reporting-services/report-server/report-server-executionlog-and-the-executionlog3-view)) olaylar kullanılarak yeni çözümün kullanım desenlerine ilişkin bilgi edinilebilir. Etkinlik günlüğünün analiz edilmesi, gerçek kullanımın beklentilerden farklı olup olmadığının belirlenmesine yardımcı olabilir. Çözümün yeterli düzeyde desteklendiğini de doğrulayabilir.

Etkinlik günlüğünün incelenmesiyle şu sorular yanıtlanabilir:

- İçerik ne sıklıkta görüntüleniyor?
- İçeriği kim görüntülüyor?
- İçerik genelde bir uygulama veya çalışma alanı aracılığıyla mı görüntüleniyor?
- Çoğu kullanıcı bir tarayıcıyı veya mobil uygulamayı mı kullanıyor?
- Abonelikler kullanılıyor mu?
- Bu çözümü temel alan yeni raporlar oluşturuluyor mu?
- İçerik sık güncelleştiriliyor mu?
- Güvenlik nasıl tanımlanmış?
- Veri yenileme hataları gibi sorunlar sık yaşanıyor mu?
- Daha fazla eğitim verilmesi gerektiğini belirten endişe verici etkinlikler (örneğin, önemli dışarı aktarma etkinliği veya çok sayıda farklı rapor paylaşımı) gerçekleşiyor mu?

> [!IMPORTANT]
> Etkinlik günlüğünün düzenli olarak incelendiğinden emin olun. Bunun yalnızca yakalanması ve geçmişin depolanması denetim ve uyumluluk açısından değer sunar. Ancak, etkin eylemin gerçekleştirilebildiği durumlarda gerçek değer elde edilir.

## <a name="support-the-solution"></a>Çözümü destekleme

Geçiş işlemi tamamlanmış olsa da, geçiş sonrası dönemi sorunların ve performansa ilişkin endişelerin giderilmesi açısından büyük önem taşır. Zamanla, iş ihtiyaçları geliştikçe geçirilen çözümde de bazı değişiklikler yapılır.

Destek, kuruluşun self servis iş zekasını yönetme şekline bağlı olarak farklı şekilde sunulur. Tüm iş birimlerindeki Power BI şampiyonları, resmi olmayan şekilde temel destek sunar. Resmi olmayan bu önemli rolün teşvik edilmesi gerekir.

Destek biletleri aracılığıyla BT tarafından yönetilen resmi destek sürecinin olması sistem odaklı isteklerin işlenmesi ve ilerletme için önemlidir.

Power BI’ı kuruluş içinde destekleyip yöneten ve buna ilişkin eğitim sunan iç danışmanlar olarak görev yapan bir [Mükemmeliyet Merkezi (COE)](center-of-excellence-establish.md) oluşturabilirsiniz. COE, bir iç portalda faydalı Power BI içeriği sunmadan sorumlu olabilir.

Son olarak, içerik tüketicilerine içeriğe ilişkin soruların kime iletileceğinin net olarak bildirilmesi gerekir. Bunun yanı sıra, sorunlara veya geliştirmelere ilişkin geri bildirimde bulunma yönteminin de sunulması gerekir.

## <a name="next-steps"></a>Sonraki adımlar

[Bu serinin son makalesi](powerbi-migration-learn-from-customers.md), müşteri Power BI geçişlerine ilişkin bilgileri içerir.

Diğer faydalı kaynakları da inceleyebilirsiniz:

- [Microsoft’un BI dönüşümü](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Power BI kuruluş dağıtımı planlama teknik incelemesi](https://aka.ms/PBIEnterpriseDeploymentWP)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

Deneyimli Power BI iş ortakları, kuruluşunuzun başarıyla geçiş yapmasına yardımcı olabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.