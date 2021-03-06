---
title: Power BI Desktop'ı başlatma ile ilgili sorunları giderme
description: Power BI Desktop'ı başlatma ile ilgili sorunları giderme
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: troubleshooting
ms.date: 11/14/2020
LocalizationGroup: Troubleshooting
ms.openlocfilehash: c41f8f9b23ef57d5dd6fd4b851918b7ffa5904a0
ms.sourcegitcommit: ab28cf07b483cb4b01a42fa879b788932bba919d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98226951"
---
# <a name="troubleshoot-opening-power-bi-desktop"></a>Power BI Desktop uygulamasını açma sorunlarını giderme

Bu makalede Power BI'ın açılamadığı çeşitli durumlar açıklanır ve bunlara çözüm sağlanır. 

## <a name="resolve-issues-with-opening-encrypted-pbix-files"></a>Şifrelenmiş PBIX dosyalarını açma sorunlarını çözme

Bilgi korumasını desteklemeyen bir Power BI Desktop sürümü kullanarak şifrelenmiş PBIX dosyalarını açamazsınız.

Power BI Desktop'ı kullanmaya devam etmeniz gerekiyorsa, önerilen çözüm bu uygulamayı bilgi korumasını destekleyen bir sürümü güncelleştirmektir. [Power BI Desktop'ın en son sürümünü](https://www.microsoft.com/download/confirmation.aspx?id=58494) indirebilirsiniz (bu bağlantı, yükleme yürütülebilir dosyasını doğrudan indirme bağlantısıdır). Power BI Desktop'ın en son sürümü bilgi korumasını destekler ve şifrelenmiş PBIX dosyalarının şifresini çözüp bu dosyaları açabilir.

###

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Şirket içi veri ağ geçidi ve Power BI Desktop ile ilgili sorunları giderme

Power BI Desktop’ta eski *Power BI Şirket içi veri ağ geçidi* sürümlerini yüklemiş ve çalıştırıyor olan kullanıcıların, Power BI şirket içi veri ağ geçidinin yerel makinedeki adlandırılmış kanallara uyguladığı yönetimle ilgili ilke kısıtlamaları nedeniyle Power BI Desktop uygulamasını açması engellenebilir.

Şirket içi veri ağ geçidiyle ilgili sorunları gidermek ve Power BI Desktop’ın açılmasını sağlamak için kullanabileceğiniz üç seçenek vardır:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>1\. Çözüm: Power BI Şirket içi veri ağ geçidinin en son sürümünü yükleyin

Power BI şirket içi veri ağ geçidinin en son sürümü yerel makinede adlandırılmış kanal kısıtlaması gerçekleştirmez ve Power BI Desktop uygulamasının düzgün şekilde açılmasını sağlar. Power BI Şirket içi veri ağ geçidini kullanmaya devam etmeniz gerekiyorsa sizin için önerilen çözüm bunu güncelleştirmenizdir. [Power BI Şirket içi veri ağ geçidinin en son sürümünü](https://go.microsoft.com/fwlink/?LinkId=698863) indirebilirsiniz. Bunun yükleme dosyasının doğrudan bağlantısı vardır.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-microsoft-service"></a>2\. Çözüm: Microsoft’un Power BI Şirket içi veri ağ geçidi hizmetini kaldırın ve ya durdurun

Artık gerekmiyorsa Power BI Şirket içi veri ağ geçidi hizmetini kaldırabilirsiniz. Öte yandan isterseniz Microsoft’un Power BI Şirket içi veri ağ geçidi hizmetini durdurabilirsiniz; bu işlem ilke kısıtlamasını kaldırır ve Power BI Desktop’ın açılmasına izin verir.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>3\. Çözüm: Power BI Desktop uygulamasını yönetici ayrıcalığıyla çalıştırın

Bunun yerine Power BI Desktop uygulamasını yönetici olarak başlatabilir, bu yolla başarıyla açılmasını sağlayabilirsiniz. Daha önce açıklandığı gibi, yine de Power BI şirket içi veri ağ geçidinin en son sürümünü yüklemeniz önerilir.

Power BI Desktop çok işlemli bir mimari olarak tasarlanmıştır ve bu işlemlerden bazıları Windows adlandırılmış kanallarını kullanarak iletişim kurar. Bu adlandırılmış kanalları engelleyen başka işlemler de olabilir. Virüsten koruma yazılımının ya da güvenlik duvarlarının kanalları engellediği veya trafiği belirli bir bağlantı noktasına yeniden yönlendirdiği durumlar gibi, güvenlik nedeniyle böyle bir engel oluşuyor olabilir. Power BI Desktop’ı yönetici ayrıcalığıyla açmak bu sorunu çözülebilir. Yönetici ayrıcalığıyla açamıyorsanız, adlandırılmış kanalların düzgün iletişim kurmasını engelleyen güvenlik kurallarını saptamak için yöneticinize danışın. Daha sonra, Power BI Desktop’ı ve ilgili alt işlemlerini izin verilenler listesine ekleyin.

## <a name="resolve-issues-when-connecting-to-sql-server"></a>SQL Server'a bağlanma sorunlarını giderme

SQL Server veritabanına bağlanmayı denediğinizde aşağıdaki metne benzer bir hata iletisi alıyor olabilirsiniz:

`"An error happened while reading data from the provider:`\
`'Could not load file or assembly 'System.EnterpriseServices, Version=4.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxx' or one of its dependencies.`\
`Either a required impersonation level was not provided, or the provided impersonation level is invalid. (Exception from HRESULT: 0x80070542)'"`

Genellikle SQL Server bağlantısını kurmadan önce Power BI Desktop’ı yönetici olarak açarak bu sorunu çözebilirsiniz.

Power BI Desktop’ı yönetici olarak açıp bağlantıyı kurduktan sonra, gerekli DLL’ler uygun şekilde kaydedilir. Bundan sonra, Power BI Desktop’ın yönetici olarak açılması gerekmez. SQL Server'a alternatif Windows kimlik bilgileriyle kullandığınız durumlarda her bağlantı öncesinde Power BI Desktop'ı yönetici olarak açmanız gerekir.

## <a name="get-help-with-other-launch-issues"></a>Diğer başlatma sorunlarıyla ilgili yardım alma

Power BI Desktop ile ilgili mümkün olduğu kadar çok sayıda sorunu ele almak için elimizden geleni yapıyoruz. Birçok müşteriyi etkileyebilecek sorunları düzenli olarak kontrol edip makalelerimizde bu sorunlara yer veriyoruz.

Power BI Desktop uygulamasını açma sorunları Şirket içi veri ağ geçidiyle ilgili değilse veya önceki çözümler sorunu gidermediyse, sorununuzun tanımlanması ve çözülmesine yardımcı olmaları için *Power BI destek ekibine* (<https://support.powerbi.com>) destek olayı gönderebilirsiniz.

Gelecekte Power BI Desktop’la ilgili başka sorunlarla karşılaşma olasılığına karşı izlemeyi açmak ve günlük dosyalarını toplamak yararlı olur. Günlük dosyaları sorunu yalıtmaya ve belirlemeye yardımcı olabilir. İzlemeyi açmak için **Dosya** > **Seçenekler ve ayarlar** > **Seçenekler**’i belirtin, **Tanılama**’yı ve ardından **İzlemeyi etkinleştir**’i seçin. Bu seçeneği belirlemek için Power BI Desktop’ın çalışıyor olması gerekir ama ileride ortaya çıkabilecek Power BI Desktop ‘ı açma sorunları konusunda faydalı olacağını düşünüyoruz.
