
# Protokoły

## TCP
Transmission Control Protocol, czyli protokół sterowania transmisją.
Połączeniowy, niezwodny, strumieniowy protokół komunikacyjny stosowany do przesyłania danych między procesami uruchomionymi na różnych maszynach.

Jest to protokół zorientowany połączeniowo, co oznacza że stawia większy nacisk na jakość połączenia. Dzięki temu zapewnione jest że przepływ danych będzie pełny i nic nie zostanie stracone, lecz jest przez to wolniejszy niż UDP

Protokół TCP musi posiadać gotową sesję połączenia w celu przesłania danych. Odbywa się to poprzez three-way handshake:
1. Wysłanie przez pierwszą maszynę wiadomości SYN aby rozpocząć synchronizację
2. Odesłanie przez drugą maszynę wiadomośći SYN ACK w celu potwierdzenia otrzymania wiadomości SYN
3. Odesłanie przez pierwszą maszynę otrzymania potwierdzenia za pomocą wiadomości ACK
## UDP
User Datagram Protocol, jest to protokół bezpołączeniowy, czyli taki który wysyła dane bez poprzednio ustalonego połączenia i śledzenia sesji. Nie ma też mechanizmów kontroli przepływu i retransmisji. Dzięki temu przesył danych jest szybszy w porównaniu do TCP, lecz kosztem możliwej utraty danych w procesie. 

# Różnice między TCP a UDP
| Factor | TCP | UDP |
| ---- | ---- | ---- |
| Rodzaj połączenia | Wymaga ustalenia sesji w celu wysłania danych | Nie wymaga sesji |
| Sekwencyjność danych | Pozwala na wysyłanie danych sekwencyjne (czyli w kolejności) | Nie pozwala na sekwenycjny przesył danych |
| Ponowne przesyłanie danych | Pozwala na ponowne przesłanie danych jeśli wystąpił błąd podczas przesyłu | Nie pozwala na ponowne przesłanie danych. Utracone dane są nieodzyskiwalne |
| Dostarczenie | Jest gwarantowane | Nie jest gwarantowane |
| Wykrywanie błędów | Dokładnie sprawdza czy wszystkie dane zostały przesłane w niezmienionym stanie | Minimalne sprawdzanie błędów |
| Nadawanie (Broadcasting) | Nie wspiera | Wspiera |
| Prędkość | Wolne, ale zapewnia pełny przesył danych | Szybkie, ale możliwa utrata danych |

TCP jest najlepsze do:
- Przesyłania maili lub wiadomości
- Przesyłania plików
- Przeglądania sieci
UDP jest najlepsze do:
- Livestreamów
- Gier online
- Czatów wideo

## IP


# Przestrzeń adresowa