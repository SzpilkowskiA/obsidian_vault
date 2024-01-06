Jenkins jest jednym z najpopularniejszych narzędzi CI/CD, a jego popularność wynika z wielu zalet w porównaniu do innych narzędzi. Oto kilka głównych zalet korzystania z Jenkinsa:

1. **Długa Historia i Stabilność:**
    
    - Jenkins ma długą historię i silne wsparcie społeczności. To narzędzie jest rozwijane od wielu lat, co przekłada się na stabilność i dojrzałość.
2. **Wsparcie dla Wielu Technologii:**
    
    - Jenkins oferuje szerokie spektrum wtyczek, co umożliwia integrację z różnymi technologiami i narzędziami. Można dostosować Jenkinsa do konkretnych potrzeb projektu.
3. **Otwarty Kod:**
    
    - Jenkins jest projektem open source, co oznacza, że jest dostępny bezpłatnie i może być dostosowany do indywidualnych potrzeb. Ponadto, otwarty kod zachęca do współpracy i rozwijania funkcji przez społeczność.
4. **Łatwość Użycia:**
    
    - Jenkins zapewnia intuicyjny interfejs użytkownika, który ułatwia konfigurację i zarządzanie procesami CI/CD. Nawigacja po panelu kontrolnym Jenkinsa jest stosunkowo prosta, co pomaga w szybkim dostosowywaniu i korzystaniu z narzędzia.
5. **Wieloplatformowość:**
    
    - Jenkins działa na wielu platformach, co pozwala na elastyczne wdrożenie na różnych systemach operacyjnych. Jest kompatybilny z systemami Unix, Linux, Windows, i można go uruchomić w kontenerach Docker.
6. **Ciągłe Wspieranie i Aktualizacje:**
    
    - Społeczność Jenkinsa aktywnie wspiera narzędzie, dostarczając regularne aktualizacje, łatki bezpieczeństwa i nowe funkcje. To zapewnia, że Jenkins jest zawsze gotowy do obsługi najnowszych technologii i wymagań branżowych.
7. **Rozbudowane Funkcje i Rozszerzenia:**
    
    - Jenkins oferuje szeroką gamę funkcji, takich jak budowanie, testowanie, wdrażanie, raportowanie i integrację z systemami kontroli wersji. Wielość dostępnych rozszerzeń pozwala dostosować Jenkinsa do skomplikowanych scenariuszy wytwarzania oprogramowania.
8. **Skalowalność:**
    
    - Jenkins jest elastyczny i skalowalny, co oznacza, że może obsługiwać zarówno niewielkie projekty, jak i duże przedsięwzięcia. Możliwość konfiguracji klastrów Jenkinsa pozwala na dostosowanie do rosnących potrzeb projektu.
9. **Integracja z Chmurą:**
    
    - Jenkins oferuje integrację z różnymi usługami chmurowymi, co ułatwia przenoszenie procesów CI/CD do chmury obliczeniowej.
10. **Wsparcie Społecznościowe:**
    
    - Dostępność szerokiej społeczności Jenkinsa oznacza, że można znaleźć wiele przykładów, porad i rozwiązań problemów online, co ułatwia korzystanie z narzędzia.

Należy jednak pamiętać, że wybór narzędzi zależy od specyfiki projektu i wymagań. Choć Jenkins posiada wiele zalet, inne narzędzia CI/CD mogą być bardziej odpowiednie dla konkretnych kontekstów.

Alternatywy dla Jenkinsa istnieją, i każde narzędzie ma swoje zalety i wady. Oto kilka popularnych alternatyw oraz potencjalne ograniczenia, które mogą wpływać na wybór jednego narzędzia nad drugim:

1. **Travis CI:**
    
    - **Zalety:** Łatwa konfiguracja, szybkie uruchamianie, wsparcie dla wielu języków programowania.
    - **Ograniczenia:** Bezpłatna wersja może być ograniczona czasowo, a zaawansowane funkcje mogą być dostępne jedynie w płatnych planach.
2. **GitLab CI/CD:**
    
    - **Zalety:** Zintegrowane z platformą GitLab, łatwa konfiguracja, zarządzanie kodem, wbudowane repozytoria.
    - **Ograniczenia:** Związane z zależnością od ekosystemu GitLab, co może być niewygodne dla zespołów korzystających z innych systemów kontroli wersji.
