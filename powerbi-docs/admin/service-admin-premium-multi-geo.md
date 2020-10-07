---
title: Power BI Premium için Multi-Geo desteği
description: İçeriği Power BI kiracısının ana bölgesi dışındaki bölgelerde yer alan veri merkezlerine nasıl dağıtabileceğinizi öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: how-to
ms.date: 05/26/2019
LocalizationGroup: Premium
ms.openlocfilehash: 5d8841c35b2086f9a7e452cdcb4aa9a0fc4c16bd
ms.sourcegitcommit: 51b965954377884bef7af16ef3031bf10323845f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91599648"
---
# <a name="configure-multi-geo-support-for-power-bi-premium"></a>Power BI Premium için Multi-Geo desteğini yapılandırma

Multi-Geo, çok uluslu müşterilerin bölgesel, sektöre özel veya kurumsal veri yerleşimi gereksinimlerini karşılamasına yardımcı olan bir Power BI Premium özelliğidir. Bir Power BI Premium müşterisi olarak, içeriği Power BI kiracısının ana bölgesi dışındaki bölgelerde yer alan veri merkezlerine dağıtabilirsiniz. Bir coğrafi bölge (coğrafya) birden çok bölge içerebilir. Örneğin, Birleşik Devletler bir coğrafi bölgedir ve Orta Batı ABD ile Orta Güney ABD de Birleşik Devletler'deki bölgelerdir. İçeriği aşağıdaki coğrafyalardan herhangi birine dağıtmayı seçebilirsiniz:

- Amerika Birleşik Devletleri
- Kanada
- Birleşik Krallık
- Brezilya
- Avrupa
- Japonya
- Hindistan
- Asya Pasifik
- Avustralya
- Afrika

Multi-Geo Power BI Almanya, 21Vianet tarafından sağlanan Power BI Çin veya ABD hükümeti için Power BI'da sağlanmaz.

Multi-Geo artık Power BI Embedded ile de kullanılabilir. Daha fazla bilgi için bkz. [Power BI Embedded'da Multi-Geo desteği](../developer/embedded/embedded-multi-geo.md).

## <a name="enable-and-configure"></a>Etkinleştirme ve yapılandırma

Yeni kapasiteler için, açılan listeden varsayılan bölgenin dışında bir bölge seçerek Multi-Geo'yu etkinleştirin.  Kullanılabilir her kapasite, şu anda bulunduğu bölgeyi (**Orta Batı ABD**) gösterir.

![Kapasite boyutu: bölge seçin. Power BI Multi-Geo](media/service-admin-premium-multi-geo/power-bi-multi-geo-capacity-size.png)

Siz kapasiteyi oluşturduktan sonra kapasite o bölgede kalır ve oluşturulan tüm çalışma alanlarının içeriği o bölgede depolanır. Çalışma alanı ayarları ekranındaki açılan liste aracılığıyla çalışma alanlarını bir bölgeden diğerine geçirebilirsiniz.

![Çalışma alanını düzenle: Kullanılabilir bir kapasite seçin. Power BI Multi-Geo](media/service-admin-premium-multi-geo/power-bi-multi-geo-edit-workspace.png)

Değişikliği onaylamanız için bu iletiyi görürsünüz.

![Atanmış çalışma alanını değiştirme onayı](media/service-admin-premium-multi-geo/power-bi-multi-geo-change-assigned-workspace-capacity.png)

Şu anda bir geçiş sırasında ağ geçidi kimlik bilgilerini sıfırlamanız gerekmez.  Bunlar Premium kapasite bölgesinde depolandıktan sonra, geçiş sonunda bunları sıfırlamanız gerekecektir.

Geçiş sırasında, yeni veri kümelerini yayımlama veya zamanlanmış veri yenileme gibi bazı işlemler başarısız olabilir.  

Multi-Geo etkinleştirildiğinde aşağıdaki öğeler Premium bölgesinde depolanır:

- İçeri aktarma ve DirectQuery veri kümeleri için modeller (.ABF dosyaları)
- Sorgu önbelleği
- R görüntüleri

Bu öğeler kiracı için ana bölgede kalır:

- Gönderme veri kümeleri
- Excel çalışma kitapları
- Pano/rapor meta verileri: örneğin, kutucuk adları ve kutucuk sorguları
- Ağ geçidi sorguları veya zamanlanmış yenileme işleri için hizmet veri yolları
- İzinler
- Veri kümesi kimlik bilgileri



## <a name="view-capacity-regions"></a>Kapasite bölgelerini görüntüleme

Yönetici Portalı’nda, Power BI kiracınızın tüm kapasitelerini ve bunların şu anda bulundukları bölgeleri görüntüleyebilirsiniz.

![Premium kapasiteleri görüntüleme](media/service-admin-premium-multi-geo/power-bi-multi-geo-premium-capacities.png) 

## <a name="change-the-region-for-existing-content"></a>Mevcut içeriğin bölgesini değiştirme

Mevcut içeriğin bölgesini değiştirmeniz gerekiyorsa, iki seçeneğiniz vardır.

- İkinci bir kapasite oluşturun ve çalışma alanlarını taşıyın. Kiracının yedek sanal çekirdekleri olduğu sürece ücretsiz kullanıcılar herhangi bir kapalı kalma deneyimi yaşamaz.
- İkinci bir kapasite oluşturma seçeneğiniz yoksa, içeriği geçici olarak Premium'dan paylaşılan kapasiteye geri taşıyabilirsiniz. Fazladan sanal çekirdeğe ihtiyacınız olmaz ama ücretsiz kullanıcılar belirli bir kapalı kalma deneyimi yaşar.

## <a name="move-content-out-of-multi-geo"></a>İçeriği Multi-Geo'nun dışına taşıma  

Çalışma alanlarını Multi-Geo kapasitesinin dışına almak için iki yoldan birini kullanabilirsiniz:

- Çalışma alanının bulunduğu yerdeki geçerli kapasiteyi silin.  Bu işlem çalışma alanını ana bölgedeki paylaşılan kapasiteye geri taşır.
- Tek tek çalışma alanlarını geriye, ana kiracıda yer alan Premium kapasiteye geçirin.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

- Veri aktarımını başlatmadan önce bölgeler arasında başlattığınız her taşıma işleminin tüm kurumsal ve resmi uyumluluk gereksinimlerini karşıladığını onaylayın.
- Uzak bölgede depolanan ve önbelleğe alınan bir sorgu, o bölgede bekletilir. Öte yandan, taşınan diğer veriler birden çok coğrafya arasında ileri ve geri gidebilir.
- Verileri Multi-Geo ortamında bir bölgeden diğerine taşındığında, kaynak veriler bu verilerin taşındığı kaynak bölgede en çok 30 gün kalabilir. Bu süre boyunca son kullanıcıların bunlara erişimi olmaz. Veriler 30 gün boyunca bu bölgeden kaldırılır ve yok edilir.
- İçeri aktarılan veri modelleri için sorgu metni ve sorgu sonucu trafiği giriş bölgesi üzerinden aktarılmaz. Rapor meta verileri yine uzak bölgeden gelir ve bazı DNS yönlendirme durumları trafiği bölgenin dışına taşıyabilir. 

- [Veri akışları](../transform-model/service-dataflows-overview.md) özelliği şu anda Multi-Geo’da desteklenmiyor.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium nedir?](service-premium-what-is.md)
- [Power BI Embedded kapasiteleri için Multi-Geo](../developer/embedded/embedded-multi-geo.md)

Başka sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

