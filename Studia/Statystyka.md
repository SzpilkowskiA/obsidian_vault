# Wykład 1 - 27.02
za każdym razem na 8:45
slajdy udostępnianie = można mieć wyjebane

#zaliczenie
Egzamin pisemny:
- duża część prawie testowa - tak/nie/jednozdaniowe-wyrazowe odpowiedzi
- druga częśc bardziej wyrafinowana - odpowiedź pełnym zdaniem - z dziesięć zadań
- pseudokod/kod - jedno dwa zadanka, może jedno tylko tak było w zeszłym roku
koniec notatek

# Nauka na egzamin

## Wykład 1 - język R

## Wykłąd 2 - Rozkłady empiryczne i Model statystyczny

#### Populacja a próba

- Populacja - to zbiór dowolnych elementów, nieidentycznych z punktu widzenia danej cechy, który jest obiekterm zainteresowania statystyki.
  Populacja jest niejako **zbiorem wszystkich możliwych wyników danego badania**
  
- Próba - jest to **podzbiór populacji**, który jest wynikiem skończonej ilości badań danego parametru.

niech x = (x$_1$, x$_2$, ... , x$_n$)' będzie próbką, tzn. x$_1$, x$_2$, ... , x$_n$ będą obserwacjami zmiennej losowej X.

Zadaniem **statystyki opisowej** jest prezentacja rozkładu zmiennej X w próbce x (**rozkładu empirycznego**), za pomocą tabeli lub wykresu.

#### Rozkład empiryczny
Jest to rozkład zmiennej X w próbce x. Co to oznacza? przykładowo chcemy sprawdzić ile psów mają średnio ludzie. Grupa badawcza ma 10 osób i zadajemy im pytanie ile mają psów. od każdej spisujemy ilość.
Rozkład empiryczny może wyglądać tak:
0,0,1,0,3,0,1,0,10,10
może być posortowany:
0,0,0,0,0,1,1,3,10,10
może być przedstawiony w tabeli:

| Ilość osób 	| Ilość psów na osobę 	|
|--------------|---------------------	|
| 4          	| 0                   	|
| 1          	| 1                   	|
| 1          	| 2                   	|
| 1          	| 3                   	|
| 1          	| 9                   	|
| 2          	| 10                  	|

albo graficznie za pomocą wykresu.

#### Statystyki opisowe:
##### Klasyczne:
Uśredniają wartości próbki, np. momenty zwykłe

##### Pozycyjne
Bazujące na posortowanych (rosnąco) wartościach próbki, np. dolny kwartyl

#### Chakarterystyki tendencji centralnej rozkładu empirycznego:
- moment zwykły rzędu r
  m$_r$ = $1/n$ $\sum_{k=1}^n x^{r}_{k}$

Na przykład dla naszej ankiety z psami średnia wyniosłaby:
0 + 0 + 0 + 0 + 0 + 1 + 1 + 3 + 10 + 10 = 25
25/10 = 2.5

- Mediana:
	- n - nieparzyste
	  Me = x$_i$
	  i = (n+1)/2
	- n - parzyste
	  Me = (x$_i$ + x$_j$)/2
	  i = n/2, j = n/2 + 1

Dla naszej ankiety mediana wyniosłaby:
najpierw sortujemy wartości - 0,0,1,0,3,0,1,0,10,10 $\to$ 0,0,0,0,0,1,1,3,10,10
sprawdzamy czy n jest parzyste czy nieparzyste: n = 10 $\to$ n jest parzyste

i = 10/2 = 5
j = 10/2 + 1 = 6

Me = (x$_5$ + x$_6$)/2 = (0 + 1)/2 = 0.5

Jak widać mediana a średnia mocno się różni od siebie w tym przypadku, ponieważ średnią zakłócają nam dwie osoby które mają 10 psów, gdzie reszta ma od 0-3.

#### Charakterystyki rozrzutu rozkładu empirycznego:

- Odchylenie standardowe
  Jest to taka miara zmienności rozkładu, która mówi o tym o ile średnio odchylają się wartości badanej cechy od średniej arytmetycznej. Duże odchylenie informuje nas o tym że populacja jest bardzo zróżnicowana, a małe odchylenie mówi, że poszczególne jednostki skupiają się blisko średniej.
  
  Kiedy odchylenie standardowe z próby a kiedy z populacji?
  - Populacja
    Załóżmy że kupiłem 30 ciasteczek i chcę wiedzieć, ile średnio ważą i jakie jest odchylenie standardowe wagi moich ciasteczek. Interesują mnie tylko i wyłącznie kupione ciastka. Wtedy korzystamy z wzoru na odchylenie standardowe z populacji
  - Próba
    Jeśli chciałbym wiedzieć ile średnio ważą **wszystkie** ciastka z tej cukierni i jakie jest ich odchylenie standardowe - chce wiedzieć jaka jest szansa że przy następnym zakupie ciastka będzie ono większe lub mniejsze. Wtedy korzystam z wzoru dla próby.

  ![[Pasted image 20230611143425.png]]
  
  - n -  ilość obserwacji/pomiary - np. ilość odpowiedzi w ankiecie z psami
  - x$_k$ - wartość pomiaru zmiennej X na pozycji k
  - $\bar{x}$ - średnia arytmetyczna próby/populacji
   Powyższy wzór jest dla **próby** a nie **populacji**. W przypadku populacji bierzemy 1/n a nie 1/(n-1).
   
- Współczynnik zmienności
  Oznacza stosunek odchylenia standardowego do średniej.
  ![[Pasted image 20230611154602.png]]



Średnia arytmetyczna
Otrzymujemy ją poprzez zsumowanie wszystkich badanych obiektów i podzielenie tej sumy przez liczbęobiektów
![[Pasted image 20230611155048.png]]

Wady średniej arytmetycznej:
- Duży wpływ wartości skrajnych. Np. firma ma 5 pracowników, czworo zarabia 6000zł, a jedna 100 000zł. Średnie zarobki w tej firmie wyjdą na poziomie 24 800zł.
- Często przyjmuje wartość ułamka. Np. średnia ilość dzieci w rodzinach badanych wynosi 2,137 dziecka, co jest niemożliwe.
- Wszystkie wartości są tak samo ważne i mają identyczny wpływ na wynik. Np średnia cen książki na przestrzeni 10 lat nie weźmie pod uwagę inflacji oraz zainteresowania (książka w 2013 mogłaby kosztować 10zł, a w 2023 50zł). Przez co ustalenie ceny do sprzedaży dałoby niepoprawną kwotę (np 25zł czyli 25zł mniej niż powinna być).

Średnia Trymowana (ucinana, obcięta)
Jest to rodzaj średniej w której obserwacje porządkuje się od najmniejszej do największej, odrzuca się mały procent najbardziej ekstremalnych obserwacji na obu krańcach.
Zazwyczaj odrzuca się minimum i maksimum próbki lub wartości poniżej 25 centyla i powyżej 75 centyla (czyli 1/4 najniższych i najwyższych obserwacji)

![[Pasted image 20230611163855.png]]
Gdzie:
- k - ilość odrzucanych obserwacji

Moda (dominanta, wartość modalna)
jest to wartość najczęstsza występująca.
Modę nie zawsze da się obliczyć - jeśli występuje więcej niż jedna lub brak wartości dominujących.

Kwantyle
kwantyl rzędu _q_ (0 < _q_ < 1) w populacji jest taką liczbą x$_q$, że q * 100% elementów tej populacji ma wartość badanej cechy nie większą od x$_q$.
Przykładowo kwantyl rzędu 1/2 (q = 1/2) to mediana
Kwartyl to kwantyl rzędy 1/4 czyli dzieli populację na 4 części (1/4, mediana, 3/4)

Rozstęp = max - min

Średnia harmoniczna
Jest wykorzystywana do wyznaczania wartości średniej, gdy wartości cechy podawane są w przeliczeniu na stałą jednostkę innej zmiennej (np. km/h,  m$^3$/h itd.)
![[Pasted image 20230611165745.png]]

Przykład rowerzysty:
nie można użyć średniej arytmetycznej do zmierzenia średniej prędkości
przejechał 20km w ciągu godziny a następnie 20km w ciągu dwóch.
pierwsza prędkość to 20km/h druga to 10km/h.
Użycie średniej arytmetycznej da namy wynik 15km/h co oznacza że łącznie zajeło mu przejechanie 40km w 2h i 40min, ale wiemy przecież że jechał 3h.
Trzeba użyć średniej harmonicznej - wynik wyjdzie 13.3km/h co daje nam łączny czas 3h

Moment
Moment zwykły rzędu k to wartość oczekiwana k-tej potęgi tej zmiennej