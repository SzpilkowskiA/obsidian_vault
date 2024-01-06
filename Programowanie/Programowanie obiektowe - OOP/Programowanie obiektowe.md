# Programowanie obiektowe
## Wstęp
Jest to paradygmat programowania, w którym programy definiuje się za pomoca [[Obiekty|obiektów]] - elementów łączących stan (czyli dane, inaczej zwane atrybutami) i zachowanie (czyli procedury, tu [[Klasy#^6324e5|metody]]). Obiektowy program komputerowy wyrażony jest jako zbiór takich obiektów, które komunikują się ze soba w celu wykonywania zadań.

Podejście to różni się od tradycyjnego [programowania proceduralnego](https://pl.wikipedia.org/wiki/Programowanie_proceduralne "Programowanie proceduralne"), gdzie dane i [procedury](https://pl.wikipedia.org/wiki/Podprogram "Podprogram") nie są ze sobą bezpośrednio związane. Programowanie obiektowe ma ułatwić pisanie, konserwację i wielokrotne użycie programów lub ich fragmentów.

Największym atutem programowania, projektowania oraz analizy obiektowej jest zgodność takiego podejścia z rzeczywistością – mózg ludzki jest w naturalny sposób najlepiej przystosowany do takiego podejścia przy przetwarzaniu informacji

Programowanie obiektowe składa się z 4 podstawowych filarów:
- [[Abstrakcja|Abstrakcji]] - modelowania obiektu o ograniczony kontekscie (symulator lotu będzie zawierał obiekt samolot z danymi na temat kontroli lotu, natomiast system rezerwacji biletów będzie zawierał samolot z listą miejsc)
- [[Enkapsulacja|Enkapsulacji]] - ukrycia części danych i metod obiektu zostawiając limitowany dostęp poprzez interfejs 
- [[Dziedziczenie|Dziedziczenia]] - tworzenia nowych klas, które są oparte na klasach nadrzędnych (np. z klasy zwierzę możemy stworzyć klasy kot, pies i jeż)
- [[Polimorfizm|Polimorfizmu]] - umiejętnośc programu do wykrycia prawdziwej klasy obiektu i użycia jej implementacji nawet wtedy gdy jej typ jest nieznany w tym kontekście 

Kompozycja jest zawsze lepsza od dziedziczenia

Zasady [[SOLID|SOLID]] - pięć zasad projektowania które mają na celu ułatwić zrozumienie projektu oprogramowania oraz uczynić projekt elastycznym i łatwym w utrzymaniu.