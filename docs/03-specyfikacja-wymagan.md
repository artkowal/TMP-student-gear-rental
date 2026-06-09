# 3. Specyfikacja wymagań

Oznaczenia priorytetów (MoSCoW): 
- **M** – Must have,
- **S** – Should have, 
- **C** – Could have, 
- **W** – Won't have.

## 3.1. Wymagania funkcjonalne

### Konto i logowanie

| ID | Wymaganie | Priorytet | Źródło |
|---|---|---|---|
| FR-01 | System umożliwia logowanie kontem uczelnianym | M | konkurencja, dokumentacja |
| FR-02 | System udostępnia profil użytkownika i dane kontaktowe | S | wywiad |

### Katalog sprzętu

| ID | Wymaganie | Priorytet | Źródło |
|---|---|---|---|
| FR-03 | System wyświetla katalog sprzętu z aktualną dostępnością | M | wywiad, ankieta |
| FR-04 | System prezentuje szczegóły sprzętu (zdjęcie, opis, kategoria, stan) | M | konkurencja |
| FR-05 | System umożliwia filtrowanie i wyszukiwanie sprzętu | S | ankieta |
| FR-06 | System wyświetla kalendarz dostępności egzemplarza | S | konkurencja |

### Rezerwacje i wypożyczenia

| ID | Wymaganie | Priorytet | Źródło |
|---|---|---|---|
| FR-07 | Student rezerwuje sprzęt online na wybrany termin | M | wywiad, ankieta |
| FR-08 | System blokuje rezerwację przy zaległym zwrocie (BR-03) | M | dokumentacja |
| FR-09 | System blokuje rezerwację po przekroczeniu limitu 3 aktywnych (BR-04) | M | dokumentacja |
| FR-10 | Student anuluje rezerwację przed jej rozpoczęciem | S | wywiad |
| FR-11 | Pracownik akceptuje lub odrzuca rezerwację | M | wywiad |
| FR-12 | Pracownik rejestruje wydanie sprzętu | M | wywiad |
| FR-13 | Pracownik rejestruje zwrot sprzętu | M | wywiad |
| FR-14 | System wysyła automatyczne przypomnienie o terminie zwrotu | M | wywiad |
| FR-15 | System oznacza wypożyczenie jako przeterminowane | S | wywiad |

### Stan sprzętu i historia

| ID | Wymaganie | Priorytet | Źródło |
|---|---|---|---|
| FR-16 | Pracownik zgłasza uszkodzenie sprzętu przy zwrocie | S | wywiad |
| FR-17 | System prowadzi historię wypożyczeń egzemplarza | S | wywiad |
| FR-18 | Administrator oznacza sprzęt jako w serwisie lub wycofany | S | dokumentacja |
| FR-19 | System identyfikuje egzemplarz kodem QR/kreskowym | C | konkurencja |

### Administracja i raporty

| ID | Wymaganie | Priorytet | Źródło |
|---|---|---|---|
| FR-20 | Administrator dodaje, edytuje i usuwa sprzęt w katalogu | M | dokumentacja |
| FR-21 | Administrator zarządza kontami i rolami użytkowników | M | konkurencja |
| FR-22 | Kierownik generuje raporty wykorzystania sprzętu | S | wywiad |

## 3.2. Wymagania niefunkcjonalne

### Wydajność

| ID | Wymaganie | Kryterium |
|---|---|---|
| NFR-01 | Czas odpowiedzi przy przeglądaniu katalogu | ≤ 2 s dla 95% żądań |
| NFR-02 | Obsługa użytkowników równoczesnych | min. 200 bez degradacji |
| NFR-03 | Czas zapisu rezerwacji | ≤ 1 s |

### Użyteczność

| ID | Wymaganie | Kryterium |
|---|---|---|
| NFR-04 | Responsywność interfejsu | poprawny układ od 320 px |
| NFR-05 | Realizacja rezerwacji bez instrukcji | ≥ 90% testerów kończy zadanie |
| NFR-06 | Zgodność z WCAG 2.1 | poziom AA |

### Bezpieczeństwo

| ID | Wymaganie | Kryterium |
|---|---|---|
| NFR-07 | Uwierzytelnianie przez SSO uczelni | brak odrębnych haseł w systemie |
| NFR-08 | Szyfrowanie transmisji | TLS 1.2+ |
| NFR-09 | Zgodność z RODO | usuwalność danych na żądanie, log dostępu |
| NFR-10 | Autoryzacja oparta na rolach (RBAC) | rozdział uprawnień student/administrator |

### Niezawodność i utrzymanie

| ID | Wymaganie | Kryterium |
|---|---|---|
| NFR-11 | Dostępność systemu | ≥ 99% w godzinach pracy uczelni |
| NFR-12 | Kopie zapasowe | codziennie, retencja 30 dni |
| NFR-13 | Zgodność z przeglądarkami | 2 ostatnie wersje Chrome, Firefox, Edge, Safari |

## 3.3. User stories i kryteria akceptacji

| ID | User story | Kryteria akceptacji |
|---|---|---|
| US-01 | Jako student chcę widzieć dostępność sprzętu, aby nie udawać się do stanowiska bez potrzeby. | Przy każdym sprzęcie widoczny status zgodny ze stanem rzeczywistym. |
| US-02 | Jako student chcę zarezerwować sprzęt online, aby mieć pewność jego dostępności. | Po wyborze terminu i potwierdzeniu, przy spełnieniu reguł, tworzona jest rezerwacja z potwierdzeniem. |
| US-03 | Jako student chcę otrzymać przypomnienie o zwrocie, aby uniknąć przekroczenia terminu. | Na 24 h przed terminem wysyłany jest e-mail z przypomnieniem. |
| US-04 | Jako pracownik chcę szybko wydać sprzęt, aby ograniczyć kolejki. | Po skanowaniu kodu i potwierdzeniu status zmienia się na „wypożyczony" w < 1 s. |
| US-05 | Jako pracownik chcę zgłosić uszkodzenie przy zwrocie, aby zachować odpowiedzialność. | Notatka o uszkodzeniu zapisuje się w historii egzemplarza. |
| US-06 | Jako administrator chcę dodać sprzęt do katalogu, aby był dostępny do rezerwacji. | Po zapisaniu danych sprzęt pojawia się w katalogu jako dostępny. |
| US-07 | Jako kierownik chcę raport najczęściej wypożyczanego sprzętu, aby planować zakupy. | Dla wybranego zakresu dat generowana jest lista/wykres wypożyczeń. |

## 3.4. Przypadek użycia UC-02 – Rezerwacja sprzętu

| Pole | Treść |
|---|---|
| Aktor główny | Student |
| Cel | Rezerwacja dostępnego sprzętu na wybrany termin |
| Warunki wstępne | Student zalogowany (FR-01), brak zaległości (BR-03), mniej niż 3 aktywne wypożyczenia (BR-04) |
| Warunek końcowy | Rezerwacja w statusie „oczekująca", sprzęt zablokowany na termin |
| Scenariusz główny | 1. Student otwiera katalog. 2. Filtruje sprzęt (FR-05). 3. Sprawdza kalendarz dostępności (FR-06). 4. Wybiera termin. 5. Potwierdza rezerwację. 6. System weryfikuje reguły (BR-03, BR-04). 7. System tworzy rezerwację i wysyła potwierdzenie (FR-07). |
| Scenariusze alternatywne | 6a. Zaległy zwrot — komunikat o blokadzie (FR-08). 6b. Limit wypożyczeń przekroczony — komunikat (FR-09). 4a. Kolizja terminu — system proponuje wolny termin. |
