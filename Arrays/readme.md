# Tablice


## Czym są tablice?

> An *array* is a container object that holds a fixed number of values of a single type.

* Szczególny przypadek obiektu.
* Struktura danych przechowująca określoną ilość uporządkowanych elementów wybranego typu (może zawierać zarówno
obiekty, jak i typy proste).
* Elementy tablicy ułożone są w określonej kolejności.
* Rozmiar tablicy jest niezmienny, ustalany w momencie jej utworzenia.


## Jak używać tablic?

* Każdemu elementowi tablicy odpowiada jego numer, tak zwany indeks.
* Indeksy numerowane są od zera, zatem w 5-elementowej tablicy ostatni indeks to `4`.
* Dostęp do poszczególnych elementów tablicy można uzyskać przy pomocy tego indeksu.
* Koszt dostępu do poszczególnych elementów tablicy jest stały (i bardzo niewielki).


## Jak działa tablica?

* Ciągły blok w pamięci o rozmiarze będącym iloczynem rozmiarów tablicy i pojedynczej jej wartości.
Np. 5-elementowa tablica wartości typu `int` (zajmujących 4 bajty) zajmie łącznie 20 bajtów.
* Indeks określa pozycję w tym bloku, np. dla `0` są to pierwsze 4 bajty, dla `1` - kolejne, itd.
* Tablica zawiera wartości (w przypadku typów prostych) lub referencje (w przypadku obiektów).
* Blok ten alokowany jest na stercie (czyli w tej samej pamięci, co zwykłe obiekty).


## Pojęcia

* *Array* - tablica, dosłownie z ang. *szyk*. Dodatkowo sugeruje uporządkowanie elementów.
* *Index* - indeks.
* *Indices* - indeksy (liczba mnoga).
* *Element* - element.
* *Length* - rozmiar (ilość elementów).


## Zastosowanie

* Prosta kolekcja danych różnego rodzaju.
* Parametry uruchomieniowe programu są do niego przekazywane w formie tablicy.
* Obiekty typu `String` wewnętrznie są zbudowane w oparciu o tablicę bajtów.
* Operacje wejścia/wyjścia - odczyt/zapis danych strumieniowych można usprawnić posługując się buforem w postaci
tablicy bajtów zamiast pobierać/pisać po jednym bajcie.
* Tablica może też służyć jako reprezentacja bardziej złożonych typów danych, np. drzew binarnych.


## Wykorzystanie tablic w praktyce

* Pole `length` zawiera rozmiar tablicy.
* TODO

---

## Dodatkowe informacje

* Rodzaje pamięci w JVM
* Operacje wejścia/wyjścia
* Binarne drzewo poszukiwań:
    * https://pl.wikipedia.org/wiki/Binarne_drzewo_poszukiwa%C5%84
    * https://pl.wikipedia.org/wiki/Przechodzenie_drzewa
   
