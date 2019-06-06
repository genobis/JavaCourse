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

* Pole `length` zawiera rozmiar tablicy (np. `myArray.length`).
* Dostęp do poszczególnych wartości można uzyskać za pomocą operatora indeksu `[]` (np. indeks `0`: `myArray[0]`).
* Tak uzyskaną wartość można przypisać do zmiennej (np. `String value = myArray[0];`) lub przekazać do metody
(np. `System.out.println(myArray[0]);`).
* Możliwe jest również działanie odwrotne - przypisywanie wartości do tablicy (np. `myArray[0] = value;`)
* Dla n-elementowej tablicy dozwolony zakres indeksów to `0`-`n-1`. Próba uzyskania dostępu do nieistniejącego indeksu
(dla pustej tablicy jest to już indeks `0`!) powoduje wystąpienie wyjątku `ArrayIndexOutOfBoundsException`.

## Obsługa parametrów uruchomieniowych

* Klasa narzędziowa [Arrays](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html) zawiera sporo przydatnych
metod, m.in. `Arrays.toString()` umożliwiająca przedstawienie tablicy w czytelnej dla człowieka postaci.
* W przypadku parametrów uruchomieniowych dobrą praktyką jest sprawdzenie czy ilość parametrów (elementów tablicy) jest
właściwa i czy są one poprawne. Na tej podstawie można zaprezentować odpowiedni komunikat i uniknąć wyjątków na dalszym
etapie działania.
* Wszystkie przekazywane parametry są zawsze typu `String`, nawet jeśli zawierają cyfry. Aby przekształcić parametr na
pożądany typ, należy dokonać konwersji. Metoda `Integer.parseInt()` (z klasy
[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)) pozwala na przekształcenie tekstu na `int`
(np. `int myInt = Integer.parseInt("33");`). 

---

## Dodatkowe informacje

* Rodzaje pamięci w JVM
* Operacje wejścia/wyjścia
* Binarne drzewo poszukiwań:
    * https://pl.wikipedia.org/wiki/Binarne_drzewo_poszukiwa%C5%84
    * https://pl.wikipedia.org/wiki/Przechodzenie_drzewa
   
