# Kolokwium — grupa B

**Czas: 45 min | maksymalnie 10 punktów**

Możesz korzystać z `man`, `--help`, prezentacji z zajęć i własnych notatek. Zasady korzystania z AI, komunikatorów i pomocy innych osób określa prowadzący na początku kolokwium.

**Wykonaj fork** publicznego repozytorium prowadzącego, sklonuj własny fork i pracuj wyłącznie w nim. Pliki `dane/*.log` są tylko do odczytu: **nie wolno ich zmieniać**. Twórz pliki wynikowe w katalogu `raporty/`, który należy samodzielnie utworzyć.

## A. Strumienie, filtry i potoki — 2 pkt

**1. (1 pkt)** Utwórz `raporty/bledy.txt` zawierający **wszystkie** wiersze zaczynające się dokładnie od `ERROR;` ze wszystkich `dane/*.log`, posortowane alfabetycznie. Użyj `grep`, `sort` i przekierowania `>`. W wyniku nie powinno być nazw plików źródłowych przed wierszami logów.

**2. (1 pkt)** Utwórz `raporty/ile_bledow.txt` zawierający **jedną liczbę** — liczbę wierszy z `raporty/bledy.txt`. Użyj `wc -l` i przekierowania (możesz użyć `<`).

## B. Uprawnienia i archiwizacja — 2 pkt

**3. (1 pkt)** Ustaw `src/analiza.sh` prawa **750** (`rwxr-x---`) przy użyciu `chmod`. Utrwal wynik poleceniem `stat` w pliku `raporty/uprawnienia.txt` jako samą liczbę `750` (np. `stat -c '%a' ...`).

**4. (1 pkt)** Utwórz `raporty/oddanie.tar.gz` zawierające **katalog `dane/`, katalog `src/` i plik `README.md`**. Nie pakuj folderu `.git` ani całego katalogu repozytorium. Użyj `tar`.

## C. Skrypt Bash — 4 pkt

Uzupełnij istniejący `src/analiza.sh`. Poprawne uruchomienie:

```bash
bash src/analiza.sh dane
```

**5. (1 pkt)** Pobierz katalog z pierwszego argumentu (`$1`), a jeśli go nie podano, użyj `dane`. Jeżeli katalog nie istnieje, wyświetl komunikat na **stderr** i zakończ z kodem **2**. Zastosuj `if` oraz test `-d`.

**6. (1 pkt)** Użyj pętli **`for`**, aby przejść po plikach `*.log` w wybranym katalogu. Wypisz dokładnie jeden wiersz na plik w formacie:

```text
nazwa.log;liczba_ERROR;STATUS
```

Liczba w drugim polu to liczba linii zaczynających się od `ERROR;` (użyj `grep`). Jeżeli nie ma żadnych plików `.log`, skrypt nie może wypisać dosłownego `*.log`.

**7. (2 pkt)** Ustaw `STATUS` na **`ALARM`**, jeśli w danym pliku znajdują się **co najmniej 2 wiersze zaczynające się od `TIMEOUT;`**. W przeciwnym razie wpisz **`OK`**. Użyj `if`. **Drugie pole zawsze pozostaje liczbą wpisów `ERROR;`**, niezależnie od kryterium alarmu.

Nie wypisuj nagłówka ani dodatkowych informacji na stdout, a pola oddzielaj pojedynczym średnikiem bez spacji. Sprawdź również:

```bash
bash src/analiza.sh
bash src/analiza.sh /nieistniejacy_katalog
```

## D. Git/GitHub — 2 pkt

**8. (1 pkt)** Wykonaj **co najmniej dwa własne commity**, każdy po innym etapie pracy (np. A+B, następnie C). Komunikaty mają jasno opisywać wykonane zmiany. Sprawdź `git log --oneline`.

**9. (1 pkt)** Wyślij rozwiązanie na **własny publiczny fork** (`git push`). Sprawdź w przeglądarce pliki z `raporty/` oraz zmiany w `src/analiza.sh`, a prowadzącemu przekaż URL forka.

## Co oddajesz?

Adres własnego publicznego forka, zawierającego `raporty/bledy.txt`, `raporty/ile_bledow.txt`, `raporty/uprawnienia.txt`, `raporty/oddanie.tar.gz` i uzupełniony `src/analiza.sh`.

**Ważne:** Git przechowuje tylko informację, czy plik jest wykonywalny — nie zachowuje dokładnych praw `750` po klonowaniu. Dlatego wymagamy osobno pliku `uprawnienia.txt`; prowadzący może również sprawdzić faktyczny wynik `chmod` na komputerze, na którym pracujesz.
