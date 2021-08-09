Bu repo [Kodluyoruz](https://www.kodluyoruz.org/) SQL eğitimi için hazırlamış olduğum repo. İçerisinde SQL ödevlerinin soru ve cevaplarını içeren bir adet README dosyası barındırıyor.

#### Dvdrental Database linki:
```
https://www.postgresqltutorial.com/postgresql-sample-database/
```
***

# *Homework_1*

<details close> 
<summary>Question_1 And Answer</summary>

**film** tablosunda bulunan **title** ve **description** sütunlarındaki verileri sıralayınız.

```SQL
SELECT title,description FROM film;
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük **VE** 75 ten küçük olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film 
WHERE ( length > 60 AND length < 75 );
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 **VE** replacement_cost 12.99 **VEYA** 28.99 olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film 
WHERE (rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99);
```
</details>

<details close>
<summary>Question_4 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 **VE** replacement_cost 12.99 **VEYA** 28.99 olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film 
WHERE (rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99);
```
</details>

<details close>
<summary>Question_5 And Answer</summary>

**film** tablosundaki uzunluğu(length) 50 ten büyük **olmayıp** aynı zamanda rental_rate değeri 2.99 veya 4.99 **olmayan** verileri sıralayınız.

```SQL
SELECT * FROM film
WHERE NOT length > 50 AND (NOT (rental_rate = 2.99 OR rental_rate = 4.99 ));
```
</details>

***
# *Homework_2*

<details close>
<summary>Question_1 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

```SQL
SELECT * FROM film
WHERE replacement_cost BETWEEN 12.99 AND 16.98;
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**actor** tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

```SQL
SELECT first_name,last_name FROM actor
WHERE first_name IN ('Penelope','Nick','Ed');
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 **VE** replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

```SQL
SELECT * FROM film
WHERE (rental_rate IN (0.99,2.99,4.99)) AND (replacement_cost IN (12.99,15.99,28.99));
```
</details>

***

# *Homework_3*

<details close>
<summary>Question_1 And Answer</summary>

**country** tablosunda bulunan **country** sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

```SQL
SELECT country FROM country
WHERE country LIKE 'A%a';
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**country** tablosunda bulunan **country** sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```SQL
SELECT country FROM country
WHERE country LIKE '______%n';
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan **title** sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

```SQL
SELECT title FROM film
WHERE title ILIKE '%T%T%T%T%';
```
</details>

<details close>
<summary>Question_4 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verilerden **title** 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

```SQL
SELECT title FROM film
WHERE (title LIKE 'C%') AND ( (length > 90) AND (rental_rate = 2.99 ) );
```
</details>

---

# *Homework_4*

<details close>
<summary>Question_1 And Answer</summary>

**film** tablosunda bulunan **replacement_cost** sütununda bulunan birbirinden farklı değerleri sıralayınız.

```SQL
SELECT DISTINCT(replacement_cost) FROM film;
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**film** tablosunda bulunan **replacement_cost** sütununda birbirinden farklı kaç tane veri vardır?

```SQL
SELECT COUNT(DISTINCT(replacement_cost)) FROM film;
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

```SQL
SELECT COUNT(*) FROM film
WHERE (title LIKE 'T%') AND (rating = 'G');
```
</details>

<details close>
<summary>Question_4 And Answer</summary>

**country** tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

```SQL
SELECT COUNT(*) FROM country
WHERE (country ILIKE '_____');
```
</details>

<details close>
<summary>Question_5 And Answer</summary>

**city** tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?

```SQL
SELECT COUNT(*) FROM city
WHERE city ILIKE '%r';
```
</details>

---

# *Homework_5*

<details close>
<summary>Question_1 And Answer</summary>

**film** tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

```SQL
SELECT * FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5;
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**film** tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci 5 filmi sıralayınız.

```SQL
SELECT * FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
OFFSET 5
LIMIT 5;
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**customer** tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

```SQL
SELECT * FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4;
```
</details>

---

# *Homework_6*

<details close>
<summary>Question_1 And Answer</summary>

film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

```SQL
SELECT AVG(rental_rate) FROM film;
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**film** tablosunda bulunan filmlerden kaçtanesi 'C' karekteri ile başlar?

```SQL
SELECT COUNT(*) FROM film
WHERE title LIKE 'C%';
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

```SQL
SELECT MAX(length) FROM film
WHERE rental_rate = 0.99;
```
</details>

<details close>
<summary>Question_4 And Answer</summary>

**film** tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?


```SQL
SELECT COUNT(DISTINCT replacement_cost) FROM film
WHERE length > 150 ;
```
</details>

--- 

# *Homework_7*

<details close>
<summary>Question_1 And Answer</summary>

**film** tablosunda bulunan filmleri **rating** değerlerine göre gruplayınız.

```SQL
SELECT rating , COUNT(*) FROM film
GROUP BY rating;
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**film** tablosunda bulunan filmleri **replacement_cost** sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

```SQL
SELECT replacement_cost , COUNT(*) FROM film
GROUP BY replacement_cost
HAVING COUNT(*) > 50;
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**customer** tablosunda bulunan **store_id** değerlerine karşılık gelen müşteri sayılarını nelerdir?
fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

```SQL
SELECT store_id, COUNT(*) FROM customer
GROUP BY store_id;
```
</details>

<details close>
<summary>Question_4 And Answer</summary>

**city** tablosunda bulunan şehir verilerini **country_id** sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıra country_id bilgisini ve şehir sayısını paylaşınız.

```SQL
SELECT country_id , COUNT(*) FROM city
GROUP BY country_id
ORDER BY COUNT(*) DESC
LIMIT 1;

```
</details>

---

# *Homework_8*

<details close>
<summary>Question_1 And Answer</summary>

**Test** veritabanınızda **employee** isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

```SQL
CREATE TABLE employee (
	id integer,
	name varchar(50),
	birthday DATE,
	email varchar(100)
);

```
</details>

<details close>
<summary>Question_2 And Answer</summary>

Oluşturduğumuz **employee** tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

```SQL
insert into employee (id, name, birthday, email) values (1, 'Damien', '7/29/2005', 'dbirch0@edublogs.org');
insert into employee (id, name, birthday, email) values (2, 'Kial', '9/26/2005', 'kabele1@phpbb.com');
insert into employee (id, name, birthday, email) values (3, 'Bill', '8/10/2018', 'bboorn2@buzzfeed.com');
insert into employee (id, name, birthday, email) values (4, 'Hussein', '11/17/2002', 'hneiland3@feedburner.com');
insert into employee (id, name, birthday, email) values (5, 'Irene', '10/11/2019', 'ibeeble4@studiopress.com');
insert into employee (id, name, birthday, email) values (6, 'Kayle', '4/28/2006', 'kwenderoth5@umich.edu');
insert into employee (id, name, birthday, email) values (7, 'Gretel', '4/6/2017', 'glyptrit6@alibaba.com');
insert into employee (id, name, birthday, email) values (8, 'Bobbye', '7/29/2014', 'bllewellen7@seesaa.net');
insert into employee (id, name, birthday, email) values (9, 'Balduin', '6/4/2012', 'bhucklesby8@harvard.edu');
insert into employee (id, name, birthday, email) values (10, 'Flynn', '1/29/2008', 'fyoxall9@free.fr');
insert into employee (id, name, birthday, email) values (11, 'Simeon', '4/3/2008', 'sgelardia@skyrock.com');
insert into employee (id, name, birthday, email) values (12, 'Bibby', '9/1/2000', 'bballaamb@eepurl.com');
insert into employee (id, name, birthday, email) values (13, 'Alvira', '5/19/2010', 'abowmerc@etsy.com');
insert into employee (id, name, birthday, email) values (14, 'Lacy', '4/15/2006', 'lbrucknerd@exblog.jp');
insert into employee (id, name, birthday, email) values (15, 'Jorie', '5/14/2012', 'jcharlete@parallels.com');
insert into employee (id, name, birthday, email) values (16, 'Vittorio', '7/15/2013', 'vwoolgerf@reference.com');
insert into employee (id, name, birthday, email) values (17, 'Obadiah', '11/14/2002', 'ocrowleyg@guardian.co.uk');
insert into employee (id, name, birthday, email) values (18, 'Jessalin', '9/15/2019', 'jbearh@apple.com');
insert into employee (id, name, birthday, email) values (19, 'Erminia', '5/27/2006', 'eunitti@merriam-webster.com');
insert into employee (id, name, birthday, email) values (20, 'Carolee', '12/7/2019', 'cdebruynej@dmoz.org');
insert into employee (id, name, birthday, email) values (21, 'Madlin', '1/13/2001', 'mbeecroftk@naver.com');
insert into employee (id, name, birthday, email) values (22, 'Sonnie', '8/3/2017', 'sshirlandl@time.com');
insert into employee (id, name, birthday, email) values (23, 'Odelle', '6/19/2002', 'opalerm@shutterfly.com');
insert into employee (id, name, birthday, email) values (24, 'Maible', '3/31/2010', 'mwintourn@squarespace.com');
insert into employee (id, name, birthday, email) values (25, 'Annette', '1/25/2018', 'agreallyo@paginegialle.it');
insert into employee (id, name, birthday, email) values (26, 'Julian', '9/25/2019', 'jterrellp@tmall.com');
insert into employee (id, name, birthday, email) values (27, 'Halsey', '1/18/2017', 'hmcmainsq@alibaba.com');
insert into employee (id, name, birthday, email) values (28, 'Seymour', '12/12/2015', 'sbreadmorer@moonfruit.com');
insert into employee (id, name, birthday, email) values (29, 'Allie', '12/29/2005', 'akleints@desdev.cn');
insert into employee (id, name, birthday, email) values (30, 'Bucky', '12/10/2013', 'bswiftt@ehow.com');
insert into employee (id, name, birthday, email) values (31, 'Horton', '2/27/2011', 'hhurdwellu@cocolog-nifty.com');
insert into employee (id, name, birthday, email) values (32, 'Pinchas', '1/26/2012', 'pdracksfordv@unicef.org');
insert into employee (id, name, birthday, email) values (33, 'Wayland', '8/19/2001', 'wrootew@tiny.cc');
insert into employee (id, name, birthday, email) values (34, 'Sunny', '9/19/2003', 'sbithellx@examiner.com');
insert into employee (id, name, birthday, email) values (35, 'Kim', '2/9/2012', 'kbirdseyey@webs.com');
insert into employee (id, name, birthday, email) values (36, 'Sheba', '12/3/2005', 'skemberyz@mozilla.org');
insert into employee (id, name, birthday, email) values (37, 'Conny', '3/13/2004', 'cpaddie10@oaic.gov.au');
insert into employee (id, name, birthday, email) values (38, 'Florida', '8/31/2018', 'frutty11@msu.edu');
insert into employee (id, name, birthday, email) values (39, 'Dean', '1/24/2011', 'dbourgour12@alexa.com');
insert into employee (id, name, birthday, email) values (40, 'Shandee', '2/11/2005', 'sdeferraris13@un.org');
insert into employee (id, name, birthday, email) values (41, 'Curtis', '4/22/2008', 'cvermer14@guardian.co.uk');
insert into employee (id, name, birthday, email) values (42, 'Malinde', '4/20/2012', 'mperford15@wikimedia.org');
insert into employee (id, name, birthday, email) values (43, 'Thorstein', '1/24/2016', 'tdicey16@multiply.com');
insert into employee (id, name, birthday, email) values (44, 'Maximilien', '6/18/2016', 'mblackster17@cnn.com');
insert into employee (id, name, birthday, email) values (45, 'Aymer', '11/11/2006', 'aheadingham18@bizjournals.com');
insert into employee (id, name, birthday, email) values (46, 'Malia', '5/1/2009', 'mhellings19@bing.com');
insert into employee (id, name, birthday, email) values (47, 'Sile', '11/28/2014', 'sboschmann1a@homestead.com');
insert into employee (id, name, birthday, email) values (48, 'Lura', '6/10/2011', 'labate1b@google.fr');
insert into employee (id, name, birthday, email) values (49, 'Jacob', '11/23/2010', 'jgritsunov1c@over-blog.com');
insert into employee (id, name, birthday, email) values (50, 'Jacquie', '11/27/2001', 'jlefever1d@businesswire.com');

```
</details>

<details close>
<summary>Question_3 And Answer</summary>

Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.

```SQL
UPDATE employee
SET name = 'UPDATE'
WHERE name ILIKE 'a%' AND id >10
RETURNING *;

UPDATE employee
SET name = 'Changed'
WHERE name LIKE '%l'
RETURNING *;

UPDATE employee
SET name = 'Changed'
WHERE id = 'Bobbye'
RETURNING *;

UPDATE employee
SET birthday = '1996-02-07'
WHERE id BETWEEN 1 AND 5
RETURNING *;

UPDATE employee
SET birthday = '2010-09-04',
	email = 'changed@gmail.com'
WHERE name LIKE 'C%'
RETURNING *;
```
</details>

<details close>
<summary>Question_4 And Answer</summary>

Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

```SQL
DELETE FROM employee
WHERE name = 'UPDATE'
RETURNING *;

DELETE FROM employee
WHERE name ILIKE '__r%'
RETURNING *;

DELETE FROM employee
WHERE name LIKE 'C%' AND (id BETWEEN 15 AND 35)
RETURNING *;

DELETE FROM employee
WHERE name ILIKE '%a'
RETURNING *;

DELETE FROM employee
WHERE id = 28
RETURNING *;
```
</details>

***
# *Homework_9*

<details close>
<summary>Question_1 And Answer</summary>

**city** tablosu ile **country** tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```SQL
SELECT city, country FROM city
INNER JOIN country ON city.country_id = country.country_id;
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**customer** tablosu ile **payment** tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```SQL
SELECT payment_id, first_name, last_name FROM customer
INNER JOIN payment ON customer.customer_id = payment.customer_id;
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**customer** tablosu ile **rental** tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```SQL
SELECT rental_id, first_name, last_name FROM customer
INNER JOIN rental ON customer.customer_id = rental.customer_id;
```
</details>

***

# *Homework_10*

<details close>
<summary>Question_1 And Answer</summary>

**city** tablosu ile **country** tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.

```SQL
SELECT city, country FROM country
LEFT JOIN city ON city.country_id = country.country_id;
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**customer** tablosu ile **payment** tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.

```SQL
SELECT payment_id, first_name, last_name FROM customer
RIGHT JOIN payment ON customer.customer_id = payment.customer_id;
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**customer** tablosu ile **rental** tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.

```SQL
SELECT rental_id, first_name, last_name FROM customer
FULL JOIN rental ON customer.customer_id = rental.customer_id;
```
</details>

***

# *Homework_11*

<details close>
<summary>Question_1 And Answer</summary>

**actor** ve **customer** tablolarında bulunan **first_name** sütunları için tüm verileri sıralayalım.
```SQL
(
SELECT first_name FROM actor
)
UNION ALL
(
SELECT first_name FROM customer
)
ORDER BY first_name;
```
</details>

<details close>
<summary>Question_2 And Answer</summary>

**actor** ve **customer** tablolarında bulunan **first_name** sütunları için kesişen verileri sıralayalım.
```SQL
(
SELECT first_name FROM actor
)
INTERSECT
(
SELECT first_name FROM customer
)
ORDER BY first_name;
```
</details>

<details close>
<summary>Question_3 And Answer</summary>

**actor** ve **customer** tablolarında bulunan **first_name** sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.
```SQL
(
SELECT first_name FROM actor
)
EXCEPT
(
SELECT first_name FROM customer
)
ORDER BY first_name;
```
</details>

<details close>
<summary>Question_4 And Answer</summary>

İlk 3 sorguyu tekrar eden veriler için de yapalım.

```SQL
-- 4.1
(
SELECT first_name FROM actor
)
UNION ALL
(
SELECT first_name FROM customer
)
ORDER BY first_name;
```
```SQL
-- 4.2
(
SELECT first_name FROM actor
)
INTERSECT ALL
(
SELECT first_name FROM customer
)
ORDER BY first_name;
```
```SQL
-- 4.3
(
SELECT first_name FROM actor
)
EXCEPT ALL
(
SELECT first_name FROM customer
)
ORDER BY first_name;
```
</details>

</br>


## Contributing

Please open a thread for changes..!

## License

[MIT](https://choosealicense.com/licenses/mit/)