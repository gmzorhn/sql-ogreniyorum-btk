## TEMEL SQL KOMUTLARI

1. DATA MANİPÜLASYON KOMUTLARI:
- select: veritabanındaki tablolardan kayıt çeker.
- ınsert: tabloya yeni kayıt ekler. 
- truncate: tablonun içini boşaltır. (delete tablonun birkaçını siler komut verirsin ama truncate afbrika ayarına geri döner.)

2. VERİTABANI MANİPÜLASYON KOMUTLARI (create, alter, drop)
- create: database oluşrurma, veritabanı nesnesini oluşturur. 
- alter: veritabanı nesnesi özelliğini değiştir.
- drop: veritabanı nesnesini siler.

* alter table: tablonun özelliklerini değiştir.
* drop ındex: ındexi siler. 

## SELECT
- Tablodaki verileri listelemek için kullanılır.
- Verileri sorgular, çeker.

```sql
SELECT 
KOLON1,KOLON2,KOLON3,...
FROM TABLOADI
WHERE <ŞARTLAR>

USE DENEME
SELECT ID,CUSTOMERNAME
FROM
CUSTOMERS

**VEYA**

USE DENEME
SELECT * FROM
CUSTOMERS
```

BU TABLODAKİ VERİLERİN İLK SEÇENEĞİNDE SADECE ID VE CUSTOMERNAME GELİR. AMA İKİNCİ KOD TÜM TABLOYU GÖSTERİR. 

```sql
USE DENEME
SELECT
[ID], [CUSTOMERNAME], [CITY], [BIRTHDATE],
[DISTRICT], [GENDER]
FROM
CUSTOMERS
```

Bu sorgu, "DENEME" veritabanındaki CUSTOMERS tablosundan seçilen sütunları listeler.
Sütun adlarında boşluk veya özel karakter varsa (örneğin: FATHERS NAME), SQL'de hata almamak için bu adlar köşeli parantezle yazılır(otomatik yazılır): [FATHERS NAME] olarak.

```SQL
SELECT * FROM TabloAdi;
SELECT Kolon1, Kolon2 FROM TabloAdi;
```

## INSERT
- Yeni kayıt ekler.

```sql
INSERT INTO Musteriler (Ad, Soyad)
VALUES ('Omer', 'Colakoglu');
```

DOĞUM GÜNLERİNİ İKİ ŞEKİLDE YAZABİLİRİZ:
```sql
'1990-12-21' VEYA '19901221'
```
```sql
INSERT INTO CUSTOMERS
(ID,CUSTOMERNAME,CITY,BIRTHDATE,DISTRICT,GENDER)
VALUES
(5,'MEHMET ÖZAL', 'ANTALYA', '1990-12-21','ALANYA','E')
```

- BU ŞEKİLDE OLUNCA HATA VERİR. ÇÜNKÜ 5 YANİ ID ZATEN OTOMATİK OLARAK GELİYOR ÇÜNKÜ SATIR SAYISINI SİSTEM BİLİYOR. HEM INSERT KISMINDAKİ ID ÇIKACAK HEM DE VALUE KISMINDAKİ 5 ÇIKACAK O ZAMAN ÇALIŞIR. 

**ŞİMDİ EXCEL TABLOSUNA GİDİYORUZ**
EXCEL'DE customername, cıty, dıstrıct, bırhdate, gender değerleri var. 1000 kişilik bir tablo düşünelim. bunları INSERT EDECEĞİZ.
EXCEL DE FORMÜL:
ilk satır  
```sql
="INSERT INTO CUSTOMERS(CUSTOMERNAME,CITY,DISTRICT,BIRTHDATE,GENDER) VALUES('"&A2&"',...)"
```
-tek tırnak çift tırnak hücresini seç değer olsun.

## UPDATE
- Kayıtları günceller.

```sql
UPDATE Customers
SET Age = 40
WHERE ID = 5;
```
```SQL
SELECT * FROM CUSTOMERS

UPDATE CUSTOMERS
SET NATION='US',AGE=40

DATEDIFF(YEAR,'2002-02-28',GETDATE())
```

BU KOMUT İLE HERKESİN YAŞINI DOĞUM TARİHLERİNE GÖRE KENDİSİ YAZAR.

Yaş güncelleme örneği:

```SQL
UPDATE Customers
SET Age = DATEDIFF(YEAR, Birthdate, GETDATE());
```

## DELETE
- Kayıt siler.
```SQL
DELETE FROM Customers
WHERE ID = 18;
```

