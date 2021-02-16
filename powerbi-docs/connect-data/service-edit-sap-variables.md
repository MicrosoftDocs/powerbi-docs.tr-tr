---
title: Power BI hizmetinde SAP değişkenlerini düzenleme
description: Azure ve Power BI
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: conceptual
ms.date: 02/05/2021
LocalizationGroup: Data from databases
ms.openlocfilehash: 1451b6812e9304eb1933de6cde2ed3cc681b7207
ms.sourcegitcommit: 00e3eb2ec4f18d48a73cfd020bb42d08e859ad06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2021
ms.locfileid: "100531919"
---
# <a name="edit-sap-variables-in-the-power-bi-service"></a>Power BI hizmetinde SAP değişkenlerini düzenleme

Rapor yazarları DirectQuery ile SAP Business Warehouse veya SAP HANA'yı kullanırken artık son kullanıcıların Premium ve paylaşılan çalışma alanları için **Power BI Hizmeti**'nde SAP değişkenlerini düzenlemesine izin verebilir. Bu özelliğin Çalışma Alanım sayfasının Benimle paylaşılan sekmesindeki ve V1 Çalışma Alanlarından oluşturulan Uygulamalardaki raporlar için ÇALIŞMADIĞINI unutmayın. 

![Değişkenleri düzenle iletişim kutusu](media/service-edit-sap-variables/sap-edit-variables-dialog.png)

Bu belgede Power BI'da değişkenleri düzenlemek için nelerin gerektiği, bu özelliğin nasıl etkinleştirileceği ve Power BI hizmetinde değişkenlerin nerede düzenlendiği konuları açıklanır.

## <a name="requirements-for-sap-edit-variables"></a>SAP değişkenleri düzenleme gereksinimleri

SAP değişkenleri düzenleme özelliğini kullanmak için birkaç gereksinim karşılanmalıdır. Aşağıdaki listede bu gereksinimlere yer verilmiştir.

**DirectQuery bağlantıları gerekli** – SAP veri kaynağına DirectQuery kullanarak bağlanmalısınız. İçeri Aktarma bağlantıları desteklenmez.

**SSO kurulumu gerekli** – bu özelliğin çalışması için çoklu oturum açma (SSO) yapılandırılmalıdır. Daha fazla bilgi için [çoklu oturum açmaya (SSO) genel bakış](service-gateway-sso-overview.md) konusuna bakın.

**Yeni Ağ Geçidi bitleri gerekli** - En son ağ geçidini indirin ve mevcut ağ geçidinizi güncelleştirin. Daha fazla bilgi için [hizmet ağ geçidi](service-gateway-onprem.md) konusuna bakın.

**SAP HANA için yalnızca çok boyutlu** – SAP HANA için, SAP değişkenleri düzenleme özelliği yalnızca çok boyutlu modellerde çalışır; ilişkisel kaynaklarda çalışmaz.

**Bağımsız bulutlarda desteklenmez** – Şu anda Bağımsız bulutlarda Power Query Online yoktur ve Bağımsız bulutlarda bu özellik de desteklenmez.

## <a name="how-to-enable-the-feature"></a>Özelliği etkinleştirme

**SAP değişkenleri düzenleme** özelliğini etkinleştirmek için Power BI Desktop'ta SAP HANA veya SAP BW veri kaynağına bağlanın. Ardından **Dosya > Seçenekler ve ayarlar > Seçenekler**'e gidin ve sol bölmedeki Geçerli Dosya bölümünde **DirectQuery**'yi seçin. Bunu seçtiğinizde, aşağıdaki resimde gösterildiği gibi sağ bölmede DirectQuery seçeneklerini ve seçebileceğiniz **Son kullanıcıların rapordaki SAP değişkenlerini değiştirmesine izin ver** onay kutusunu görürsünüz.

![DirectQuery seçenekleri](media/service-edit-sap-variables/sap-preview-setting-in-desktop.png)

## <a name="use-sap-edit-variables-in-power-bi-desktop"></a>Power BI Desktop'ta SAP değişkenleri düzenleme özelliğini kullanma

Power BI Desktop'ta SAP değişkenleri düzenleme özelliğini kullanırken, şeritteki **Sorguları Düzenle** menüsünden Değişkenleri düzenle bağlantısını seçerek değişkenleri düzenleyebilirsiniz. Orada aşağıdaki iletişim kutusu görüntülenir. Bu özellik Power BI Desktop'ta bir süre için kullanılabilir. Rapor oluşturucuları aşağıdaki iletişim kutusunu kullanarak rapor için değişkenleri seçebilir.

![Öğeleri Ekle](media/service-edit-sap-variables/sap-variables-add-items.png)

## <a name="use-sap-edit-variables-in-the-service"></a>Hizmette SAP değişkenleri düzenleme özelliğini kullanma

Rapor Power BI hizmetine yayımlandıktan sonra kullanıcılar yeni Filtre bölmesinde **Değişkenleri düzenle** bağlantısını görebilir. Raporu ilk kez yayımlıyorsanız Değişkenleri düzenle bağlantısının görüntülenmesi 5 dakika kadar sürebilir. Bağlantı görüntülenmezse veri kümesini el ile yenilemeniz gerekecektir.
Bunu şu yolla yapabilirsiniz:

1. Power BI hizmetinde, çalışma alanına ilişkin içerik listesinden **Veri Kümeleri** sekmesini seçin.

2. Yenilemeniz gereken veri kümesini bulun ve **Yenile** simgesini seçin.

    ![Değişkenleri düzenle](media/service-edit-sap-variables/sap-edit-variables-link.png)

3. Değişkenleri düzenle bağlantısının seçilmesi **Değişkenleri düzenle** iletişim kutusunu açar ve kullanıcılar burada değişkenleri geçersiz kılabilir. **Sıfırla** düğmesinin seçilmesi değişkenleri iletişim kutusu açıldığında görüntülenen ilk değerlerine sıfırlar.

    ![Değişkenleri düzenle iletişim kutusu](media/service-edit-sap-variables/sap-edit-variables-dialog.png)

4. **Değişkenleri düzenle** iletişim kutusunda yapılan tüm değişiklikler yalnızca bu kullanıcı için kalıcı olur (Power BI'daki diğer kalıcılık davranışlarına benzer biçimde). Aşağıdaki resimde gösterilen **Varsayılana sıfırla**'nın seçilmesi, raporu değişkenler de dahil olmak üzere rapor oluşturucusunun özgün durumuna sıfırlar.

    ![Varsayılana sıfırla](media/service-edit-sap-variables/reset-to-default.png)

SAP HANA veya SAP BW kullanan **Değişkenleri düzenle** özelliğinin etkinleştirildiği Power BI hizmetinde yayımlanmış raporla çalışırken, rapor sahibi bu varsayılan ayarları değiştirebilir. Raporun sahibi düzenleme modunda değişkenleri değiştirebilir ve söz konusu ayarların bu raporda *yeni varsayılan ayarlara* dönüşmesini sağlamak için raporu kaydedebilir. Rapor sahibi tarafından bu tür bir değişiklik yapıldıktan sonra rapora erişen diğer tüm kullanıcılar varsayılan ayarlar olarak bu yeni ayarları görür.

## <a name="next-steps"></a>Sonraki adımlar

SAP HANA, SAP BW veya DirectQuery hakkında daha fazla bilgi için aşağıdaki makaleleri okuyun:

- [Power BI Desktop'ta SAP HANA Kullanma](desktop-sap-hana.md)
- [DirectQuery ve SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
- [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
- [Power BI'da DirectQuery kullanma](desktop-directquery-about.md)
