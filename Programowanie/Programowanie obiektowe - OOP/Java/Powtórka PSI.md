 1. 4 Filary OOP
	- Abstrakcja - modelowanie obiektu o ograniczonym kontekście. Przykładowo implementując klasę Samolot w aplikacji do rezerwacji miejsc na pokładzie nie będziemy implementować zbędnych zmiennych i metod odpowiadających za lot samolotu (np. kontrolę silników, kokpitu itp.)
	- Enkapsulacja - ukrycie części danych oraz metod zostawiając limitowany dostęp poprzez interfejsy
	- Dziedziczenie - tworzenie klas opartych na klasach nadrzędnych (np. klasa kot dziedzicząca po klasie zwierzę)
	- Polimorfizm - umiejętność programu do wykrycia prawdziwej klasy obiektu i użycia jej implementacji mimo że jej typ jest nieznany w tym kontekście.
	
2. SOLID
	- S - Single Responsibility Principle
		- Klasa powinna podlegać zmianie tylko z jednego powodu
		- Jak pomaga to w tworzeniu lepszego kodu?
			- **Testy** - Klasa z jedną odpowiedzialnością będzie miała mniej przypadków testów
			- **Mniejsza liczba powiązań** - Mniej funkcjonalności w jednej klasie sprawi, że będzie ona miała mniej zależności
			- **Organizacja** - Mniejsze, lepiej zorganizowane klasy, są łatwiejsze do przeszukiwania niż monolityczne.
		- Wykorzystanie w kodzie:
			- Załóżmy że mamy klasę książkę, której odpowiedzialnością jest przechowywanie danych o danej książce - nazwa, autor i zawartość. Posiada także metody które są bezpośrednio zależne z funkcjonowaniem książki - zamiana słowa w tekście oraz usunięcie słowa z tekstu. Jeśli chcemy "przeczytać" książkę, to musimy jakoś wypisać jej zawartoś w konsoli. Zamiast dodawać metodę bezpośrednio do klasy Książka, tworzymy osobną klasę BookReader która będzie zajmowała się wyświetlaniem tekstu z książki.
	- O - Open/Closed Principle
		- Klasy powinny być otwarte na rozszerzenia ale zamknięte dla modyfikacji.
		- Załóżmy że mamy klasę ElectricGuitar, która posiada informacje o modelu, producencie, nastrojeniu i głośności. Wszystko działa, ale po jakimś czasie ludziom znudził się wygląd podstawowej gitary i chcieliby gitarę która posiada inny kolor/wzór. Zamiast modyfikować istniejącą klasę ElectricGuitar, tworzymy nową klasę FlamePatternElectricGuitar która dziedziczy po klasie ElectricGuitar. Poprzez rozszerzenie istniejącej klasy, dodajemy nową funkcjonalnośc przy tym upewniając się że reszta aplikacji będzie działała tak jak powinna.
	- L - Liskov Substitution Principle
		- Rozszerzając klasę trzeba pamiętać, aby możliwe było przekazywanie obiektów nowej podklasy w miejsce obiektów klasy bazowej bez psucia kodu klienta.
		- Przykładowo mamy klasę Car, która posiada silnik oraz metody które służą do uruchomienia go. Tworzymy teraz klasy dziedziczące MotorCar oraz ElectricCar. Tylko jest jeden problem - auto elektrycznie nie posiada silnika. Więc zastąpienie w kodzie obiektu Car które korzysta z metod gdzie wymagany jest silnik, sprawi że program nie będzie działał. Jest to naruszenie  tej zasady. Możliwym rozwiązaniem jest przerobienie naszego modelu na korzystanie interfejsów które uwzględnią bezsilnikowy stan auta.
	- I - Interface Segregation Principle
		- Klientom nie powinno się narzucać zależności od nieużywanych metod.
		- Załóżmy że mamy interfejs ZarządzanieDziennikiem. Posiada on metody sprawdźOcenę(), wpiszOcenę(), zmieńOcenę(). Konto nauczyciela musiałoby mieć dostęp do wszystkich z tych metod, jednakże uczeń nie powinien móc zmienić ani wpisać sobie oceny. Zatem, z pojedynczego interfejsu o kilku metodach, rodzielimy sobie go na interfejsy które posiadają pojedyncze metody. Dzięki temu przy tworzeniu klasy KontoUcznia nie musimy implementować niepotrzebnych metod które są tylko dla nauczyciela.
	- D - Dependency Inversion Principle
		- Wysokopoziomowe klasy nie powinny być zależne od niskopoziomowych. Obie grupy powinny być zależne od abstrakcji. Abstrakcje nie powinny być zależne od szczegółów. Szczegóły z kolei powinny zależeć od abstrakcji.
		- Załóżmy że mamy klasę Żarówka i Włącznik. Nie możemy umieścić żarówki w włączniku ponieważ wysokopoziomowy Włącznik będzie zależny od niskopoziomowej żarówki. Zamiast tego, zrobimy interfejs Switch oraz Switchable. Nastepnie sprawimy że żarówka będzie implementowała interfejs Swichable, a włącznik będzie implementował interfejs Switch. Teraz możemy do jakichkolwiek Włączników implementujących interfejs Switch, możemy użyć jakiegokolwiek obiektu implementującego interfejs Switchable.
		
