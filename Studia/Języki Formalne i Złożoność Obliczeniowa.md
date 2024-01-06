# Sprawy Administracyjne
Zaliczenie:
- Zdanie ćwiczeń
- 50% z:
	- test końcowy - materiał obejmowac będzie wiedzę wykładową praktyczną (zadania) oraz część algorytmiczna.
	- na wykładzie będą podawane zadania algorytmiczne do napisania w pseudokodzie (od. około końca października). Ich rozwiązywanie/przesyłanie w wyznaczonym czasie jest obowiązkowe.
	- część algorytmiczna testu końcowego będzie (częściowo) podobna do rozwiązywanych j.w. zadań algorytmicznych
		- na ćwiczeniach tablicowych, począwszy od drugiego spotkania piszemy krótkie (5 min.) sprawdziany 0-1. Ich zakres: materiał teoretyczny (brzmienie definicji oraz twierdzeń) oraz proste zadania (domowe lub podobne do rozwiązywanych na zajęciach). Sprawdziany 0-1 są niepowtarzalne/nieodrabialne.
	- Ostateczna punktacja: całkowita liczba punktów do uzyskania 20, w tym 16 za część teoretyczną i zadaniową, 2pkt za część algorytmiczną, 1 punkt za jakość i pilność w rozwiązywaniu bieżących zadań algorytmicznych oraz 1pk. za odpowiednio przeliczone sprawdziany 0-1
	- punktacja i oceny:
		- 10-12/13-14/15-16/17-18/19-20 => 3/3,5/4/4,5/5
	- Slajdy nie są udostępniane. Zostaną podane strony w podręcznikach gdzie znajduje się omawiany materiał:
		- J.E. Hopcroft, R. Motwani - Wprowadzenie do teorii automatów, języków i obliczeń (HUM)
		- M. Sipser Wprowadzenie do teorii obliczeń (SIP)
		- G.E. Revesz Introduction to Formal Languages (REV)
	- Dyżury: wtorek 12:00-13:00, środa 14:00-15:00, pok. B2-30

# Wykład 1 
### Materiały z książek
- HUM: 29-32
- SIP: 13-14
- REV: 1-2

