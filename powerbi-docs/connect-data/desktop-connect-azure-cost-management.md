---
title: Power BI Desktop’ta Azure Maliyet Yönetimi verilerine bağlanma
description: Power BI Desktop ile Azure'a kolayca bağlanın ve Azure maliyeti ile kullanımınız hakkında içgörüler edinin
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 12/10/2020
LocalizationGroup: Connect to data
ms.openlocfilehash: 6d99e91657d0c5f0bbd1e9c665f00d16c34ba24f
ms.sourcegitcommit: 772c65b7b440ab082510bf3f64b871d19139d451
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2020
ms.locfileid: "97353255"
---
# <a name="create-visuals-and-reports-with-the-azure-cost-management-connector-in-power-bi-desktop"></a>Power BI Desktop'ta Azure Maliyet Yönetimi bağlayıcısı ile görseller ve raporlar oluşturma

Azure harcamalarınızı daha iyi anlamanıza yardımcı olan güçlü, özelleştirilmiş görselleştirmeler ve raporlar oluşturmak için Power BI Desktop için Azure Maliyet Yönetimi bağlayıcısını kullanabilirsiniz. Azure Maliyet Yönetimi bağlayıcısı şu anda [Microsoft Müşteri Sözleşmesi](https://azure.microsoft.com/pricing/purchase-options/microsoft-customer-agreement/) veya [Kurumsal Anlaşması](https://azure.microsoft.com/pricing/enterprise-agreement/) olan müşterileri destekler.  

Azure Maliyet Yönetimi bağlayıcısı, Azure’da kimlik doğrulaması için OAuth 2.0 kullanır ve bağlayıcıyı kullanacak kullanıcıları tanımlar. Bu işlemde oluşturulan belirteçler belirli bir süre için geçerlidir. Power BI sonraki oturum açma için belirteci saklar. OAuth 2.0, bu izinlerin güvenli bir şekilde işlenmesini sağlamak için arka planda devam eden işlemin standardıdır. Bağlanmak istiyorsanız, Kurumsal Anlaşmalar için [Kuruluş Yöneticisi](/azure/billing/billing-understand-ea-roles) hesabını veya Microsoft Müşteri Sözleşmeleri için [Faturalama hesabı sahibini](/azure/billing/billing-understand-mca-roles) kullanmanız gerekir. 

> [!NOTE]
> Bu bağlayıcı, önceden kullanılabilir olan [Azure Consumption Insights ve Azure Maliyet Yönetimi (Beta)](desktop-connect-azure-consumption-insights.md) bağlayıcılarının yerini alır. Önceki bağlayıcı ile oluşturulan raporların bu bağlayıcı kullanılarak yeniden oluşturulması gerekir.

> [!NOTE]
> Power BI Desktop için Azure Maliyet Yönetimi bağlayıcısı, kamu bulutlarına bağlanmayı desteklemez. 


## <a name="connect-using-azure-cost-management"></a>Azure Maliyet Yönetimi’ni kullanarak bağlanma

Power BI Desktop’ta **Azure Maliyet Yönetimi bağlayıcısını** kullanmak için:

1.  **Giriş** şeridinde **Veri Al**’ı seçin.
2.  Veri kategorileri listesinden **Azure**'ı seçin.
3.  **Azure Maliyet Yönetimi**’ni seçin.

    ![Verileri alma](media/desktop-connect-azure-cost-management/azure-cost-management-00b.png)

4. Görüntülenen iletişim kutusunda, **Microsoft Müşteri Sözleşmeleri** için **Faturalama Profili Kimliği** bilginizi veya **Kurumsal Anlaşma** için **Kayıt Numarası** bilginizi girin. 


## <a name="connect-to-a-microsoft-customer-agreement-account"></a>Microsoft Müşteri Sözleşmesi hesabına bağlanma 

Bir **Microsoft Müşteri Sözleşmesi** hesabına bağlanmak için, Azure portalından **Faturalama profili kimliğinizi** alabilirsiniz:

1.  [Azure portalında](https://portal.azure.com/)**Maliyet Yönetimi + Faturalandırma**’ya gidin.
2.  Faturalama profilinizi seçin. 
3.  Menüdeki **Ayarlar** bölümünde, kenar çubuğundan **Özellikler**’i seçin.
4.  **Faturalama profili** bölümünde **Kimlik**’i seçin. 
5.  **Kapsam Seçin** için **Faturalama Profili Kimliği**’ni seçin ve önceki adımdaki faturalama profili kimliğini yapıştırın. 
6.  Ay sayısını girip **Tamam**’ı seçin.

    ![Faturalama Profili Kimliği kapsamındaki Azure Maliyet Yönetimi özelliklerini gösteren ekran görüntüsü.](media/desktop-connect-azure-cost-management/azure-cost-management-01a.png)

7.  İstendiğinde, Azure kullanıcı hesabı ve parolanızla oturum açın. Erişimin başarılı olması için bir Fatura hesabı kullanmalısınız. 


## <a name="connect-to-an-enterprise-agreement-account"></a>Kurumsal Anlaşma hesabına bağlanma

Bir Kurumsal Anlaşma (EA) hesabıyla bağlantı kurmak için, Azure portalından kayıt kimliğinizi alabilirsiniz:

1.  [Azure portalında](https://portal.azure.com/)**Maliyet Yönetimi + Faturalandırma**’ya gidin.
2.  Fatura hesabınızı seçin.
3.  **Genel Bakış** menüsünde **Faturalama hesabı kimliği**’ni kopyalayın.
4.  **Kapsam Seçin** için **Kayıt Numarası**’nı seçin ve önceki adımdaki faturalama profili kimliğini yapıştırın. 
5.  Ay sayısını girip **Tamam**’ı seçin.

    ![Kayıt Numarası kapsamındaki Azure Maliyet Yönetimi özelliklerini gösteren ekran görüntüsü.](media/desktop-connect-azure-cost-management/azure-cost-management-01b.png)

6.  İstendiğinde, Azure kullanıcı hesabı ve parolanızla oturum açın. Kurumsal Anlaşmalar için Kurumsal Yönetici hesabı kullanmalısınız.

## <a name="data-available-through-the-connector"></a>Bağlayıcı aracılığıyla kullanılabilir olan veriler

Başarıyla kimlik doğrulaması yapmanızın ardından **Gezgin** penceresi, aşağıdaki kullanılabilir veri tablolarıyla birlikte görüntülenir:

| **Tablo** | **Açıklama** |
| --- | --- |
| **Bakiye özeti** | Kurumsal Anlaşmalar için bakiye özeti. |
| **Faturalama olayları** | Yeni faturalar, kredi satın almaları vb. için olay günlüğü. Yalnızca Microsoft Müşteri Sözleşmesi. |
| **Budgets** | Mevcut bütçe hedeflerine göre gerçek maliyetleri ve kullanımı görüntülemek için bütçe ayrıntıları. |
| **Ücretler** | Azure kullanımı, Market ücretleri ve ayrı faturalanan ücretlerin ay bazında özeti. Yalnızca Microsoft Müşteri Sözleşmesi. |
| **Credit lots** | Belirtilen faturalama profili için Azure kredi lot satın alma ayrıntıları. Yalnızca Microsoft Müşteri Sözleşmesi. |
| **Fiyat listeleri** | Belirtilen faturalama profili veya EA kaydı için geçerli ölçüm ücretleri. |
| **RI ücretleri** | Son 24 ayda Ayrılmış Örneklerinizle ilişkili ücretler. |
| **RI önerileri (paylaşılan)** | Son 7, 30 veya 60 günde tüm aboneliklerinizdeki kullanım eğilimlerinden yola çıkarak Ayrılmış Örnek için satın alma önerileri. |
| **RI önerileri (tek)** | Son 7, 30 veya 60 günde tek bir aboneliğinizdeki kullanım eğilimlerinden yola çıkarak Ayrılmış Örnek için satın alma önerileri. |
| **RI kullanım ayrıntıları** | Mevcut Ayrılmış Örneklerinizin geçen ayki tüketim ayrıntıları. |
| **RI kullanım özeti** | Günlük Azure rezervasyonu kullanım yüzdesi. |
| **Kullanım ayrıntıları** | Kurumsal Anlaşma kaydında belirtilen faturalama profilinin tüketilen miktar ve tahmini ücretlerinin dökümü. |
| **Amorti edilmiş kullanım ayrıntıları** | Kurumsal Anlaşma kaydında belirtilen faturalama profilinin tüketilen miktar ve tahmini itfa edilen ücretlerinin dökümü. |

Önizleme iletişim kutusunu görmek için bir tablo seçebilirsiniz. Tablo adlarının yanlarında bulunan kutuları seçerek bir veya daha fazla tablo seçebilir ve ardından **Yükle** seçeneğini belirleyebilirsiniz.

![Gezgin iletişim kutusunu gösteren ekran görüntüsü.](media/desktop-connect-azure-cost-management/azure-cost-management-01c.png)

**Yükle**’yi seçtiğinizde veriler Power BI Desktop’a yüklenir. 

Seçtiğiniz veriler yüklendiğinde, veri tabloları ve alanları **Alanlar** bölmesinde gösterilir.


## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop’ı kullanarak birçok farklı veri kaynağına bağlanabilirsiniz. Daha fazla bilgi için aşağıdaki makaleleri inceleyin:

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop'taki veri kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)