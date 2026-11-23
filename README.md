# Kolokwium właściwe — grupa B — Diagnostyka stanowiska akwizycji danych

**Podstawy informatyki | Nanoinżynieria Materiałów | AGH WFiIS**

**Czas: 45 minut. Maksimum: 10 punktów.**

Repozytorium startowe do indywidualnego kolokwium praktycznego. Logi przedstawiają fikcyjne dane diagnostyczne. Nie dodawaj haseł, tokenów ani prywatnych kluczy SSH.

## Przed rozpoczęciem

1. Zaloguj się na GitHub i sprawdź, czy połączenie SSH działa: `ssh -T git@github.com`.
2. Wykonaj **Fork** TEGO repozytorium na własne konto (repozytorium publiczne).
3. Sklonuj **własny fork** przez SSH: `git clone git@github.com:TWOJ_LOGIN/PI-Kolokwium-2026-Grupa-B.git`.
4. Wejdź do katalogu repozytorium i upewnij się, że `git remote -v` wskazuje Twoje konto.
5. Otwórz [`ZADANIA.md`](ZADANIA.md). Plików w `dane/` nie zmieniaj.

Jeśli fork ma inną nazwę, użyj adresu SSH skopiowanego bezpośrednio z przycisku **Code** na GitHubie.

## Szybkie sprawdzenie środowiska

```bash
pwd
ls -lah
head -n 3 dane/proba_A.log
bash -n src/analiza.sh
```

Rozwiązanie oddajesz przez dwa własne commity i `git push` do forka. Następnie przekazujesz prowadzącemu **URL publicznego forka** (nie Pull Request). Jeżeli GitHub jest niedostępny, postępuj zgodnie z awaryjną instrukcją prowadzącego.