3. Wzorce projektowe
	1. Wzorce KREACYJNE - mechanizmy tworzenia obiektów
		- FACTORY
			- udostępnia interfejs do tworzenia obiektów w ramach klasy bazowej, ale pozwala podklasom zmienić typ tworzonych obiektów. (pola i przeszkody w heroesach). W heroesach użyłem factory do tworzenia obiektów pól podczas deserializacji mapy z JSONa.
		- ABSTRACT FACTORY
			- pozwala tworzyć rodziny spokrewnionych ze sobą obiektów bez określania ich konkretnych klas. Przykładowo chcemy stworzyć obiekty GUI na bazie systemu z którego korzysta użytkownik. Wystarczy wtedy stworzyć fabryki przycisków które służą do tworzenia przycisków kompatybilnych np. z systemem MacOS.
		- BUILDER
			- daje możliwość tworzenia złożonych obiektów krok po kroku (kreatury w heroesach)
		- PROTOTYPE
			- umożliwa kopiowanie obiektów bez tworzenia zależności między twoim kodem, a klasami obiektów.
		- SINGLETON
			- pozwala zapewnić istnienie wyłącznie jednej instancji danej klasy. Ponadto daje globalny punk dostępowy do tejże instancji. Zapewnienie tego jest banalne. Wystarczy aby obiekt przechowywał dane o swojej instancji. Następnie w konstruktorze dodajemy warunek że jeśli instancja jest nullem to tworzymy nową, przypisujemy ją do zmiennej w klasie i ją zwracamy. Dzięki temu, późniejsza próba stworzenia instancji obiektu zamiast tworzyć nową, zwróci już istniejącą. 
	2. Wzorce STRUKTURALNE - Składanie obiektów i klas w większe struktury które dalej są elastyczne i efektywne
		- ADAPTER
			- Pozwala na współdziałanie obiektów o niekompatybilnych interfejsach. Przykładowo chcemy sprawdzić czy prostopadłościan o podstawie foremnej zmieści się do okrągłego otworu o danym promieniu. Jednakże metoda otworu przyjmuje jako parametr klasę Walca. Możemy stworzyć adapter do prostopadłościanu który będzie dziedziczył po klasie Walec i przez to możemy sprawdzić czy zadaptowany prostopadłościan będzie pasował do otworu.
		- MOST
			- Pozwala podzielić dużą klasę lub blisko spokrewnione ze sobą klasy na dwie hierarchię: abstrakcję oraz implementację, nad którymi można pracować niezależnie od siebie. Abstrakcja odpowiada interfejsowi, a Implementacja odpowiada za funkcjonalność. Przykładowo pilot jest częścią abstrakcyjną a urządzenie częścią implementacyjną. 
		- KOMPOZYT
			- Pozwala komponować obiekty w struktury drzewiaste, a potem traktować je tak, jakby były one osobnymi obiektami. Przykładem mogą być zamówienia które składają się z opakowań i przedmiotów. Duży karton zawierałby młotek, śrubokręt, opakowanie w którym są gwoździe oraz opakowanie w którym są śruby.
		- DEKORATOR
			- Pozwala nadać dodatkowe obowiązki obiektom poprzez umieszczenie tych obiektów w specjalnych obiektach opakowujących, które zawierają odpowiednie zachowania
		- FASADA
			- Wyposaża bibliotekę, framework lub inny złożony zestaw klas w uproszczony interfejs. Robiąc aplikację do konwersji plików dźwiękowych zamiast udostępniać użytkownikowi dużą i skomplikowaną bibliotekę, tworzymy prosty inferfest który posiada metodę convert która przyjmuje ścieżkę do pliku oraz format na który ma zostać przekonwertowany plik.
		- PYŁEK
			- Pozwala zmieścić większą liczbę obiektów  w dostępnej pamięci RAM poprzez współdzielenie elementów opisujących stan obiektu. Część opisu stanu jest wspólna dla wielu obiektów więc nie muszą one zawierać kopii wszystkich danych.
		- PROXY
			- Pozwala tworzyć zastępce dla innego obiektu. Pełnomocnik (Proxy) nadzoruje dostęp do pierwotnego obiektu, pozwalając na wykonanie jakiejś czynności przed lub po przekazaniu do niego żądania.
	3. Wzorce BEHAWIORALNE - dotyczą algorytmów i rozdzielania odpowiedzialności między obiektami
		- ŁAŃCUCH ZOBOWIĄZAŃ
			- Pozwala przekazaywać żądania według łańcucha obiektów obsługujących. Załóżmy że chcemy stworzyć aplikację która wykorzystuje logowanie. Możemy wykorzystać łańcuch zobowiązań aby wykonywał odpowiednie kroki jedno po drugim. Wystarczy wtedy stworzyć aby obiekt obsługujący posiadał informacje o kolejnym w kolejności obiekcie. Tworzy się wtedy lista jednokierunkowa.
		- POLECENIE
			- Zmienia żądanie w samodzielny obiekt zawierający wszystkie inne informacje o tym żądaniu. Na przykład można zrobić edytor tekstu z podstawowymi funkcjonalnościami kopiowania, wycinania, wklejania i cofania. Każda funkcjonalność dziedziczyłaby po klasie Polecenie i jej zmienne i metody odpowiadałyby danej funkcjonalności. Przykładowo funkcja wytnij przechowywałaby wycięty tekst, komunikowała się z edytorem aby usunął część tekstu zaczynającym i kończońcym się na zaznaczeniu oraz zapisaniu wyciętego tekstu do schowka.
		- ITERATOR
			- Pozwala przechodzić sekwencyjnie po elementach zbioru bez konieczności eksponowania jego formy
		- MEDIATOR
			- Pozwala zredukować chaos zależności pomiędzy obiektami. Przykładowo posiadamy GUI w którym elementy typu przyciski, pola tekstowe itp komunikują się ze sobą. Niestety jest to relacja wiele do wielu co sprawia że dodanie nowego elementu może wiązać się z wzrostem geometrycznym. Zamiast tego dodajemy mediatora, czyli obiekt który będzie kontrolował zachowania między pojedynczymi obiektami. W heroesach mediatorem był silnik gry. Kreatura zamiast komunikować się z polem na którym stanęło, wysyłało zapytanie o to do silnika gry który zwracał odpowiedź, a następnie ten silnik gry sam aplikował efekt na kreaturę.
		- PAMIĄTKA
			- Pozwala zapisywać i przywracać wcześniejszy stan obiektu bez ujawniania szczegółów jego implementacji.
		- OBSERWATOR
			- Pozwala zdefiniować mechanizm subskrybcji by powiadamiać wiele obiektów o zdarzeniach odbywających się w obserwowanym obiekcie
		- STAN
			- Pozwala obiektowi zmienić swoje zachowanie gdy zmieni się jego wewnętrzny stan. Wygląda to tak, jakby obiekt zmienił swoją klasę.
		- STRATEGIA
			- Pozwala zdefiniować rodzinę algorytmów, umieścić je w osobnych klasach i uczynić obiekty tych klas wymienialnymi. Przykładowo chcemy stworzyć różne strategie opłaty za zamówienie. Chcemy aby użytkownik mógł płacić kartą, blikiem oraz paypalem. Wszystkie te strategie służą w jednym celu ale każdy jest osiągany w inny sposób np. płacenie kartą polega na wpisaniu danych karty oraz ich potwierdzeniu przez bank, a opłata blikiem wymaga wpisania kodu blik oraz potwierdzenia w aplikacji bankowej.
		- METODA SZABLONOWA
			- Definiuje szkielet algorytmu w klasie bazowej, ale umożliwia podklasom nadpisanie poszczególnych etapów algorytmu bez konieczności zmiany jego struktury. Przykładowo chcemy wrzucić posta na różne media społecznościowe 
		- ODWIEDZAJĄCY
			- Pozwala oddzielić algorytmy od obiektów na których pracują

