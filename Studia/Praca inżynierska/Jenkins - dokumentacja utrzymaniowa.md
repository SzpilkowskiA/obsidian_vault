## Logowanie się

**Uwaga:** Żeby mieć dostęp do Jenkinsa, trzeba być podłączonym przez VPN.

W celu zalogowania się wejdź na adres:
http://api.promostal.tech:8081/
A następnie zaloguj się za pomocą loginu i hasła administratora

Po zalogowaniu zostaniesz przekierowany na ekran główny Jenkinsa
##  Zmiana ustawień

W celu zmiany ustawień wybierz opcję "Manage Jenkins" z lewego paska bocznego znajdującego się na ekranie głównym Jenkinsa.
![[Pasted image 20231215095722.png]]
Po przejściu na ekran otrzymasz wiele możliwych elementów do konfiguracji takich jak konfiguracja systemu, pluginów czy narzędzi

**Uwaga** Zapisanie ustawień nie jest trwałe w przypadku całego środowiska, ponieważ konfiguracja całego systemu jest przechowywana w postaci kodu znajdującym się w katalogu sklonowanego repozytorium zawierającego Jenkinsa. Jeśli chcesz aby zmiany były zapisane oraz wykorzystane po ponownym uruchomieniu kontenera Jenkins, muszą one zostać przekonwertowane jako kod. Jak to zrobić możesz dowiedzieć się w sekcji **Kopiowanie wygenerowanej konfiguracji z poziomu Jenkinsa**.

### JCasC - Jenkins Configuration as a Code

Konfiguracja Jenkinsa jest przechowywana w postaci kodu znajdującym się w głównym katalogu Jenkinsa, z którego Jenkins jest uruchamiany oraz budowany.

Konfiguracja może zostać napisana ręcznię, bądź zmodyfikowana z wygenerowanego kodu
#### Kopiowanie wygenerowanej konfiguracji z poziomu Jenkinsa

Plugin JCasC oferuje możliwość ustawienia konfiguracji Jenkinsa za pomocą graficznego interfesju użytkownika, a następnie podejrzenia bądź skopiowania kodu wygenerowanego przez plugin.
**Uwaga** Czasami wygenerowany kod nie działa poprawnie, więc nie można go przekleić w każdym przypadku bezpośrednio z wygenerowanego przykładu.

Aby pobrać wygenerowaną konfigurację należy:
1. Wejść w zarządzanie konfiguracją Jenkinsa
   ![[Pasted image 20231215095724.png]]
2. Wejść do ustawień pluginu JCasC:
   ![[Pasted image 20231215095828.png]]
3. Wybrać opcję pobrania dokumentacji (Download Configuration) lub podejrzenia konfiguracji (View Configuration)
   ![[Pasted image 20231215095928.png]]
   Sam Jenkins podpowiada nam że wygenerowany kod nie jest zamierzony do bezpośredniego użycia.

#### Aktualizacja/tworzenie konfiguracji w formie kodu

Aby stworzyć lub zaktualizować konfigurację można zrobić to na dwa spososby:
1. Skorzystać z dokumentacji pluginu JCasC ([link](https://plugins.jenkins.io/configuration-as-code/)) i napisać ją ręcznie
2. Skorzystać z generatora w instancji Jenkinsa oraz skopiowanie wygenerowanej konfiguracji (jak to zrobić sprawdź wyżej). Należy pamiętać że konfiguracja ta może nie działać poprawnie bez wprowadzenia zmian.
   
## Zarządzanie Pipelineami

Aby wejść w szczegóły danego pipeline'u należy kliknąć w jego nazwę na ekranie głównym
![[Pasted image 20231215102817.png]]

Zostaniemy przekierowani na ekran szczegółów wybranego przez nas pipeline'u

Zobaczymy na nim ostatnie uruchomienia oraz statusy poszczególnych etapów.

Po lewej stronie znajduje się menu boczne które zapewnia funkcje edycji oraz historię poszczególnych uruchomień.
Lista edycji zawiera poszczególne opcje:
- Status - strona główna danego pipeline'u która pokazuje uruchomienia
- Changes - zmiany w kodzie z danego repozytorium które jest wykorzystywane między poszczególnymi uruchomieniami
- Build Now - ręczne uruchomienie pipeline'u
- Configure - zmiana konfiguracji danego pipeline'u (**Uwaga** konfiguracja ta zostanie stracona jeśli nie zostanie zaktualizowana konfiguracja w postaci kodu znajdujący się w katalogu Jenkinsa na maszynie hosta)
- Delete Pipeliene - usunięcie pipeliene'u
- Full Stage View - podgląd samych uruchomień danego pipeline'u
- Favourite - dodanie pipeline'u do ulubionych
- Open Blue Ocean - przekierowanie do nowocześniejszego widoku pipeline'u
- Rename - zmiana nazwy pipeline'u
- Pipeline Syntax - przekierowanie do generatorów ułatwiających tworznienie skryptów wykonywanych przez pipeline