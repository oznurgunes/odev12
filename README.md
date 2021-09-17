1)film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?<br><code>
 select count(*) from film
where length >
(select avg(length)from film);</code><br>
2)film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?<br><code>
  select count(*) from film
where rental_rate =
(select max(rental_rate)from film);</code><br>
3)film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.<br><code>
  select* from film
where rental_rate  = 
(select min(rental_rate)from film)
union
select* from film
where replacement_cost  = 
(select min(replacement_cost)from film);</code><br>
4)payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.<br><code>
  select * from payment
where amount=
(select max(amount) from payment);
