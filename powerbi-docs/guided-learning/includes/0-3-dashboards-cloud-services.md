---
ms.openlocfilehash: d600581b9d1df8c8436da45e9629fccb79873c21
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61260624"
---
Öğrendiğimiz üzere, Power BI'daki genel iş akışı şöyledir: Power BI Desktop'ta bir rapor oluşturursunuz, bu raporu Power BI hizmetinde yayımlar ve başka kullanıcılarla paylaşırsınız. Böylece kullanıcılar raporu hizmette veya bir mobil uygulamada görüntüleyebilir.

Ancak, bazı kullanıcılar iş akışına Power BI hizmeti ile başlar. Şimdi bu hizmete hızlıca göz atıp Power BI'da hızlıca görsel oluşturmanın kolay ve popüler yolu hakkında bilgi edineceğiz: *içerik paketleri*.

**İçerik paketi**, Salesforce gibi belirli veri kaynaklarına dayalı önceden yapılandırılmış, hazır görsellerden ve raporlardan oluşan bir koleksiyondur. İçerik paketlerini kullanmak, TV karşısında yiyeceğiniz bir yemeği mikrodalga fırında ısıtmaya veya fast food yemek siparişi vermeye benzer. Yalnızca birkaç tıklama ve açıklamanın ardından, birlikte uyum sağlayacak şekilde tasarlanmış girişlerden oluşan bir koleksiyon hızlı bir şekilde servis edilir.

Şimdi içerik paketlerine, hizmete ve bunların nasıl çalıştığına hızlıca göz atalım. Sonraki bölümlerde içerik paketleri (ve hizmet) ile ilgili daha ayrıntılı bilgi vereceğiz. Bunu ana yemekten önce gelen bir aperitif olarak düşünebilirsiniz.

## <a name="create-out-of-the-box-dashboards-with-cloud-services"></a>Bulut hizmetleriyle kullanıma hazır panolar oluşturma
Power BI ile verilere kolayca bağlanabilirsiniz. Power BI hizmetinde, giriş ekranının sol alt köşesindeki **Veri Al** düğmesini seçmeniz yeterlidir.

![](media/0-3-dashboards-cloud-services/c0a3_1.png)

*Tuvalde* (Power BI hizmetinin ortasındaki alan) Power BI hizmetindeki kullanılabilir veri kaynakları gösterilir. Power BI; Excel dosyaları, veritabanları veya Azure verileri gibi yaygın olarak kullanılan veri kaynaklarının yanı sıra Salesforce, Facebook, Google Analytics ve diğer tüm SaaS hizmet çeşitleri gibi **yazılım hizmetlerine** (SaaS sağlayıcıları veya bulut hizmetleri olarak da bilinir) kolayca bağlanabilir.

![](media/0-3-dashboards-cloud-services/c0a3_2.png)

**Power BI hizmeti** bu yazılım hizmetleri için panolarda ve raporlarda önceden ayarlanmış, kullanıma hazır görsellerden oluşan bir koleksiyon (**İçerik Paketleri**) sunar. İçerik paketleri sayesinde, seçtiğiniz hizmetten edindiğiniz verilerle Power BI'da hızlıca çalışmaya başlarsınız. Örneğin, Salesforce içerik paketini kullandığınızda Power BI, Salesforce hesabınıza bağlanır (kimlik bilgilerinizi sağladığınızda) ve ardından Power BI'a, görsellerden ve panolardan oluşan önceden tanımlı bir koleksiyon ekler.

Power BI tüm hizmet türleri için içerik paketleri sunar. Aşağıdaki görüntüde, **Hizmetler** kutusundaki (önceki görüntüde gösterilmiştir) **Al** seçeneğini belirlediğinizde görüntülenen, hizmetlerin alfabetik olarak sıralandığı ilk ekran gösterilmektedir. Aşağıdaki görüntüde de görebileceğiniz üzere birçok seçeneğiniz vardır.

