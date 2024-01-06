Metoda Factory to wzorzec kreacyjny który zapewnia interfejs do tworzenia obiektów w superklasie, pozwalając podklasom do zmiany typu obiektu który zostanie stworzony.

## Problem
Wyobraź sobię że tworzysz aplikację do zarządzania logistyką. Pierwsza wersja aplikacji obsługuje tylko trasport lądowy za pomocą ciężarówek, przez co większość kodu żyje w klasie ```Truck```.

Po jakimś czasie, twoja aplikacja staje się popularna. Każdego dnia dostajesz tuziny żądań od firm zajmujących się transportem lądowym, żebyś zaimplementował do aplikacji także transport morski.

Świetne wieści, co nie? Ale co z kodem? Na ten moment, większość kodu jest sprzężona w klasie ```Truck```. Dodanie klasy ```Ships``` do aplikacji sprawi, że potrzebne będą zmiany w całym kodzie aplikacji. Co więcej, jeśli później zdecydujesz się na dodanie nowego środku transportu do aplikacji, będziesz musiał wprowadzać zmiany na nowo.
W rezultacie, skończysz z bardzo brzykim kodem, który będzie zawierał wiele warunków zmieniających zachowanie aplikacji w zależności od klasy obiektu transportacji.

## Rozwiązanie
Metoda Factory sugeruje żebyś zamienił bezpośrednie wywołania tworzenie obiektów (za pomocą operatora ```new```), na wywołania za pomocą specjalnej metody ```factory```. Bez obaw: obiekty będą dalej tworzone za pomocą operatora ```new```, ale będą wywoływane z metody ```factory```. Obiekty zwracane przez metodę ```factory``` są często określane jako **produkty**.

Na pierwszy rzut oka, ta zmiana może się wydawać bezsensowna: przenieśliśmy wywołanie konstruktowa z jednej części programu do innej. Jednakże, rozważ to: teraz możesz nadpisywać metodę ```factory``` w subklasie i zmienić klasę produktów tworzonych przez tą metodę.

Mamy jednak małą limitacje: podklasy mogą zwrócić różne typy produktó tylko wtedy, gdy produkty te mają wspólną klasę bazową lub interfejs. Dodatkowi, metoda `factory` w bazowej klasie powinna mieć swój typ zwracany zadeklarowany jako ten interfejs.

Na przykład, obydwie klasy `Truck` i `Ships` powinny implementować interfejs `Transport`, który deklaruje metodę `deliver`. Każda klasa implementuje tą metodę w inny sposób: ciężarówki dostarczją towar lądem, a statki drogą morską. Metoda `factory` w klasie RoadLogistics zwraca obiekty ciężarówek, natomiast metoda fabryczna w klasie SeaLogistics zwraca statki.

Kod który korzysta z metody factory (często zwanym `client`) nie widzi różnicy między produkatmi zwracanymi przez różne subklasy. Klient traktuje wszystkie te produkty jako abstrakcyjny `Transport`.

Klient wie że wszystkie obiekty transportu powinny mieć mietodę deliver, ale jak dokładnie ona działa nie jest dla niego ważne.

## Struktura
![[Pasted image 20221123124728.png]]

1. **Produkt** deklaruje interfejs, który jest wspólny dla wszystkich obiektów które mogą zostac stworzone przez **kreatora** i jego podklasy
2. **Concrete Products** to różne implementacje interfejsu **produktu**
3. Klasa **Kreator** deklaruje metodę factory która zwraca nowe obiekty produktów. Ważne jest to aby typ zwracany przez tą metodę pasował do interfejsu produktu. Możesz zadeklarować metodę factory jako abstrakcyjną aby zmusić wszystkie podklasy do implementacji ich własnych wersji metod. Jako alternatywa, podstawowa wersja metody factory poże zwrócić jakiś defaultowy typ produktu. 