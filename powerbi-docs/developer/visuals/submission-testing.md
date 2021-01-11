---
title: Daha iyi tümleşik BI içgörüleri için Power BI tümleşik analizlerindeki Power BI görsellerinin gönderim testleri
description: Bu makalede, AppSource’ta yayımlanmadan önce görselinizin geçmesi gereken test çalışmaları açıklanır. İsteğe bağlı test çalışmaları da vardır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 04/15/2020
ms.openlocfilehash: b5054d821dc797f1606fea8ec5d0bb43569a57e5
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888478"
---
# <a name="submission-testing-of-a-power-bi-visual"></a>Bir Power BI görselinin gönderim testi

Görselinizin [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)’da yayımlanmadan önce bu makalede listelenen testleri geçmesi gerekir. Göndermeden önce görselinizi test edin. Görseliniz gerekli test çalışmalarını geçemezse reddedilir.

Yayımlama süreci hakkında daha fazla bilgi için bkz. [Power BI görsellerini İş Ortağı Merkezi’nde yayımlama](./office-store.md).

## <a name="testing-a-new-version-of-a-published-visual"></a>Yayımlanmış bir görselin yeni sürümünü test etme

Önceden yayımlanmış bir görselin yeni sürümünü test ediyor veya hata ayıklama çalışması yapıyorsanız Power BI Desktop'ta Geliştirici modunu etkinleştirerek yerel dosya sürümüyle AppSource sürümünü geçersiz kılabilirsiniz.

Geliştirici modunu etkinleştirmek için şu adımları izleyin:

1. Power BI Desktop'ı açın.

2.  **Dosya** > **Seçenekler ve ayarlar**'ı seçin.

3.  **Seçenekler**'i belirleyin.

4. Seçenekler penceresindeki GEÇERLİ DOSYA listesinde **Rapor ayarları**'nı seçin.

5. Geliştirici Modu bölümünde **Bu oturum için geliştirici modunu aç**'ı seçin.

>[!NOTE]
>Power BI Desktop'ta Geliştirici modu yalnızca bir oturum için geçerlidir. Test için yeni bir Power BI Desktop örneği açarsanız Geliştirici modunu yeniden etkinleştirmeniz gerekir.

## <a name="general-test-cases"></a>Genel test çalışmaları

Görselinizin genel test çalışmalarını geçtiğini doğrulayın.

| Test çalışması | Beklenen sonuçlar
| --------- | ----------------
| **Kategori** ve **Değer** içeren bir **Yığılmış sütun grafiği** oluşturun. Bu grafiği görselinize dönüştürün ve sonra yeniden sütun grafiğine dönüştürün. | Bu dönüştürme işlemlerinden sonra hata görünmüyor. |
| Üç ölçüye sahip bir **Ölçer** oluşturun. Bunu görselinize dönüştürün ve sonra yeniden **Ölçere** dönüştürün. | Bu dönüştürme işlemlerinden sonra hata görünmüyor. |
| Görselinizde seçimler yapın. | Diğer görseller seçimleri yansıtıyor. |
| Diğer görsellerdeki öğeleri seçin. | Görseliniz, filtrelenmiş verileri diğer görsellerdeki seçime göre gösterir. |
| Min/Maks **dataViewMapping** koşullarını denetleyin. | Alan demetleri birden çok alanı veya tek bir alanı kabul edebilir ya da diğer demetler tarafından belirlenir. Min/Maks **dataViewMapping** koşullarının, görselinizin özelliklerinde doğru bir şekilde ayarlanması gerekir. |
| Farklı sıralardaki tüm alanları kaldırın. | Alanlar rastgele bir sırada kaldırıldıklarından görseller doğru şekilde temizleniyor. Konsolda veya tarayıcıda hata yok. |
| Her olası demet yapılandırmasıyla **Biçim** bölmesi açılır. | Bu test, null başvuru özel durumlarını tetiklemez. |
| Görsel, sayfa ve rapor düzeyindeki **Filtre** bölmesini kullanarak verileri filtreleyin. | Filtreler uygulandıktan sonra araç ipuçları doğru görünüyor. Araç ipuçları filtrelenmiş değeri gösterir. |
| **Dilimleyici** kullanarak verileri filtreleyin. | Filtreler uygulandıktan sonra araç ipuçları doğru görünüyor. Araç ipuçları filtrelenmiş değeri gösterir. |
| Yayımlanan görseli kullanarak verileri filtreleyin. Örneğin, bir pasta dilimi grafiği veya bir sütun grafiği seçin. | Filtreler uygulandıktan sonra araç ipuçları doğru görünüyor. Araç ipuçları filtrelenmiş değeri gösterir. |
| Çapraz filtreleme destekleniyorsa filtrelerin doğru çalıştığını onaylayın. | Uygulanan seçim, raporun bu sayfasındaki diğer görselleri filtreler. |
| Ctrl, Alt ve Shift tuşlarıyla seçin. | Beklenmeyen bir davranış oluşmadı. |
| **Görünüm Modu**’nu **Gerçek boyut**, **Sayfaya sığdır** veya **Genişliğe sığdır** olarak değiştirin. | Fare koordinatları doğru. |
| Görselinizi yeniden boyutlandırın. | Görsel, yeniden boyutlandırma işlemine doğru şekilde tepki veriyor. |
| Rapor boyutunu en düşük olarak ayarlayın. | Görüntüleme hatası yok. |
| Kaydırma çubuklarının doğru çalıştığından emin olun. | Gerekli durumlarda kaydırma çubukları olmalıdır. Kaydırma çubuğu boyutlarını denetleyin. Kaydırma çubukları çok geniş veya uzun olamaz. Kaydırma çubuklarının konumu ve boyutu, görselinizin diğer öğeleriyle uyumlu olmalıdır. Görselin farklı boyutları için kaydırma çubuklarının gerekli olduğunu doğrulayın. |
| Görselinizi bir **Panoya** sabitleyin. | Görsel doğru şekilde görüntülenmelidir. |
| Görselin birden çok sürümünü tek bir rapor sayfasına ekleyin. | Görselin tüm sürümleri düzgün şekilde görüntülenip çalışmalıdır. |
| Görselin birden çok sürümünü birden çok rapor sayfasına ekleyin. | Görselin tüm sürümleri düzgün şekilde görüntülenip çalışmalıdır. |
| Rapor sayfaları arasında geçiş yapın. | Görsel doğru şekilde görüntüleniyor. |
| Görselinizin Okuma ve Düzenleme görünümlerini test edin. | Tüm işlevler doğru şekilde çalışıyor. |
| Görselinizde animasyonlar kullanıyorsanız görselinizin öğelerini ekleyin, değiştirin veya silin. | Görsel öğelerin animasyonu doğru şekilde çalışıyor. |
| **Özellik** bölmesini açın. Özellikleri açıp kapatın, özel metin girin, kullanılabilir seçenekleri test edin ve hatalı veriler girin. | Görsel doğru şekilde yanıt veriyor. |
| Raporu kaydedip yeniden açın. | Tüm özellikler ayarları korunuyor. |
| Rapordaki sayfaları değiştirin ve sonra geri alın. | Tüm özellikler ayarları korunuyor. |
| Görselin sağladığı farklı seçenekler de dahil olmak üzere görselinizdeki tüm işlevleri test edin. | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Aşağıdaki testlerde olduğu gibi tüm sayısal, tarih ve karakter veri türlerini test edin. | Tüm veriler düzgün şekilde biçimlendirilmiş. |
| Araç ipucu değerlerinin biçimlendirmesini, eksen etiketlerini ve biçimlendirmeye sahip diğer görsel öğeleri gözden geçirin. | Tüm öğeler düzgün şekilde biçimlendirilmiş. |
| Veri etiketlerinin biçim dizesini kullandığını doğrulayın. | Tüm veri etiketleri doğru şekilde biçimlendirilmiş. |
| Araç ipuçlarındaki sayısal değerlerin otomatik biçimlendirmesini açıp kapatın. | Araç ipuçları, değerleri doğru şekilde görüntülüyor. |
| Veri girişlerini sayısal, metin, tarih-saat ve modeldeki farklı biçim dizeleri gibi farklı veri türleriyle test edin. Binlerce satır, tek bir satır veya iki satır gibi farklı veri birimlerini test edin. | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Görselinize null, sonsuz, negatif değer ve hatalı değer türleri gibi kötü veriler sağlayın. | Tüm ekranlar ve özellikler doğru çalışıyor. |

