# Cykl Życia Oprogramowania
Jest to wskazanie kolejnych faz życia oprogramowania, określnenie czynności wykonywanych w poszczególnych fazach oraz ustalenie kolejności ich realizacji.

Ma za zadanie opisać proces budowy, uruchamiania oraz utrzymywania aplikacji.

Modele opisujące cykl życia oprogramowania:
- Model kaskadowy
- Realizacja przyrostowa
- Model spiralny
- Prototypowanie
- "Metody lekkie"

W rozwoju oprogramowania bazującego na paradygmacie obiektowym duże znaczenie zyskał Unified Process oraz Rational Unified Process (RUP)

Model Kaskadowy (model wodospadu)
- Klasyczny model cyklu życia oprogramowania zaproponowany przez analogię do sposobu prowadzenia innych przedsięwzięć inżynieryjnych
- Liniowy proces w którym wyrużnia się 5 podstawowych kroków podczas tworzenia opdogramowania:
	1. Określenie wymagań - określenie celów oraz szczegółowych wymagań wobec tworzonego systemu
	2. Projketowanie - szczegółowy projekt systemu spełniającego wcześniej ustalonych wymagań
	3. Implementacja (kodowanie) - implementacja poszczególnych modułów systemu w konkretnym środowiksu
	4. Testowanie - 
	5. Konserwacja - 
Dodatkowe fazy modelu kaskadowego
- Faza strategiczna - podjęcie strategicznych decyzji dot dalszych etapów prac wykonywanych przed podjęciem formalnych decyzji o uruchomieniu danego projektu
- Faza analizy - budowanie logicznego modelu systemu
- Faza dokumentacji - wytwarzanie dokumentacji użytkownika
- Faza instalacji - przekazanie systemu użytkownikowi

Wady modelu kaskadowego:
- Narzucenie twórcom oprogramowania ścisłej kolejności wykonywania prac
- Wysoki koszt błędów popełnianych we wstępnych fazach tworzenia oprogramowania (błedy z fazy wymagań są wykrywane dopiero podczas testowania)
- Długa przerwa w kontaktach z klientem (ryzyko utraty zainteresowania klienta realizowanym projektem)

Zmodyfikowany model kaskadowy z iteracjami

Unified Process
- UP opracowany został przez twórców UMI i upowszechniony w 1999 roku
- UP opiera się na powszechnie akceptowanych praktykach, takich jak cykl iteracyjny oraz rozwój oprogramowania oparty na zarządzaniu zagrożeniami (risk-driven developement)
- Cykl iteracyjny polega na:
	- organizacji procesu w krótkie (np. 4 tygodniowe) mini-projekty nazywane iteracjami
	- każda z iteracji składa się z analizy wymagań, projektowania, implementacji i testowania
	- wynikiem każdej iteracji jest uruchamialny, ale nie kompletny system; oprogramowanie rozwijane jest poprzez sukcesywne wprowadzenie nowych funkcjonalności z gwarancją natychmiastowej oceny kierunku rozwoju aplikacji przez odbiorcę końcowego.

