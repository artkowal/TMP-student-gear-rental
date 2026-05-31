# 10. Karty wymagań (Volere)

## 10.1. Szablon karty

| Pole | Opis |
|---|---|
| Requirement ID | Identyfikator wymagania |
| Type | Typ (funkcjonalne / niefunkcjonalne) |
| Description | Opis wymagania |
| Rationale | Uzasadnienie |
| Source | Źródło |
| Fit Criterion | Mierzalne kryterium akceptacji |
| Customer Satisfaction | Zadowolenie przy realizacji (1–5) |
| Customer Dissatisfaction | Niezadowolenie przy braku (1–5) |
| Priority | Priorytet (MoSCoW) |
| Dependencies | Powiązania |
| Conflicts | Sprzeczności |
| History | Historia zmian |

## 10.2. Karty wymagań

### FR-07 – Rezerwacja sprzętu online

| Pole | Wartość |
|---|---|
| Requirement ID | FR-07 |
| Type | Funkcjonalne |
| Description | Student rezerwuje dostępny sprzęt online na wybrany termin |
| Rationale | Eliminacja kolejek i zapewnienie dostępności |
| Source | Ankieta (89%), wywiad |
| Fit Criterion | Rezerwacja w ≤ 4 krokach; zapis ≤ 1 s; sprzęt zablokowany na termin |
| Customer Satisfaction | 5 |
| Customer Dissatisfaction | 5 |
| Priority | Must have |
| Dependencies | FR-01, FR-03, BR-03, BR-04 |
| Conflicts | FR-11 (rozwiązane: status „oczekująca") |
| History | v1.0 – 2026-05-31 |

### FR-14 – Automatyczne przypomnienie o zwrocie

| Pole | Wartość |
|---|---|
| Requirement ID | FR-14 |
| Type | Funkcjonalne |
| Description | System wysyła automatyczne przypomnienie o terminie zwrotu |
| Rationale | Ograniczenie przekraczania terminów |
| Source | Wywiad |
| Fit Criterion | E-mail wysyłany jednorazowo na 24 h przed terminem; dostarczalność ≥ 95% |
| Customer Satisfaction | 4 |
| Customer Dissatisfaction | 4 |
| Priority | Must have |
| Dependencies | FR-12, serwer poczty |
| Conflicts | brak |
| History | v1.0 – 2026-05-31; v1.1 – kanał push (FR-26) |

### FR-08 – Blokada rezerwacji przy zaległości

| Pole | Wartość |
|---|---|
| Requirement ID | FR-08 |
| Type | Funkcjonalne |
| Description | System blokuje rezerwację przy zaległym zwrocie |
| Rationale | Egzekwowanie regulaminu (BR-03) |
| Source | Analiza dokumentacji |
| Fit Criterion | Próba rezerwacji przy zaległości skutkuje blokadą i komunikatem w 100% przypadków |
| Customer Satisfaction | 3 |
| Customer Dissatisfaction | 4 |
| Priority | Must have |
| Dependencies | FR-07, BR-03 |
| Conflicts | FR-07 (rozwiązane: komunikat informacyjny) |
| History | v1.0 – 2026-05-31 |

### NFR-01 – Czas odpowiedzi katalogu

| Pole | Wartość |
|---|---|
| Requirement ID | NFR-01 |
| Type | Niefunkcjonalne (wydajność) |
| Description | Czas odpowiedzi przy przeglądaniu katalogu poniżej 2 s |
| Rationale | Utrzymanie użyteczności na urządzeniach mobilnych |
| Source | Ankieta, dobra praktyka |
| Fit Criterion | ≤ 2 s dla 95% żądań przy 200 użytkownikach równoczesnych |
| Customer Satisfaction | 3 |
| Customer Dissatisfaction | 4 |
| Priority | Must have |
| Dependencies | NFR-02 |
| Conflicts | brak |
| History | v1.0 – 2026-05-31 |

### NFR-09 – Zgodność z RODO

| Pole | Wartość |
|---|---|
| Requirement ID | NFR-09 |
| Type | Niefunkcjonalne (bezpieczeństwo/prawne) |
| Description | Zgodność z RODO w zakresie danych studentów |
| Rationale | Wymóg prawny |
| Source | Inspektor RODO, ograniczenie C-02 |
| Fit Criterion | Usuwalność danych w ≤ 30 dni; log dostępu; zgoda na przetwarzanie |
| Customer Satisfaction | 2 |
| Customer Dissatisfaction | 5 |
| Priority | Must have |
| Dependencies | NFR-08, NFR-10 |
| Conflicts | ZM-02 (wymagana umowa powierzenia) |
| History | v1.0 – 2026-05-31 |

## 10.3. Mapowanie struktury Volere

| Grupa Volere | Zakres | Lokalizacja |
|---|---|---|
| Project Drivers | Cel, interesariusze, użytkownicy | 01-kontekst-interesariusze.md |
| Project Constraints | Ograniczenia, założenia, słownik | 09-SRS.md, karty Volere |
| Functional Requirements | Zakres, wymagania funkcjonalne | 03-specyfikacja-wymagan.md |
| Non-functional Requirements | Wymagania niefunkcjonalne | 03-specyfikacja-wymagan.md |
| Project Issues | Ryzyka, zmiany | 07-zarzadzanie-zmiana.md |

## 10.4. Interpretacja skali satysfakcji

- Customer Satisfaction (1–5): poziom zadowolenia przy realizacji wymagania.
- Customer Dissatisfaction (1–5): poziom niezadowolenia przy braku wymagania.
- Wysokie obie wartości oznaczają wymaganie krytyczne.
- Niska satysfakcja i wysokie niezadowolenie odpowiadają wymaganiom kategorii Basic w modelu Kano.
