### Merhaba, ben Enes 👋

İstanbul'da yaşayan bir backend geliştiriciyim. Ağırlıklı olarak **C#, .NET ve SQL** ile çalışıyorum. Fintech tarafında geçen yıllarım bana verinin tutarlı kalmasını, bir hatanın loglardan geriye doğru izlenebilmesini ve yetkilerin doğru yerde durmasını önemsemeyi öğretti. Projelerimde de en çok bu konular üzerine düşünüyorum.

Çalıştığım ekiplere bildiklerimi getirmeyi, karşılığında da kendimden deneyimli insanlardan öğrenmeyi seviyorum. Şu an **yeni bir pozisyon arıyorum**.

#### Üzerinde çalıştığım projeler

**[TodayEcommerce.Core](https://github.com/enesvct/TodayEcommerce.Core)** · .NET 8, PostgreSQL, Redis, Elasticsearch, Hangfire

Bir e-ticaret altyapısının ürün, sipariş ve stok kısmı. Amacım CRUD yazmak değil, gerçek hayatta karşılaşılan problemleri küçük bir kod tabanında çözmekti:
- Sipariş ve olayları aynı transaction içinde yazan **outbox pattern**, böylece veritabanı ile arama indeksi birbirinden kopmuyor.
- Aynı anda son ürünü almaya çalışan iki istek için **optimistic concurrency**, iki kez basılan "Satın al" butonu için **idempotency key**.
- Modüller arası "geri al" olmadığı için **saga ve telafi** adımları; mesajları bilerek ters sırada teslim eden testlerle doğruladım.
- Modüler monolit ve Clean Architecture sınırları **mimari testleriyle** korunuyor, toplamda 160'tan fazla test var.

**[TodayDbGate](https://github.com/enesvct/TodayDbGate)** · .NET, MCP, PostgreSQL / SQL Server / MySQL

Yapay zekâ asistanlarının şirket veritabanlarına kontrollü şekilde erişmesini sağlayan bir MCP gateway. Asistan veriyi görebiliyor ama ne görebileceğine ve ne yapabileceğine gateway karar veriyor:
- Her bağlantı için token bazlı **salt okunur / okuma-yazma** yetkisi; salt okunur sorgular ayrıca her zaman geri alınan bir transaction içinde çalışıyor.
- Kişisel veriler için kolon ve tablo bazlı **maskeleme**: kısmi gizleme, HMAC ile sabit takma ad (gruplama ve sayma bozulmadan) ya da tamamen engelleme.
- Çalışan her sorgu **audit log**'a yazılıyor ve yönetim panelinden canlı izlenebiliyor.

**[Fikir Kuluçkası](https://github.com/EmaHOLDING/ideamanagment)** · Next.js 16, TypeScript, Supabase

Ekiplerin fikirlerini tek panoda toplayıp birlikte değerlendirdiği bir çalışma alanı. Kurum hesabında duruyor, kodunu ben yazdım:
- Yetki kuralları uygulama kodunda değil, PostgreSQL'de **Row Level Security** ile tanımlı ve CI'da **pgTAP** testleriyle doğrulanıyor.
- Her düzenleme yeni bir **versiyon** olarak saklanıyor, kimin neyi değiştirdiği görülebiliyor.
- Supabase Realtime ile pano değişiklikleri herkese **anında** yansıyor; kimin hangi kartla çalıştığı görünüyor.

#### Kullandıklarım

C#, T-SQL, ASP.NET Core (MVC, Web API), Entity Framework, Dapper, MS SQL Server, PostgreSQL, Redis, Elasticsearch, Hangfire, Docker, Git. Son zamanlarda TypeScript ve Next.js ile de çalışıyorum.

📫 [LinkedIn](https://linkedin.com/in/enesakkus) · enesakkus3455@gmail.com

---

<details>
<summary><b>🇬🇧 English</b></summary>

<br>

### Hi, I'm Enes 👋

I'm a backend developer based in Istanbul, working mostly with **C#, .NET and SQL**. My years in fintech taught me to care about data staying consistent, about being able to trace an error back through the logs, and about permissions living in the right place. Those are the things I think about most in my projects too.

I like bringing what I know to the teams I work with, and learning from people more experienced than me in return. I'm currently **open to new opportunities**.

#### Projects

**[TodayEcommerce.Core](https://github.com/enesvct/TodayEcommerce.Core)** · .NET 8, PostgreSQL, Redis, Elasticsearch, Hangfire

The product, order and stock core of an e-commerce backend. The goal wasn't CRUD, but solving real-world problems in a small codebase:
- An **outbox pattern** that writes orders and events in the same transaction, so the database and the search index never drift apart.
- **Optimistic concurrency** for two requests racing for the last item, and an **idempotency key** for a double-clicked "Buy" button.
- **Saga and compensation** steps, since there is no rollback across modules, verified by tests that deliver messages in the wrong order on purpose.
- Modular monolith and Clean Architecture boundaries guarded by **architecture tests**, 160+ tests in total.

**[TodayDbGate](https://github.com/enesvct/TodayDbGate)** · .NET, MCP, PostgreSQL / SQL Server / MySQL

An MCP gateway that lets AI assistants reach company databases in a controlled way. The assistant can see the data, but the gateway decides what it sees and what it can do:
- Per-connection, token-based **read-only / read-write** access; read-only queries also run in a transaction that is always rolled back.
- Column and table level **masking** of personal data: partial hiding, stable HMAC pseudonyms (so grouping and counting still work), or blocking entirely.
- Every query goes to an **audit log** that can be watched live from the admin panel.

**[Idea Incubator](https://github.com/EmaHOLDING/ideamanagment)** · Next.js 16, TypeScript, Supabase

A shared board where teams collect and discuss ideas. It lives under an organization account, but I wrote it:
- Access rules live in PostgreSQL as **Row Level Security** policies, not in app code, and are checked in CI with **pgTAP** tests.
- Every edit is stored as a new **version**, so you can see who changed what.
- Board changes show up for everyone **in real time** with Supabase Realtime, including who is working on which card.

#### Tools

C#, T-SQL, ASP.NET Core (MVC, Web API), Entity Framework, Dapper, MS SQL Server, PostgreSQL, Redis, Elasticsearch, Hangfire, Docker, Git. Lately also TypeScript and Next.js.

📫 [LinkedIn](https://linkedin.com/in/enesakkus) · enesakkus3455@gmail.com

</details>
