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

</br>

## Contributing
Değişiklikler için lütfen bir konu açınız..!

## License

[MIT](https://choosealicense.com/licenses/mit/)