4. Pytania teoretyczne
- Różnica między Tablicą, Listą, Mapą a Setem:
	- Tablica wymaga ustalenia wielkości, a umieszczenie obiektu w niej wymaga indeksu
	- Lista posiada dynamiczny rozmiar i nie musi mieć indexów
	- Mapa to obiekt mapujący wartości do kluczy, nie może posiadać duplikatów kluczy i klucz może posiadać co najwyżej jedną wartość (można użyć listy do przechowywania kilku)
	- Set to kolekcja nie posiadająca duplikatów
- Różnica między ArrayList a LinkedList
	- ArrayList 
		- używa **dynamicznej tablicy** do przechowywania elementów. 
		- Manipulacja nią jest wolniejsza bo używa tablicy, jeśli element jest usunięty to wszystkie następne są przesuwane w pamięci. 
		- Może służyć tylko jako lista bo implementuje List. 
		- Jest lepsze do przechowywania i pobierania danych. 
		- Pamięc dla elementów jest przyległa.
		- Standardowo przydzielana jest wielkość 10
		- ArrayList to tablica której można zmieniać wielkość
	- LinkedList
		- Korzysta z Double Linked List do przechowywania elementów
		- Manipulacja jest szybsza bo nie wymaga przesuwania bitów w pamięci
		- Może służyć zarówno jako lista jak i kolejka
		- Miejsce w pamięci nie jest przyległe
		- Nie ma standardowej wielkości, inicjalizowana jest jako pusta lista
