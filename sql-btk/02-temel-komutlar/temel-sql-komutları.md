## SELECT
- Tablodaki verileri listelemek için kullanılır.

SELECT * FROM TabloAdi;
SELECT Kolon1, Kolon2 FROM TabloAdi;

## INSERT
- Yeni kayıt ekler.

INSERT INTO Musteriler (Ad, Soyad)
VALUES ('Omer', 'Colakoglu');

## UPDATE
- Kayıtları günceller.

UPDATE Customers
SET Age = 40
WHERE ID = 5;

Yaş güncelleme örneği:

UPDATE Customers
SET Age = DATEDIFF(YEAR, Birthdate, GETDATE());

## DELETE
- Kayıt siler.

DELETE FROM Customers
WHERE ID = 18;

## TRUNCATE
- Tablonun tüm verilerini siler.

TRUNCATE TABLE Customers;


## WHERE Koşulu
Verileri filtrelemek için kullanılır.

SELECT * FROM Customers
WHERE City = 'İstanbul';

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

WHERE Age BETWEEN 20 AND 30;
WHERE CustomerName LIKE '%han';
WHERE City IN ('İstanbul', 'Ankara');

## INSERT Formülü (Excel'den Veri Aktarmak İçin)

="INSERT INTO Customers(CUSTOMERNAME,CITY,DISTRICT,BIRTHDATE,GENDER) VALUES('"&A2&"','"&B2&"','"&C2&"','"&D2&"','"&E2&"')"

- Excel’de 1000 kişilik veri varsa bu yöntemle SQL kodları üretilebilir.
