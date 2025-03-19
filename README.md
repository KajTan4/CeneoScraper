# CeneoScraper

## Kod produtu, o którym bedą pobierane opinie
84514582
## Algorytm pobierania opini o pojedyńczym produkcie z serwisu Ceneo.pl

   1.   Rządanie dostępu do strony z opiniami o produkcie
   2.   Jeśli operacja zakończy się sukcesem, wyodrębnienie z kodu strony fragmentów odpowiadających poszczególnym opiniom
   3. Dla każdej opinii wydobycie z kodu HTML poszczególnych składowych i zapisanie ich w postaci złożonych struktur danych 
   4.   Jeżeli istnieje kolejna storna z opiniami, przejście na tą stronę i powtórzenie dla niej kroków 1-4
   5.   zapisanie wszystkich opinii w bazie danych

## Struktura opinii w serwisie Ceneo.pl
|Składowa | Zmienna | Selektor|
|.........|.........|.........|
|opinia|review|div.js.product-review|
|identyfikator opinii|review_id|['data-entry-id']|
|autora|author|span.user-post__author-name|
|rekomendację|recomendation|span.user-post__text|
|liczbę gwiazdek|stars|span.user-post__score-count|
|treść opinii|content|div.user-post__text|
|listę zalet|pros|div.review-feature__item--positive|
|listę wad|cons|div.review-feature__item--negative|
|ile osób uznało opinię za przydatną|likes|button.vote-yes > span|
|ile osób uznało opinię za nieprzydatną|dislikes|button.vote-no > span|
|data wystawienia opinii|publish_date|span.user-post__published > time:nth-child(1)['datatime']|
|data zakupu produktu|purchase_date|span.user-post__published > time:nth-child(2)['datatime']|
 