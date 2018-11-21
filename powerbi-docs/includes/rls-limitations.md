## <a name="limitations"></a>Sınırlamalar

Bulut modellerindeki satır düzeyi güvenlik hakkındaki geçerli sınırlamalar burada liste halinde verilmiştir.

* Power BI hizmetinde tanımlanmış olduğunuz roller ve kurallar varsa bunları Power BI Desktop'ta tekrar oluşturmanız gerekir.

* RLS özelliğini yalnızca Power BI Desktop ile oluşturulan veri kümelerinde tanımlayabilirsiniz. RLS özelliğini Excel ile oluşturulmuş olan veri kümeleri için etkinleştirmek isterseniz öncelikle dosyalarınızı Power BI Desktop (PBIX) biçimine dönüştürmeniz gerekir. [Daha fazla bilgi](../desktop-import-excel-workbooks.md)

* Yalnızca ETL ve DirectQuery bağlantıları desteklenir. Analysis Services canlı bağlantıları şirket içi modelde işlenir.

* Soru-Cevap ve Cortana için RLS desteği henüz sunulmamaktadır. Tüm modellerde RLS yapılandırıldıysa panolar için Soru-Cevap giriş kutusu görünmez. Bu özellik yol haritasına eklenmiş durumdadır ancak kesin tarih mevcut değildir.

## <a name="known-issues"></a>Bilinen sorunlar

Bilinen sorunların biri, önceden yayımlanmış olan bir raporu Power BI Desktop uygulamasından yayımlamaya çalıştığınızda ortaya çıkan hata iletisidir. Senaryo aşağıdaki gibidir.

1. Anna, Power BI hizmetinde yayımlanmış ve RLS yapılandırması yapılmış bir veri kümesine sahiptir.

1. Anna raporu Power BI Desktop uygulamasında güncelleştirip tekrar yayımlar.

1. Anna bir hata alır.

**Geçici çözüm:** Bu sorun giderilene kadar Power BI Desktop dosyasını Power BI hizmetinden yayımlayın. Bu işlemi, **Veri Al** > **Dosyalar** adımlarını izleyerek yapabilirsiniz.
