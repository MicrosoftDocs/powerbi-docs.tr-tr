---
title: SSL sertifikası oluşturma
description: Geliştirici sunucusu için el ile sertifika oluşturmaya yönelik geçici yönergeler
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: d24135cc55ebc8cdfd2a1279cb2a2a46f8f0bc3e
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880198"
---
# <a name="create-an-ssl-certificate"></a>SSL sertifikası oluşturma

Bu makalede SSL sertifikasını oluşturma işlemi açıklanır.

Windows 8 veya üstünde PowerShell `New-SelfSignedCertificate` cmdlet’ini kullanarak sertifika oluşturmak için aşağıdaki komutu çalıştırın:

```cmd
pbiviz --create-cert
```

Araç, Windows 7 için OpenSSL yüklemesini gerektirir. OpenSSL yardımcı programının komut satırından kullanılabilmesi gerekir.

OpenSSL’yi yüklemek için [OpenSSL](https://www.openssl.org) veya [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries) sitesine gidin.



## <a name="create-a-certificate-mac-os-x"></a>Sertifika oluşturma (Mac OS X)

Genellikle OpenSSL yardımcı programı Linux veya Mac OS X işletim sisteminde sağlanır.

Aşağıdaki komutlardan birini çalıştırarak da yardımcı programı yükleyebilirsiniz:
* *Brew* paket yöneticisinden:

    ```cmd
    brew install openssl
    brew link openssl --force
    ```

* *MacPorts* kullanarak:

    ```cmd
    sudo port install openssl
    ```

Yeni sertifikayı oluşturmak üzere OpenSSL yardımcı programını yükledikten sonra aşağıdaki komutu çalıştırın:

```cmd
pbiviz --create-cert
```

## <a name="create-a-certificate-linux"></a>Sertifika oluşturma (Linux)

OpenSSL yardımcı programı Linux işletim sisteminizde yoksa, aşağıdaki komutlardan birini kullanarak yükleyebilirsiniz:

* *APT* paket yöneticisi için:

    ```cmd
    sudo apt-get install openssl
    ```

* *Yellowdog Güncelleştiricisi* için:

    ```cmd
    yum install openssl
    ```

* *Redhat Paket Yöneticisi* için:

    ```cmd
    rpm install openssl
    ```

OpenSSL yardımcı programı işletim sisteminizde zaten varsa, aşağıdaki komutu çalıştırarak yeni sertifikayı oluşturun:

```cmd
pbiviz --create-cert
```

Öte yandan, [OpenSSL](https://www.openssl.org) veya [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries) sitesine giderek de OpenSSL yardımcı programını alabilirsiniz.

## <a name="generate-the-certificate-manually"></a>Sertifikayı el ile oluşturma

Sertifikalarınızın herhangi bir araçla oluşturulabileceğini belirtebilirsiniz.

OpenSSL yardımcı programı sisteminizde zaten yüklenmişse aşağıdaki komutları çalıştırarak yeni sertifikayı oluşturun:

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

Genellikle aşağıdakilerden birini çalıştırarak PowerBI-visuals-tools web sunucusu sertifikalarını bulabilirsiniz:

* Araçların genel örneği için:

    ```cmd
    %appdata%\npm\node_modules\PowerBI-visuals-tools\certs
    ```

* Araçların yerel örneği için:

    ```cmd
    <custom visual project root>\node_modules\PowerBI-visuals-tools\certs
    ```

PEM biçimini kullanıyorsanız sertifika dosyasını *PowerBICustomVisualTest_public.crt* olarak ve privateKey öğesini *PowerBICustomVisualTest_public.key* olarak kaydedin.

PFX biçimini kullanıyorsanız, sertifika dosyasını *PowerBICustomVisualTest_public.pfx* olarak kaydedin.

PFX sertifika dosyanıza şifre gerekiyorsa aşağıdakileri yapın:
1. Yapılandırma dosyasında şunu belirtin:

    ```cmd
    \PowerBI-visuals-tools\config.json
    ```

1. `server` bölümünde "*YOUR PASSPHRASE*" yer tutucusunun yerine kendi şifrenizi belirtin:

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
