---
title: Sertifika iptal denetimi Power BI Desktop
description: Kullanıcı arabirimindeki ve kayıt defterindeki Power BI Desktop sertifikaları iptal etme
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: conceptual
ms.date: 01/25/2021
LocalizationGroup: Create reports
ms.openlocfilehash: 482f0f8279de9818b631ff79e7b37a215e7397bd
ms.sourcegitcommit: 7ed995eed0fd6e718748accf87bae384211cd95d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2021
ms.locfileid: "99057015"
---
# <a name="certificate-revocation-in-power-bi-desktop"></a>Power BI Desktop sertifika iptali

Power BI, bir sertifika denetimini etkinleştirmek veya devre dışı bırakmak için iki yol sunar. 2020 Kasım 'da, Power BI Desktop Web bağlantıları için basit bir açık/kapalı sertifika iptali denetimi sunuyoruz. Artık sertifika iptal denetimi üzerinde daha ayrıntılı denetime sahip olabilirsiniz.

## <a name="simple-certificate-revocation"></a>Basit sertifika iptali

Power BI Desktop ' deki Kullanıcı arabiriminde özelliği etkinleştirebilir veya devre dışı bırakabilirsiniz.

- **Dosya** menüsünde **Seçenekler ve ayarlar**  >  **seçenekleri**>, **güvenlik**' i seçin, sonra **sertifika iptal denetimini etkinleştir**' i seçin veya temizleyin.

## <a name="more-fine-grained-control"></a>Daha ayrıntılı denetim

Sertifika iptal denetimi üzerinde üçüncü bir seçenekle daha ayrıntılı denetime sahip olabilirsiniz. 

- **Temel**  Temel denetim, iptal durumu bilinmeyen olan sertifikaları kabul eder, örneğin sertifika bunu belirtmez. Bu denetim, kurumsal proxy sunucuları kullanan kuruluşlar için önemlidir. Bu, Power BI Desktop onay kutusunu seçmekle aynıdır.
- **Devre dışı** Power BI Desktop onay kutusunu devre dışı bırakmayla aynı.
- **Kapsamlı** İptal denetimini devre dışı bırakabilir veya etkinleştirebilirsiniz; bu  , bilinmeyen bir iptal durumu olan sertifikaları kabul etmez. 


|Sertifika iptal bilgileri durumu | Kapsamlı denetim | Temel denetim | Yok |
|---------|---------|---------|---------|
|İptal Edildi     |  ❌  | ❌  | ✔   |
|Bilinmiyor  |  ❌    |  ✔   |    ✔  |
|İptal edilmemiş  | ✔  |    ✔ |    ✔  |

Basit etkinleştir veya devre dışı bırak onay kutusu hala Power BI Desktop Kullanıcı arabiriminde. Daha ayrıntılı denetim kullanmak için aşağıdaki DWORD kayıt defteri değerini ayarlayın: `DisableCertificateRevocationCheck` . Bu değeri Power BI Desktop kayıt defteri anahtarında ayarlarsınız. Bu, işletim sisteminize bağlı olarak bunlardan biridir:

```
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Microsoft Power BI Desktop
```

Veya

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft Power BI Desktop
```

Kayıt defteri değerini aşağıdaki değerlerden birine ayarlayın: 

|Değer  |Mod  |Yapılandırma  |
|---------|---------|---------|
|0     | Temel   | İptal durumu bilinmeyen sertifikalar kabul edilir. Power BI Desktop onay kutusunu etkinleştirmeye eşdeğerdir. |
|1     | Devre dışı  | Tüm iptal denetimlerini yoksayar. Power BI Desktop onay kutusunu devre dışı bırakmaya eşdeğerdir.  |
|2     | Kapsamlı  |  Sertifika iptali gerektirmez. , Bilinmeyen iptal durumu olan sertifikaları kabul etmez |

Bu kayıt defteri ayarını, bugün daha ayrıntılı denetim özelliğinden faydalanmak için yapılandırın.