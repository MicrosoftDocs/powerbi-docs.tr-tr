---
title: Power BI Desktop’ta Azure Maliyet Yönetimi verilerine bağlanma
description: Power BI Desktop’ı kullanarak Azure'a kolayca bağlanma ve maliyet yönetimiyle ilgili içgörüler elde etme
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/14/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1ef9deac169873d7faee33abdae9f8f38aa09c6d
ms.sourcegitcommit: 549401b0e1fad15c3603fe7f14b9494141fbb100
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72308019"
---
# <a name="connect-to-azure-cost-management-data-in-power-bi-desktop"></a>Power BI Desktop’ta Azure Maliyet Yönetimi verilerine bağlanma

Azure harcamalarınızı daha iyi anlamanıza yardımcı olan güçlü, özelleştirilmiş görselleştirmeler ve raporlar oluşturmak için Power BI Desktop için Azure Maliyet Yönetimi bağlayıcısını kullanabilirsiniz. Azure Maliyet Yönetimi bağlayıcısı şu anda [Microsoft Müşteri Sözleşmesi](https://azure.microsoft.com/pricing/purchase-options/microsoft-customer-agreement/) veya [Kurumsal Anlaşması](https://azure.microsoft.com/pricing/enterprise-agreement/) olan müşterileri destekler.  

Azure Maliyet Yönetimi bağlayıcısı, Azure’da kimlik doğrulaması için OAuth 2.0’ı kullanır. Bağlanmak istiyorsanız, Kurumsal Anlaşmalar için [Kuruluş Yöneticisi](https://docs.microsoft.com/azure/billing/billing-understand-ea-roles) hesabını veya Microsoft Müşteri Sözleşmeleri için [Faturalama hesabı sahibini](https://docs.microsoft.com/azure/billing/billing-understand-mca-roles) kullanmanız gerekir. 

> [!NOTE]
> Bu bağlayıcı, önceden kullanılabilir olan [Azure Maliyet Yönetimi (Beta)](desktop-connect-azure-consumption-insights.md) bağlayıcısının yerini alır. Önceki bağlayıcı ile oluşturulan raporlar, bu bağlayıcı kullanılarak yeniden oluşturulmalıdır.

## <a name="connect-using-azure-cost-management"></a>Azure Maliyet Yönetimi’ni kullanarak bağlanma

Power BI Desktop’ta **Azure Maliyet Yönetimi bağlayıcısını** kullanmak için:

1.  **Giriş** şeridinde **Veri Al**’ı seçin.
2.  Veri kategorileri listesinden **Azure**’ı seçin.
3.  **Azure Maliyet Yönetimi**’ni seçin.

    ![Veri al](media/desktop-connect-azure-cost-management/azure-cost-management-00b.png)

4. Görüntülenen iletişim kutusunda, **Microsoft Müşteri Sözleşmeleri** için **Faturalama Profili Kimliği** bilginizi veya **Kurumsal Anlaşma** için **Kayıt Numarası** bilginizi girin. 


## <a name="connect-to-a-microsoft-customer-agreement-account"></a>Microsoft Müşteri Sözleşmesi hesabına bağlanma 

Bir **Microsoft Müşteri Sözleşmesi** hesabına bağlanmak için, Azure portalından **Faturalama profili kimliğinizi** alabilirsiniz:

1.  [Azure portalında](https://portal.azure.com/) **Maliyet Yönetimi + Faturalandırma**’ya gidin.
2.  Faturalama profilinizi seçin. 
3.  Menüdeki **Ayarlar** bölümünde, kenar çubuğundan **Özellikler**’i seçin.
4.  **Faturalama profili** bölümünde **Kimlik**’i seçin. 
5.  **Kapsam Seçin** için **Faturalama Profili Kimliği**’ni seçin ve önceki adımdaki faturalama profili kimliğini yapıştırın. 
6.  Ay sayısını girip **Tamam**’ı seçin.

    ![Faturalama kimliğini alma](media/desktop-connect-azure-cost-management/azure-cost-management-01a.png)

7.  İstendiğinde, Azure kullanıcı hesabı ve parolanızla oturum açın. 


## <a name="connect-to-an-enterprise-agreement-account"></a>Kurumsal Anlaşma hesabına bağlanma

Bir Kurumsal Anlaşma (EA) hesabıyla bağlantı kurmak için, Azure portalından kayıt kimliğinizi alabilirsiniz:

1.  [Azure portalında](https://portal.azure.com/) **Maliyet Yönetimi + Faturalandırma**’ya gidin.
2.  Fatura hesabınızı seçin.
3.  **Genel Bakış** menüsünde **Faturalama hesabı kimliği**’ni kopyalayın.
4.  **Kapsam Seçin** için **Kayıt Numarası**’nı seçin ve önceki adımdaki faturalama profili kimliğini yapıştırın. 
5.  Ay sayısını girip **Tamam**’ı seçin.

    ![Faturalama kimliğini alma](media/desktop-connect-azure-cost-management/azure-cost-management-01b.png)

6.  İstendiğinde, Azure kullanıcı hesabı ve parolanızla oturum açın. 

## <a name="data-available-through-the-connector"></a>Bağlayıcı aracılığıyla kullanılabilir olan veriler

Başarıyla kimlik doğrulaması yapmanızın ardından **Gezgin** penceresi, aşağıdaki kullanılabilir veri tablolarıyla birlikte görüntülenir:



| **Tablo** | **Açıklama** |
| --- | --- |
| **Balance summary** | Kurumsal Anlaşmalar için bakiye özeti. |
| **Faturalama olayları** | Yeni faturalar, kredi satın almaları vb. için olay günlüğü. Yalnızca Microsoft Müşteri Sözleşmesi. |
| **Budgets** | Mevcut bütçe hedeflerine göre gerçek maliyetleri ve kullanımı görüntülemek için bütçe ayrıntıları. |
| **Charges** | Azure kullanımı, Market ücretleri ve ayrı faturalanan ücretlerin ay bazında özeti. Yalnızca Microsoft Müşteri Sözleşmesi. |
| **Credit lots** | Belirtilen faturalama profili için Azure kredi lot satın alma ayrıntıları. Yalnızca Microsoft Müşteri Sözleşmesi. |
| **Pricesheets** | Sağlanan faturalama profili veya Kurumsal Anlaşma kaydı için geçerli ölçüm ücretleri. |
| **RI charges** | Son 24 ayda Ayrılmış Örneklerinizle ilişkili ücretler. |
| **RI recommendations (shared)** | Son 7, 30 veya 60 günde tüm aboneliklerinizdeki kullanım eğilimlerinden yola çıkarak Ayrılmış Örnek için satın alma önerileri. |
| **RI recommendations (single)** | Son 7, 30 veya 60 günde tek bir aboneliğinizdeki kullanım eğilimlerinden yola çıkarak Ayrılmış Örnek için satın alma önerileri. |
| **RI usage details** | Mevcut Ayrılmış Örneklerinizin geçen ayki tüketim ayrıntıları. |
| **RI usage summary** | Günlük Azure rezervasyon kullanım yüzdesi. |
| **Usage details** | Kurumsal Anlaşma kaydında belirtilen faturalama profilinin tüketilen miktar ve tahmini ücretlerinin dökümü. |
| **İtfa edilen kullanım ayrıntıları** | Kurumsal Anlaşma kaydında belirtilen faturalama profilinin tüketilen miktar ve tahmini itfa edilen ücretlerinin dökümü. |

Önizleme iletişim kutusunu görmek için bir tablo seçebilirsiniz. Tablo adlarının yanlarında bulunan kutuları seçerek bir veya daha fazla tablo seçebilir ve ardından **Yükle** seçeneğini belirleyebilirsiniz.

![Faturalama kimliğini alma](media/desktop-connect-azure-cost-management/azure-cost-management-01c.png)

**Yükle**’yi seçtiğinizde veriler Power BI Desktop’a yüklenir. 

Seçtiğiniz veriler yüklendiğinde, veri tabloları ve alanları **Alanlar** bölmesinde gösterilir.


## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop’ı kullanarak birçok farklı veri kaynağına bağlanabilirsiniz. Daha fazla bilgi için aşağıdaki makaleleri inceleyin:

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   