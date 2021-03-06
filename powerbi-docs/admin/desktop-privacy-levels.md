---
title: Power BI Desktop'taki gizlilik düzeylerini anlama
description: Power BI Desktop gizlilik düzeyleri
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: reference
ms.date: 09/09/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: 7dc5554844bafac1f8877ef7e2e8627d8078e981
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96386824"
---
# <a name="power-bi-desktop-privacy-levels"></a>Power BI Desktop gizlilik düzeyleri
**Power BI Desktop**'ta gizlilik düzeyleri, bir veri kaynağının diğer veri kaynaklarından ne ölçüde yalıtılacağını tanımlayan bir yalıtım düzeyi belirtir. Kısıtlayıcı bir yalıtım düzeyi bilgilerin veri kaynakları arasında paylaşılmasını engellese de işlevselliği azaltabilir ve performansı etkileyebilir.

**Dosya > Seçenekler ve ayarlar > Seçenekler** yoluna gidildiğinde ve ardından **Geçerli Dosya > Gizlilik**'e ulaşıldığında görüntülenebilen **Gizlilik Düzeyleri** ayarı, Power BI Desktop'ın verileri birleştirirken Gizlilik Düzeyi ayarınızı kullanıp kullanmadığını belirler. Bu iletişim kutusunda, Gizlilik Düzeyleri hakkındaki bir Power BI Desktop belgesine (bu makale) yönelik bir bağlantı bulunur.

![Seçenekler iletişim kutusunun ekran görüntüsü.](media/desktop-privacy-levels/desktop_privacylevels1.png)

## <a name="configure-a-privacy-level"></a>Gizlilik düzeyi yapılandırma
Gizlilik düzeyi ayarlarını kullanarak, bir veri kaynağının diğer veri kaynaklarından ne ölçüde yalıtılacağını tanımlayan bir yalıtım düzeyi belirtebilirsiniz.

| Ayar | Açıklama | Örnek Veri Kaynakları |
| --- | --- | --- |
| **Gizli veri kaynağı** |**Gizli** veri kaynakları gizli veya hassas bilgiler içerir ve veri kaynağının görünürlüğü yetkili kullanıcılarla sınırlandırılabilir. Gizli veri kaynakları diğer veri kaynaklarından tamamen yalıtılır. |Facebook verileri, hisse ikramiyeler içeren bir metin dosyası veya çalışan inceleme bilgilerinin bulunduğu bir çalışma kitabı. |
| **Kuruluş veri kaynağı** |**Kuruluş** veri kaynakları bir veri kaynağının görünürlüğünü güvenilen bir grup kullanıcıyla sınırlar. **Kuruluş** veri kaynakları tüm **Genel** veri kaynaklarından yalıtılır ancak diğer **Kuruluş** veri kaynaklarından yalıtılmaz. |İzinlerin güvenilen bir grup için etkinleştirildiği, intranet SharePoint sitesindeki bir **Microsoft Word** belgesi. |
| **Genel veri kaynağı** |**Genel** veri kaynaklarında bulunan veriler herkes tarafından görülebilir. Yalnızca dosyalar, internet veri kaynakları veya çalışma kitabı verileri **Genel** olarak işaretlenebilir. |Microsoft Azure Market’teki ücretsiz veriler, Wikipedia sayfalarındaki veriler veya bir web sayfasından kopyalanmış veriler içeren yerel bir dosya. |

## <a name="configure-privacy-level-settings"></a>Gizlilik düzeyi ayarlarını yapılandırma
Her bir veri kaynağına ilişkin **Gizlilik** ayarları iletişim kutusuna **Dosya > Seçenekler ve ayarlar > Veri kaynağı ayarları** yolunu izleyerek de ulaşabilirsiniz.

Bir veri kaynağı gizlilik düzeyi yapılandırmak için, veri kaynağını seçin ve **Düzenle** seçeneğini belirleyin. Aşağıdaki görüntüde gösterildiği gibi, alt kısmındaki açılan menüden uygun gizlilik düzeyini seçebileceğiniz **Veri Kaynağı Ayarları** iletişim kutusu görüntülenir.

![Veri Kaynağı Ayarları iletişim kutusunun ekran görüntüsü.](media/desktop-privacy-levels/desktop_privacylevels2.png)

> [!CAUTION]
> Yüksek düzeyde gizli veya hassas veriler içeren veri kaynaklarını **Gizli** olarak yapılandırmanız gerekir.
> 

## <a name="configure-privacy-levels"></a>Gizlilik Düzeylerini yapılandırma
Varsayılan olarak **Gizlilik Düzeyleri** için **Her kaynak için verileri Gizlilik Düzeyi ayarlarınıza göre birleştirin** ayarı belirlenir ve bu, **Gizlilik Düzeyleri**'nin zorunlu tutulduğunu gösterir.

| Ayar | Açıklama |
| --- | --- |
| **Her bir kaynak için verileri Gizlilik Düzeyi ayarlarınıza göre birleştirin** (Açıktır ve varsayılan ayardır) |Gizlilik düzeyi ayarları, veri birleştirme sırasında veri kaynakları arasındaki yalıtım düzeyini belirlemek için kullanılır. |
| **Gizlilik Düzeylerini yoksayın ve potansiyel performansı geliştirin** (kapalı) |Veriler birleştirilirken gizlilik düzeyleri hesaba katılmaz ancak verilerin performansı ve işlevselliği artabilir. |

> **Güvenlik Notu:** **Gizlilik Düzeyleri** iletişim kutusunda **Gizlilik Düzeylerini yoksayın ve potansiyel performansı geliştirin** seçeneğini belirlemek, gizli veya hassas verilerin yetkisiz bir kullanıcı tarafından görülebilmesine neden olabilir. Veri kaynağının gizli veya hassas veriler içermediğinden emin olmadığınız sürece bu ayarı *kapalı* duruma getirmeyin.
> 
> 

> [!CAUTION]
> **Gizlilik Düzeylerini yoksayın ve potansiyel performansı geliştirin** ayarı Power BI hizmetinde kullanılamaz. Aynı şekilde, bu ayarın etkin olduğu, Power BI hizmetinde yayımlanan Power BI Desktop raporları hizmette kullanıldığında bu davranışı *göstermez*.
> 

**Gizlilik Düzeylerini yapılandırma**

Power BI Desktop'ta veya Sorgu Düzenleyicisi'nde, **Dosya > Seçenekler ve ayarlar > Seçenekler** seçeneğini ve ardından **Geçerli Dosya > Gizlilik** seçeneğini belirleyin.

a. **Her bir kaynak için verileri Gizlilik Düzeyi ayarlarınıza göre birleştirin** seçili olduğunda, veriler Gizlilik Düzeyleri ayarınıza göre birleştirilir. Gizlilik yalıtım alanları arasında veri birleştirmek verilerin arabelleğe alınmasına neden olur.

b. **Gizlilik Düzeylerini yoksayın ve potansiyel performansı geliştirin** seçili olduğunda, veriler Gizlilik Düzeyleriniz yok sayılarak birleştirilir ve bu nedenle, gizli veya hassas veriler yetkisiz bir kullanıcı tarafından görülebilir. Bu ayarın belirlenmesi performansı ve işlevselliği artırabilir.

> **Güvenlik Notu:** **Gizlilik Düzeylerini yoksayın ve potansiyel performansı geliştirin** seçeneğinin belirlenmesi, performansı iyileştirebilir ancak Power BI Desktop dosyasında birleştirilen verilerin gizliliğini garanti edemez.
> 
> 

