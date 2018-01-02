## <a name="faq"></a>SSS
**Soru:** Power BI hizmetindeki bir veri kümesi için önceden roller/kurallar oluşturduysam ne yapmam gerekir? Herhangi bir işlem yapmasam da bunlar çalışmaya devam eder mi?  
**Cevap:** Hayır. Görseller düzgün şekilde oluşturulmaz. Power BI Desktop uygulamasında rolleri/kuralları tekrar oluşturmanız ve Power BI hizmetinde yayımlamanız gerekir.

**Soru:** Bu rolleri Analysis Services veri kaynakları için oluşturabilir miyim?  
**Yanıt:** Verileri Power BI Desktop'a aktardıysanız yapabilirsiniz. Canlı bağlantı kullanıyorsanız Power BI hizmetinden RLS yapılandırması gerçekleştiremezsiniz. Bu yapılandırma şirket içi Analysis Services modelinde tanımlanır.

**Soru:** Kullanıcılarımın erişebileceği sütunları veya ölçüleri sınırlamak için RLS kullanabilir miyim?  
**Cevap:** Hayır. Belirli bir veri satırına erişimi olan kullanıcılar, ilgili satırdaki tüm veri sütunlarını görebilir.

**Soru:** RLS, ayrıntılı verileri gizlerken görsellerde özetlenmiş verilere erişim sunmamı sağlar mı?  
**Yanıt:** Hayır, belirli veri satırlarının güvenliğini sağlayabilirsiniz ancak kullanıcılar ayrıntıları veya özetlenmiş verileri her zaman görebilir.

