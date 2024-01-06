Git to VCS (Version Control System) czyli system służący do kontrolowania i zarządzania zmianami w kodzie/plikach.

Git posiada wiele składowych elementów:
- Commit - jest to stan/snapshot zmian wprowadzonych oraz zapisanych (lokalnie lub zdalnie). Każdy commit posiada swoje ID, zawartość oraz commita nadrzędnego (parent)
- Branch - jest to gałąź składająca się z commitów oraz zmian które aktualnie posiada. Dwa branche moga mieć te same zmiany ale też mogą rozwijać różne funkcjonalności

Git - komendy:
- git commit - commitowanie zmian do gita. Można użyć flagi -m w celu dodania wiadomości do commita
- git checkout - ustawienie głowy (HEAD) na dany commit/branch. Użycie flagi -b tworzy brancha o danej nazwie.
- git merge - 