# Grafika komputerowa w pigułce
- Obrazy generowane poprzez użycie komputerów
- W tym kursie skupimy się na renderowaniu 3D

scena 3D --renderowanie--> obraz 2D

Użycie:
- Filmy - efekty specjalne
- Gry komputerowe
- Symulacje
- Projekty w CAD i CAM 
- Architektura
- Wizualizacja danych
- Obrazowanie medyczne
- Aplikacje

Specyfikacje renderowania
- Podstawowymi specyfikacjami do renderowania są OpenGL i Direct3D

Czego się nauczymy
- Fundamentalną teorię grafiki komputerowej
- Potoku renderowania (Rendering Pipeline) - jak wygenerować obrazy 2D ze sceny 3D
- OpenGL
- Doświadczenie C++
- Fundamentalnych elementów GLSL, języka programowania wykonywanego na kartach graficznych

Zaliczenie:
- Testy wielokrotnego wyboru (50%) - plus maks. 1-2pkt za zadania na laboratoriach
- Projekty semestralne (50%) - 1/4 prezentacja badań + 3/4 projekt
- Więcej szczegółów na laboratoriach (np. daty)
- Informacje są dostępne na MS Teams i https://wp.faculty.wmi.amu.edu.pl/GRK.html

# Jak matematycznie wyrazić obiekty 3D
![[pngaaa.com-3563781.png]]
Układ współrzędnych 2D
![[1200px-Cartesian-coordinate-system.svg.png]]
Układ współrzędnych 3D


Przykład: Piramida
Oprócz wyznaczenia punktów, musimy je połączyć w celu otrzymania płaszczyzn a następnie obiektów 3D.
np. (0,1,0) (0,0,1) (1,0,0) lub (0, 1, 0) (1, 0, 0) ( 0, 0, -1)

Rozwiązanie: Nowa struktura danych
Bufor wierzchołkowy (ang. Vertex buffer) - przechowuje dane o wierzchołkach
{(0, 1, 0), (0, 0, 1), (1, 0, 0), (0, 0, -1)} 

przez co zamiast pisać współrzędne to wpisujemy index wierzchołka w buforze.

Trójkąty
współpłaszczyznowość

Przybliżenie kształtu za pomocą trójkątów

Świat poligonów (trójkątów)

Translacja wierzchołków
W grafice korzrystamy z 3 przekształceń:
1. Skalowanie - zastosowane na całym obiekcie, i na wierzchołki wrzucamy tą samą funkcję przekształcenia.
2. Rotacja (obrót) - obracanie wokół układu
3. Translacja - przemieszczanie wierzchołków

Transformacja
- f:X -> Y
- Te funkcje operują na wektorach.
- f:R3 -> R2  =>  f(x1, x2, x3) = (x1+2x2 | 3x3)

Skalowanie
f(x, y) = (x * Sx | y * Sy)

Translacja
f(x, y) = (x + Tx | y + Ty)

Rotacja
Polar Coordinates:
x = r * cos($\theta$)
y = r * cos($\theta$)

x' = r * cos($\theta$ * $\delta$) = r * cos() * cos() - r * sin() * sin()
y' = r * sin($\theta$ * $\delta$)

Rotacja wokół środka geometrycznego
- translacja do środka układów współrzędnych
- rotacja
- translacja do punktu startowego

Jak zastosować transformacje natychmiastowo:
Macierze transformacji - Asocjacyjne
- Niech x będzie wierzchołkiem
- Macierze transformacji A i B, C jest iloczynem A i B
- Wtedy A(Bx) = (AB)x = Cx
	- stosuje transformacje w pojedynczym mnożeniu macierzowo-wektorowym
- Jeśli mamy scenę złożoną z milionów 

Iloczyn macierzowo-wektorowy jako przekształcenie
