Bu repo [Kodluyoruz](https://www.kodluyoruz.org/) SQL eğitimi için hazırlamış olduğum repo. İçerisinde SQL ödevlerinin soru ve cevaplarını içeren bir adet README dosyası barındırıyor.

#### Dvdrental Database linki:
```
https://www.postgresqltutorial.com/postgresql-sample-database/
```
***
# *Homework_1*
</br>

<details open> 
<summary>Question_1 And Answer</summary>

**film** tablosunda bulunan **title** ve **description** sütunlarındaki verileri sıralayınız.

```SQL
SELECT title,description FROM film;
```
</details>

</br>

<details open>
<summary>Question_2 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük **VE** 75 ten küçük olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film 
WHERE ( length > 60 AND length < 75 );
```
</details>

</br>

<details open>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 **VE** replacement_cost 12.99 **VEYA** 28.99 olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film 
WHERE (rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99)
```
</details>

</br>

<details open>
<summary>Question_4 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 **VE** replacement_cost 12.99 **VEYA** 28.99 olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film 
WHERE (rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99)
```
</details>

</br>

<details open>
<summary>Question_5 And Answer</summary>

**film** tablosundaki uzunluğu(length) 50 ten büyük **olmayıp** aynı zamanda rental_rate değeri 2.99 veya 4.99 **olmayan** verileri sıralayınız.

```SQL
SELECT * FROM film
WHERE NOT length > 50 AND (NOT (rental_rate = 2.99 OR rental_rate = 4.99 ))
```
</details>


***
# *Homework_2*

</br>

<details open>
<summary>Question_1 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

```SQL
SELECT * FROM film
WHERE replacement_cost BETWEEN 12.99 AND 16.98
```
</details>
</br>

<details open>
<summary>Question_2 And Answer</summary>

**actor** tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

```SQL
SELECT first_name,last_name FROM actor
WHERE first_name IN ('Penelope','Nick','Ed')
```
</details>
</br>

<details open>
<summary>Question_3 And Answer</summary>

**film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 **VE** replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

```SQL
SELECT * FROM film
WHERE (rental_rate IN (0.99,2.99,4.99)) AND (replacement_cost IN (12.99,15.99,28.99))
```
</details>
</br>

***

## Contributing
Please open a thread for changes..!

## License

[MIT](https://choosealicense.com/licenses/mit/)
