---
title: Power BI görselleri için SSL sertifikası oluşturma
description: Windows, Mac veya Linux'ta Power BI Görsel Araçlar paketini kullanarak veya el ile SSL sertifikası oluşturmayı öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 05/08/2020
ms.openlocfilehash: 8eeca13acb1568a671618dca75d20cb7667b538b
ms.sourcegitcommit: 6bc66f9c0fac132e004d096cfdcc191a04549683
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91747563"
---
# <a name="create-an-ssl-certificate"></a>SSL sertifikası oluşturma

Bu makalede Power BI görselleri için Güvenli Yuva Katmanı (SSL) sertifikası oluşturma ve yükleme adımları anlatılmaktadır.

Windows, macOS X ve Linux yordamları için Power BI Görsel Araçlar **pbiviz** paketini yüklemiş olmanız gerekir. Daha fazla bilgi için bkz. [Geliştirici ortamını ayarlama](./custom-visual-develop-tutorial.md#setting-up-the-developer-environment). 

## <a name="create-a-certificate-on-windows"></a>Windows'da sertifika oluşturma

Windows 8 ve üzeri sürümlerde PowerShell `New-SelfSignedCertificate` cmdlet’ini kullanarak sertifika oluşturmak için aşağıdaki komutu çalıştırın:

```powershell
pbiviz --install-cert
```

Windows 7'de `pbiviz` aracını kullanabilmeniz için komut satırından OpenSSL yardımcı programına erişebiliyor olmanız gerekir. OpenSSL’yi yüklemek için [OpenSSL](https://www.openssl.org) veya [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries) sayfasına gidin.

Sertifika yükleme hakkında daha fazla bilgi ve yönergeler için bkz. [Windows için sertifika oluşturma ve yükleme](./custom-visual-develop-tutorial.md#windows).

## <a name="create-a-certificate-on-macos-x"></a>macOS X'te sertifika oluşturma

OpenSSL yardımcı programı genellikle macOS X işletim sistemiyle birlikte sunulur.

Aşağıdaki komutlardan birini çalıştırarak da OpenSSL yardımcı programını yükleyebilirsiniz:

- *Brew* paket yöneticisinden:
  
  ```cmd
  brew install openssl
  brew link openssl --force
  ```

- *MacPorts* kullanarak:
  
  ```cmd
  sudo port install openssl
  ```

OpenSSL yardımcı programını yükledikten sonra yeni bir sertifika oluşturmak için aşağıdaki komutu çalıştırın:

```cmd
pbiviz --install-cert
```

Daha fazla bilgi ve yönergeler için bkz. [OS X için sertifika oluşturma ve yükleme](./custom-visual-develop-tutorial.md#osx).

## <a name="create-a-certificate-on-linux"></a>Linux'ta sertifika oluşturma

OpenSSL yardımcı programı genellikle Linux işletim sistemiyle birlikte sunulur.

Başlamadan önce `openssl` ve `certutil` öğelerinin yüklendiğinden emin olmak için aşağıdaki komutları çalıştırın:

```sh
which openssl
which certutil
```

`openssl` ve `certutil` yüklü değilse `openssl` ve `libnss3` yardımcı programlarını yükleyin.

### <a name="create-the-ssl-configuration-file"></a>SSL yapılandırma dosyasını oluşturma

*/tmp/openssl.cnf* adlı bir dosya oluşturun ve içine aşağıdaki metni ekleyin:

```
authorityKeyIdentifier=keyid,issuer
basicConstraints=CA:FALSE
keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
subjectAltName = @alt_names

[ alt_names ]
DNS.1=localhost
```

### <a name="generate-root-certificate-authority"></a>Kök sertifika yetkilisini oluşturma

Yerel sertifikaları imzalamak üzere kök sertifika yetkilisini (CA) oluşturmak için aşağıdaki komutları çalıştırın:

```sh
touch $HOME/.rnd
openssl req -x509 -nodes -new -sha256 -days 1024 -newkey rsa:2048 -keyout /tmp/local-root-ca.key -out /tmp/local-root-ca.pem -subj "/C=US/CN=Local Root CA/O=Local Root CA"
openssl x509 -outform pem -in /tmp/local-root-ca.pem -out /tmp/local-root-ca.crt
```

### <a name="generate-a-certificate-for-localhost"></a>localhost için sertifika oluşturma 

Oluşturulan CA ve *openssl.cnf* öğelerini kullanarak `localhost` için bir sertifika oluşturmak üzere aşağıdaki komutları çalıştırın:

```sh
PBIVIZ=`which pbiviz`
PBIVIZ=`dirname $PBIVIZ`
PBIVIZ="$PBIVIZ/../lib/node_modules/powerbi-visuals-tools/certs"
# Make sure that $PBIVIZ contains the correct certificate directory path. ls $PBIVIZ should list 'blank' file.
openssl req -new -nodes -newkey rsa:2048 -keyout $PBIVIZ/PowerBIVisualTest_private.key -out $PBIVIZ/PowerBIVisualTest.csr -subj "/C=US/O=PowerBI Visuals/CN=localhost"
openssl x509 -req -sha256 -days 1024 -in $PBIVIZ/PowerBIVisualTest.csr -CA /tmp/local-root-ca.pem -CAkey /tmp/local-root-ca.key -CAcreateserial -extfile /tmp/openssl.cnf -out $PBIVIZ/PowerBIVisualTest_public.crt
```

### <a name="add-root-certificates"></a>Kök sertifikaları ekleme

Kök sertifikayı Chrome tarayıcısının veritabanına eklemek için şunu çalıştırın:

```sh
certutil -A -n "Local Root CA" -t "CT,C,C" -i /tmp/local-root-ca.pem -d sql:$HOME/.pki/nssdb
```

Kök sertifikayı Mozilla Firefox tarayıcısının veritabanına eklemek için şunu çalıştırın:

```sh
for certDB in $(find $HOME/.mozilla* -name "cert*.db")
do
certDir=$(dirname ${certDB});
certutil -A -n "Local Root CA" -t "CT,C,C" -i /tmp/local-root-ca.pem -d sql:${certDir}
done
```

Sistem genelinde geçerli olacak bir kök sertifika eklemek için şunu çalıştırın:

```sh
sudo cp /tmp/local-root-ca.pem /usr/local/share/ca-certificates/
sudo update-ca-certificates
```

### <a name="remove-root-certificates"></a>Kök sertifikaları kaldırma

Bir kök sertifikayı kaldırmak için şunu çalıştırın:

```sh
sudo rm /usr/local/share/ca-certificates/local-root-ca.pem
sudo update-ca-certificates --fresh
```

## <a name="generate-a-certificate-manually"></a>Sertifikayı el ile oluşturma

OpenSSL kullanarak SSL sertifikasını el ile de oluşturabilirsiniz. Sertifikalarınızı oluşturmak için istediğiniz aracı kullanabilirsiniz.

OpenSSL yardımcı programı yüklüyse yeni bir sertifika oluşturmak için şu komutu çalıştırın:

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBIVisualTest_private.key -out PowerBIVisualTest_public.crt -days 365
```

Genellikle aşağıdakilerden birini çalıştırarak `PowerBI-visuals-tools` web sunucusu sertifikalarını bulabilirsiniz:

- Araçların genel örneği için:
  
  ```cmd
  %appdata%\npm\node_modules\PowerBI-visuals-tools\certs
  ```

- Araçların yerel örneği için:
  
  ```cmd
  <Power BI visual project root>\node_modules\PowerBI-visuals-tools\certs
  ```

### <a name="pem-format"></a>PEM biçimi

Gizliliği Artırılmış Posta (PEM) sertifika biçimini kullanıyorsanız sertifika dosyasını *PowerBIVisualTest_public.crt*, özel anahtarı ise *PowerBIVisualTest_private.key* olarak kaydedin.

### <a name="pfx-format"></a>PFX biçimi

Kişisel Bilgi Değişimi (PFX) sertifika biçimini kullanıyorsanız sertifika dosyasını *PowerBIVisualTest_public.pfx* olarak kaydedin.

PFX sertifika dosyanız için şifre gerekiyorsa:

1. Yapılandırma dosyasında şunu belirtin:
   
   ```cmd
   \PowerBI-visuals-tools\config.json
   ```
   
1. `server` bölümünde \<YOUR PASSPHRASE> yer tutucusunun yerine kendi şifrenizi belirtin:

    ```cmd
    "server":{
        "root":"webRoot",
        "assetsRoute":"/assets",
        "privateKey":"certs/PowerBIVisualTest_private.key",
        "certificate":"certs/PowerBIVisualTest_public.crt",
        "pfx":"certs/PowerBIVisualTest_public.pfx",
        "port":"8080",
        "passphrase":"<YOUR PASSPHRASE>"
    }
    ```

## <a name="next-steps"></a>Sonraki adımlar
- [Power BI görseli geliştirme](custom-visual-develop-tutorial.md)
- [Örnek Power BI görselleri](samples.md)
- [Power BI görsellerini AppSource'ta yayımlama](office-store.md)