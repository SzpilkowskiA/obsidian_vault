# UML
## Wstęp
UML (Unified Modeling Lanugage, pol. Zunifikowany Język Programowana) - pół-formalny język wykorzystywany do modelowania różnego rodzaju systemów.

## Wykorzystanie
UML służy do modelowania dziedziny problemu (opisywania-modelowania fragmentu istniejącej rzeczywistości), w przypadku stosowania go do analizy oraz do modelowania rzeczywistości która ma dopiero powstać - tworzy się w nim głównie modele systemów informatycznych. UML jest używany wraz ze swoją reprezentacją graficzną - jego elementom są przypisane odpowiednie symbole wiązane ze sobą na diagramach.
Między obiektami występują [[Relacje między obiektami (UML)|relacje]].

## Diagramy
### Diagramy stuktur:
- Klas (najczęściej spotykanie, ang. class diagram)
- Obiektów (ang. object diagram)
- Komponentów (ang. component diagram)
- Wdrożenia (ang. deployment diagram)
--- UML 2.0 ---
- Struktur złożonych (ang composite structure diagram)
- Pakietów (ang. _package diagram_)
--- UML 2.2 ---
- Profili (ang. profile diagram, nowość wprowadzona w UML 2.2)

### Diagramy zachowań
- Czynności (ang. activity diagram)
- Przypadków użycia (ang. use case diagram)
- Maszyny stanów (ang. state machine diagram) (dla UML 1.x Stanów, ang. statechart diagram)
- Interakcji (diagram abstrakcyjny)
	- Komunikacji (ang. communication diagram) (dla UML 1.x Współdziałania, ang. collaboration diagram)
	- Sekwencji (ang. sequence diagram)
	--- UML 2.0 ---
	- Czasowe (ang. timing diagram)
	- Przeglądu interakcji (ang. interaction overview diagram)

![[Pasted image 20221005134601.png]]
Przykład klasy w UML

## Klasy 
Klasa jest reprezentowana poprzez prostokąt podzielony na trzy sekcje:
- Nazwę
- Atrybuty
- Operacje (Metody)

## Notacje klas
Dostępność metod lub atrybutów:
- **+ [[Modyfikatory dostępu#^990e7e|publiczna]]** (ang. Public) - element jest widoczny z każdego miejsca w systemie
- **# [[Modyfikatory dostępu#^d1dff9|chroniona]]** (ang. Protected) - element jest widoczny we własnej klasie i jej podklasach
- **- [[Modyfikatory dostępu#^31fce5|prywatna]]** (ang. Private) - element jest widoczny tylko we własnej klasie
- **~ [[Modyfikatory dostępu#^4ff4e2|publiczny wewnątrz pakietu]]** (ang. Default) - element jest widoczny tylko wewnątrz własnego pakietu