# 2. Pozyskiwanie wymagań

Zastosowano cztery techniki pozyskiwania wymagań: wywiad, ankietę, analizę konkurencji i analizę dokumentacji.

## 2.1. Wywiad

Forma: wywiad częściowo ustrukturyzowany. Respondenci: pracownik wypożyczalni, kierownik jednostki.

Pytania:

1. Przebieg procesu wypożyczenia.
2. Główne problemy obecnego procesu.
3. Najczęstsze przypadki uszkodzeń i strat.
4. Liczba obsługiwanych osób dziennie.
5. Oczekiwane funkcje systemu.

Wnioski:

| Ustalenie | Wymaganie |
|---|---|
| Brak mechanizmu przypominania o zwrotach | FR-14 |
| Potrzeba podglądu dostępności w czasie rzeczywistym | FR-03 |
| Brak rejestru uszkodzeń per egzemplarz | FR-16, FR-17 |
| Kolejki w godzinach szczytu | FR-07 |

## 2.2. Ankieta

Forma: ankieta elektroniczna. Próba: 52 odpowiedzi. Grupa docelowa: studenci.

| Pytanie | Wynik |
|---|---|
| Wypożyczanie sprzętu na uczelni w przeszłości | 71% tak |
| Główne czynniki zniechęcające | kolejki 44%, brak informacji o dostępności 38%, godziny otwarcia 18% |
| Preferencja rezerwacji online | 89% tak |
| Najważniejsza funkcja | dostępność 41%, rezerwacja 33%, powiadomienia 16% |
| Preferowane urządzenie | telefon 68%, komputer 32% |

Wnioski:

- Wysokie zapotrzebowanie na rezerwację online (89%).
- Dominacja urządzeń mobilnych (68%) uzasadnia wymaganie responsywności NFR-04.
- Priorytet funkcji: dostępność i rezerwacja.

## 2.3. Analiza konkurencji

| System | Funkcja referencyjna | Wymaganie |
|---|---|---|
| Booqable | Kalendarz dostępności, katalog ze zdjęciami | FR-02, FR-04 |
| myTurn | Identyfikacja sprzętu kodem QR/kreskowym | FR-19 |
| Rezerwacja sal (USOS) | Logowanie kontem uczelnianym | FR-01, NFR-07 |
| Wypożyczalnie pojazdów | Statusy wypożyczenia, kaucje | statusy wypożyczenia, kaucja jako zmiana |

Wnioski: standardem rynkowym są katalog, kalendarz dostępności, statusy wypożyczenia, identyfikacja egzemplarza kodem QR oraz logowanie zintegrowane z uczelnią.

## 2.4. Analiza dokumentacji

Analizowane dokumenty: regulamin wypożyczalni, wzór protokołu zdawczo-odbiorczego, arkusz ewidencyjny.

| Dokument | Ustalenie |
|---|---|
| Regulamin | Reguły biznesowe BR-01–BR-04 |
| Protokół zdawczo-odbiorczy | Zakres danych rejestrowanych przy wydaniu i zwrocie |
| Arkusz ewidencyjny | Atrybuty sprzętu: nr inwentarzowy, kategoria, stan |

Reguły biznesowe:

- BR-01: Wypożyczać może wyłącznie student z aktywnym statusem.
- BR-02: Domyślny maksymalny czas wypożyczenia wynosi 14 dni (konfigurowalny per kategoria).
- BR-03: Student z zaległym zwrotem nie może utworzyć nowej rezerwacji.
- BR-04: Student może mieć maksymalnie 3 aktywne wypożyczenia.

## 2.5. Uzasadnienie wyboru metod

| Technika | Uzasadnienie | Mocna strona | Ograniczenie |
|---|---|---|---|
| Wywiad | Pogłębione zrozumienie procesu od strony obsługi | Szczegółowość | Mała próba, subiektywność |
| Ankieta | Dane ilościowe od grupy docelowej | Reprezentatywność | Brak pogłębienia |
| Analiza konkurencji | Identyfikacja standardów rynkowych | Dobre praktyki | Rozwiązania nie zawsze adekwatne |
| Analiza dokumentacji | Formalne reguły i procesy | Twarde fakty | Ryzyko nieaktualności |

Dobór metod oparto na triangulacji: połączeniu danych jakościowych (wywiad), ilościowych (ankieta), zewnętrznego benchmarku (konkurencja) oraz źródeł wewnętrznych (dokumentacja). Wymaganie potwierdzone w więcej niż jednym źródle traktowane jest jako istotne.
