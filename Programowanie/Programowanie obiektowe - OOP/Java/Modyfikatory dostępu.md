# Modyfikatory dostępu
## Wstęp
Modyfikatory dostępu to [[Słowa kluczowe|słowa kluczowe]], które mają wpływ na widoczność elementu który poprzedzają. Są to słowa kluczowe `public`, `protected` i `private`. Brak jakiegokolwiek ze wspomnianych słów kluczowych także ma wpływ na dostępność danego elementu. Czasami brak modyfikatora dostępu określa się jako dostęp typu “package”. Modyfikatory dostępu mogą być stosowane na przykład przed definicją [[Klasy|klasy]], czy [[Interfejs|interfejsu]]. Możemy ich także używać przed polami klasy, metodami czy [typami wewnętrznymi](https://www.samouczekprogramisty.pl/klasy-wewnetrzne-i-anonimowe-w-jezyku-java/). 
- ### PUBLIC
`public` który pozwala na najbardziej swobodny dostęp do elementu, który poprzedza. `public` może być używane przed definicjami klas, pól w klasach, metod czy typów wewnętrznych. Zakładając, że klasa poprzedzona jest `public` i element w tej klasie jest także `public`, jest on dostępny dla wszystkich.	 ^990e7e
- ### PROTECTED
Modyfikator `protected` ma znaczenie w przypadku dziedziczenia. Elementy poprzedzone tym modyfikatorem dostępu są udostępnione dla danej klasy i jej podklas. Dodatkowo elementy oznaczone modyfikatorem `protected` dostępne są dla innych klas w tym samym pakiecie. Modyfikatora `protected` nie można stosować przed klasami ^d1dff9
- ### DEFAULT
Brak modyfikatora dostępu również ma znaczenie. W przypadku gdy pominiemy modyfikator dostępu wówczas dana klasa czy element jest dostępna wyłącznie wewnątrz tego samego pakietu. Jest to podzbiór uprawnień, które nadaje modyfikator `protected`. Proszę spójrz na przykład poniżej: ^4ff4e2
- ### PRIVATE
Słowo kluczowe `private` jest najbardziej restrykcyjnym modyfikatorem dostępu. Może być stosowane wyłącznie przed elementami klasy, w tym przed klasami wewnętrznymi. Oznacza on tyle, że dany element (klasa, metoda, czy pole) widoczny jest tylko i wyłącznie wewnątrz klasy. Proszę spójrz na zmodyfikowaną klasę licznika: ^31fce5

## Porównanie modyfikatorów dostępu