- Różnica między Klasą Abstrakcyjną a Interfejsem
	- Klasa Abstrakcyjna
		- Możliwe jest posiadanie treści metod
		- Może posiadać zmienne instancji
		- Dozwolone są konstruktory
		- Dozwolone są metody statyczne
		- Klasa może dziedziczyć tylko po jednej klasie abstrakcyjnej
		- Może zapewnić implementację interfejsu
		- Może rozszerzać inną klasę i implementować wiele interfejsów
		- Może zawierać prywatne i chronione elementy
	- Interfejs
		- Może mieć tylko metody abstrakcyjne (czyli takie, które nie posiadają treści)
		- Nie może mieć zmiennych instancji
		- Nie może posiadać żadnego konstruktora
		- Metody statyczne są niedozwolone
		- Jeden interfejs może być implementowany przez wiele klas
		- Interfejs nie może zapewnić implementacji klasy abstrakcyjnej
		- Interfejs może rozszerzać tylko inny interfejs Javy
		- Elementy interfejsu są domyślnie publiczne
- Różnica między operatorem == a metodą Equals()
	- == jest operatorem i używamy go do porównania referencji (lub porównywania adresów). Sprawdza, czy obydwa obiekty wskazują na tę samą lokalizację w pamięci
	- equals() jest **metodą** która porównuje wartości obiektów. Można ją nadpisać aby działała odpowiednio do danej implementacji