3. **CircleCI:**
    
    - **Zalety:** Łatwa konfiguracja, elastyczność, skalowalność, wsparcie dla kontenerów.
    - **Ograniczenia:** Płatna usługa, a ograniczenia w darmowej wersji mogą sprawić, że niektóre funkcje są dostępne jedynie na płatnych planach.
4. **TeamCity:**
    
    - **Zalety:** Bogate funkcje, łatwa integracja z narzędziami JetBrains, wygodne interfejsy użytkownika.
    - **Ograniczenia:** Płatna usługa, a jej zasoby mogą być uważane za bardziej wymagające niż niektóre darmowe narzędzia.
5. **Bamboo:**
    
    - **Zalety:** Integracja z narzędziami Atlassian, prosta konfiguracja dla projektów korzystających z tego samego ekosystemu.
    - **Ograniczenia:** Płatna usługa, może być mniej elastyczna w przypadku projektów spoza ekosystemu Atlassian.
6. **GoCD:**
    
    - **Zalety:** Elastyczność w definiowaniu procesów CI/CD, wsparcie dla zaawansowanych scenariuszy.
    - **Ograniczenia:** Może wymagać więcej pracy w konfiguracji niż niektóre bardziej intuicyjne narzędzia.
7. **Azure DevOps:**
    
    - **Zalety:** Integracja z innymi narzędziami Microsoft, usługi chmurowe, środowisko deweloperskie DevOps.
    - **Ograniczenia:** Integracja może być mniej wygodna dla projektów spoza ekosystemu Microsoft, a niektóre funkcje mogą być bardziej zorientowane na specyficzne technologie.

Warto zauważyć, że to, co może być uznawane za ograniczenia, zależy od indywidualnych potrzeb projektu i preferencji zespołu. Każde narzędzie ma swoje miejsce i może być odpowiednie w różnych kontekstach wytwarzania oprogramowania. Ostateczny wybór zależy od konkretnych wymagań projektu, preferencji zespołu oraz dostępnych zasobów.

1. **Izolacja Środowiskowa:**
    
    - **Zaleta:** Docker umożliwia pakowanie aplikacji i jej zależności w kontenery, co eliminuje problemy związane z różnicami w środowiskach systemowych. Każdy kontener działa w izolowanym środowisku, co zapewnia jednolitą i powtarzalną pracę na różnych etapach procesu CI/CD.
2. **Reprodukowalność Środowiska:**
    
    - **Zaleta:** Dzięki obrazom Dockerowym, można precyzyjnie zdefiniować i replikować środowisko, w którym aplikacja jest testowana i wdrażana. To ułatwia uniknięcie problemów związanych z różnicami między środowiskiem deweloperskim a produkcyjnym.
3. **Szybkie Wdrażanie:**
    
    - **Zaleta:** Kontenery Dockerowe są lekkie i uruchamiają się bardzo szybko. To przyspiesza procesy budowania, testowania i wdrażania, co skraca czas cyklu dostarczania oprogramowania.
4. **Skalowalność:**
    
    - **Zaleta:** Docker umożliwia łatwe skalowanie aplikacji, zarówno poziomo (dodawanie instancji kontenerów) jak i pionowo (zwiększanie zasobów kontenera). To pozwala na dostosowywanie infrastruktury do dynamicznie zmieniających się potrzeb projektu.
5. **Łatwość Zarządzania Zależnościami:**
    
    - **Zaleta:** Docker pozwala na zdefiniowanie wszystkich zależności aplikacji w pliku Dockerfile. To ułatwia zarządzanie wersjami, aktualizacjami i konfiguracją, co eliminuje problemy związane z różnicami w środowiskach.
6. **Jednolity Proces Budowania:**
    
    - **Zaleta:** Proces budowania aplikacji w kontenerze Dockerowym jest jednolity i niezależny od lokalnego środowiska deweloperskiego. To przekłada się na spójność między etapami cyklu dostarczania.
7. **Wsparcie dla Mikrousług:**
    
    - **Zaleta:** Docker doskonale współpracuje z architekturą opartą na mikrousługach. Każda usługa może być opakowana w osobny kontener, co ułatwia zarządzanie i skalowanie poszczególnych części systemu.
