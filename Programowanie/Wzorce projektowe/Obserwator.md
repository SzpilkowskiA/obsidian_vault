 Observer jest to behawioralny wzorzec projektowy, który pozwala zdefiniofać mechanizm subskrypcji do powiadamiania wielu obiektów o wszelkich wydarzeniach, które te obiekty obserwują.

## Problem
Sklep z komórkami, klient chce nowego Iphone'a 14 Pro Max, ale nie wie czy jest na stanie.
Chodzenie codziennie i sprawdzanie jest bez sensu.
Wysyłanie maili przez sklep do każdego klienta kiedy nowy produkt trafi na półki też jest bez sensu.
Albo klient traci czas, albo sklep marnuje zasoby wysyłając kilka tysięcy emaili dziennie.
## Rozwiązanie
Implementacja subskrybcji. Tworzymy obiekt który może posiadać interesujące stany (publisher), i sprawimy że będzie on powiadamiał obiekty które chcą śledzić zmiany publishera (subscribers).

Nie jest to skomplikowane jak się wydaje. W rzeczywistości, potrzebujemy:
1. Array do przechowywania listy odniesień do subskrybentów.
2. Kilka publicznych metod, które pozwolą dodawać i usuwać subskrybentów z listy.

![[Pasted image 20221027230047.png]]

Kiedy ważne wydarzenie stanie się w obiekcie Publisher, przechodzi on przez liste subskrybentów i wywołuje specjalną metodę która powiadamia te obiekty.

Dlatego bardzo ważne jest to, że wszyscy subskrybenci implementują ten sam interface i publisher komunikuje się z nimi tylko poprzez ten interfejs. Interfejs powininen deklarować metodę powiadamiania, razem ze zbiorem parametrów które publisher może użyć do przekazania danych w kontekście wraz z powiadomieniem.

![[Pasted image 20221029143241.png]]

Jeśli aplikacja posiada kilka róznych typów publisherów i chcesz żeby subskrybenci byli kompatybilni z każdym z nich, można nawet sprawić, że każdy publisher będzie obsługiwał ten sam interfejs. Ten interfejs musiałby tylko opisać kilka metod subskrypcji.

## Struktura

![[Pasted image 20221029144110.png]]

1. Publisher wydaje wydarzenia do innych obiektów. Te wydarzenia występują wtedy, kiedy publisher zmieni swój stan lub wykona jakieś zachowanie. Publisher zawiera infrastrukture subskrybcji, która pozwala dołączyć nowym subskrybentom oraz odejść starym.
2. Kiedy nowe wydarzenie ma miejsce, publisher przechodzi przez listę subskrybentów i wywołuję metodę powiadamiania, która jest zadeklarowana w interfejsie subskrypcji, na każdym obiekcie subskrybenta.
3. Interfejs subskrybenta deklaruje interfejs powiadomień. W większości przypadków, składa się on z pojedyńczej metody ```update```. Metoda może mieć kilka parametrów które pozwalają publisherowi przekazać szczegóły wydarzenia wraz z updatem.
4. Concrete Subscribers wykonują pewne akcje w odpowiedzi do powiadomienia wydanego przez publishera. Wszystkie te klasy muszą implementować ten sam interfejs, po to, żeby publisher nie był sprzężony z konkretnymi klasami.
5. Zazwyczaj, subskrybenci potrzebują pewnych informacji kontekstowych, żeby poprawnie obsłużyć update. Z tego powodu, publisher często przekazuje częśc danych kontekstowych jako argumenty metody powiadamiania. Publisher może przekazać samego siebie jako argument, pozwalając subskrybentowi pobranie wymaganych danych,
6. Klient tworzy obiekty publishera i subskrybentów osobno, a następnie rejestruje subskrybentów do aktualizacji publishera.

#Pseudokod
```
// Klasa bazowa wydawcy zawiera kod zarządzania subskrypcją i metody powiadamiania.

class EventManager is 
	private field listeners: hash map of event types and listeners
	
	method subscribe(eventType, listener) is
		listeners.add(eventType, listener) 
	
	method unsubscribe(eventType, listener) is
		listeners.remove(eventType, listener)
	
	method notify(eventType, data) is
		foreach (listener in listeners.of(eventType)) do
			listener.update(data)
	 
// The concrete publisher contains real business logic that's
// interesting for some subscribers. We could derive this class
// from the base publisher, but that isn't always possible in
// real life because the concrete publisher might already be a
// subclass. In this case, you can patch the subscription logic
// in with composition, as we did here.

class Editor is
	private field events: EventManager
	private field file: File 
	
	constructor Editor() is
		events = new EventManager()
	
	// Methods of business logic can notify subscribers aboutchanges.
	
	method openFile(path) is 
		this.file = new File(path)
		events.notify("open", file.name)
	
	method saveFile() is 
		file.write()
		events.notify("save", file.name)
	// ...
 
// Here's the subscriber interface. If your programming language
// supports functional types, you can replace the whole
// subscriber hierarchy with a set of functions.

interface EventListener is
	method update(filename)

// Concrete subscribers react to updates issued by the publisher
// they are attached to.

class LoggingListener implements EventListener is
	private field log: File
	private field message
	
	constructor LoggingListener(log_filename, message) is
		this.log = new File(log_filename)
		this.message = message
	
	method update(filename) is
		log.write(replace('%s',filename,message))

class EmailAlertsListener implements EventListener is
	private field email: string
	
	constructor EmailAlertsListener(email, message) is
		this.email = email
		this.message = message
	
	method update(filename) is
		system.email(email, replace('%s',filename,message))

// An application can configure publishers and subscribers at
// runtime.
class Application is
	method config() is
		editor = new TextEditor()
		
		logger = new LoggingListener( 
			"/path/to/log.txt", 
			"Someone has opened the file: %s");
		editor.events.subscribe("open", logger)
		
		emailAlerts = new EmailAlertsListener(  
			"admin@example.com",
			"Someone has changed the file: %s")
		editor.events.subscribe("save", emailAlerts)
```
