# SQL Nedir?

**SQL (Structured Query Language)**
 - Yapısal Sorgulama Dili
 - Verinin ana dili SQL dilidir. 
 - En Büyük Veritabanı sistemi -> Microsoft SQL.
 - Veritabanı yönetimi ve veri sorgulama için kullanılan standart bir dildir.

## Neden SQL?

- Veritabanı yönetimi için standart dildir.
- Microsoft SQL Server, MySQL, PostgreSQL, Oracle gibi sistemlerde kullanılır.
- Tablolarla çalışır, verileri sorgulamak ve yönetmek için kullanılır.

## SQL Ne İşe Yarar?

- Veritabanı oluşturmak
- Veri eklemek
- Veri silmek
- Verileri sorgulamak
- Verileri güncellemek

## Veritabanı Sunucu:

- İstemci Bilgisayar -> İstemci bağlanmak istiyor. Kullanıcı adı ve şifresini veriyor. 
- Veritabanı sunucu ise kontrol ediyor. Yetkili bir kullanıcı mı diye. Daha sonra hatalıysa yanlış diyor doğruysa bağlantı kabul edilir.

## Temel SQL Komutları

- `SELECT`: Veri çekmek için. Select*From Tablo ismi. İstemci bilgisayarın anlayacğı şekilde yazar. 
- `INSERT INTO`: Veri eklemek için.Yeni kayıt eklendi. 
INSERT INTO MUSTERİLER (AD, SOYAD)  
VALUES ('OMER', 'COLAKOGLU')
- `DELETE`: Veri silmek için
- `UPDATE`: Veri güncellemek için
- `CREATE TABLE`: Yeni tablo oluşturmak için

## İlişkisel Veritabanı Nedir?

İlişkisel veritabanları (RDBMS) verileri tablolar halinde tutar, ilişkiler kurar ve veri tekrarını azaltır.

Orderfiche:

-Paymenttype:kredi kartı (1)
-CustomerID 
-Deliveryttype
-Date
-Netprıce
-Totalvat
-Totalprice

Orderline: 

-ID
-ITEMID
-Amount
-Unıtprıce
-Vat
-Vatamount
-Nettotal
-Total

Veritabanı Yönetim Sistemleri
1. Microsoft SQl Server (t-sql)
2. Oracle (pl sql)
3. MySQL
4. PostgreSQL
5. IBM DB2

## BTK Derslerinden Notlar

- SQL ilişkisel veritabanlarında kullanılır.
- İlk derslerde SELECT ile veri çekmeyi öğrendik.
- SQL büyük harflerle yazılsa da küçük harf de kabul eder.

## Bu sorulara yanıt verebilir misin?
SQL: 
Veritabanı Yönetim Sistemi:
Veritabanı Sunucusu:
Client-Server Mimarisi nasıl çalışır?
İlişkisel Veritabanı:
Veritabanı Yönetim Sistemi yazılımları hangileridir?

# SQL Server

SSMS: SQL Server Management Studio
SSIS: Integration Services
SSRS: Reporting Services
SSAS: Analysis Services

## SQL Server Kurulumu ve Yapılandırma
- Kurulum sırasında Collation, Authentication türleri gibi ayarlar yapılır.
- İlk tablo SSMS üzerinden veya T-SQL komutlarıyla oluşturulur.
- SQL Server sadece T-SQL komutları ile çalışır (arka planda).

# Sanalallaştırma:
VNWare?
-Nasıl kurulur?
-üzerinde sanal bir işletim sistemi nasıl kurulur?
SQL Server nasıl kurulur? seçtiğim parametreler?
SQL Server sürümleri nelerdir?
SQL Server MAnagement Studio (SSMS):
SQL Server hizmetleri:
Collation:

SQL KURULDU İLK DATABASE TABLE YAPILDI:
- management studio kullanımı
- sql server authentication türleri
- sql server üzerinde tablo oluşturma
- management studio üzerinden tabloya kayıt girme
- sql server'ın geri planda sadece tsql komutları çalıştırıyor olması. 