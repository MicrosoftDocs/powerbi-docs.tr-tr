---
title: "Gizlilik ayarlarını devre dışı bırakma"
description: "Yenileme için gizlilik ayarlarını devre dışı bırakmak üzere Personal Gateway'de Hızlı Birleştirme özelliğini etkinleştirme."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 02/06/2018
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: 54d5f5ec2db890de0fbcef5ef0633548b90a6079
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="disable-privacy-setting-in-power-bi-gateway---personal"></a>Power BI Gateway - Personal'da gizlilik ayarlarını devre dışı bırakma
> [!NOTE]
> Power BI için kişisel ağ geçidinin **şirket içi veri ağ geçidi (kişisel mod)** adlı yeni bir sürümü vardır. Aşağıdaki makalede **Power BI Gateway - Personal** adlı eski sürüm açıklanmaktadır. Bu sürüm, 31 Temmuz 2017 tarihinden sonra kullanımdan kaldırılacak ve artık çalışmayacaktır. Kişisel ağ geçidinin yeni sürümü hakkında bilgi için [**Şirket içi veri ağ geçidi (kişisel mod)** başlıklı makaleye bakın](service-gateway-personal-mode.md). Hızlı birleştirme özelliği kişisel ağ geçidinin yeni sürümünde de sunulmaktadır ve bu makalede açıklanmıştır.
> 
> 

Kişisel ağ geçidi ile birlikte kullanıldığında veri kaynaklarınıza ilişkin gizlilik ayarlarına bağlı olarak aşağıdaki hatayı alabilirsiniz.

> *Veri kümesindeki veriler işlenirken bir hata oluştu.*
> 
> *[Veriler birleştirilemiyor] &lt;sorgu parçası&gt;/&lt;…&gt;/&lt;…&gt;, birlikte kullanılamayan gizlilik düzeylerine sahip veri kaynaklarına erişiyor. Lütfen bu veri birleşimini yeniden oluşturun.*
> 
> 

Bu hatayı çözmek için **Hızlı Birleştirme** özelliğini açabilirsiniz. **Hızlı Birleştirme** farklı veri kaynaklarının birleştirilmesine izin vererek gizlilik ayarlarını yok sayar.

> [!NOTE]
> Veriler birleştirilirken gizlilik düzeyleri dikkate alınmaz. Bu, verileri birleştirirken gizli verilerin başka bir veri kaynağına geçmesine neden olabilir.
> 
> 

## <a name="what-is-fast-combine"></a>Hızlı Birleştirme nedir?
Gizlilik düzeyleri ve Hızlı Birleştirme hakkında daha fazla bilgi için [Gizlilik Düzeyleri](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540) bölümüne bakabilirsiniz. Gizlilik düzeyi varsayılan olarak özeldir ve bu, yukarıda belirtilen hatanın oluşmasına neden olabilir. Bu durum, özel ayarı veri kaynağını diğer kaynaklardan ayırdığı için meydana gelir. Bunun sorun yaratabileceği durumlara örnek olarak parametreli bir sorgunun başka bir veri kaynağından girişleri alması gösterilebilir.

Hızlı Birleştirme özelliği açıldığında özel ayarı yok sayılır ve yürütmeye izin verilir.

## <a name="turn-on-fast-combine"></a>Hızlı Birleştirme özelliğini etkinleştirme
Kişisel ağ geçidiniz için Hızlı Birleştirmeyi etkinleştirmek üzere aşağıdaki adımları uygulayın. Şirket içi veri ağ geçidinde bu ayar bulunmaz.

1. **ConnectorConfig.xml** dosyasını açın.  Bu, makinenizdeki iki konumdan birinde olabilir.  Bilgisayarda yöneticiyseniz aşağıdaki konumdadır.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Bilgisayarda yönetici değilseniz aşağıdaki konumdadır.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
    
2. Yapılandırma dosyası için true değerine sahip **&lt;EnableFastCombine&gt;** öğesini ekleyin. Bu öğe eklendiğinde **Hızlı Birleştirme** açılır.
   
   <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
   
   ![](media/refresh-enable-fast-combine/configfile.png)
3. Çıkın ve ağ geçidi yapılandırma ekranını yeniden başlatın.
4. Hızlı Birleştirme özelliğinin etkin olduğunu belirten bir durum görüntülenir.
   
   ![](media/refresh-enable-fast-combine/fastcombineenabled.png)

## <a name="turn-off-fast-combine"></a>Hızlı Birleştirmeyi Kapatma
1. **ConnectorConfig.xml** dosyasını açın.  Bu, makinenizdeki iki konumdan birinde olabilir.  Bilgisayarda yöneticiyseniz aşağıdaki konumdadır.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Bilgisayarda yönetici değilseniz aşağıdaki konumdadır.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2. **&lt;EnableFastCombine&gt;** öğesini yapılandırma dosyasından kaldırın. Bu öğe kaldırıldığında **Hızlı Birleştirme** kapatılır.
3. Çıkın ve ağ geçidi yapılandırma ekranını yeniden başlatın.
4. Artık **Hızlı Birleştirme** özelliğinin etkin olduğunu belirten bir durum görüntülenmez.

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidi (kişisel mod) - yeni sürüm kişisel ağ geçidi ](service-gateway-personal-mode.md)
[Gizlilik Düzeyleri](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[Power BI Desktop'taki genel sorgu görevleri](desktop-common-query-tasks.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