- Różnica między JDK, JRE i JVM
	- JDK (Java Developement Kit) to pakiet programity javy które zawiera JRE oraz zestaw narzędzi niezbędnych do tworzenia oraz kompilowania oprogramowania.
	- JRE (Java Runtime Environment) to środowisko uruchomieniowe javy, w skład wchodzi JVM a także zbiór klas oraz narzędzi wymaganych do uruchomienia aplikacji
	- JVM (Java Virtual Machine) Jest to maszyna wirtualna oraz środowisko zdolne do wykonywania skompilowanego kodu.
- Różnica między Hashtable i Hashmap
	- HashTable jest zsynchronizowane i nie zezwala na klucze ani wartości nullowe
	- HashMap nie jest zsynchronizowana i zezwala na null. Nie gwarantuje że kolejnośc mapy pozostanie stała w czasie. 
- Różnica między wyjątkiem Checked i Unchecked
	- Checked - jeśli zamierzamy rzucić ten wyjątek to musimy go umieścić w klauzuli throws w sygnaturze metody. Muszą być obsłużone
	- Unchecked - nie trzeba umieszczać wyjątku w klauzuli throws ale można. Nie muszą być obsłużone
- Różnica między Override a Overload
	- Overloading - te same nazwy metod ale inne parametry
	- Overriding - te same podpisy metod w klasie nadrzędnej jak i podrzędnej
- Różnica między Throw a throws
	- Throw używane jest to wyrzucenia wyjątku
	- Throws używane jest w sygnaturze metody aby poinformować o wyjątku który może się pojawić
- Różnica między a+=b a a = a+b
	- a+=b oznacza a = (T) (a + b) gdzie T to typ obiektu a. a = a + b może nie zadziałać jeśli obiekty a i b są różnych typów np.
			```byte a = 1;
			int b = 2;
			a += b; // compiles
			a = a + b; // doesn't compile as a byte + int = int
			a = (byte) (a + b); // compiles as this is the same as +=```
- Co oznacza *public static void main( String args[] )*
	- public - modyfikator dostępu
	- static - metoda jest używana bez tworzenia obiektu klasy
	- void - typ zwracany metody
	- main - nazwa metody
	- String args[] - parametrs przekazywany do metody głównej
- Czy można wykonać program beze metody main?
	- Samego programu bez metody nie można uruchomić bez metody main, lecz można uruchomić kod w bloku static
- Czym jest obiekt *immutable*
	- Jest to obiekt, którego po stworzeniu nie można już modyfikować. Jeśli spróbujemy zmodyfikować obiekt immutable otrzymamy nowy obiekt (klon). Dobrym przykładem jest String.
- Jak działa sterta, stos i referencja
	- Sterta przechowuje obiekty a stos przechowuje zmienne. Referencja to adres w pamięci.
- Jak działa String Pool
	- String Pool jest specjalnym miejscem w pamięci do którego trafiają niektóre obiekty typu String które są utworzone poprzez literał. Jest on wykorzystywany w celach optymalizacyjnych czyli Stringi o tej samej zawartości będą wskazywały na to samo miejsce w pamięci komputera. Zmniejsza to użycie pamięci jak i przyspiesza porównywanie Stringów - jest duże prawdopodobieństwo że wskazują one na ten sam obszar pamięci.
- Jak działa Garbage Collector
	- Jest odpowiedzialny za czyszczenie sterty. Jeśli znajdują się na niej obiekty które nie są już używane zostaną one usunięte aby zwolnić miejsce dla nowych obiektów. 
- Jak działa NullPointerException
	- jeśli wywołamy metodę na referencji wskazującej na null zostanie rzucony ten wyjątek. Oznacza on że wartoś ma wartość null czyli pustą.
- Jaka jest różnica między String. StringBuildere i StringBuffer
	- String - to klasa immutable. Jeśli będziemy chcieli zmienić zawartość Stringa to zostanie utworzony nowy obiekt.
	- StringBuilder jest klasą mutable. Jest niesynchronizowany, bardziej wydajny od StringBuffera
	- String Buffer jest mutable. Jest synchronizowany i mniej wydajny od StringBuildera.
- Czy można nadpisać metodę private lub static?
	- private nie można bo nie mamy do niej dostępu z zewnątrz klasy
	- static nie można ponieważ metody static są częścią samej klasy
