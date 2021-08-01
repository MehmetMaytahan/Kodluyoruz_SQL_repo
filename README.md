Bu repo [Kodluyoruz](https://www.kodluyoruz.org/) SQL eğitimi için hazırlamış olduğum repo. İçerisinde SQL ödevlerinin soru ve cevaplarını içeren bir adet README dosyası barındırıyor.

#### Dvdrental Database linki:
```
https://www.postgresqltutorial.com/postgresql-sample-database/
```
***
# *Homework_1*
</br>

<details close> 
<summary>Question_1 And Answer</summary>

**film** tablosunda bulunan **title** ve **description** sütunlarındaki verileri sıralayınız.

```SQL
SELECT title,description FROM film;
```
</details>

</br>

<details close>
<summary>Question_2 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük **VE** 75 ten küçük olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film 
WHERE ( length > 60 AND length < 75 );
```
</details>

</br>

<details close>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 **VE** replacement_cost 12.99 **VEYA** 28.99 olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film 
WHERE (rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99);
```
</details>

</br>

<details close>
<summary>Question_4 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 **VE** replacement_cost 12.99 **VEYA** 28.99 olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film 
WHERE (rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99);
```
</details>

</br>

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

</br>

<details close>
<summary>Question_1 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

```SQL
SELECT * FROM film
WHERE replacement_cost BETWEEN 12.99 AND 16.98;
```
</details>
</br>

<details close>
<summary>Question_2 And Answer</summary>

**actor** tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

```SQL
SELECT first_name,last_name FROM actor
WHERE first_name IN ('Penelope','Nick','Ed');
```
</details>
</br>

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

</br>

<details close>
<summary>Question_2 And Answer</summary>

**country** tablosunda bulunan **country** sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```SQL
SELECT country FROM country
WHERE country LIKE '______%n';
```
</details>

</br>

<details close>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan **title** sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

```SQL
SELECT title FROM film
WHERE title ILIKE '%T%T%T%T%';
```
</details>

</br>
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

</br>

<details close>
<summary>Question_2 And Answer</summary>

**film** tablosunda bulunan **replacement_cost** sütununda birbirinden farklı kaç tane veri vardır?

```SQL
SELECT COUNT(DISTINCT(replacement_cost)) FROM film;
```
</details>

</br>

<details close>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

```SQL
SELECT COUNT(*) FROM film
WHERE (title LIKE 'T%') AND (rating = 'G');
```
</details>

</br>

<details close>
<summary>Question_4 And Answer</summary>

**country** tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

```SQL
SELECT COUNT(*) FROM country
WHERE (country ILIKE '_____');
```
</details>

</br>

<details close>
<summary>Question_5 And Answer</summary>

**city** tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?

```SQL
SELECT COUNT(*) FROM city
WHERE city ILIKE '%r';
```
</details>

---



## Contributing

Please open a thread for changes..!

## License

[MIT](https://choosealicense.com/licenses/mit/)
