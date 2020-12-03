---
title: Power BI Desktop’ta raporları modellerden ayırma
description: Power BI Desktop’ta raporları modellerden ayırma rehberi.
author: peter-myers
ms.author: v-pemyer
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 04/11/2020
ms.openlocfilehash: a45299015883615b4773fe5db1c9864e01a47c4b
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96418382"
---
# <a name="separate-reports-from-models-in-power-bi-desktop"></a>Power BI Desktop’ta raporları modellerden ayırma

Yeni bir Power BI Desktop çözümü oluştururken yapmanız gereken ilk görevlerden biri "veri al"dır. Veri alma işlemi, tamamen farklı iki sonuç oluşmasına neden olabilir. Şunlara yol açabilir:

- Bir Power BI veri kümesi veya uzaktan barındırılan Analysis Services modeli olabilecek, zaten yayımlanmış bir modele [Canlı Bağlantı](../connect-data/desktop-report-lifecycle-datasets.md) oluşturun.
- Bir İçeri aktarma, DirectQuery veya Bileşik model olabilecek yeni bir modelin geliştirme sürecini başlatın.

Bu makale ikinci senaryoyu ele alır. Bir raporun ve modelin tek bir Power BI Desktop dosyasında birleştirilmesi gerekip gerekmediği hakkında rehberlik sağlar.

## <a name="single-file-solution"></a>Tek dosya çözümü

_Tek dosya çözümü_, modeli temel alan yalnızca tek bir rapor olduğunda işe yarar. Bu durumda, hem modelin hem de raporun aynı kişinin çalışmaları olması olasıdır. Rapor başkalarıyla paylaşılabilmiş olsa da bunu _Kişisel BI_ çözümü olarak tanımlarız. Bu tür çözümler, rol kapsamlı raporları veya genellikle _geçici_ raporlar olarak açıklanan, iş zorluğunun tek seferlik değerlendirmelerini temsil edebilir.

:::image type="content" source="media/report-separate-from-model/single-file-solution.png" alt-text="Tek bir dosya, aynı kişi tarafından geliştirilen bir model ve rapor içerir." border="true":::

## <a name="separate-report-files"></a>Rapor dosyalarını ayırma

Şu gibi durumlarda model ve rapor geliştirmeyi farklı Power BI Desktop dosyalarına ayırmak mantıklı olur:

- Veri modelcileri ve rapor yazarları farklı kişilerdir.
- Bir modelin, şu anda veya gelecekte birden çok raporun kaynağı olduğu bilinir.

:::image type="content" source="media/report-separate-from-model/separate-report-files.png" alt-text="Üç PBIX dosyası vardır. İlki yalnızca bir model içerir. Diğer ikisi yalnızca raporlar içerir ve Power BI hizmetinde barındırılan modele canlı olarak bağlanır. Raporlar farklı kişiler tarafından geliştirilir." border="true":::

Veri modelcileri, model tasarımlarını test etmek ve doğrulamak için Power BI Desktop rapor yazma deneyimini kullanmaya devam edebilir. Ancak dosyalarını Power BI hizmetinde yayımladıktan hemen sonra, raporu çalışma alanından kaldırmaları gerekir. Ayrıca, yeniden yayımladıkları ve veri kümesinin üzerine yazdıkları her seferde raporu kaldırmayı hatırlamaları gerekir.

### <a name="preserve-the-model-interface"></a>Model arabirimini koruma

Bazen model değişiklikleri kaçınılmaz olur. Bu durumda veri modelcileri, model arabirimini kesmemeye dikkat etmelidir. Aksi takdirde, ilgili rapor görsellerinin veya pano kutucuklarının kesintiye uğraması olasıdır. Bozuk görseller hata olarak görünür ve bu durum rapor yazarlarını ve tüketicileri rahatsız edebilir. Daha da kötüsü, veriye olan güvenin azalmasına neden olabilir.

Bu nedenle model değişikliklerini dikkatle yönetin. Mümkünse, şu değişikliklerden kaçının:

- Tabloları, sütunları, hiyerarşileri, hiyerarşi düzeylerini veya ölçüleri yeniden adlandırma.
- Sütun veri türlerini değiştirme.
- Ölçü ifadelerini farklı bir veri türü döndürecek şekilde değiştirmek.
- Ölçüleri farklı bir giriş tablosuna taşımak. Bunun nedeni, bir ölçünün taşınmasının, ölçüleri kendi giriş tablosu adlarıyla tam olarak belirten rapor kapsamlı ölçülerin kesilmesini sağlayabilmesidir. Tam ölçü adlarını kullanarak DAX ifadeleri yazmanızı önermiyoruz. Daha fazla bilgi için bkz. [DAX: Sütun ve ölçü başvuruları](dax-column-measure-references.md).

Yeni tabloları, sütunları, hiyerarşileri, hiyerarşi düzeylerini veya ölçüleri eklemek, tek bir özel durum haricinde güvenlidir: Yeni bir ölçü adının rapor kapsamlı bir ölçü adıyla çakışma olasılığı vardır. Çakışmadan kaçınmak için rapor yazarlarının, raporlarında ölçüleri tanımlarken bir adlandırma kuralı benimsemesini öneririz. Rapor kapsamlı ölçü adlarının başına ön ek olarak alt çizgi veya başka karakterler koyabilirler.

Modellerinizde hataya neden olan değişiklikler yapmanız gerekiyorsa, şunlardan birini yapmanızı öneririz:

- Power BI hizmetinde [veri kümesinin ilgili içeriğini görüntüleyin](../consumer/end-user-related.md).
- Power BI hizmetinde [Veri kökeni](../collaborate-share/service-data-lineage.md) görünümünü keşfedin.

Her iki seçenek de ilgili raporları ve panoları hızlıca tanımlamanızı sağlar. İlgili her yapıt için ilgili kişiyi kolayca görebilmeniz nedeniyle veri kökeni görünümü büyük olasılıkla daha iyi bir seçimdir. Aslında bu, ilgili kişiye yönelik bir e-posta iletisi açan bir köprüdür.

İlgili her yapıtın sahibiyle iletişim kurarak, planlı hataya neden olan değişiklikleri bu kişilere bildirmenizi öneririz. Bu şekilde, raporları onarmak ve yeniden yayımlamak için hazırlanarak kapalı kalma süresini ve bunun yol açtığı rahatsızlığı en aza indirmeye yardımcı olabilirler.

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Desktop'tan Power BI hizmetindeki veri kümelerine bağlanma](../connect-data/desktop-report-lifecycle-datasets.md)
- [Power BI hizmetinde ilgili içeriği görüntüleme](../consumer/end-user-related.md)
- [Veri kökeni](../collaborate-share/service-data-lineage.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