- Czy można zadeklarować zmienne static i metody w klasie abstract?
	- tak. można
- Jakie typy obszarów pamięci są przydzielane przez JVM?
	- Obszar Klasy - przechowuje struktury klas, na przykład stałe i pola inicjowane podczas uruchomienia programu, dan i cały kod metod
	- Sterta - obszar danych środowiska wykonawczego, w którym pamięć jest przydzielana obiektom
	- Stos - przechowuje ramki. Zawiera zmienne lokalne i wyniki pośrednie, a także bierze udział w wywołaniach i zwrotach metod.
	- Rejestr licznika programu - zawiera adres aktualnie wykonywanej instrukcji maszyny Javy
	- Stos metod natywnych - zawiera wszystkie metody natywne, które używane są w aplikacji.
- Czy można przeciążyć metodę main()?
	- Tak, można
- Czy możemy zadeklarować konstruktor jako final?
	- Nie. Konstruktor nie może być dziedziczony, więc nie ma sensu deklarować go jako final.
- Czy możemy zadeklarować interfejs jako final?
	- Nie. Ponieważ interfejs musi być zaimplementowany przez jakąś klasę zgodnie z jego definicją.
- Jaka jest różnica między static binding a dynamic binding?
	- static binding - są to wiązania które mogą zostać rozwiązane w czasie kompilacji przez kompilator. Wszystkie metody static, private i final są statycznie wiązane
	- dynamic binding - są to wiązania któych rozwiązanie może określić kompilator. Przykładem jest nadpisywanie.
- Jak utworzyć klasę tylko do odczytu?
	- moża to zrobić za pomocą słowa kluczowego private oraz getterów. Bez setterów nie będziemy w stanie modyfikować tych właściwości tylko je pobierać.
- Jak utworzyć klasę tylko do zapisu?
	- tak samo jak wyżej ale z setterami zamiast getterów
- Czy po każdym boku try musi wystąpić block catch?
	- Nie musi. Może wystąpić catch lub finally, ale nie musi żaden z nich.
- Jak działa słowo kluczowe final?
	- klasy - klasa nie może być rozszerzania
	- metody - metoda nie może być nadpisywana
	- zmienne - nie mogą być modyfikowane po inicjalizacji
- Różnica między final, finally i finalize
	- final - słowo kluczowe
	- finally - część bloku try-catch-finally która wykonuje się zawsze po blokach try/catch
	- finalize - metoda wykonywana zaraz przed tym jak Garbage Collector chce usunąc ten obiekt z pamięci.
- Co to jest Hibernate?
	- To framework służący do mapowania obiektowo relacyjnego. Odpowiada za sprawną komunikację z bazą danych.
- Czym jest i do czego służy klasa Locale?
	- Klasa Locale przechowuje informacje na temat wariantu dostosowania pod konkretny region. Tyczy się to języka, formatowania np. daty, separatora dziesiętnego itp.
- Czym są mikroserwisy i kiedy warto je stosować
	- Mikroserwisy to podejście do tworzenia architektury oprogramowania, gdzie cały program składa się z mniejszych, niezależnych od siebie elementów, które się ze sobą komunikują. Możemy podzielić tradycyjną, monolityczną aplikację na zwinne mikroserwisy i umieścić je w chmurze
- Kontrakt HashCode() i Equals()
	- equals() porównuje wartości obiektów i zwraca czy są one równe
	- hashCode() generuje dla obiektu kod hash w formie liczby całkowitej. Jest generowany na podstawie stanu obiektu. Powstały kod powinien zapewniać jak największą unikatowość wygenerowanego hashu.
	- Kontrakt:
		1. Każde wywołanie metody hashCode() na tym samym obiekcie **musi** zwrócić ten sam hash
		2. Jeśli dwa obiekty są sobie równe (wg. metody equals) to ich hashcode też musi być równy.
		3. Jeżeli dwa obiekty są różne (wg. metody equlas) to ich hashcode **może** być równy, jednak powinno być to unikane.
		4. **zwrotność** x.equals(x) zawsze daje true
		5. **symetryczność** x.equals(y) = y.equals(x)
		6. **przechodność** jeśli x.equals(y) = true i y.equals(z) = true to x.equals(z) także równa się true
		7. **spójność** - każdorazowe wywolanie metody equals musi zwrócić tą samą wartość
		8. każdy obiekt jest różny od null. Czyli każde wywołanie na nullu musi zwrócić false (x.equals(null) => false)
