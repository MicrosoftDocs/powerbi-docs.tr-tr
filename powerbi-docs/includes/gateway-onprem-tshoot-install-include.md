## <a name="update-to-the-latest-version"></a>Son sürüme güncelleştirme
Ağ geçidi sürümü güncel olmadığında birçok sorun ortaya çıkabilir.  En son sürümü kullandığınızdan emin olmak, her zaman için iyi bir uygulamadır.  Ağ geçidini bir ay veya daha uzun süredir güncelleştirmediyseniz ağ geçidinin en son sürümünü yükleyerek, sorunu yeniden oluşturup oluşturamadığınızı görmenizde yarar vardır.

## <a name="common-issues"></a>Sık karşılaşılan sorunlar
Aşağıda, İnternet erişiminin kısıtlandığı ortamlarda yaygın olarak karşılaşılan birkaç sorun ve birçok müşteriye yardımcı olmuş çözümler verilmiştir.

### <a name="authentication-to-proxy-server"></a>Ara sunucu kimlik doğrulaması
Ara sunucunuz bir etki alanı kullanıcı hesabında kimlik doğrulaması gerektirebilir. Varsayılan olarak ağ geçidi, Windows hizmeti oturum açma kullanıcısı için bir Hizmet SID'si kullanır. Oturum açma kullanıcısının bir etki alanı kullanıcısı olarak değiştirilmesi bu konuda yardımcı olabilir. Daha fazla bilgi için bkz. [Ağ geçidi hizmet hesabını etki alanı kullanıcısı olarak değiştirme](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>Ara sunucunuzun yalnızca 80 ve 443 numaralı bağlantı noktalarının trafiğine izin vermesi
Bazı ara sunucular trafiği yalnızca 80 ve 443 numaralı bağlantı noktalarıyla kısıtlar. Varsayılan olarak, Azure Service Bus iletişimi, 443 dışındaki bağlantı noktaları üzerinde gerçekleşir.

Ağ geçidinin Azure Service Bus ile doğrudan TCP yerine HTTPS kullanarak iletişim kurmasını zorlayabilirsiniz. *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* dosyasını değiştirmeniz gerekir. `AutoDetect` değerini `Https` olarak değiştirin. Bu dosya varsayılan olarak *C:\Program Files\On-premises data gateway* konumunda bulunur.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>Yükleme
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Hata: Kullanıcı gruba eklenemedi.  (-2147463168   PBIEgwService   Performance Log Users   )
Ağ geçidini bir etki alanı denetleyicisine yüklemeye çalışıyorsanız bu hatayı alabilirsiniz. Etki alanı denetleyicisinde dağıtım desteklenmemektedir. Ağ geçidini etki alanı denetleyicileri dışındaki bir makineye dağıtmanız gerekir.

### <a name="installation-fails"></a>Yükleme başarısız oldu
Yükleme makinesindeki virüsten koruma yazılımı eskiyse yükleme hatalarıyla karşılaşabilirsiniz. Virüsten koruma yazılımını güncelleştirebilir veya yalnızca ağ geçidi yüklemesi tamamlanana kadar virüsten koruma yazılımını devre dışı bırakıp daha sonra yeniden etkinleştirebilirsiniz.

