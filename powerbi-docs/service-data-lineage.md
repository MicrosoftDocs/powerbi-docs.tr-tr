---
title: Veri kökeni (önizleme)
description: Modern iş zekası (BI) projelerinde verilerin veri kaynağından hedefine akışı birçok müşteri için önemli güçlüklerden biridir.
author: paulinbar
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: painbar
LocalizationGroup: ''
ms.openlocfilehash: e91f1d5084957ee7266161b9a34f916e2902d1f4
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72019579"
---
# <a name="data-lineage-preview"></a>Veri kökeni (önizleme)
Modern iş zekası (BI) projelerinde verilerin veri kaynağından hedefine akışını anlamak güç olabilir. Birden çok veri kaynağına, yapıta ve bağımlılığa yayılan gelişmiş analiz projeleri oluşturduğunuzda bu güçlük daha da artar.  "Bu verileri değiştirirsem ne olur?" veya "Bu rapor neden güncel değil?" gibi soruları yanıtlamak kolay olmayabilir. Bunu anlamak için bir uzman takımı veya derin bir araştırma gerekebilir. Veri kökeni görünümünü bu soruları yanıtlamanıza yardımcı olmak için tasarladık.

[ ![Power BI köken görünümü](media/service-data-lineage/power-bi-lineage-view-cropped.png) ](media/service-data-lineage/power-bi-lineage-view-full-size.png#lightbox)
 
Power BI'da panolar, raporlar, veri kümeleri ve veri akışları gibi çeşitli yapıt türleri vardır. Birçok veri kümesi ve veri akışı SQL Server gibi dış veri kaynaklarına ve diğer çalışma alanlarındaki dış veri kümelerine bağlanır. Bir veri kümesi sahip olduğunuz çalışma alanının dışındaysa, BT'deki birine veya başka bir analiste ait veri kümesinde olabilir. Dış veri kaynakları ve veri kümeleri verilerin nihai olarak nereden geldiğini bilmeyi zorlaştırır. Hem karmaşık projeler hem de daha basit olanlar için köken görünümünü sunuyoruz. 

Köken görünümünde çalışma alanında yer alan tüm yapıtlar arasındaki köken ilişkilerini ve çalışma alanının tüm dış bağımlılıklarını görürsünüz. Veri akışlarının zaten bir diyagram görünümü vardı ve köken görünümü de o görünümü genişletir. Hem yukarı hem de aşağı doğru akan veri akışlarıyla bağlantılar da dahil olmak üzere tüm çalışma alanı yapıtları arasındaki bağlantıları gösterir. Ayrı veri akışları diyagramı görünümü Kasım'dan başlayarak kaldırılacaktır.

## <a name="explore-lineage-view"></a>Köken görünümünü inceleme

Çalışma Alanım dışında, ister yeni ister klasik olsun her çalışma alanının otomatik olarak bir köken görünümü vardır. Bu görünümü görmek için çalışma alanında en azından Katkıda Bulunan rolüne sahip olmanız gerekir. Ayrıntılar için bu makalenin [İzinler](#permissions) bölümüne bakın. 

- Köken görünümüne erişmek için çalışma alanı listesi görünümüne gidin. **Liste görünümü**'nün yanındaki oka dokunun ve **Köken görünümü**'nü seçin.

    [ ![Köken görünümüne geçme](media/service-data-lineage/power-bi-lineage-list-view-cropped.png) ](media/service-data-lineage/power-bi-lineage-list-view.png#lightbox)

    Bu görünümde tüm çalışma alanı yapıtlarını ve verilerin birinden diğerine nasıl aktığını görürsünüz.

**Veri kaynakları**

Veri kümeleriyle veri akışlarının verilerini aldığı veri kaynaklarını görürsünüz. Veri kaynağı kartlarında, kaynağı belirlemeye yardımcı olabilecek daha fazla bilgi görürsünüz. Örneğin Azure SQL Server için veritabanı adı da gösterilir.

![Ağ geçidi olmadan köken görünümü veri kaynağı](media/service-data-lineage/power-bi-lineage-data-source-no-gateway.png)
 
**Ağ geçitleri**

Veri kaynağı şirket içi bir ağ geçidi üzerinden bağlandıysa, ağ geçidi bilgileri veri kaynağı kartına eklenir. Ağ geçidi yöneticisi veya veri kaynağı kullanıcısı olarak izinleriniz varsa, ağ geçidi gibi ek bilgiler görürsünüz.

![Ağ geçidiyle köken görünümü veri kaynağı](media/service-data-lineage/power-bi-lineage-data-source-with-gateway.png)

**Veri kümeleri ve veri akışları**
 
Veri kümelerinde son yenileme zamanını ve veri kümesinin sertifikalı veya yükseltilmiş olup olmadığını görürsünüz.

![Köken görünümünde sertifikalı veri kümesi](media/service-data-lineage/power-bi-lineage-external-certified-dataset.png)
 
Çalışma alanındaki rapor başka bir çalışma alanındaki veri kümesi üzerinde oluşturulduysa, veri kümesi kartında kaynak çalışma alanının adını görürsünüz. Kaynak çalışma alanının adını seçerek o çalışma alanını gidersiniz.
 
- Herhangi bir yapıt için seçenekler menüsünü görüntülemek için üç nokta(...) simgesini seçin. Liste görünümünde sağlanan tüm eylemleri sunar.
  
Veri kümelerinde daha fazla meta veri görmek için veri kümesi kartının kendisini seçin. Veri kümesiyle ilgili ek bilgiler yan bölmede görüntülenir.

![Daha fazla bilgi içeren yan bölme](media/service-data-lineage/power-bi-lineage-side-pane.png)
 
## <a name="show-lineage-for-any-artifact"></a>Herhangi bir yapıt için kökeni gösterme 

Belirli bir yapıtın kökenini görmek istediğinizi varsayalım.

- Yapıtın altındaki çift oku seçin.

    [ ![Belirli bir yapıtın kökenini vurgulama](media/service-data-lineage/power-bi-lineage-highlight-cropped.png) ](media/service-data-lineage/power-bi-lineage-highlight-full-size.png#lightbox)

    Power BI söz konusu yapıtla ilgili tüm yapıtları vurgular ve kalanları soluk gösterir. 

## <a name="navigation-and-full-screen"></a>Gezinti ve tam ekran 

Köken görünümü etkileşimli bir tuvaldir. Tuvalde gezinmek, yakınlaştırmak ve uzaklaştırmak için fareyi veya dokunmatik yüzeyi kullanabilirsiniz.  

- Yakınlaştırmak ve uzaklaştırmak için sağ alt köşedeki menüyü ya da farenizi veya dokunmatik yüzeyinizi kullanın. 

- Grafın kendisine daha fazla yer açmak için sağ alt köşedeki tam ekran seçeneğini kullanın. 

    ![Yakınlaştırma, uzaklaştırma veya tam ekran](media/service-data-lineage/power-bi-lineage-zoom-full-screen.png)

## <a name="permissions"></a>İzinler

- Köken görünümünü görmek için Power BI Pro lisansınız olmalıdır.
- Köken görünümü yalnızca çalışma alanına erişimi olan kullanıcılara sağlanır.
- Kullanıcıların çalışma alanı üzerinde Yönetici, Üye veya Katkıda Bulunan rolü olmalıdır. Görüntüleyici rolü olan kullanıcılar köken görünümüne geçemez.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Köken görünümü Internet Explorer'da kullanılamaz. Ayrıntılar için bkz. [Power BI için desteklenen tarayıcılar](power-bi-browsers.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Çalışma alanları arasında veri kümelerine giriş (önizleme)](service-datasets-across-workspaces.md)
