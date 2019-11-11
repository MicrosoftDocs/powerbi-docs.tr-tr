---
title: Power BI Desktop’ta Python Betiklerini Çalıştırma
description: Power BI Desktop'ta Python Betikleri Çalıştırma
author: otarb
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/16/2019
ms.author: otarb
LocalizationGroup: Connect to data
ms.openlocfilehash: dbde3abec716e4868a6efce98129ea8c76506d7e
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73865988"
---
# <a name="run-python-scripts-in-power-bi-desktop"></a>Power BI Desktop'ta Python Betikleri Çalıştırma

**Power BI Desktop**'ta Python betiklerini doğrudan çalıştırabilir ve elde edilen veri kümelerini bir Power BI Desktop veri modeline aktarabilirsiniz.

## <a name="install-python"></a>Python'ı Yükleme

Power BI Desktop'ta Python betikleri çalıştırabilmek için yerel makinenize **Python** yüklemeniz gerekir. **Python**’ı [Resmi Python indirme sayfasından](https://www.python.org/) indirebilirsiniz. Geçerli Python betik sürümü, yükleme yolunda Unicode karakterlerini ve boşlukları destekler.

### <a name="install-required-python-packages"></a>Gerekli Python paketlerini yükleme

Power BI Python tümleştirmesi için iki Python paketinin yüklenmesi gerekir:

- [Pandas](https://pandas.pydata.org/) - Veri işleme ve analiz için bir yazılım kitaplığı. Sayısal tabloları ve zaman serilerini işlemek için veri yapıları ve işlemler sunar. İçeri aktarılan verilerinizin bir [pandas veri çerçevesinde](https://www.tutorialspoint.com/python_pandas/python_pandas_dataframe.htm) yer alması gerekir. Veri çerçevesi iki boyutlu bir veri yapısıdır. Örneğin veriler tablo şeklinde, satırlar ve sütunlar halinde hizalanır.
- [Matplotlib](https://matplotlib.org/) - Python için çizim kitaplığı ve bunun sayısal [NumPy](https://www.numpy.org/) matematik uzantısı. Genel amaçlı GUI araç setleri (örneğin Tkinter, wxPython, Qt veya GTK+) kullanarak çizimleri uygulamalara eklemek için nesne yönelimli bir API sağlar.

1. İki paketi yüklemek için konsolda veya kabukta [pip](https://pip.pypa.io/en/stable/) komut satırı aracını kullanın. Pip aracı en son Python sürümleriyle birlikte paketlenmiştir.

```CMD
pip install pandas
pip install matplotlib
```

## <a name="enable-python-scripting"></a>Python betiğini etkinleştirme

Python betiğini etkinleştirmek için:

1. Power BI Desktop’ta **Dosya** > **Seçenekler ve ayarlar** > **Seçenekler** > **Python betiği**’ni seçin. Python betiği seçenekleri sayfası görüntülenir.

   ![](media/desktop-python-scripts/python-scripts-7.png)

1. Gerekirse, **Algılanan Python giriş dizinleri:** metin kutusunda yerel Python yükleme yolunuzu belirtin. 

   Yukarıdaki resimde Python'ın yerel yükleme yolu **C:\Python** dizinidir. Bu yolun, Power BI Desktop'ın kullanmasını istediğiniz yerel Python yüklemesine ait olduğundan emin olun.

1. **Tamam**'ı seçin.

Python yüklemenizi belirttikten sonra Power BI Desktop’ta Python görsellerini çalıştırmaya başlamak için hazırsınız demektir.

## <a name="run-python-scripts"></a>Python betiklerini çalıştırma

Yalnızca birkaç adımda Python betiklerini çalıştırabilir ve veri modeli oluşturabilirsiniz. Bu modelden raporlar oluşturabilir ve bunları Power BI hizmetinde paylaşabilirsiniz.

### <a name="prepare-a-python-script"></a>Python betiği hazırlama
İlk olarak yerel Python geliştirme ortamınızda bir betik oluşturun ve bu betiğin başarıyla çalıştığından emin olun. Örneğin burada pandas’ı içeri aktaran ve bir veri çerçevesi kullanan basit bir Python betiği verilmiştir:

```python
import pandas as pd
data = [['Alex',10],['Bob',12],['Clarke',13]]
df = pd.DataFrame(data,columns=['Name','Age'],dtype=float)
print (df)
```
Çalıştırıldığında şu çıktıyı verir:

```python
     Name   Age
0    Alex  10.0
1     Bob  12.0
2  Clarke  13.0
```

Power BI Desktop'ta bir Python betiğini hazırlamaya ve çalıştırmaya ilişkin bazı sınırlamalar vardır:

* Yalnızca pandas veri çerçeveleri içeri aktarılır; dolayısıyla Power BI’a aktarmak istediğiniz verilerin veri çerçevesinde temsil edildiğinden emin olun
* 30 dakikadan uzun süren herhangi bir Python betiği çalıştırma işlemi zaman aşımına uğrar
* Python betiğindeki etkileşimli çağrılar (kullanıcı girişinin beklenmesi gibi) betik yürütme işlemini durdurur
* Python betiğindeki çalışma dizinini ayarlarken çalışma dizinine yönelik bir tam yol (göreli yol yerine) tanımlamanız *gerekir*
* İç içe tablolar şu anda desteklenmemektedir 

### <a name="run-your-python-script-and-import-data"></a>Python betiğinizi çalıştırma ve verileri içeri aktarma

Power BI Desktop’ta Python Betiğinizi çalıştırmak için:

1. Giriş şeridinde **Veri Al** > **Diğer...** öğesini seçin.
   
1. Aşağıdaki resimde gösterildiği gibi **Diğer** > **Python betiği**’ni seçin:

   ![](media/desktop-python-scripts/python-scripts-1.png)
   
1. **Bağlan**'ı seçin. Python altyapınız olarak yerel makinenizin en son yüklenen Python sürümü seçilir. Betiğinizi görüntülenen Python betiği iletişim kutusuna kopyalayın. Burada, daha önce gösterilen basit Python betiğini girdik.

   ![](media/desktop-python-scripts/python-scripts-6.png)

1. **Tamam**'ı seçin. Betik başarıyla çalıştırılırsa Gezgin iletişim kutusu görüntülenir ve verileri yükleyip kullanabilirsiniz. Örneğin resimde gösterildiği gibi **df** onay kutusunu ve ardından **Yükle**’yi seçin.

   ![](media/desktop-python-scripts/python-scripts-5.png) 

### <a name="troubleshooting"></a>Sorun giderme

Python yüklenmez veya tanımlanmazsa bir uyarı görüntülenir. Birden fazla yerel makine yüklemeniz olduğunda da uyarı görebilirsiniz. Önceki Python’ı yükleme ve Python betiğini etkinleştirme bölümlerini yeniden ziyaret edin ve gözden geçirin.

![](media/desktop-python-scripts/python-scripts-3.png)

### <a name="refresh"></a>Yenile

Power BI Desktop'ta bir Python betiğini yenileyebilirsiniz. Yenilemek için **Giriş** şeridine gidin ve **Yenile**’yi seçin. Python betiğini yenilediğinizde Power BI Desktop Python betiğini yeniden çalıştırır.

## <a name="next-steps"></a>Sonraki adımlar

Power BI'da Python kullanımı ile ilgili aşağıdaki ek bilgilere göz atın.

* [Power BI Desktop'ta Python Görselleri Oluşturma](desktop-python-visuals.md)
* [Power BI ile harici bir Python IDE kullanma](desktop-python-ide.md)
