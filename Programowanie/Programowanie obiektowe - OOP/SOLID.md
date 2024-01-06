# S.
**Single Responsibility Principle** - Zasada pojedynczej odpowiedzialności.

	Klasa powinna podlegać zmianie tylko z jednego powodu

Spróbuj uczynić każdą klasę odpowiedzialną tylko za jędną część funkcjonalności oferowanej przez oprogramowanie i niech ta funkcjonalnośc będzie całkowicie hermetyzowana (ukryta) przez klasę.

# O.
**Open/Closed Principle** - Zasada otwarte/zamknięte.

	Klasy powinny być otwarte na rozszerzenia, ale zamnkięte dla modyfikacji.

Główną ideą tej zasady jest zapobieżenie zepsucia istniejącego kodu gdy implementuje się nowe funkcjonalności.

# L.
**Liskov Substitution Principle** - Zasada podstawienia Listova

	Rozszerzając klasę trzeba pamiętać, aby było możliwe przekazywanie obiektów nowej podklasy w miejsce obiektów klasy bazowej bez popsucia kodu klienta

Oznacza to, że podklasa powinna pozostać kompatybilna z zachowaniem klasy bazowej. Nadpisując metodę, należy rozszerzać zachowanie klasy bazowej zamiast zamieniać je na coś zupełnie innego.

- Typy parametrów metody podklasy powinny być zgodne z lub  
bardziej abstrakcyjne niż typy parametrów metody klasy bazo-  
wej.
- Typ obiektu zwracanego przez metody podklasy powinien być  
zgodny z lub być podtypem obiektu zwracanego przez metodę  
klasy bazowej.
- Metoda w podklasie nie powinna rzucać wyjątków o typie któ-  
rego nie rzuca metoda klasy bazowej.
- Podklasa nie powinna wzmacniać warunków wstępnych.
- Podklasa nie powinna osłabiać warunków końcowych.
- Niezmienniki klasy bazowej muszą zostać zachowane.
- Podklasa nie powinna zmieniać wartości prywatnych pól klasy  
bazowej.

# I.
**Interface Segregation Principle** - Zasada segregacji interfejsów.

	Klientom nie powinno się narzucać zależności od nieużywanych metod

Staraj się tworzyć interfejsy na tyle wąsko wyspecjalizowane, żeby klienci nie musieli implementować zachowań których nie potrzebują.

# D.