- Czym jest i do czego służy JDBC?
	- JDBC (Java DataBase Connectivity) to interfejs programowania służący do łączenia się z różnymi bazami danych. 
- Czym jest servlet?
	- Servlet jest to klasa która obsługuje żądania, przetwarza je i zwraca odpowiedź.

5. Bazy danych
- Rodzaje baz danych
	- Relacyjne - (np. MySQL) dane przechowywane są w relacjach (tabelach) i mogą być ze sobą powiązane
	- Obiektowe - baza danych oparta na obiektach
	- Relacyjno-Obiektowe - kompromis między bazami relacyjnymi i obiektowymi. Pozwala na operowanie na danych jak na obiektach, jednakże posiadają bazę relacyjną jako wewnętrzny mechanizm przechowywania danych.
	- Nierelacyjne - (np. MongoDB) zamiast w relacjach, dane są przechowywane np. w dokumentach (JSON), parach klucz-wartość lub za pomocą grafów
	- Strumieniowe
	- Temporalne
- Transakcje
	- Transakcja - metoda wykorzystywana przez aplikację do grupowania, operacji odczytu i zapisu w jedną logiczną jednostkę. Wynikiem transakcji jest albo Sukces albo Porażka
	- Transakcja gwarantuje jedną rzecz - wykonanie wszystkich operacji albo zmieni dane (COMMIT) jeśli wszystkie one będą zakończone sukcesem, lub brak tych zmian, jeśli choć jedna zakończy się porażką (ROLLBACK).
	- Transakcje mają swoje wady i zalety jak i ograniczenia. Nie są całkowicie darmowe (np. w kontekście wydajności). Gwarance bezpieczeństwa transakcji można znaleźć pod akronimem ACID:
		- A (Atomicity - Atomowość) - zapewnia że operacja lub zestaw operacji objętych **transakcją** zostanie **wykonana w całości** lub **anulowana**. Np. mamy Sukces -> Sukces -> Porażkę -> Sukces, to transakcja zostanie anulowana, a wykonane zmiany zostaną cofnięte - zajdzie ROLLBACK. Gdyby wszystkie operacje zakończyły się sukcesem, zmiany zostałyby zaakceptowane - COMMIT.
		- C (Consistency - Spójność) - odpowiada za fakt, że "baza kest w dobrym stanie" i tak na prawdę powinna być traktowana jako **właściwość aplikacji** a nie cecha **bazy danych**. Właściwośc aplikacji oznacza że to ona powinna sprawdzić czy transakcję w ogóle można wykonać (np. przy przelewie saldo konta powinno być nieujemne). Można zrzucić część odpowiedzialności na bazy danych za pomocą **triggerów** lub **ograniczeń**, jednak jeśli z przyczyn błędu aplikacji, dojdzie do zapisu błędnych danych, to sama baza tego nie powstrzyma.
		- I (Isolation - Izolacja) - oznacza, że transakcje są od siebie **odizolowane** - nie mogą mieć na siebie wpływu. Jest to ważne w przypadku dostępu do tych samych zasobów. Inna definicja to taka, że izolacja **gwarantuje** że transakcje które są wykonywane w sposób równoległy pozostawią bazę w stanie takim, jakby zostały one wykonane w sposób sekwencyjny.
		- D (Durability - Trwałość) - to obietnica, że po udanym zaakceptowaniu transakcji, zapisane dane nie zostaną zapomniane (bez względu na sytuacje awaryjne). Można to uzyskać poprzez zapich danych na dyski + dodanie operacji dziennika logów **WAL** (Write Ahead Log - operacja jest najpierw zapisywana do dziennika, a następnie wykonywana) lub przez **replikację** bazy danych.