### Język
#### Funkcje języka:
- Poznawcza
- Społeczna
- Ekspresywna
#### Rodzaje języków
- Naturalne - powstawał w sposób ewolucyjny (żywe np. polski, martwe np. łacina, języki grup zawodowych...)
- Sztuczne - stworzone przez człowieka z pewnym celem (czy język migowy jest językiem naturalnym czy szucznym?... język rachunku zdań - p ^ q -> r?... a język esperanto?... a Python?...)
#### Trzy działy nauki o języku
- Syntaktyka (gramatyka) - nauka o poprawnej (zgodnej z regułami gramatyki języka) budowie wyrażeń tego języka (składnia):
	- Saw you Peter? -> Did you see Peter?
	-  x + 2(=(1 -> (x + 2) = 1
- Semantyka (znaczenie wyrażeń) - nauka o znaczeniu wyrażeń tego języka.
	- Małe dziewczynki chodzą powoli (syntaktycznie ok) *przymiotnik* + *rzeczownik* + *czasownik* + *przysłówek*
	- Miętowe włosy grają żwawo (semantycznie?... ). 
	- "Miętowe Włosy" grają żwawo (semantycznie ok, Miętowe Włosy jako nazwa kapeli).
- Pragmatyka (dotyczy sposobów użycia języka w różnych sytuacjach i w celu uzyskania różnych efektów) - nauka o sposobach posługiwania się wyrażeniami języka, niejawnych sposobach przekazu informacji przez wypowiedź, sposobach jej rozumienia
	- Zimno tu... (Zamnkij okno...)
	- Czy możesz podać sól? (Mogę nie jest zbyt grzeczne)
	- Będziemy w kontakcie... (po rozmowie kwalifikacyjnej)
#### Badania nad językami - kilka nazwisk
- Ferdinand de Saussure, Szwajcar, 1857-1913, nieco poza naszymi zainteresowaniami
- Franz Boas, Niemiec (1858-1942), atropolog i językoznawca, badacz kultur północnoamerykańskich, rdzennych a wymierających już wówczas plemion. TezaL Przez poznanie języka do poznania badanej społeczności. Metoda: Katalogowanie i analizowanie mało znanych?nieznanych języków.
- Leonard Bloomfield, USA (1887-1949), językoznawca, autor
- Noam Chomsky, USA (1928-teraz), językoznawca, socjolog, autor Syntactic Structures  (1957), twórca gramatyk (transformacyjno)-generatywnych i tzw. hierarchii Chomsky'ego języków.

### Naom Chomsky - głowna idea
Język, choć zawiera potencjalnie nieskończenie wiele zdań, należy opisać **skończonym** zbiorem reguł, które pozwalają go wyprodukować (wygenerować). Taki zbiór reguł generujących język tworzyć będzie gramatykę tego języka. 
W matematyce i informatyce takie rzeczy robimy codziennie:
	- procedura przypisania jedynki n = 0, n:= n+1
	- definicja zbioru FOR formuł języka rachunku zdań:
Oznaczmy noun - rzeczownik, adj - przymiotnik. Niech "gramatyka" ma następujące reguły:
noun ->adj noun, noun -> noun **and** noun, adj -> adj **and** adj
noun -> cat|dog adj -> small|big|grey|black\

zaczynając od noun i zastępując lewe strony reguł prawymi możemy wyprodukować ciąg *small cat and black dog* w następujący sposób:
noun =>
noun **and** noun =>
adj noun **and** noun =>
adj noun **and** adj noun =>
**small** noun **and** adj noun =>
... =>
**small cat and black dog**.

Kiedy nie byłeś na jednej lekcji matematyki w podstawówce i nie wiesz ile to 2 + 3 * 4... czy to wynosi 14 czy 20? bo nie znasz kolejności działań
Tak bywa też w logice: p ^ q v r ma różne wartości przy ułożeniu nawiasów tak (p^q) v r lub tak p ^ (q v r)

Podobne kłopoty sprawiają zdania języka naturalnego. Prowadzi to to dwu- i wieloznaczności:
- Jan filmuje kamerą swojego ojca
- Kogo Jan filmuje kamerą? (Jan filmuje kamerą) swojego ojca
- Czyją kamerą Jan filmuje? Jan filmuje (kamerą swojego ojca)

#### Wieloznaczność semantyczna
- Flying planes can be dangerous:
	- Latające samoloty mogą być niebezpieczne
	- Latanie samolotami może być niebezpieczne
- Susan saw the man in the park with a telescope:
	- Susan widziała w parku mężczyznę przez teleskop
	- Susan widziałą w praku mężczyznę, który miał teleskop
	- Susan widziała mężczyznę w parku z teleskopem

#### Pisanie progamu:
- konieczność znajomości gramatyki języka programowania
- wyprodukowanie skończonego ciągu znaków, składającego się z liter i cyfr, o odpowiedniej strukturze, w nadziei, że ten ciąg jest poprawnie napisanym progamem.
- sprawdzenie, czy tak jest następuje w czasie parsowania, podczas wykonywania twz. analizy leksykalnej, która ciąg znaków z wejścia dzieli na tokeny (podstawowem atomowe, znaczące elementy języka), oraz podczas wykonywania tzw. analizy syntaktycznej, która na wejścu daje drzewo reprezentujące program.
- Będziemy zatem traktować języki jako obiekty podlegające dwom rodzajom działań:
	- generowaniu - odpowiedzalne za generowanie będą gormalizmy zwane gramatykami, oraz
	- rozpoznawaniu - odpowiedzialnymi za to formalizmami będą automaty.

Pojęcia podstawowe
Przez alfabet (czasem używamy słowa **słownik**) będziemy rozumieć dowolny niepusty i skończony zbiór symboli (liter, znaków) atomowych, tj. takich w skład których nie wchodza inne litery z tego zbioru. 
Alfabety w literaturze oznacza się literami $\Sigma$ (Sigma) lub V, V$_1$
My najczęściej będziemy stosować drugi zapis.

**Definicja**: **Słowem** nad alfabetem V nazywamy dowolny skończony ciąg symboli alfabetu V
Zbiór wszystkich słów nad alfabetem V oznaczamy V*. Do V* należy, zgodnie z definicją słowo składające się z 0 symboli alfabetu V. Nazywamy je słowem pustym i oznaczamy $\varepsilon$. Oznaczamy: V+ = V*/{$\varepsilon$}

$\varepsilon$ (epsilon) => słowo puste, element neutralny, składające się z 0 symboli alfabetu

![[Pasted image 20221011164745.png]]

Przykłady
1. V = {0, 1}. Mamy: $\varepsilon$ (epsilon), 0, 1, 01, 11, 01011, 11001100... należące do V*
2. Niech V = {a, ą, b, c, ć... x, y, z, ź, ż}. Wówczas klops, kloss, kos, aman, ąę należy do V$_1$*. Uwaga: cały słownik jezyka polskiego jest właściwym podzbiorem V$_1$*
3. Niech V$_2$ będzie zbiorem wszystkich znaków z klawiatury. Wówczas każdy poprawnie napisany program np. w języki Python jest słowem nad V$_2$. Oczywiście, nie jest na odwrót.
4. Niech V$_3$ będzie zbiorem słów (ustalonego) słownika języka polskiego. Słowna tego słownika traktujemy jako elementy niepodzielne (atomy). Wówczas niektóre słowa nad V$_3$ są poprawnymi zdaniami języka polskiego (choć oczywiście nie wszystkie).

# Wykład 2

Podstawowa operacja na słowach - **konkatenacja**
**Konkatenacja**:
Dla dowolnych słów P I Q należących do V* konkatenacja P i Q oznacza PQ, zdefiniowana jest w następujący sposób:
1. jeśli P = a1...an i Q - b1...bm, to PQ = a1...anb1...bm
2. jeśli P = $\varepsilon$ (odp. Q = $\varepsilon$), to PQ = Q (odp. PQ = P)
**Uwaga**: Punkt (2) definicji oznacza, że $\varepsilon$ jest **elementem neutralnym** operacji konkatenacji słów.

Własności operacji konkatenacji:
	1. łączność: dla dowolnych P, Q i R zachodzi P(QR) = (PQ)R
	2. w ogólności - brak przemienności, tzn. nie jest tak, że dla dowolnych słów P i Q zachodzi PQ = QP
	3. brak elemntu odwrotnego (-P) takiego że P(-P) = 1

Odbicie zwierciedlane słowa
Niech P $\in$ V*. **Odbiciem zwierciedlanym słowa** P (rewersem P) nazywamy słowo oznaczone P$^{-1}$ zdefiniowane indukcyjnie w następujący sposób:
1. $\varepsilon$$^{-1}$ = $\varepsilon$
2. (Pa)$^{-1}$ = aP$^{-1}$

obliczyć abc$^{-1}$
abc$^{-1}$ = c(ab)$^{-1}$ = c(b(a)$^{-1}$) = c(b(a($\varepsilon$)$^{-1}$)) =cba$\varepsilon$ = cba

Podsłowo
Niech P należy do V*. Słowo Q nazywamy podsłowem słowa P jeśli istnieją słowa Q1 * Q2 należące do V* takie, że P = Q$_1$QQ$_2$. Jeśli nadto Q$_1$ (odp. Q$_2$) jest słowem pustym, to Q nazywamy prefiksem (odp. sufiksem słowa P)

To, że Q jest podsłowem słowa P oznaczamy symbolicznie Q $\sqsubset$ P.
Ćwiczenie. Oblicz liczbę podsłów słowa abcabca.

Długość słowa
Długość słowa P należącego do V* nazywamy liczbę naturalną |P| określoną indukcyjnie w następujący sposób:
1. |$\varepsilon$| = 0
2. |Pa| = |P| + 1

Konkatenacja Języków
Konkatenacją języków L$_1$, L$_2$  $\in$ V* nazywamy język oznaczany L$_1$L$_2$ taki, że:
 L$_1$L$_2$ = {P$_1$P$_2$ : P$_1$ $\in$ L1, P$_2$ $\in$ L2}

Przykład:
 L$_1$ = {a, aa},  L$_2$ = {$\varepsilon$, b, ab}

 L$_1$L$_2$ = {a, ab, a$^2$b, a$^2$, a$^3$b}

Operacje potęgi języka
Potęga słowa 
Niech P należy do V* i niech n $\geq$  0, n-tą potęgą słowa P nazywamy słowo oznaczane P$^n$ zdefiniowane indukcyjnie w następujący sposób
(i) P$^0$ = $\varepsilon$
(ii) P$^{n+1}$ = P$^n$$\cdot$P

Potęga języka
Niech L $\subset$ V* i niech n $\geq$ 0. n-tą potęgą jęzuyka L nazywamy język oznaczany L$^n$ zdefiniowany indykcyjnie w następujący sposób
(i) L$^0$ = {$\varepsilon$}
(ii) L$^{n+1}$ = L$^n$$\cdot$L

Uwaga obiekty epsilon, zbiór pusty i {$\varepsilon$} są rózne między sobą

Jak obliczyc z definicji wartość L$^2$
Dla L = {a, ab} obliczyć L$^n$ dla n = 0, 1, 2, 3
- L$^0$ = {$\varepsilon$}
- L$^1$ = {a, ab}
- L$^2$ = {a$^2$, a$^2$b, aba, (ab)$^2$}
- L$^3$ = {a$^3$, a$^2$ba, aba$^2$,(ab)$^2$a, a$^3$b, a$^2$bab, aba$^2$b, (ab)$^3$ }

Dla L = {a$^n$ : n $\geq$ 0} obliczyć L$^n$ dla n = 0, 1, 2, 3
- L$^0$ = {$\varepsilon$} 
- L$^1$ = {$\varepsilon$, a, a$^2$, a$^3$, a$^4$..., a$^n$}
- L$^2$ = {$\varepsilon$, a, a$^2$, a$^3$, a$^4$..., a$^n$}
- L$^3$ = {$\varepsilon$, a, a$^2$, a$^3$, a$^4$..., a$^n$}

Dla L = {a$^n$ : n $>$ 0} obliczyć L$^n$ dla n = 0, 1, 2, 3
- L$^0$ = {$\varepsilon$} 
- L$^1$ = {a, a$^2$, a$^3$, a$^4$..., a$^n$}
- L$^2$ = {a$^2$, a$^3$, a$^4$..., a$^n$} 
- L$^3$ = {a$^3$, a$^4$..., a$^n$}

Uwaga: To, że zachodzi P $\in$ L$^n$ oznacza, że słowo P można podzielić na n podsłów (niekoniecznie takich smaych), z których każde należy do L. Formalnie:
Jeżeli P $\in$ L$^n$ to P = P$_1$P$_2$ ... P$_n$ i wszystkie P$_i$ $\in$ L

**Przykład**
Niech L = {a, ab}. Dla jakiego n zachodzi aababaabab $\in$ L$^n$?

a | ab | ab | a | ab | ab $\Rightarrow$ L$^6$

Niech L = {a ,ab, ba ,aab, baab}. Dla jakiego n zachodzi abaabaab $\in$ L$^n$?
Jest to niejednoznaczne

a|baab|aab lub ab|aab|aab $\Rightarrow$ n = 3
a|baab|a|ba $\Rightarrow$ n = 4
a|ba|a|ba|ab $\Rightarrow$ n = 5

##### Operacja domknięcia Kleene'ego języka
Mając język L możemy obliczyć wszystkie jego potęgi i wysumować:
L$^*$ = L$^0$ $\cup$ L$^1$ $\cup$ L$^2$ $\cup$ L$^3$ $\cup$ L$^4$ $\cup$ L$^5$ $\cup$ L$^6$ $\cup$ ...
Uzyskany język, będący sumą wszystkich potęg języka L nazwyamy domknięciem Kleene'ego języka L i oznaczamy L$^*$

Domknięciem Kleene'ego języka L nazywamy język
L$^*$ = $\bigcup$ (n $\geq$ 0) L$^n$

##### Pozytywne domknięcie Kleene'ego
Pozytywnym domknięciem Kleene'ego języka L nazywamy język
L$^+$ = $\bigcup$ (n $\geq$ 1) L$^n$

Oczywiście zachodzi L$^+$ $\subset$ L$^*$ 

L$^+$ = L$^*$ wtety i tylko wtedy, gdy $\varepsilon$ $\in$ L

L$_1$ = {a}, L$_2$ = {$\varepsilon$, a}

L$_1$$^n$ = {a$^n$}
L$_1$$^*$ = {a, a$^2$, a$^3$, ... , a$^n$} $\Rightarrow$ L$_1$$^*$ = {a$^n$ : n $>$ 0}

L$_2$$^n$ = { a$^m$ : 0 $\leq$ m $\leq$ n} 
L$_2$$^*$ = {$\varepsilon$, a, a$^2$, a$^3$, ... , a$^m$} $\Rightarrow$ L$_2$$^*$ = {a$^n$ : n $\geq$ 0}

**Zadanie**
Niech L = {aa, ab, ba, bb}. Podaj wzór strukturalny języka L$^*$

SIP 43
REV 9-10

# Wykład 3

HUM: 37-78
SIP: 29-76
REV: 60-70

##### Pojęcie stanu
Nieformalne - stan urządzenia to gotowośc tego urządzenia do wykonania pewnej czynności pod wpływem pewnego zewnętrznego impulsu.

"Politechniczny" model automatu skończenie stanowego

###### Deterministyczny automat skończenie stanowy
Deterministycznym automatem skończenie stanowum nazywamy uporządkowaną piątkę:
$\mathfrak{A}$ = <K, T $\delta$, q$_0$, H>
1. K jest niepustym i skończonym **zbiorem stanów**
2. T jest niepustym i skończonym alfabetem wejścia (taśmy)
3. q$_0$ $\in$ K jest wyróżnionym stanem początkowym
4. H $\subset$ L jest wyróżnionym zbiorem stanów akceptujących (końcowym)
5. $\delta$ jest funkcją przejścia taką, że $\delta$ : K x T -> K

Przykład:
K = {q$_0$, q$_1$, q$_2$}, T = {a, b}, H = {q$_2$}

$\delta$ : K x T -> K

# Wykład 4

Liczba wystąpień symbolu a w słowie P jest oznaczanej jest oznaczane:
	#$_a$P

1. Dlaczego deterministyczny skończenie stanowy jest skończenie stanowy?
	Ponieważ liczba stanów w których może się stanąć jest skończona
2. Dlaczego deterministyczny automat skończenie stanowy jest deterministyczny?
	Dla każdego wejścia jest tylko jeden wynik. Nie ma wyboru. jak jest w danym stanie i widzi dany symbol to przechodzi do danego.
3. Determinizm automatu a kształ diagramu: z każdego stanu wychodzą krawędzie znaczone **wszystkimi** symolami taśmy i dla każdego symbolu jest to **dokładnie jedna** krawędź.
4. Co by było, gdyby było inaczej?

| $\delta$ |      a      |     b      |
|------------ | ------------| ------------|
|$\to$ q$_0$ | | |
|q$_1$ | | |
|q$_2$ | | |

Naruszenie warunku 3. prowadzi do pojęcia automatu skończenie stanowego niedeterministycznego, tj. takiego, w którym wartościami funckji przejścia są **zbiory** stanów, tzn. $\delta$ : K x T -> P(K)

# Wykład 5

Idea **niederministycznego** automatu skończenie stanowego:
o ile funkcja przejścia automatu deterministycznego każdej parze (stan, symbol) przyporządkowywała jeden stan (to znaczy mieliśmy $\delta$ : K x T $\to$ K), to 
funkcja przejścia automatu niedeterministycznego każdej parze (stan, symbol) będzie przyporządkowywać pewien zbiór stanów tzn będziemy mieli delta : K x T -> P(K), gdzie zbiór P(A) (zbiór potęgowy zbioru A) jest zdefiniowany nastepująco:
P(A) = {B : B $\subset$ A}
Przypomnienie: jeśli A = {a, b, c}, to
P(A) = {0, {a}, {b}, {c}, {a,b}, {a, c}, {b, c}, {a,b,c}}
oraz jesli $\bar{\bar{A}}$  = n to $\bar{\bar{P(A)}}$ = 2$^n$

Niedeterministyczny automat skończenie stanowy
Niedeterministycznym automatem skończenie stanowym nazywamy uporządkowaną piątkę:
$\mathfrak{A}$ = $\langle$K, T, $\delta$, Q$_0$, H$\rangle$, w której
1. K jest niepustym i skończonym zbiorem **stanów**
2. T jest niepustym i skończonym **alfabetem wejścia** (taśmy)
3. Q$_0$ $\subset$ K jest wyróżnonym **zbiorem stanów początkowych**
4. H $\subset$ K jest wyróżnionym zbiorem **stanów akceptujących** (końcowych)
5. $\delta$ jest (nied.) **funkcją przejścia** taką, że $\delta$ : K x T $\to$ P(K)

Drzewiasta reprezentacja przejścia niedereministycznego automatu skończnie stanowego nad słowem.
Niech niedeterministyczny automat skończenie stanowy $\mathfrak{A}$ będzie zadany następującą tabelą przejścia: $\delta$ : K x T $\to$ P(K)

| $\delta$ |      a      |     b      |
|------------ | ------------| ------------|
|$\to$ q$_0$ | {q$_0$, q$_2$} | {q$_0$, q$_1$} |
|q$_1$ | {q$_0$, q$_1$} | {q$_0$} |
|q$_2$ | $\emptyset$ | {q$_2$} |

# Wykład 6

Twierdzenie Scotta, łatwa inkluazja
Dla każdego języka akceptowanego przez deterministyczny automat skończenie stanowy $\mathfrak{A}$ można skonstruować niedeterministyczny automat skończenie stanowy $\mathfrak{A'}$ taki, że L($\mathfrak{A}$) = L($\mathfrak{A'}$), tzn. $\mathfrak{L}$$_{det}$ = $\mathfrak{L}$$_{ndet}$.

Twierdzenie Scotta, trudniejsza inkluzja
Dla każdego języka akceptowanego przez niedeterminisczyny automat skończenie stanowy $\mathfrak{A}$ można skonstruować deterministyczny automat skoczenie stanowy $\mathfrak{A'}$ taki, że L($\mathfrak{A}$)  = L($\mathfrak{A'}$), tzn. $\mathfrak{L}$$_{det}$ = $\mathfrak{L}$$_{ndet}$. 

