---
title: SSL sertifikası oluşturma
description: Geliştirici sunucusu için el ile sertifika oluşturmaya yönelik geçici yönergeler
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 3287e8a7eb1c36c3f0d8a1fc24faa0442de2dddf
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425448"
---
# <a name="creating-ssl-certificate"></a>SSL sertifikası oluşturma

PowerShell New-SelfSignedCertificate cmdlet’ini Windows 8 veya daha yeni bir işletim sisteminde kullanarak sertifikayı oluşturmak için aşağıdaki komutu çalıştırın.

Araç, **Windows** **7** için OpenSSL yüklemesini gerektirir. Yardımcı `openssll` komut satırında kullanılabilir olmalıdır.

OpenSSL’i yüklemek için burayı ziyaret edin: [https://www.openssl.org](https://www.openssl.org) veya [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-mac-os-x"></a>Sertifika oluştur (Mac OS X)

OpenSSL yardımcıları Linux veya Mac OS X işletim sistemlerinde genellikle kullanılabilir durumdadır.

Tersi durumda,

*Brew* paket yöneticisini

```cmd
brew install openssl
brew link openssl --force
```

veya *MacPorts*’u kullanarak yükleyebilirsiniz

```cmd
sudo port install openssl
```

Yeni sertifika çağrısı oluşturmak için OpenSSL’i yükledikten sonra:

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-linux"></a>Sertifika oluşturun (Linux)

OpenSSL yardımcıları Linux işletim sisteminizde kullanılamıyor. Aşağıdaki komutları kullanarak yükleyebilirsiniz.

*APT* paket yöneticisi için:

```cmd
sudo apt-get install openssl
```

*Yellowdog Güncelleştiricisi* için:

```cmd
yum install openssl
```

*Redhat Paket Yöneticisi* için:

```cmd
rpm install openssl
```

OpenSSL işletim sisteminizde kullanılabiliyorsa, yeni sertifika

```cmd
pbiviz --create-cert
```

oluşturmak için çağrı yapın.

Ya da şuralardan alın: [https://www.openssl.org](https://www.openssl.org) veya [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)

## <a name="generate-certificate-manually"></a>Sertifikayı el ile oluşturma

Herhangi bir araç tarafından oluşturulan sertifikalarınızı belirtebilirsiniz.

Sisteminizde OpenSSL yüklüyse, yeni bir sertifika oluşturmak için aşağıdaki komutu çalıştırabilirsiniz

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

PowerBI-visuals-tools web sunucusu sertifikaları genellikle şuralarda bulunur

```cmd
%appdata%\npm\node_modules\PowerBI-visuals-tools\certs
```

araçların genel örneği için

veya

```cmd
<custom visual project root>\node_modules\PowerBI-visuals-tools\certs
```

araçların yerel örneği için.

PEM biçimini kullanıyorsanız, cert dosyasını `PowerBICustomVisualTest_public.cer` ve privateKey’i `PowerBICustomVisualTest_public.key` olarak kaydetmelisiniz.
PFX biçimin kullanıyorsanız cert dosyasını `PowerBICustomVisualTest_public.pfx` olarak kaydedin.

PFX cert dosyanız parola gerektiriyorsa

```cmd
\PowerBI-visuals-tools\config.json
```

sunucu bölümünde şunu belirtmeniz gerekir:

```cmd
"server":{
    "root":"webRoot",
    "assetsRoute":"/assets",
    "privateKey":"certs/PowerBICustomVisualTest_private.key",
    "certificate":"certs/PowerBICustomVisualTest_public.crt",
    "pfx":"certs/PowerBICustomVisualTest_public.pfx",
    "port":"8080",
    "passphrase":"YOUR PASSPHRASE"
}
```