- REST API
	- jest to styl architektoniczny który opiera się na komunikacji między klientem, API a bazą danych. Komunikacja odbywa się za pośrednictwem requestów HTTP, które następnie zwracają odpowiedź w postaci pliku JSON lub XML.
	- Protokoły HTTP:
		- Dostęp do zasobów odbywa się za pomocą protokołu HTTP. Wykorzystywane jest głównie 5 podstawowych czasowników HTTP:
			- GET - pobiera określony zasób według podanego identyfikatora
			- POST - tworzy nowy zasób. Jest wykorzystywany do wszystkich innych operacji, które nie wpisują się w ramy innych metod. Może służyć do pobierania danych w przypadku kiedy musimy w ramach body dostarczyć dodatkowe parametry.
			- PUT - Aktualizuje dany zasób na podstawie podanego identyfikatora. Może służyć do tworzenia nowego zasobu jeśli jego identyfikator jest znany.
			- DELETE - Usuwa określony zasób według identyfikatora.
			- PATCH - aktualizuje część wskazanego zasobu. od PUTa różni się tym że aktualizuje jedynie część zasobu.
	- Odpowiedź
		- Formaty danych jakie możemy otrzymać z REST API to najczęściej:
			- JSON - JavaScript Object Notation
			- XML - Extensible Markup Language
	- Model dojrzałości REST API:
		- LEVEL 0: THE SWAMP OF POX - Udostępnia usługi na wskazanym, jednym adresie, bez podzialu na metody HTTP. Klient przekazuje w żądaniu informace na temat działania jakie chce wykonać.
		- LEVEL 1: RESOURCES: Dostęp do zasobów odbywa się po konkretnych adresach bez podzialu na metody HTTP:
		  ```
		  http://localhost:8080/cars/get
		  http://localhost:8080/cars/add
		  http://localhost:8080/cars/update
		  http://localhost:8080/cars/delete
		  ```
		- LEVEL 2: HTTP VERBS - Stały adres i czasowniki HTTP
		  ```
		  GET http://localhost:8080/cars/
		  POST http://localhost:8080/cars/
		  PUT http://localhost:8080/cars/
		  DELETE http://localhost:8080/cars/
		  ```
		- LEVEL 3: HIPEREMEDIA CONTROLS - 
	- Statusy odpowiedzi:
		- Protokół HTTP dostarcza wiele statusów odpowiedzi, którymi możemy dostarczać klientowi w zależności od przebiegu jego żądania. Jest 5 podstawowych grup:
			-   1xx – informacyjne
			-   2xx – powodzenie realizacji
			-   3xx – przekierowania
			-   4xx – błąd po stronie klienta
			-   5xx – błąd po stronie serwera
	- 6 warunków REST API:
		1. Architektura klient-serwer - klient musi skomunikować się z serwerem aby uzyskać dostęp do usługi
		2. Jednolity interfejs - dla realizacji konkretnego działania jet tylko jedna droga dojścia
		3. Bezstanowośc - bez względu na to jakie wcześniej operacje zostały wykonane, to zawsze każda kolejna operacja nie będzie zmieniała rezultatu dla innej.
		4. Możliwośc zapisywania danych w buforze - wszystkie żadania, które trafiają do RESTa powinny być zapisane w buforze, jeżeli serwer nie jest w stanie obsłużyc na bieżąco wszystkich żądań.
		5. System warstwowy - jasny podział na warstwy. Użytkownik niekoniecznie musi mieć dostęp bezpośrednio do aplikacji - aplikacja może mieć dodatkową warstwę np. uwierzytelniającą
		6. Kod na żądanie - opcjonalny warunek. Użytkownik po wykonaniu danego żądania, może otrzymać odpowiedź zwrotną w formie kodu, który następnie może wykorzystać w swojej aplikacji.
- SOAP - Simple Object Access Protocol
	- SOAP jest bezpieczniejszy niż REST ale cięższy w implementacji. Wykorzystuje format XML do przesyłu danych. 
	- Umożliwia aplikacjom przekazywanie wiadomości mimo tego że są napisane w różnych językach programowania.