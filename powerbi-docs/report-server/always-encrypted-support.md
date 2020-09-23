---
title: Power BI Rapor Sunucusu'nda Always Encrypted özelliği
description: Bu makalede, Microsoft SQL Server ve Microsoft Azure SQL Veritabanı veri kaynağı türleri kullanılırken Power BI Rapor Sunucusu'ndaki Always Encrypted desteği açıklanır.
author: maggiesMSFT
ms.reviewer: cfinlan
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/22/2020
ms.author: maggies
ms.openlocfilehash: f921d9dbeb16d1b960e22f228f7833c8fbf184b4
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90861257"
---
# <a name="always-encrypted-in-power-bi-report-server"></a>Power BI Rapor Sunucusu'nda Always Encrypted özelliği

Bu makalede, Microsoft SQL Server ve Microsoft Azure SQL Veritabanı veri kaynağı türleri kullanılırken Power BI Rapor Sunucusu'ndaki Always Encrypted desteği açıklanır. SQL Server'ın Always Encrypted özellikleri hakkında daha fazla bilgi için [Always Encrypted](/sql/relational-databases/security/encryption/always-encrypted-database-engine) makalesine bakın.

## <a name="always-encrypted-user-isolation"></a>Always Encrypted kullanıcı yalıtımı

Şu anda Power BI Rapor Sunucusu rapora erişimi olan kullanıcıların rapordaki Always Encrypted sütunlarına erişimini kısıtlamamaktadır.  Dolayısıyla sunucuya sütun ana anahtarı aracılığıyla sütun şifreleme anahtarına erişim verildiyse, kullanıcıların erişebildikleri raporların tüm sütunlarına erişimleri olacaktır.

## <a name="always-encrypted-column-usage"></a>Always Encrypted sütun kullanımı

### <a name="key-storage-strategies"></a>Önemli depolama stratejileri

|Depolama  |Destekleniyor  |
|---------|---------|
|Windows Sertifika Depolama Alanı | Evet |
|Azure Key Vault | Hayır |
| Yeni Nesil Şifreleme (CNG) | Hayır |

### <a name="certificate-storage-and-access"></a>Sertifika depolama ve erişimi

Sertifikaya erişimi olması gereken hesap, hizmet hesabıdır. Sertifika yerel bilgisayarın sertifika depolama alanında depolanmalıdır. Daha fazla bilgi için bkz.

- [Rapor Sunucusu Hizmet Hesabını Yapılandırma](/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager) (Configuration Manager)
- "Always Encrypted için sütun ana anahtarlarını oluşturma ve depolama" adlı SQL Server makalesinin [Sertifikaları uygulamaların ve kullanıcıların kullanımına sunma](/sql/relational-databases/security/encryption/create-and-store-column-master-keys-always-encrypted#making-certificates-available-to-applications-and-users) bölümü.

### <a name="column-encryption-strategy"></a>Sütun şifreleme stratejisi

Power BI Rapor Sunucusu'nda sütun şifreleme stratejisi *belirlenimci* veya *rastgele* olabilir. Aşağıdaki tabloda kullanılan stratejiye bağlı olarak farklar açıklanır.

|Kullanım  |Belirlenimci  |Rastgele  |
|---------|---------|---------|
|Sorgunun sonuçlarında olduğu gibi okunabilir, örneğin SELECT deyimleri. | Evet  | Evet  |
|Sorgu içinde Group By (gruplandırma ölçütü) varlığı olarak kullanılabilir. | Evet | Hayır |
|COUNT ve DISTINCT haricinde toplama alanı olarak kullanılabilir. | Hayır, COUNT ve DISTINCT hariç | Hayır |
|Rapor parametresi olarak kullanılabilir | Evet | Hayır |

[Belirlenimci ile rastgele şifreleme karşılaştırması](/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption) hakkında daha fazla bilgi edinin.

### <a name="parameter-usage"></a>Parametre kullanımı

Parametre kullanımı yalnızca belirlenimci şifreleme için geçerlidir.

**Tek değerli parametre**.  Bir Always Encrypted sütunu için tek değerli parametre kullanabilirsiniz.

**Çok değerli parametre**. Bir Always Encrypted sütunu için birden çok değeri olan çok değerli parametre kullanamazsınız.

Bunlar **Basamaklı parametrelerdir**. Always Encrypted ile basamaklı parametreleri kullanabilmeniz için aşağıdakilerin *tümü* doğru olmalıdır:

- Tüm Always Encrypted sütunları belirlenimci stratejiyle Always Encrypted olmalıdır.
- Always Encrypted sütunları için kullanılan tüm parametreler tek değerli parametre olmalıdır.
- Tüm SQL karşılaştırmaları Eşittir (=) işlecini kullanır.

## <a name="datatype-support"></a>Veri türü desteği

| SQL Veri türü | Alanı okumayı destekler | Group By öğesi olarak kullanımı destekler | Toplamaları (COUNT, DISTINCT, MAX, MIN, SUM vb.) destekler | Parametreleri kullanarak eşitlik yoluyla filtrelemeyi destekler | Notlar |
| --- | --- | --- | --- | --- | --- |
| int | Evet | Evet | COUNT, DISTINCT | Evet, Tamsayı olarak |   |
| float | Evet | Evet | COUNT, DISTINCT | Evet, Float olarak |   |
| nvarchar | Evet | Evet | COUNT, DISTINCT | Evet, Metin olarak | Belirlenimci şifrelemede, karakter sütunları için binary2 sıralama düzeninde bir sütun harmanlama kullanılmalıdır. Ayrıntılar için SQL Server [Always Encrypted](/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption) makalesine bakın.  |
| varchar | Evet | Evet | COUNT, DISTINCT | Hayır |   |
| decimal | Evet | Evet | COUNT, DISTINCT | Hayır |   |
| numeric | Evet | Evet | COUNT, DISTINCT | Hayır |   |
| tarih saat | Evet | Evet | COUNT, DISTINCT | Hayır |   |
| datetime2 | Evet | Evet | COUNT, DISTINCT | Evet, Tarih/Saat olarak | Sütunun milisaniye duyarlığı yoksa (diğer bir deyişle datetime2(0) değilse) desteklenir |

## <a name="aggregation-alternatives"></a>Toplama alternatifleri

Şu anda belirlenimci Always Encrypted sütunlarında desteklenen toplamalar yalnızca doğrudan Eşittir (=) işlecini kullanan toplamalardır. Bu SQL Server sınırlaması Always Encrypted sütunlarının doğasından kaynaklanır. Kullanıcılar veritabanının içinde değil raporun içinde toplamalıdır.

## <a name="always-encrypted-in-connection-strings"></a>Bağlantı dizelerinde Always Encrypted

SQL Server veri kaynağı için bağlantı dizesinde Always Encrypted özelliğini etkinleştirmeniz gerekir. [Uygulama sorgularında Always Encrypted özelliğini](/sql/relational-databases/security/encryption/develop-using-always-encrypted-with-net-framework-data-provider#enabling-always-encrypted-for-application-queries) etkinleştirme hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar

SQL Server ve Azure SQL Veritabanı'nda [Always Encrypted](/sql/relational-databases/security/encryption/always-encrypted-database-engine)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)