![](media/0-3-dashboards-cloud-services/c0a3_3.png)

Biz, amaçlarımız doğrultusunda **GitHub**'ı seçeceğiz. GitHub çevrimiçi kaynak denetimine ilişkin bir uygulamadır. GitHub içerik paketine ilişkin bilgileri ve kimlik bilgilerini girdiğimde paket, verilerimi içeri aktarmaya başlar.

![](media/0-3-dashboards-cloud-services/c0a3_4.png)

Veriler yüklendiğinde, önceden tanımlı GitHub içerik paketi panosu görünür.

![](media/0-3-dashboards-cloud-services/c0a3_5.png)

**Panonun** yanı sıra, panoyu oluşturmak için (GitHub içerik paketinin parçası olarak) oluşturulan **Rapor** ile birlikte verilerin içeri aktarıldığı sırada oluşturulan ve GitHub Raporunun oluşturulması için kullanılan **Veri Kümesini** de (GitHub'dan çekilen veri koleksiyonu) görürsünüz.

![](media/0-3-dashboards-cloud-services/c0a3_6.png)

Panoda herhangi bir görsele tıklayıp söz konusu görselin oluşturulduğu **Rapor** sayfasına otomatik olarak yönlendirilebilirsiniz. **Top 5 users by pull requests** görseline tıkladığınızda Power BI, Rapordaki **Pull Requests** sayfasını (görselin oluşturulduğu Rapor sayfası) açar.

## <a name="asking-questions-of-your-data"></a>Verileriniz hakkında soru sorma
Ayrıca verileriniz hakkında soru da sorabilirsiniz. Power BI hizmeti, sorunuza göre gerçek zamanlı olarak birtakım görseller oluşturur. Aşağıdaki görüntüde, **Doğal Dil Sorgusu** çubuğunda yazılı olanlara göre Power BI'ın, giderilen Sorun Sayısını (Count of Issues) gösterdiği bir dizi görseli görebilirsiniz.

![](media/0-3-dashboards-cloud-services/c0a3_7.png)

Bir görseli beğendiğinizde Doğal Dil Sorgusu çubuğunun sağ tarafında bulunan **Raptiye** simgesini seçerek söz konusu görseli panoya sabitleyebilirsiniz. Bu örnekte, görsel GitHub panosuna (seçili pano bu olduğundan) sabitlenmiş durumdadır.

![](media/0-3-dashboards-cloud-services/c0a3_8.png)

## <a name="refreshing-data-in-the-power-bi-service"></a>Power BI hizmetinde verileri yenileme
Bir içerik paketine ilişkin veri kümesini veya Power BI'da kullandığınız diğer verileri **yenilemeyi** seçebilirsiniz. Yenileme ayarlarını yapmak için bir veri kümesinin yanındaki üç nokta seçeneğini belirlediğinizde bir menü görünür.

![](media/0-3-dashboards-cloud-services/c0a3_9.png)

Bu menünün alt kısmında bulunan **Yenilemeyi Zamanla** seçeneğini belirleyin. Tuvalde, Ayarlar iletişim kutusunu görünür. Burada, yenileme ayarlarını ihtiyaçlarınıza uygun şekilde belirleyebilirsiniz.

![](media/0-3-dashboards-cloud-services/c0a3_10.png)

Power BI hizmetine hızlı bakış konusunu burada noktalayabiliriz. Bu hizmet ile yapabileceğiniz daha pek çok şey var ancak bunlara bu kursun ilerleyen kısımlarında değineceğiz. Ayrıca, bağlanabileceğiniz birçok veri türünün olduğunu ve tüm içerik paketi türlerini kullanabileceğinizi aklınızdan çıkarmayın. Üstelik her geçen gün bunlara yenileri de eklenmektedir.

Şimdi bu **Başlangıç** bölümünü özetleyip sonraki adımlar için hazırlanacağınız sıradaki konumuza geçelim.

