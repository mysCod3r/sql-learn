# SQL LEARN

> ## [DATA MANİPÜLASYON KOMUTLARI]()
> - `SELECT` -> VERİTABANINDAKİ TABLODAN KAYITLARI ÇEKER
> - `INSERT` -> TABLOYA YENİ KAYIT EKLER
> - `UPDATE` -> TABLODAKİ VERİLERİN BİR YA DA BİRDEN ÇOK ALANINI DEĞİŞTİRİR
> - `DELETE` -> TABLODAN KAYIT SİLER (Sayaçlar sıfırlanmaz.)
> - `TRUNCATE` -> TABLONUN İÇİNİ BOŞALTIR (Tablonun ilk haline döner. Sayaçlar vs sıfırlanır.)

> ## [VERİTABANI MANİPÜLASYON KOMUTLARI]()
> - `CREATE` -> BİR VERİTABANI NESNESİ OLUŞTURUR (TABLE, VİEW, DATABASE...)
> - `ALTER` -> BİR VERİTABANI NESNESİNİN ÖZELLİĞİNİ DEĞİŞTİRİR
> - `DROP` -> BİR VERİTABANI NESNESİNİ SİLER
>  ## [&nbsp;&nbsp;&nbsp;&nbsp;ÖRNEKLER:]()
> - `CREATE DATABASE` -> YENİ VERİTABANI OLUŞTURUR
> - `ALTER DATABASE` -> BİR VERİTABANININ ÖZELLİKLERİNİ DEĞİŞTİRİR
> - `CREATE TABLE` -> YENİ TABLO OLUŞTURUR
> - `ALTER TABLE` -> BİR TABLONUN ÖZELLİKLERİNİ DEĞİŞTİRİR
> - `DROP TABLE` -> BİR TABLOYU TAMAMEN SİLER
> - `CREATE INDEX` -> INDEX OLUŞTURUR
> - `DROP INDEX` -> INDEX'İ SİLER 

> ## [SELECT KOMUTU]()
> `SELECT` kolon1, kolon2, kolon3...
>
> `FROM` tabloadı
>
> `WHERE` <şartlar>

> ## [INSERT KOMUTU]()
> `INSERT INTO` tabloadi
>
> (kolon1, kolon2, kolon3...)
>
> `VALUES`
>
> (deger1, deger2, deger3...)

> ## [UPDATE KOMUTU]()
> `UPDATE` tabloadi `SET`
>
> kolon1 = deger1, kolon2 = deger2, kolon3 = deger3...
>
> `WHERE` <şartlar>

> ## [DELETE KOMUTU]()
> `DELETE FROM` tabloadi 
>
> `WHERE` <şartlar>

> ## [WHERE KOMUTU]()
> `SELECT` kolon1, kolon2, kolon3...
>
> `FROM` tabloadı
>
> `WHERE` <şartlar>

> ## [DISTINCT KOMUTU]()
> TEKRAR EDEN SONUÇLARI TEKE DÜŞÜRÜR
>
> `SELECT DISTINCT` kolon1, kolon2, kolon3...
>
> `FROM` tabloadı
>
> `WHERE` <şartlar>

> ## [ORDER BY KOMUTU]()
> SONUCUN HANGİ KOLONA GÖRE SIRALANACAĞI BELİRTİLİR
>
> `SELECT * FROM` tabloadı
>
> `ORDER BY ` kolon1 `ASC`, kolon2, kolon3 `DESC`, kolon4...
>
> - önce kolon1 e göre sonra kolon2 ye göre sıralar
> 
> - `ASC` ARTAN SIRA - `DESC` AZALAN SIRA

#
| OPERATÖR |        |        | 
| -------- | ------ | ------ |
| = | EŞİTTİR |  |
| <> | EŞİT DEĞİLDİR |  |
| > | BÜYÜKTÜR |  |
| < | KÜÇÜKTÜR |  |
| >= | BÜYÜKTÜR YA DA EŞİTTİR |  |
| <= | KÜÇÜKTÜR YA DA EŞİTTİR |  |
| BETWEEN | ARASINDADIR | `WHERE` ID `BETWEEN` 100 AND 150 // `WHERE` BIRTHDATE `BETWEEN` '1999-01-01' AND '1999-12-31'|
| LIKE | İLE BAŞLAR, İLE BİTER, İÇERİR | `WHERE` NAME `LIKE` 'Ali%' -> Ali ile başlayan herşey, `WHERE` NAME `LIKE` '%Ali%' -> İçinde Ali geçen herşey|
| IN | İÇİNDEDİR | `WHERE` city `IN` ('ANKARA', 'İSTANBUL', 'İZMİR') |
| NOT LIKE | İLE BAŞLAMAZ, İLE BİTMEZ, İÇERMEZ |  |
| NOT IN | İÇİNDE DEĞİLDİR |  |

#
| OPERATÖR |        |        | 
| -------- | ------ | ------ |
| `TOP` | KAÇ SATIR SONUÇ DÖNECEĞİ | `SELECT TOP 10 * FROM TABLOADI` |
| `TOP _ PERCENT` | TABLODAKİ HÜCRENİN YÜZDE _ Sİ KADAR SONUÇ DÖNER | `SELECT TOP 10 PERCENT * FROM TABLOADI` |
|  |  |  |



# AGGREGATE FUNCTIONS VE GROUP BY
- ## AGGREGATE FUNCTIONS
-- `WHERE` kullanımında aggregate fonksiyon kullanılamaz. Onun yerine `HAVING` kullanılır.

| FONKSİYON |                     |        | 
| --------- | ------- | ------------------- |
| `COUNT`   | Bir veritabanı tablosundaki satır sayısını döndürür.| `COUNT(`kolonAdi`)` |
| `SUM`     | Sayısal bir sütunun toplamını döndürür. | `SUM(`kolonAdi`)` |
| `AVG`     | Bir dizi değerin ortalamasını hesaplar. | `AVG(`kolonAdi`)` |
| `MIN`     | NULL olmayan değerler kümesindeki en düşük değeri (minimum) döndürür. | `MIN(`kolonAdi`)` |
| `MAX`     | NULL olmayan değerler kümesindeki en yüksek değeri (maksimum) döndürür. | `MAX(`kolonAdi`)` |
| `AS` | GELEN SONUCUN TABLODAKİ KOLON ADINI AYARLAR | `SELECT SUM(`kolonAdi`) AS` tablodaGörünecekBaşlık |

- ## GROUP BY

> `SELECT` kolon1, kolon2, ...
>
> `FROM` tabloadı
> 
> `GROUP BY` kolon1, kolon2, ...

| FONKSİYON |                     |        | 
| --------- | ------- | ------------------- |
| `COUNT`   | Bir veritabanı tablosundaki satır sayısını döndürür.| `COUNT(`kolonAdi`)` |
| `SUM`     | Sayısal bir sütunun toplamını döndürür. | `SUM(`kolonAdi`)` |
| `AVG`     | Bir dizi değerin ortalamasını hesaplar. | `AVG(`kolonAdi`)` |
| `MIN`     | NULL olmayan değerler kümesindeki en düşük değeri (minimum) döndürür. | `MIN(`kolonAdi`)` |
| `MAX`     | NULL olmayan değerler kümesindeki en yüksek değeri (maksimum) döndürür. | `MAX(`kolonAdi`)` |
| `AS` | GELEN SONUCUN TABLODAKİ KOLON ADINI AYARLAR | `SELECT SUM(`kolonAdi`) AS` tablodaGörünecekBaşlık |
