# Podstawy Gradle


## Co to jest Gradle?

> Gradle is an open-source build automation tool.

* Gradle to po prostu program uruchamiany na komputerze. Może być również zintegrowany z IDE (np. IntelliJ).
* Zapewnia standaryzację struktury projektu, rozpoznawanej przez różne IDE.
* Pozwala na wykonywanie zadań, np. budowanie projektu, jego uruchamianie, a także obsługuje zależności
(dodatkowe biblioteki).


## build.gradle

* Zachowanie Gradle determinuje treść pliku `build.gradle`.
* Skrypty Gradle pisze się w języku Groovy (niedawno dodano również obsługę Kotlina).
* Najprostszy przykład poprawnego `build.gradle`:

    ```
    
    ```


## Pluginy

* Właściwa funkcjonalność wynika z użycia wtyczek (pluginów).
* Plik `build.gradle` rozpoznawalny przez IDE jako plik projektu w Javie zawiera plugin `java`:

    ```groovy
    plugins {
        id 'java'
    }
    ```
    
* Starszy, ale wciąż często spotykany sposób definiowania pluginów:
    ```groovy
    apply plugin 'java'
    ```
    
* Więcej informacji: https://docs.gradle.org/current/userguide/plugins.html


## Struktura projektu

* Standardowa podstawowa struktura projektu:
    ```
    HelloGradle
    ├── build.gradle
    └── src
        └── main
            └── java
                └── pl
                    └── something
                        └── hello
                            └── Main.java
    ```

* Powyższy przykład zawiera pojedynczą klasę `Main` w pakiecie `pl.something.hello`.


## Gradle Wrapper - co to jest?

* Gradle Wrapper to niewielkie, zintegrowane z projektem narzędzie, które uniezależnia go od wersji Gradle obecnej
w systemie (może go wcale nie być!).
* Umożliwia obsługę projektu bez użycia dodatkowych narzędzi.
* Pobiera Gradle w wybranej wersji i osadza go w projekcie.
* Syndrom jajka i kury - aby dołączyć Gradle Wrappera, dzięki któremu Gradle nie jest potrzebny, potrzebne jest użycie
Gradle...
* Jeżeli Gradle jest zainstalowany na komputerze, wykonanie polecenia `gradle wrapper` spowoduje dołączenie do projektu
narzędzia Gradle Wrapper.
* IntelliJ potrafi zrobić to samo nawet gdy Gradle nie jest zainstalowany. Wystarczy otworzyć katalog zawierający
`build.gradle` jako projekt i wybrać opcję
    > use Gradle 'wrapper' task configuration.


## Gradle Wrapper w projekcie
* Po załadowaniu Gradle Wrappera, struktura projektu przedstawia się następująco:

    ```
    HelloGradle
    ├── build.gradle
    ├── gradle
    │   └── wrapper
    │       ├── gradle-wrapper.jar
    │       └── gradle-wrapper.properties
    ├── gradlew
    ├── gradlew.bat
    └── src
        └── main
            └── java
                └── pl
                    └── something
                        └── hello
                            └── Main.java
    ```
    
* Pliki wykonywalne `gradlew` (systemy uniksowe) i `gradlew.bat` (Windows) pozwalają na wykonywanie zadań Gradle przez
Gradle Wrappera.
* Edytując `gradle/wrapper/gradle-wrapper.properties` można ustawić pożądaną wersję Gradle Wrappera (wymaga wywołania
polecenia `gradlew wrapper` by pobrać nową wersję).
* Pliki `gradlew`, `gradlew.bat` oraz katalog `gradle` mogą być objęte systemem kontroli wersji.
* Pliki i katalogi z nazwami zaczynającymi się od `.` (np. `.gradle`) można bezpiecznie zignorować. W żadnym wypadku
nie powinny być one wersjonowane!
* Więcej informacji: https://docs.gradle.org/current/userguide/gradle_wrapper.html


## Podstawowe zadania Gradle

* Zadania Gradle można wywoływać z poziomu IntelliJ, z panelu Gradle (domyślnie zadokowany po prawej stronie okna).
* Alternatywnie z linii poleceń, np. dla Windows:

    ```
    gradlew.bat build
    ```

    Lub systemów uniksowych:
    
    ```bash
    ./gradlew build
    ```
    
    Analogicznie wygląda wywołanie pozostałych zadań z linii poleceń!
* Artefakty budowania można znaleźć w katalogu `build`.
* `build` spowoduje zbudowanie projektu, `clean` czyści istniejące artefakty (produkty budowania).
* Czegoś brakuje - plik `jar` jest generowany, ale nie ma możliwości jego prostego uruchomienia.

## Uruchamianie aplikacji

* Przed uruchomieniem/dystrybuowaniem aplikacji należy wskazać klasę startową.
* Potrzebny jest do tego plugin `application`.
* Uzupełniony `build.gradle`:

    ```groovy
    plugins {
        id 'java'
        id 'application'
    }
    
    application {
        mainClassName = 'pl.something.hello.Main'
    }
    ```
* Dochodzą nowe zadania, m.in. `run` (uruchamia program) i `distZip` (tworzy archiwum zip w `build/distributions`
wraz z plikami wykonywalnymi umożliwiającymi łatwe uruchomienie aplikacji).

## Podsumowanie

* Automatyzacja zadań związane z obsługą projektu.
* Integracja z IDE.
* Zadania definiowane w `build.gradle`.
* Łatwe uruchamianie poza IDE i dystrybucja gotowej aplikacji.
* Gradle Wrapper pozwala na używanie Gradle w pożądanej wersji nawet gdy program ten nie jest dostępny.