## <a name="optional-browser-testing"></a>İsteğe bağlı tarayıcı testi

AppSource ekibi, görseli Google Chrome, Microsoft Edge ve Mozilla Firefox tarayıcılarının en güncel Windows sürümlerinde doğrular.
İsteğe bağlı olarak görselinizi aşağıdaki tarayıcılarla test edin.

| Test çalışması | Beklenen sonuçlar
| --------- | ----------------
| **Windows** |
| Google Chrome (önceki sürüm) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Mozilla Firefox (önceki sürüm) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Microsoft Edge (önceki sürüm) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Microsoft Internet Explorer 11 (isteğe bağlı) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| **macOS** |
| Chrome (önceki sürüm) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Firefox (önceki sürüm) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Safari (önceki sürüm) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| **Linux** |
| Firefox (en son sürüm ve önceki sürümler) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| **Mobil iOS** |
| Apple Safari iPad (önceki Safari sürümü) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Chrome iPad (en son Safari sürümü) | Tüm ekranlar ve özellikler doğru çalışıyor. |
| **Mobil Android** |
| Chrome (en son sürüm ve önceki sürümler) | Tüm ekranlar ve özellikler doğru çalışıyor. |

## <a name="desktop-testing"></a>Masaüstü testi

Görselinizi [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/)’ın güncel sürümünde test edin.

| Test çalışması | Beklenen sonuçlar
| --------- | ----------------
| Görselinizin tüm özelliklerini test edin. | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Power BI Desktop’taki **Yayımla** düğmesini kullanarak bir dosyayı Power BI hizmetine içeri aktarın, kaydedin, burada açın ve yayımlayın. | Tüm ekranlar ve özellikler doğru çalışıyor. |
| Duyarlığı artırıp azaltarak sayısal biçim dizesini ondalık basamağa sahip olmayacak veya üç ondalık basamağa sahip olacak şekilde değiştirin. | Görsel doğru şekilde görüntüleniyor. |

## <a name="performance-testing"></a>Performansı test etme

Görselinizin kabul edilebilir bir düzeyde çalışması gerekir. Görselin performansını doğrulamak için geliştirici araçlarını kullanın. Görsel ipuçlarına ve konsol zaman günlüklerine güvenmeyin.

| Test çalışması | Beklenen sonuçlar
| --------- | ----------------
| Çok sayıda görsel öğeye sahip bir görsel oluşturun. | Görselin iyi bir şekilde çalışması ve uygulamayı dondurmaması gerekir. Öğelerde animasyon hızı, yeniden boyutlandırma, filtreleme ve seçme gibi performans sorunlarının olmaması gerekir.

## <a name="next-steps"></a>Sonraki adımlar

Yayımlama süreci hakkında daha fazla bilgi için bkz. [Power BI görsellerini İş Ortağı Merkezi’nde yayımlama](./office-store.md).

Başka bir sorunuz mu var? [Power BI Topluluğu’na sorun](https://community.powerbi.com/).