Twierdzenie Scotta
$\mathfrak{L}$$_{det}$ = $\mathfrak{L}$$_{ndet}$

Dowód (konstrukcja)

Mamy dany niedeterministyczny automat $\mathfrak{A}$ = $\langle$K, T, $\delta$, Q$_0$, H$\rangle$.
Konstruujemy deterministyczny automat $\mathfrak{A'}$ = $\langle$K', T', $\delta$'', q$_0$', H'$\rangle$,
dla którego zajdzie L($\mathfrak{A}$)  = L($\mathfrak{A'}$).
Kładziemy: 
T' = T
K' = $\mathcal{P}$(K)
q$_0$' = Q$_0$
H' = {A $\in$ K' : A $\cap$ H $\ne$ 0}
$\delta$ '(A, a) = $\bigcup$ (q $\in$ A)  $\delta$ (q, a)

Ceną, jaką płaimy za detereminizację jest wykładniczny wzrost liczby stanów automatu deterministycznego.

K = {q$_0$, q$_1$, q$_2$}, K' = $\mathcal{P}$(K)

K' = {$\emptyset$, {q$_0$}, {q$_1$}, {q$_2$}, {q$_0$, q$_1$}, {q$_0$, q$_2$}, {q$_1$, q$_2$}, {q$_0$, q$_1$, q$_2$}}
K' = {q$\emptyset$, q$^0$, q$^1$, q$^2$, q$^{01}$, q$^{02}$, q$^{12}$, q$^{012}$} gdzie górny idex oznacza indexy poszególnych stanów w pozdbiorze P(K)

P $\in$ {0, 1}* taki, że 1 występuje na 2-gim miejscu od końca

# Wykład 7

# Wykład 8

Dzisiaj jest fajny fragment

Zadanie
Narysuj diagram przejścia deterministycznego automatu skończenie stanowego akceptującego język oznaczany wyrażeniem regularnym:
	ab* + ba*



Zadanie
Podaj wyrażenie regularne oznaczające język akceptorawny przez następuącu automat skończenie stanowy:

(  a* b a* b a*  )* ba*   -   odcięcie sufixu
a* ba* (ba* ba*) *   -   odcięcie prefixy


**Uwaga**
W definicji automatu skończenie stanowego z $\varepsilon$-przejściami założyliśmy, że Q0 i H są dowolnymi podzbiorami zbioru stanów K. Bez utraty języka akceptowanego przez automat możemy założyć, że oba te zbiory są jednoelementowe wprowadzają nowy (i jedyny) stan początkowy, nowy (i jedyny) stan końcowy oraz $\varepsilon$-przejścia w następujący sposób:

Twierdzenie Kleene'ego (łatwiejsza implikacja)
Dla każdego wyrażenia regularnego w $\in$ Reg(v) można skonstruować deterministyczny automat skończenie stanowy $\mathfrak{A}$ taki, że L(w) = L($\mathfrak{A}$).

Uwgai dot. dowodu:
1. Ponieważ umiemy pozbyć się $\varepsilon$-przejść z automatu z $\varepsilon$-przejściami i uzyskać w ten sposób automat niedeteministyczny, a ten, wykorzystując twierdzenie Scotta umiemy zdeterminizować, zatem w dowodzie wystarczy jako automat $\mathfrak{A}$ skonstruować automat z $\varepsilon$-przejściamy.
2. W dowodze będziemy posługiwać się automatami z $\varepsilon$-przejściami z jednym stanem poczatkowym i jednym stanem końcowym wprowadzone przed chwilą.
3. Dowód prowadzimy indukcją po budowie wyrażeń regularnych

Zbiór wyrażeń regularnych nad V
Zbiór wyrażeń regularnych nad alfabetem V to zbiór oznaczany przez Reg(V) zdefiniowany indukcyjnie w następujący sposób:
(i) **o** $\in$ Reg(V) - oznacza zbiór pusty - $\emptyset$
(ii) **e** $\in$ Reg(V) - oznacza $\varepsilon$
(iii) jeśli a $\in$ V, to a $\in$ Reg(V)
(iv) jeśli u,v $\in$ Reg(V), to (u + v), (u * v), (u*) $\in$ Reg(V)

Język oznaczany przez wyrażenie regularne v
Niech v $\in$ Reg(V)




Twierdzenie Kleene'ego (łatwiejsza implikacja ) - **dowód**
w = o i L(o) = $\emptyset$. Konstuujemy zatem automat (z $\varepsilon$-przejściami) $\mathfrak{A}$ taki, że L($\mathfrak{A}$) = $\emptyset$


# Wykład 9

Rozbiór gramatyczny zdań

Małe dziewczynki chodzą powoli.

S - symbol oznaczający zdanie:
	NP - grupa podmiotów (Noun Phrase):
		Adjective - przymiotnik
		Noun - rzeczownik
	VP - grupa orzeczenia (Verb Phrase):
		Verb - czasownik
		Adverb - przysłówek

Małe - przymiotnik
Dziewczynki - rzeczownik
Chodzą - czasownik
Powoli - przysłówek

Reguła przepisywania, wyprowadzenie słowa w jednym kroku, wyprowadzenie słowa

P => Q
Wyprowadzenie słowa Q ze słowa P a dokładniej wyprowadzenie słowa Q w jednym kroku ze słowa P

Rzeczy odpowiedzialne za wyprowadzenie słowa to Reguły przepisywania
Jest to para słów (R, T) przy czym zakładamy że R =/= $\varepsilon$
zapis R -> T - co ma czym zastąpić

P => Q - oznacza otrzymane słowo 
T$_1$ R T$_2$ => T$_1$ T T$_2$

=> z * nad oznacza wielokrotne wyprowadzenie w jednym kroku

1. P = Q
2. P = P$_1$ , P$_2$, P$_3$, P$_4$, ... ,P$_n$ = Q
Dla każdego i (1 < i < n-1) można wyprowadzić P$_1$ = P$_{i+1}$. 
P = P$_1$ => P$_2$ => P$_3$ => ... => P$_{n-1}$ => P$_n$ = Q


Gramatyka generatywna:

Gramatyka generatywna G to uporządkowana czwórka (V$_N$, V$_T$, S, F) w której:
- V$_N$ jest niepustym i skończonym zbiorem **nieterminałów** (symb. nieterminalnych)
- V$_T$ jest niepustym i skończonym zbiorem terminałów (symb. terminalnych), i V$_N$ $\cap$ V$_T$ = $\emptyset$.
- S $\in$ V$_N$ jest wyróżnionym **symbolem początkowym**.
- F jest skończonym zbiorem par (P, Q) takich, że P, Q $\in$ (V$_N$ $\cup$ V$_T$)* i w P występuje conajmniej jeden symbol nieterminalny.

Uwagi:
1. Pary (P, Q) będziemy nazywać **regułami przepisywania** (reg. produkcji) gramatyki
2. Zamiast zapisu (P,Q) będziemy pisać P $\to$ Q


# Wykład 10

Typy gramatyk
Gramatyka generatywna G = (V$_N$, V$_T$, S, F) jest nazywana gramatyką **typu i** jesli jej zbiór reguł przepisywania F spełnia następujące warunki:
1. i = 0: żadne (oprócz ogólnych) warunki ni są nakładane
2. i = 1: każda reguła ma postać Q$_1$AQ$_2$ $\Rightarrow$ Q$_1$PQ$_2$, gdzie Q$_1$, Q$_2$ i P $\in$ (V$_N$ $\cup$ V$_T$)*, A $\in$ V$_N$ oraz P $\neq$ $\varepsilon$. Dopuszczamy także (nie podpadająca pod powyższy schemat) regułę S $\to$ $\varepsilon$. ale wówczas S nie może pojawiaćsię po prawej stronie pozostałych reguł.
3. i = 2: każda reguła ma postać A $\to$ P, gdzie A $\in$ V$_N$ i P $\in$ (V$_N$ $\cup$ V$_T$)*.
4. i = 3: każda reugła ma postać albo A $\to$ PB, albo A $\to$ P, gdzie A, B $\in$ V$_N$ i P $\in$ V$_T$*

# Wykład 11 - 03.01

Definicja
Mówimy że gramatyka G typu 3 jest w **postawci normalnej** jesli wszystkie jej reguły przepisywania mają jedną z następujących postaci:
(i) A $\to$ aB, lub
(ii) A $\to$ $\varepsilon$
gdzie A, B $\in$ V$_N$, a $\in$ V$_T$

Uwaga: Gramatyka w postaci normalej wiąże długość wyprowadzanego słowa z liczbą kroków jego derywacji.

#Twierdzenie
Każdy język typu 3 może być generowany przez pewną gramatykę w postaecji normalnej.

*przykład ze zdjęcia 15:46*

#Twierdzenie
Dla każdej gramatyki G typu 3 można skonstruować automat skończenie stanowy $\mathfrak{A}$ (niekoniecznie deterministyczny) taki, że L(G) = L($\mathfrak{A}$).

Dowód (konstrukcja)
Niech G = (V$_N$, V$_T$, S, F). Możemy założyć (poprz. tw.), że G jest w postaci normalnej, o regułach przepisywania postaci

 A $\to$ aB, A $\to$ $\varepsilon$, A,B $\in$ V$_N$, a $\in$ V$_T$

Automat $\mathfrak{A}$ = (K, T, $\delta$, q$_0$, H) konstruujemy w następujący sposób:
K = V$_N$, T = V$_T$, Q$_0$ = {S}, H = {A $\in$ K : A $\to$ $\varepsilon$ $\in$ F}
oraz
A $\to$ aB $\in$ F gdy B $\in$ $\delta$(A, a) (niederminizm!)


Algorytmy dla języków regularnych

Uwagi wstępne:
1. W świetle uzyskanych do tej pory wuników klasy językó generowanych (odp. akceptowanych, odp. oznaczanych) przez gramatyki typu 3 (odp. automaty skończenie stanowe, odp. wyrażenia regualnre) są identyczne.
2. Elementy tej (wspólnej dla nich klasy) będziemy nazywać po prostu



Problem decyzyjny
Problemem (decyzyjnym) nazywamy uporządkowaną parę ($\mathbb{I}$, $\mathbb{P}$), w której $\mathbb{I}$ jest niepustym zbiorem, zwanym zbiorem **instancji** problemu, $\mathbb{P}$ $\subset$ $\mathbb{I}$, a podzbiór $\mathbb{P}$ nazywamy zbiorem **instancji pozytywnych** problemu.

Rozstrzygalny problem decyzyjny
Problem decyzyjny ($\mathbb{I}$, $\mathbb{P}$), nazywamy **rozstrzygalnym** jeśli istnieje algorytm $\mathcal{A}$, który zatrzymuje się dla każdej instancji i $\in$ $\mathbb{I}$ ($\mathcal{A}$(i)$\downarrow$) oraz jeśli i $\in$ $\mathbb{P}$, to $\mathcal{A}$(i) = TAK, a gdy i $\in$ $\mathbb{I}$ $\setminus$ $\mathbb{P}$, to $\mathcal{A}$(i) = NIE.

$\downarrow$ - oznacza że algorytm się **zatzrymuje**

Niech $\mathbb{A}$ będzie zbiorem wszystkich automatów skończenie stanowych o ustalonym alfabecie wejścia T. Kładziemy $\mathbb{I}$ = $\mathbb{A}$ x T*. Zatem, każda instancja i $\in$ $\mathbb{I}$ ma postać ($)


# Wykład 12 - 10.01

Oznaczamy przez Li klasę języków generowanych przez gramatyki typu i. Bezpośrednio z definicji mamy inkluzję L$_3$ $\subseteq$ L$_2$ $\subseteq$ L$_0$ oraz L$_1$ $\subseteq$ L$_0$. Brakuje natychmiastowej inkluzji L$_2$ $\subseteq$ L$_0$ (warunek na regułę S $\to$ $\varepsilon$), ale można ją udowodnić. Dodatkowo można udowodnić (częściowo to zrobimy), **że wszystkie inkluzje są właściwe**. Uzyskany ciąg inklizji L$_3$ /$\subseteq$ L$_2$ /$\subseteq$ L$_1$ /$\subseteq$ L$_0$ nazywamy **hierarchią Chomsky'ego języków**.

Wnioski:
1. Każdy język regularny (typu 3) jest językiem bezkontekstowym (wystarczy popatrzeć na prawe strony reguł...)
2. **Nie każdy** język bezkontekstowy jest regularny (kanoniczny)


Podaj reguły przepisywania gramatyki bezkontekstowej generującej język
L$_1$ = {a$^n$b$^n$ : n $\geq$ 0} $\bigcup$ {b$^n$a$^n$ : n $\geq$ 0} 
`Jak mamy sumę to robimy separację na dwa osobne przypadki`

S $\to$ aSb
S $\to$ $\varepsilon$

S $\to$ bTa
T $\to$ bTa
T $\to$ $\varepsilon$ 
źle bo S $\Rightarrow$ aSb $\Rightarrow$ abTab $\Rightarrow$ ab$^n$a$^n$ b

Rozdzielamy S na A i B żeby uzyskać dwa przypadki:
Rozdzielamy
	S $\to$ A
	S $\to$ B
A generuje a$^n$b$^n$
	A $\to$ aAb
	A $\to$ $\varepsilon$
B generuje b$^n$a$^n$ 
	B $\to$ bBa
	B $\to$ $\varepsilon$
teraz jest prawidłowo

2. 
L$_2$ = {a$^n$b$^n$ : n $\gt$ 0} $\bigcup$ {b$^n$a$^n$ : n $\gt$ 0}

3. 
L$_3$ = {PP$^{-1}$ : P $\in$ {a, b, c}* }

S $\to$ aSa
S $\to$ bSb
S $\to$ cSc
S $\to$ $\varepsilon$

L$_4$ = {a$^n$b$^m$ : n $\gt$ m $\gt$ 0}

S $\to$ aAb
A $\to$ aAb
A $\to$ aB
B $\to$ aB
B $\to$ $\varepsilon$

L$_5$ = {a$^n$b$^m$ : 0 $\leq$ n $\leq$ m}

S $\to$ $\varepsilon$
S $\to$ aSb
S $\to$ Sb

L$_5$ = {a$^n$b$^m$ : n $\neq$ m}

S $\to$ aA
S $\to$ Bb
A $\to$ aSb
A $\to$ aS
B $\to$ aSb

L$_6$ = {a$^{n+m}$c$^2$b$^n$c$^m$ : n, m $\geq$ 0}

S $\to$ aSb
S $\to$ A
A $\to$ aAb
A $\to$ c$^2$

L$_7$ = {a$^n$b$^n$ : n $\geq$ 0} $\bigcup$ {a$^n$ : n $\geq$ 0}

S $\to$ A
A $\to$ aAb
A $\to$ $\varepsilon$
S $\to$ B
B $\to$ aB
B $\to$ $\varepsilon$

L$_8$ = {a$^n$b$^m$ : n = 2m} gdzie n, m $\gt$ 0

S $\to$ a$^2$Sb
S $\to$ a$^2$b

L$_9$ = {a$^n$b$^m$ : n $\neq$ 2m} gdzie n, m $\gt$ 0

^^^ do domu ^^^

L$_{10}$ = {a$^{2n-1}$b$^{3n+1}$ : n $\gt$ 0}

S $\to$ aAb$^4$
A $\to$ a$^2$Ab$^3$
a $\to$ $\varepsilon$

L$_{11}$ = {P $\in$ {a, b}* : #$_a$P $\geq$ 3}

^^^ do domu ^^^

a teraz w drugą stronę: jakie języki generuą gramatyki G$_1$, G$_2$ i G$_3$ o następujących zbiorach reguł przepisywania:

F$_1$ = {S$\to$ aaSA, S $\to$ $\varepsilon$, A $\to$ bA, A $\to$ b}

(a$^2$)$^n$SA$^n$ $\to$ {a$^{2n}$b$^m$ : }

F$_2$ = {S$\to$ aSbb, S $\to$ A, A $\to$ ca, A $\to$ c}

F$_3$ = {S$\to$ abScd, S $\to$ A, A $\to$ dcAba, A $\to$ $\varepsilon$}



Mielismy już wprowadzenie pojęcia automatów równoważnych (akceptują te same języki).

Równoważność gramatyk
Mówimy że gramatyka G$_1$ jest **równoważna** gramatyce G$_2$ wtedy i tylko wtedy, gdy
L(G$_1$) = L(G$_2$)

Bez dowodu przyjmujemy następujące twierdzenie

#Twierdzenie 
Dla każdej CF-gramatyki G, można **efektywnie skonstruować** równoważną jej CF-gramatykę G' taką, że prawe strony wszystkich reguł przepisywania G' są rózne od $\varepsilon$,  za wyjątkiem gdy $\varepsilon$ $\in$ L(G), ale wówczas:
(i) jedyną regułą z $\varepsilon$ po prawej stronie w F' jest S' $\to$ $\varepsilon$, oraz
(ii) S' nie pojawia się po prawej stronie pozostałych reguł przepisywania w F'.

# Wykład 13 - 17.01

Typy gramatyk
Gramatyka generatywna G = (V$_N$, V$_T$, S, F) jest nazywana gramatyką **typu i** jeśli F spełnia następujące warunki:
i = 1: każda reguła ma postać Q$_1$AQ$_2$ => Q$_1$PQ$_2$ i P $\in$ (V$_N$ $\cup$ V$_T$)*, A $\in$ V$_N$


Wniosek
Dla każdej CF-gramatyki G (tj. gramatyki typu 2) można **efektywnie skonstruować** równoważnąjej gramatykę G' spełniającą warunnki CS-gramatyk (kontekstowych, typu 1)

Wniosek
l1 c L2 (ale o inkluzjji /C nie możemy jeszcze powiedzieć)

Wniosek A
Problem należenia słowa pustego $\varepsilon$ do CF-języka jest rozstrzygalny

Algorytm (instancje problemu to CF-gramatyki...)
1. Przekształcić instancję (CF-gramatykę) G do równoważnej CF-gramatyki G' zgodnie z powyższym twierdzeniem
2. Sprawdzić, czy do (skończonego!) zbioru regu przepisywania F' należy reguła S' $\to$ $\varepsilon$

Definicja
Gramatykę G nazywamy $\varepsilon$-wolną jeśli $\varepsilon$ nie stoi po prawej stronie żadnej jej reguły przepisywania.

Wniosek B
Dla każdej CF-gramatyki G można skonstruować $\varepsilon$-wolną CF_gramatykę G' taką, że L(G') = L(G) \ {$\varepsilon$}
Algorytm: Przekształcić G na G' j.w. i usunąć S' $\to$ $\varepsilon$

Definicja (postać normalna Chomsky'ego)
CF-gramatyką G jest w **postacji normalnej Chomsky'ego**, jeśli każda z jej reguł przepisywania ma jedną z następujących postaci:
(i) A $\to$ a, gdzie A $\in$ V$_N$ oraz a $\in$ V$_T$ lub
(ii) A $\to$ BC, gdzie A, B, C $\in$ V$_N$

#Twierdzenie o postaci normalnej Chomsky'ego
Dla każdej $\varepsilon$-wolnej (!) CF-gramatyki G = (V$_N$, V$_T$, S, F) możemy skonstruować równoważną CF-gramatykę G' = (V$_N$'', V$_T$, S, F') w postaci normalnej Chomsky'ego.

Dowód (szkic kroków konstrukcji)
Krok 1: Pozbywamy się terminałów **z reguł** innych niż te o kształcie A $\to$ a (koszt - dodanie nowych nieterminałów do V$_N$, usunięcie niektórych i dodanie nowych reguł do F).
Przykład: Reguła A $\to$ abXc, **dodajemy** nieterminały X$_a$, X$_b$, X$_c$, regułę **usuwamy**, a w jej miejsce **dodajemy** reguły:
A $\to$ X$_a$X$_b$XX$_c$, X$_a$ $\to$ a, X$_b$ $\to$ b, X$_c$ $\to$ c

Efekt: mamy tylko reg. kszt. A $\to$ Y$_1$Y$_2$...Y$_n$, n $\geq$ 1.

Krok 2: Pozbywamy się reguł A $\to$ Y$_1$Y$_2$...Y$_n$, n $\geq$ 3 i n = 1.
Przypadek

# Wykład 14 - 24.01

Automat ze stosem (PDA, AZS) - model "politechniczny"

- **Taśma wejściowa** - po wykonaniu odczytu przez głowicę i zmianie stanu może się przesunąć w lewo (równoważnie - głowica pzresuwa się w prawo) **lub** może pozostać nieruchoma (przypomnijmy automat skończenie stanowy z $\varepsilon$-przejściami)
- **Stos** - po wykonaniu sczytania symbolu na wierzchu stosu symbol jest niszczony, a głowica stosowa nadpisuje go **ciągiem** symboli stosowych. W ten sposób, jeśli nadpisywanym ciągiem jest ciąg pusty, to wysokość stosu ulega obniżeniu o jeden symbol
- PDA z definicji będzie **niedeterministyczny**

Automatem ze stosem nazywamy uporządkowaną siódemkę
$\mathfrak{A}$ = (Z, K, T, $\delta$, z$_0$ q$_0$, H) w której:
1. Z $\neq$ $\emptyset$ jest skończonym **alfabetem stosu**
2. T $\neq$ $\emptyset$ jest skończonym **alfabetem wejścia**
3. K $\neq$ $\emptyset$ jest skończonym **zbiorem stanów**
4. z$_0$ $\in$ Z jest symbolem **początkowym** (dnem) stosu
5. H $\subset$ K jest zbiorem stanów **akceptujących**
6. q$_0$ $\in$ K jest stanem **początkowym**
7. $\delta$: Z x K x (T $\cup$ {$\varepsilon$}) $\to$$ P(Z* x K) jest (niedetrministyczną) funkcją przejścia automatu $\mathfrak{A}$.

#Definicja
Definicja konfiguracji automatu ze stosem

**Konfiguracją** (opisem chwilowym) automatu ze stosem $\mathfrak{A}$ = (Z, K, T, $\delta$, z$_0$ q$_0$, H) nazywamy słowo postaci WqP $\in$ Z*KT* takie, że W $\in$ Z* i głowica ogląda **ostatni po prawej** symbol słowa W (wierzch stosu), q $\in$ K, natomiast P $\in$ T* jest słowem na taśmie wejściowej począwszy od symbolu czytanego przez głowicę włącznie do końca słowa wejściowego w prawo.

Popatrzmy na funkcję przejścia AZS:
	$\delta$: Z x K x (T $\cup$ {$\varepsilon$}) $\to$ P(Z* x K)

Mamy trzy sposoby **wykonywania** ruchu przez taki automat:
1. 
   - na stosie czytany jest symbol z $\in$ Z
   - na taśmie wejściowej czytany jest symbol a $\in$ T
   - urządzenie sterujące jest w stanie q
   - (W, p) $\in$ $\delta$(z, q, a) oraz W $\neq$ $\varepsilon$
	Wówczas:
   - symbol z na stosie **nadpisywany** jest ciągiem W a głowica obserwuje ostatni symbol słowa W (wierzch stosu)
   - głowica an taśmie wejściowej przesuwa się **o 1 symbol w prawo**
   - stan wewnętrzny automatu zmienia się z q na p
Pamiętajmy, że automat jest niedeterministyczny, więc takie działanie może być wykonane dla **każdego** (W, p) $\in$ $\delta$(z, q, a). Nadto, gdy W = z to na stosie nie nastuępuje żadna zmiana.

zdj
zdj

zdj 


# Wykład 15 - 31.01

