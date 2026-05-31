# 6. Walidacja wymagań

## 6.1. Checklist jakości wymagań

Kryteria oceny:

| Kryterium | Definicja |
|---|---|
| Jednoznaczne | Możliwa tylko jedna interpretacja |
| Kompletne | Opisuje także wyjątki, brak luk informacyjnych |
| Spójne | Brak sprzeczności z innymi wymaganiami |
| Testowalne | Posiada mierzalne kryterium weryfikacji |
| Realne | Wykonalne w zakładanych warunkach |
| Śledzalne | Posiada identyfikator i źródło |

Ocena wybranych wymagań:

| Wymaganie | Jednoznaczne | Kompletne | Spójne | Testowalne | Realne | Śledzalne |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| FR-07 | + | + | + | + | + | + |
| FR-14 | + | + | + | + | + | + |
| NFR-01 | + | + | + | + | + | + |
| NFR-11 | + | + | + | + | warunkowo | + |

Przykłady korekty wymagań:

| Wersja niepoprawna | Wersja poprawna |
|---|---|
| „System ma być szybki." | NFR-01: „Czas odpowiedzi przy przeglądaniu katalogu ≤ 2 s dla 95% żądań." |
| „Student dostaje przypomnienie." | FR-14: „System wysyła e-mail z przypomnieniem na 24 h przed terminem zwrotu." |

## 6.2. Scenariusze testowe

| ID | Wymaganie | Warunki wstępne | Kroki | Oczekiwany wynik |
|---|---|---|---|---|
| TC-01 | FR-07 | Student zalogowany, brak zaległości, < 3 wypożyczenia, sprzęt wolny | Katalog → wybór sprzętu → wybór terminu → potwierdzenie | Rezerwacja „oczekująca", e-mail potwierdzający, sprzęt zablokowany |
| TC-02 | FR-08 | Student z zaległym zwrotem | Próba rezerwacji | Blokada i komunikat o zaległości |
| TC-03 | FR-14 | Aktywne wypożyczenie, 24 h do terminu | Upływ czasu do T-24h | Jednorazowe wysłanie e-maila |
| TC-04 | FR-09 | 3 aktywne wypożyczenia | Próba rezerwacji czwartego sprzętu | Blokada i komunikat o limicie |
| TC-05 | FR-16 | Zwrot uszkodzonego sprzętu | Otwarcie wypożyczenia → oznaczenie uszkodzenia → opis → zatwierdzenie | Status „w serwisie", wpis w historii egzemplarza |

## 6.3. Ocena spójności i kompletności

Macierz śledzenia:

| Potrzeba | Wymaganie | User story | Test |
|---|---|---|---|
| Brak informacji o dostępności | FR-03 | US-01 | TC-01 |
| Rezerwacja online | FR-07 | US-02 | TC-01 |
| Brak przypomnień o zwrotach | FR-14, FR-15 | US-03 | TC-03 |
| Reguły regulaminu | FR-08, FR-09 | — | TC-02, TC-04 |
| Uszkodzenia sprzętu | FR-16, FR-17 | US-05 | TC-05 |

Kompletność: każda zidentyfikowana potrzeba ma odpowiadające wymaganie i scenariusz testowy.

Spójność:

- FR-07 a FR-08/BR-03 — rezerwacja blokowana z czytelnym komunikatem, bez sprzeczności.
- NFR-07 (logowanie wyłącznie SSO) — zakres ograniczony do studentów uczelni.

Zidentyfikowane luki:

- Brak wymagania dotyczącego kaucji — świadomie poza zakresem MVP.
- NFR-11 (dostępność 99%) — zależne od infrastruktury Działu IT, oznaczone jako warunkowe.
