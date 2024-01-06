# Wyk 1 09.10.2023

## Warunki zaliczenia egzaminu:
W celu zdania egzaminu z wykładu należy zdobyć 3/2n (każdy egzamin po n punktów) punktów z trzech miniegzaminów w następujących terminach:
1. 20/11/2023
2. 11/12/2023
3. luty 2024

*Uwagi*
- Miniegzaminy 1 i 2 odbywają się podczas wykładu
- Miniegzamin 3 odbędzie się podczas sesji egzaminacyjnej
- Jeśli student zobędzie mniej niż 3/2n punktów to może przystąpić do egzaminu poprawkowego
- Wartość n zostanie podana w dniu pierwszego egzaminu
- Student nie ma możliwości pisania miniegzaminu w innych terminach niż podanych powyżej
- Studen nie ma możliwosci poprawy egzaminu poprawkowego

# Materiały

A = {a, b, c} - jakiś zbiór elementów
będziemy na nim wprowadzać działania (opisane za pomocą gwiazdki * )

#Definicja
Działanie wewnętrzne w zbiorze A - nazywamy dowolne odwzorowanie 
``` * A x A -> A ``` 
``` * (a, b) = a * b ```
Zn - wszystkie liczby naturalne {0, 1, ... n-1}
(Zn, +n)
$\phi$(n) - {a $\in$ Zn : NWD(a, n) = 1}

### Własności działań
Zakładamy że * jest wewnętrzne w A
#Definicja 
Działanie jest łączne jeśli dla każdego elementu a,b,c $\in$ A:
``` a * ( b * c ) = ( a * b ) * c ```

#Definicja 
Zakładamy że * jest przemienne w A
jeśli istnieją takie a,b $\in$ A takie że a * b = b * a

#Definicja 
Kiedy działanie ma element neutralny
Mówimy że e jest elementem neturalnym działania * w zbiorze A, jeśli:
a * e = e * a = a

#Definicja 
Niech działanie * ma element neutralny
Mówimy że b $\in$ A jest elementem przeciwnym do a $\in$ A jeśli:
a * b = b * a = e

Element przeciwny do a oznaczamy -a ( dla działania (A, +))

#Stwierdzenie
Element neutralny, o ile isntieje, jest wyrażony jednoznacznie
#Dowód
Niech e i e' będą elementami neturalnymi działania *
e' = e * e'
e = e * e'
=> e = e'

#Stwierdzenie 
Jeżeli działanie jest łączne, to każdy element posiada co najwyżej jeden element przeciwny
#Dowód 
Niech b i c będą elementami przeciwnymi do a
b = b * e = b * ( a * c ) = ( b * a ) * c = e * c = c
oznacza to że b = c
#Definicja 
(G, * ) - niepusty zbiór, działanie wewnętzne
Grupa:
1. Łączność
2. Istnieje element neutralny
3. Istnieje element przeciwny
Jeśli ktoś doda warunek że ma element przemienny to powstaje grupa przemienna

sama łączność - półgrupa

#Definicja 
Niepusty podzbiór H grupy G nazywamy podgrupą, gdy dla dowonych a,b $\in$ H element ab$^{-1}$ $\in$ H Piszemy wtedy H < G.

#Stwierdzenie 
Niech G będzie grupą, H C G niepustym podzbiorem G wtedy występuje równość:
1. H jest podgrupą
2. e $\in$ H, istnieje takie a,b takie że ab, b$^{-1}$ $\in$ H
3. H wraz z działaniem * w G jest grupą

# Wykład 2 - 16.10 2023

Koncepcja bezpieczeństwa

Kryptologia dzieli się na dwie części
Kryptografia - protokoły, kryptosystemy
Kryptoanaliza - łamanie protokołów i kryptosystemów

protokół symetryczny szyfrowania:
dlaczego symetryczny? posiada klucz który służy do szyfrowania i można go odszyfrować.
cel - pufne przekazywanie wiadomości (oznaczamy M - oznaczamy dowolny ciąg bitów)
algorytm szyfrowania (oznaczany E z ang. encrypt)
szyfrogram - (oznaczany literką C)
algorytm deszyfrowania - (odnaczany D z ang. decrypt)
klucz szyfrowania - oznaczany K

C = F$_K$(M)

#Przykład
Szyfrowanie:
K = 1100
M = 0101

operacja XOR na bitach
C = 1001

K = 1100
C = 1001
M = 0101

RC4 - algorytm szyfrujący, algorytm był nie znany

ALICE - jedna strona protokołu
BOB - druga strona protokołu
CELINE - trzecia opcjonalna strona, może być ich więcej

EVE - napastnik pasywny, może nasłuchiwać na informacje między protokołem
MALLET - adwersarz, napastnik aktywny, może zmieniać/modyfikować pakiety

#Definicja 
Algorytm działący na k bitach jest czasu wielomianowego (wykładniczego) jeśli liczba operacji elementarncuch na bitach potrzebnych do wykonania tego algorytmu jest rzędu O( K$^C$ ) (Oe$^{CK}$) itnieje takie C > 0.

S(a,b) = O(log b)

Asymetryczny algorytm szyfrowania (z kluczem publicznym)
z klucza publicznego nie jesteśmy w stanie w prosty sposób wyznaczyć klucza prywatnego

# Wykład 3

# Wykład 4

# Wykład 5 - Grupy ilorazowe

Motywacja matematyczna
G - grupa
H - podgrupa G

Pyt. przez jakie podgrupy można dzielić?
Odp. Podgrupy Normalne

Pyt. jakie podgrupy są jądrami homomorfizmu "cośtam"?
f: G1 -> G2, f(x o y) = f(x) o f(y)

Motwyacja Kryptografizczna
+, -, *, / - ciało R, Q

Ciała skończone

Ciała 4-elementowe

Niech H - podgrupa grupy G.
Def. Mówimy, że H jest dzielnikiem normalnym (podgrupą normalną), gdy dla każdego x należacego do G 
xHx$^{-1}$ = H

# Wykład 6

Za tydzień mini egzamin

zbiory o dwóch działaniach

zbiór ( K, +, * ) z dwoma działaniami, spełniającymi następujące warunki:
1. ( K, + ) jest grupą abelową
2. ( K \ { 0 }, * ) też jest grupą abelową
3. dla każdego a,b,c $\in$ K spełniają a(b+c) = ab + ac oraz (b+c)a = ba + ca

nazywamy ciałem

K = R, Q

Fp = { 0, 1, 2, 3, ... p-1}
( Fp, +, * ) tworzy ciało dla p będącego liczbą pierwszą
