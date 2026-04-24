# Sprawozdanie z przygotowania i uruchomienia aplikacji Flask (K6)

## 1. Cel ćwiczenia

Celem ćwiczenia było przygotowanie środowiska pracy, uruchomienie aplikacji Flask zgodnie z instrukcjami z `README.md`, wykonanie zapytań `curl`, uruchomienie testów oraz poprawa błędu w formacie JSON.

## 2. Repozytorium i przygotowanie projektu

Wykorzystano repozytorium grupy K6:

- `https://github.com/ab-merito-primary/2026_L_II_NWh_INFI_K6`

Następnie przejrzano zawartość katalogu projektu i przygotowano środowisko wirtualne.

**Miejsce na zrzut ekranu:** `screeny/01_repo_ls.png`  
Opis: wejście do repozytorium i lista plików projektu.

**Miejsce na zrzut ekranu:** `screeny/02_venv_aktywacja.png`  
Opis: aktywacja środowiska `.venv` i weryfikacja ścieżki interpretera Python.

## 3. Uruchomienie testów

Uruchomiono testy poleceniem:

`PYTHONPATH=. py.test -q`

Wynik testów: `3 passed`.

**Miejsce na zrzut ekranu:** `screeny/03_testy_pytest.png`  
Opis: poprawne przejście testów jednostkowych.

## 4. Wprowadzone zmiany w kodzie

W projekcie wykonano modyfikacje:

- zmieniono imię wyświetlane przez aplikację na: `Michał`,
- poprawiono błąd w formacie JSON:
  - klucz `mgs` zastąpiono `msg`,
  - poprawiono składnię wartości wiadomości (brakujący cudzysłów),
- zaktualizowano test widoku JSON do nowej wartości imienia.

Stan zmodyfikowanych plików zweryfikowano przez:

`git status --short`

**Miejsce na zrzut ekranu:** `screeny/04_git_status.png`  
Opis: lista zmienionych plików po wykonanych poprawkach.

## 5. Uruchomienie aplikacji

Aplikację uruchomiono poleceniem:

`PYTHONPATH=. FLASK_APP=hello_world flask run -p 5050`

Aplikacja wystartowała poprawnie pod adresem lokalnym:

- `http://127.0.0.1:5050`

**Miejsce na zrzut ekranu:** `screeny/06_flask_running_5050.png`  
Opis: poprawnie uruchomiony serwer Flask.

## 6. Test endpointów przy użyciu curl

Wykonano zapytania:

- `curl 127.0.0.1:5050`
- `curl 127.0.0.1:5050/outputs`
- `curl "127.0.0.1:5050/?output=json"`

Otrzymane wyniki potwierdziły:

- poprawne wyświetlanie tekstu z imieniem `Michał`,
- poprawną listę dostępnych formatów,
- poprawny format JSON z kluczem `msg`.

**Miejsce na zrzut ekranu:** `screeny/05_curl_wyniki.png`  
Opis: wyniki zapytań `curl` dla endpointów aplikacji.

## 7. Informacje teoretyczne

### 7.1. Markdown (MD)

Markdown to lekki język znaczników służący do formatowania tekstu. Najczęściej używany jest do tworzenia dokumentacji technicznej, np. plików `README.md`. Umożliwia m.in. tworzenie nagłówków, list, linków i bloków kodu.

### 7.2. Charakterystyka JSON i porównanie z XML/YAML

- **JSON**: prosty i lekki format wymiany danych, bardzo popularny w API.
- **XML**: bardziej rozbudowany i „opisowy”, ale zwykle mniej czytelny i bardziej rozgadany od JSON.
- **YAML**: czytelny dla człowieka format konfiguracyjny oparty na wcięciach, często używany np. w CI/CD.

## 8. Wnioski

Ćwiczenie pozwoliło przećwiczyć pełny podstawowy proces pracy z projektem:

- przygotowanie środowiska Python,
- uruchomienie i testowanie aplikacji Flask,
- diagnozę i poprawę błędu w kodzie,
- weryfikację działania endpointów za pomocą `curl`,
- dokumentowanie wykonanych kroków w formie sprawozdania.