8. **Łatwość Przenoszenia między Środowiskami:**
    
    - **Zaleta:** Kontenery Dockerowe są przenośne, co oznacza, że aplikacja opakowana w kontener może działać w dowolnym środowisku obsługującym Docker. To ułatwia przenoszenie aplikacji między różnymi etapami cyklu życia oraz pomiędzy różnymi środowiskami (lokalne, testowe, produkcyjne).
9. **Łatwość Integracji z Narzędziami CI/CD:**
    
    - **Zaleta:** Docker integruje się z wieloma narzędziami CI/CD, co ułatwia automatyzację procesów wytwarzania oprogramowania i dostarczania.

Kombinacja tych zalet sprawia, że Docker jest popularnym wyborem w środowiskach CI/CD, pozwalając na bardziej efektywne, spójne i elastyczne zarządzanie procesami wytwarzania oprogramowania.

Tworzenie środowiska - główne zamysły z naszego projektu
1. Wstęp
	1. Wprowadzenie o tematyki rozdziału pracy
2. Opisz przebiegu tworzenia środowiska z podzialem na poszczególne fazy
	1. Przygotowanie środowiska Jenkins do wdrożenia
		1. Problemy wdrożenia środowiska CI/CD
		   - Niestandardowe dostarczenie instalki do aplikacji - zamiast wstawić na google play, klient chce aby instalka znajdowała się na sharepoincie klienta, zostanie do tego wykorzystany plugin o365 który umożliwia przesyłanie plików do odpowiedniego miejsca na sharepoincie.
		   - Serwer jest utrzymywany przez zewnętrzną firmę więc wstępnie czas konfiguracji serwera wynosił miesiąc a poza tym zmiany są wprowadzanie nie bezpośrednio, tylko poprzez tickety do firmy zewnęrznej co wydłuża czas wdrożenia
		1. Wybór wykorzystanych narzędzi
		   - Dlaczego jenkins - jest open source, jest znanym i lubianym.
		2. Opis architektury Master-Slave w Jenkinsie
		3. Przedstawienie procesu konteneryzacji serwera Jenkins
		   - Wykorzystany oficjalny obraz Jenkinsa z repozytorium Docker Hub.
		   - Do wolumenu zostają przegrane pliki konfiguracyjne
		   - Ustawiane są odpowiednie zmienne środowiskowe które przechowują dane konfiguracyjne takie jak: adres hosta docker który umożliwia Jenkinsowi uruchamianie agentów albo wyłączenie wstępnej ręcznej konfiguracji za każdym razem gdy uruchamia się kontener Jenkinsa.
		   - lista wtyczek jest zapisana w pliku tekstowym w formacie nazwa wtyczki oraz jej wersja. Następnie za pomocą narzędzia jenkins-plugin-cli, wtyczki te są instalowane automatycznie. Dzięki temu nie trzeba ręcznie wchodzić w menadżera wtyczek za każdym uruchomieniem kontrollera
		   - Wykorzystany została także biblioteka docker compose, która umożliwia przechowywanie parametrów wymaganych do uruchomienia kontenera w jednym pliku. Takimi parametrami są na przykład porty sieciowe które mają zostać udostepnione, wolumeny które mają zostać przypisane, plik ze zmiennymi środowiskowymi itd.
		1. Przedstawienie procesu konteneryzacji agentów Jenkins
		   - są dwa agenty, jeden do aplikacji mobilnej, drugi do aplikacji która komunikuje się z bazą danych w celu obsługi zapytań z aplikacji.
		   - obydwa agenty zawierają zbliżone pliki dockerfile, które różnią się zainstalowanymi narzędziami umożliwiającymi budowanie obydwu aplikacji.
		   - do mobilki flutter i android sdk
		   - do API java i maven
		   - obydwa agenty bazują na obrazie inbout agent.
	1. Planowanie, implementacja oraz wdrażanie pipelinów
		1. Planowanie infrastruktury pipelineów
		2. Proces tworzenia pipelineów
			1. Wykorzystanie pluginu JobDSL
			2. Integracja Kluczy SSH
		3. Wdrożenie oraz zarządzanie pipelinami
	2. Funkcjonalności ułatwiające zarządzanie środowiskiem CI/CD
		1. Gitea WebHooks
		2. Automatyczne powiadamianie o nieudanych buildach
3. Zakończenie
	1. Refleksja nad rozwiązaniami oraz możliwe ulepszenia
	2. Podsumowanie