## TRUNCATE
- Tablonun tüm verilerini siler. iLK HALİNE DÖNER. 
```SQL
TRUNCATE TABLE Customers;
```

## WHERE Koşulu
Verileri filtrelemek için kullanılır.

```SQL
SELECT * FROM Customers
WHERE City = 'İstanbul';
WHERE BIRTHDATE>'2002-02-28'
WHERE GENDER='K'
```

Operatörler:

| Operatör | Anlamı          |
| -------- | --------------- |
| =        | Eşittir         |
| <>       | Eşit değildir   |
| >        | Büyük           |
| <        | Küçük           |
| >=       | Büyük eşit      |
| <=       | Küçük eşit      |
| BETWEEN  | İki değer arası |
| IN       | İçinde          |
| LIKE     | Benzeyen        |
| NOT      | Değil           |
```sql
WHERE Age BETWEEN 20 AND 30;
```
**LIKE** :İLE BAŞLAR, İLE BİTER,İÇERİR

```sql WHERE CUSTOMERNAME LIKE 'ÖMER%'```
- ismi ömer ile başlayanlar.
```sql WHERE CUSTOMERNAME LIKE '%ORHAN'```
- ismi orhan ile biter.
```sql WHERE CUSTOMERNAME LIKE '%ÖMER%'```
-isminin içinde ömer geçenler
```sql
WHERE City IN ('İstanbul', 'Ankara');
```
NOT LIKE :İLE BAŞLAMAZ, İLE BİTMEZ,İÇERMEZ
```sql WHERE CUSTOMERNAME NOT LIKE 'ÖMER%'```

NOT IN : İÇİNDE DEĞİLDİR.
```sql WHERE CITY NOT IN ('İSTANBUL','BURSA')```

```sql
SELECT * FROM CUSTOMERS
WHERE CITY='İstanbul'
```
- SADECE İSTANBUL OLANLAR SEÇİLİYOR.
```sql
SELECT * FROM CUSTOMERS
WHERE CITY<>'İstanbul'
```
- iSTANBUL OLMAYANLAR SEÇİLİYOR. 

```sql
WHERE NOT CITY='İstanbul'
```
- iSTANBUL OLMAYANLAR SEÇİLİYOR. 

```sql
WHERE BIRTHDATE>'1990-01-01'
OR: '19900101'
```
VEYA BU ŞEKİLDE YAZILMASI DAHA İYİ OLACAKTIR: 1990'DAN BÜYÜK OLAN TARİHLER GELİYOR.

```sql
WHERE BIRTHDATE BETWEEN '19900101' AND '19981231'
```
(BÜYÜK EŞİTTİR VE KÜÇÜK EŞİTTİR GİBİ)

```sql
UPDATE CUSTOMERS SET AGE=DATEDIFF(YEAR,BIRTHDATE,GETDATE())
```
- BU GÜNCELLEME YAŞLARI HESAPLAR.

```sql
SELECT * FROM CUSTOMERS
WHERE AGE BETWEEN 20 AND 24
```
- BU YAŞ ARALIĞINDAKİLER GELİR.
```sql
WHERE CUSTOMERNAME LIKE '%HAN' 
```
- SONU HAN İLE BİTEN İSMLERİN GETİR KOMUTU.
```sql
WHERE CUSTOMERNAME LIKE '%MZ%' 
```
- İÇİNDE MZ GEÇENLERİ GETİR. 
```sql
WHERE CITY IN ('İSTANBUL','ELAZIĞ')
/
WHERE CITY='İSTANBUL'
```
- İÇİNDE İSTANBUL VE ELAZIĞ OLAN ŞEHİRLERİ GETİR. 

```sql
SELECT * FROM CUSTOMERS
UPDATE CUSTOMERS SET GENDER='KADIN' WHERE GENDER='K'
```
- K OLAN KISMI KADIN OLARAK DEĞİŞTİR.
- DELETE FROM CUSTOMERS  HEPSİNİ SİLER.
```sql
SELECT * FROM CUSTOMERS WHERE ID=18
```
- BU SEÇER.
```sql
DELETE FROM CUSTOMERS WHERE ID=18 
```
- SATIR SİLİNİYOR.

## INSERT Formülü (Excel'den Veri Aktarmak İçin)
```sql
="INSERT INTO Customers(CUSTOMERNAME,CITY,DISTRICT,BIRTHDATE,GENDER) VALUES('"&A2&"','"&B2&"','"&C2&"','"&D2&"','"&E2&"')"
```
- Excel’de 1000 kişilik veri varsa bu yöntemle SQL kodları üretilebilir.
