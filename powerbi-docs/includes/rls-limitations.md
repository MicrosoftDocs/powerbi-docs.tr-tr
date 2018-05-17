## <a name="limitations"></a>Sınırlamalar
Bulut modellerindeki satır düzeyi güvenlik hakkındaki geçerli sınırlamalar burada liste halinde verilmiştir.

* Power BI hizmetinde tanımlanmış rolleriniz ve kurallarınız varsa bunları Power BI Desktop'ta tekrar oluşturmanız gerekir.
* RLS özelliğini yalnızca Power BI Desktop istemcisi kullanılarak oluşturulan veri kümelerinde tanımlayabilirsiniz. RLS özelliğini Excel ile oluşturulmuş olan veri kümeleri için etkinleştirmek isterseniz öncelikle dosyalarınızı PBIX biçimine dönüştürmeniz gerekir. [Daha fazla bilgi](../desktop-import-excel-workbooks.md)
* Yalnızca ETL ve DirectQuery bağlantıları desteklenir. Analysis Services canlı bağlantıları şirket içi modelde işlenir.
* Soru-Cevap ve Cortana için RLS desteği henüz sunulmamaktadır. Tüm modellerde RLS yapılandırıldıysa panolar için Soru-Cevap giriş kutusu görünmez. Bu özellik yol haritasına eklenmiş durumdadır ancak kesin tarih mevcut değildir.
* Dış paylaşım şu anda RLS kullanan veri kümeleri için desteklenmemektedir.
* Herhangi bir model için güvenlik rollerine atanabilecek maksimum Azure AD sorumlusu (bireysel kullanıcı veya güvenlik grubu) sayısı 1000'dir. Rollere çok sayıda kullanıcı atamak için bireysel kullanıcı yerine güvenlik grubu atadığınızdan emin olun.

## <a name="known-issues"></a>Bilinen sorunlar
Bilinen sorunların biri, önceden yayımlanmış olan bir içeriği Power BI Desktop uygulamasından yayımlamaya çalıştığınızda ortaya çıkan bir hata iletisidir. Senaryo aşağıdaki gibidir.

1. Anna, Power BI hizmetinde yayımlanmış ve RLS yapılandırması yapılmış bir veri kümesine sahiptir.
2. Anna raporu Power BI Desktop uygulamasında güncelleştirip tekrar yayımlar.
3. Anna bir hata alır.

**Geçici çözüm:** Bu sorun giderilene kadar Power BI Desktop dosyasını Power BI hizmetinden yayımlayın. Bu işlemi, **Veri Al** > **Dosyalar** adımlarını izleyerek yapabilirsiniz. 

