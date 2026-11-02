# UiPath Academy – Generate Yearly Report | Dispatcher

## 📌 Proje Hakkında

Bu proje, **UiPath Academy Automation Developer Professional** eğitimi kapsamında geliştirilen *Generate Yearly Report* otomasyonunun Dispatcher aşamasıdır.

Projenin amacı, ACME System 1 uygulamasındaki Work Item kayıtlarını inceleyerek belirlenen kriterlere uygun işlemleri UiPath Orchestrator kuyruğuna aktarmaktır.

Proje, **Robotic Enterprise Framework (REFramework)** mimarisi kullanılarak geliştirilmiştir.

Bu çalışmanın öne çıkan özelliği, geliştirme sürecinin **UiPath Autopilot'a verilen komutlar aracılığıyla yapay zekâ desteğiyle gerçekleştirilmiş olmasıdır.** Böylece doğal dil ile otomasyon geliştirme yaklaşımını deneyimleme fırsatı elde edilmiştir.

## 🎯 Projenin Amacı

- ACME System 1 uygulamasına otomatik giriş yapmak.
- Work Items sayfalarındaki kayıtları okumak.
- `Type = WI4` ve `Status = Open` kriterlerine uygun kayıtları filtrelemek.
- Uygun kayıtları UiPath Orchestrator üzerindeki `Acme4Queue` kuyruğuna aktarmak.
- Performer projesinin işleyeceği verileri hazırlamak.

## ⚙️ Kullanılan Teknolojiler

- UiPath Studio
- UiPath Autopilot
- Robotic Enterprise Framework (REFramework)
- UiPath Orchestrator

## 🔄 Otomasyonun Çalışma Mantığı

1. REFramework başlatılır ve `Config.xlsx` üzerinden yapılandırma bilgileri okunur.
2. Orchestrator üzerinde tanımlanan Credential Asset kullanılarak ACME System 1 uygulamasına giriş yapılır.
3. Work Items sayfasına gidilir.
4. Sayfalardaki kayıtlar DataTable olarak alınır.
5. `WI4` türünde ve `Open` durumundaki kayıtlar filtrelenir.
6. Filtrelenen kayıtlar `Bulk Add Queue Items` aktivitesiyle `Acme4Queue` kuyruğuna eklenir.
7. Sonraki sayfaya geçilerek aynı işlemler tekrarlanır.
8. İşlenecek başka sayfa kalmadığında otomasyon tamamlanır.

## 🏗️ REFramework Özelleştirmesi

Standart REFramework yapısında transaction verisi genellikle `QueueItem` olarak ele alınırken, bu projede `TransactionItem` veri tipi `Int32` olarak düzenlenmiştir.

Her transaction, ACME System 1 üzerindeki bir Work Items sayfasını temsil eder.

Bu yaklaşım sayesinde sayfa numaraları üzerinden ilerleyen, verileri filtreleyen ve kuyruğa aktaran bir Dispatcher mimarisi oluşturulmuştur.

## 🤖 Yapay Zekâ Destekli Geliştirme

Bu projede UiPath Autopilot kullanılarak yapay zekâ destekli otomasyon geliştirme yaklaşımı uygulanmıştır.

Geliştirme sürecinde iş gereksinimleri ve otomasyon adımları doğal dil komutlarıyla Autopilot'a aktarılmıştır.

Bu çalışma, yapay zekâ araçlarının RPA geliştirme süreçlerinde nasıl kullanılabileceğini deneyimlemeyi ve komutlarla otomasyon oluşturma yaklaşımını öğrenmeyi amaçlamaktadır.

## 🔗 Orchestrator Yapılandırması

| Bileşen | Değer |
|---|---|
| Queue | `Acme4Queue` |
| Credential Asset | `System1_Credential` |
| Framework | REFramework |
| Transaction Type | `Int32` |
| Configuration | `Config.xlsx` |

## 📤 Proje Çıktısı

Dispatcher projesinin çıktısı, ACME System 1 uygulamasındaki uygun Work Item kayıtlarının Orchestrator kuyruğuna aktarılmasıdır.

Bu kayıtlar, ayrı bir proje olarak geliştirilen **Performer** otomasyonu tarafından işlenmektedir.

**Mimari:** Dispatcher → Orchestrator Queue → Performer

## 📚 Eğitim

Bu proje, **UiPath Academy – Automation Developer Professional** sertifikasyon sürecindeki *Generate Yearly Report* uygulaması kapsamında tamamlanmıştır.

---

**Not:** Bu repository eğitim ve portföy amaçlı hazırlanmıştır. Çalıştırmak için uygun UiPath Orchestrator yapılandırması ve ACME System 1 test ortamına erişim gereklidir.
