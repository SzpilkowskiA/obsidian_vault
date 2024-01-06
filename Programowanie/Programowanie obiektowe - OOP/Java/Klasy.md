# Klasy
## Wstęp
Klasy to foremki służące do tworzenia egzemplarzy obiektów. Nazwa pliku klasy jest taka sama jak nazwa klasy głównej w tym pliku. W skład Klasy wchodzą:
1. Zmienne - Zmienna to zarezerwowane miejsce w pamięci, w którym przechowywana jest wartość. Innymi słowy, gdy chcemy przechowywać dowolną wartość i nadać jej nazwę, wartość ta zajmuje zarezerwowane miejsce w pamięci i jest nazywana zmienną.
2. Konstruktory - Konstruktor jest jak specjalna metoda w [[Java|Javie]], która jest używana do inicjalizacji obiektu klasy. Konstruktor jest bardzo ważny dla każdej klasy i jeśli nie zadeklarujemy konstruktora, kompilator tworzy domyślny konstruktor klasy. Konstruktor musi mieć taką samą nazwę jak klasa Java. Nie posiada on typu zwracanego.
3. [[Metody|Metody]] - Metoda jest blokiem kodu, który jest uruchamiany tylko wtedy, gdy zostanie wywołany. Do metody można przekazywać dane, zwane parametrami. Metody służą do wykonywania pewnych czynności i są znane również jako funkcje. ^6324e5

## Tworzenie Klasy
```
class ClassName {
		int someNumber;
		String name;
		float other number;
		
		public ClassName(){
			someNumber = 5;
		}
		
		static void someMethod(){
			System.out.println("Hello World!!!");
		}
	}
```
## Tworzenie obiektu z klasy
Stworzenie klasy polega na ustaleniu jakiej klasy będzie nowy obiekt tutaj ClassName. Następnie ustalamy nazwe nowego obiektu (objectName). Przy użyciu słowa kluczowego [[Słowa kluczowe#^1bf487|new]] tworzymy nową instancję klasy obiektu za pomocą konstruktora ClassName().
```
ClassName objectName = new ClassName();
```
## Słowo kluczowe this
*[[Słowa kluczowe#^e9d952|this]]* oznacza że korzystamy z atrybutów i metod danego obiektu.
```
class SomeClass {
		int year;
		
		public void setYear(){
			this.year = 5;
		}
		
		public int getYear(){
			return this.year;
		}
		
		static void printName(){
			System.out.println(this.year);
		}
	}
```
