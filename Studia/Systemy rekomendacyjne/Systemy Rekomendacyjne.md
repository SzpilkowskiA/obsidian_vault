Rekomender - system ten kalkuluje i zapewnia odpowiedni dobór treści dla użytkownika na bazie wiedzy na jego temat, kontentu jak i interakcji między nimi.

Cele
- Biznes - maksymalizacja sprzedaży/czasu oglądania
- Dopasowany wybór - zapewnianie jakościowych pozycji z miliona opcji
- Różnorodnośc - 
- Łut szczęścia, traf (Serendipity) - dopasowywanie produktów dla ludzi którzy mogą on nich nawet nie wiedzieć


Wyzwania:
- Wysoka trafność
- Skalowalność
- Szybkie aktualizowanie (np. po każdej interakcji użytkownika)
- Rzadkość (nawet 99.9 nienzanych interakcji)
- Problem zimnego startu (bez danych ciężko jest polecić cokolwiek)
- domniemany (implicit) feedback
- Long-tail problem - duża ilość mało popularnych rzeczy sprzedaje się w małych ilościach, a mało bardzo popularnych w dużych ilościach

Matematyczne wzory

interakcje między użytkownikiem a produktem możemy wyrazić za pomocą macieży
R $\in$ R$^{MxN}$:
![[Pasted image 20230404215437.png]]

gdzie r$_{u,i}$ oznacza interkację użytkownika u z produktem i
Tą interakcja może być:
- wartość bool oznaczająca czy użytkownik obejrzał produkt (np. film)
- liczba określająca ilość produktu zakupionego przez użytkownika
- liczba określająca ocenę produktu użytkownika

W terminologii matematycznej, rekomender musi przewidzieć wartość r*$_{u,i}$ - czyli wartość oczekiwaną r$_{u,i}$ na bazie poprzednich interakcji, charakterystyk użytkownika itp.

Niepresonalizowane rekomendery:
- Most popular - wybierz produkt który sprzedał się najwięcej razy i zarekomenduj go użytkownikowi
- Highest rated - wybierz produkt który jest najlepiej oceniany i zarekomenduj go użytkownikowi
- Random - wybierz produkt losowo
- Context-aware most popular - stwórz model który przewidzi najbardziej popularny produkt na bazie danych kontekstowych (np. black friday, święta itd.)


Personalizowane:
- Repeat - poleć produkt który użytkownik kupuje najczęściej
- Most popular in clusters - klastry użytkowników na bazie ich preferencji, dla każdego klastra znajdź najpopularniejszy produkt i zarekomenduj go każdemu użytkownikowi z klastra.
- Nearest neighbours - Dla każdego użytkownika przygotuj wektor interakcji p$_u$, znajdź najbliższych sąsiadów danego użytkownika, wylicz średnie oceny produktów i na ich bazie poleć użytkownikowi najpopularniejsze produkty.



Środki oceniające - evaluation measures

Regresja:
- MSE
- RMSE
- MAE
- MAPE (MRE)
- TRE
Klasyfikacja:
- Sensitivity/Recall/True Positive Rate
- Precyzja
- Dokładność
- wynik F1
Ranking:
- HR@n
- NDCG@n
- MAP@n


Regresja

MAE - Mean Absolute Error - Średni Błąd Bezwzględny
![[Pasted image 20230404220735.png]]

MSE – Mean Squared Error - Średni Błąd Kwadratowy
![[Pasted image 20230404220743.png]]

RMSE – Root Mean Squared Error - Spierwiastkowany Średni Błąd Kwadratowy
![[Pasted image 20230404220751.png]]

MAPE (MRE) – Mean Absolute Percentage Error (Mean Relative Error)  - Średni Bezwględny Błąd Procentowy (Śreni Błąd Względny)
![[Pasted image 20230404220757.png]]

TRE – Total Relative Error - Całkowity Błąd Względny
![[Pasted image 20230404220802.png]]


