# Skrypt prezentacji — System zarządzania wypożyczalnią sprzętu studenckiego

> **Łączny czas:** około 8 minut · **Tempo mówienia:** spokojne, ok. 130 słów/min
> Każda osoba mówi ok. 2 minuty. Slajdy zmieniamy po zakończeniu swojej kwestii.

---

## Osoba A — Slajdy 1–3 · (~2 min)

---

### Slajd 1 — Tytuł

Dzień dobry. Nasz projekt dotyczy systemu informatycznego dla wypożyczalni sprzętu studenckiego. Na co dzień taka wypożyczalnia działa na zasadzie zeszytu albo arkusza kalkulacyjnego — ktoś przychodzi, wpisuje swoje dane, bierze sprzęt i tyle. To może brzmieć jak drobnostka, ale gdy sprzętu jest dużo, a chętnych jest więcej, ten sposób przestaje działać. Zajęliśmy się pełną analizą wymagań — od problemu, przez specyfikację, aż po to, jak tym systemem zarządzać, gdy wymagania się zmienią.

---

### Slajd 2 — Problem

Zanim zaczęliśmy cokolwiek projektować, zapytaliśmy: co tak naprawdę nie działa? Studenci przyznają, że największy problem to brak informacji — nie wiedzą, czy sprzęt jest wolny, zanim w ogóle przyjdą do wypożyczalni. Pracownicy tracą czas na ręczne wpisywanie danych i nikt nie przypomina studentom o terminie zwrotu, więc sprzęt jest przetrzymywany. Kierownik nie ma żadnych danych o tym, co się pożycza najczęściej, więc trudno mu planować zakupy. Każda strona tego procesu ma inny problem — i każdy z nich chcemy zaadresować w jednym systemie.

---

### Slajd 3 — Pozyskiwanie wymagań

Żeby dobrze zrozumieć te problemy, zastosowaliśmy cztery różne techniki. Przeprowadziliśmy wywiad z pracownikiem i kierownikiem — to dało nam perspektywę od wewnątrz. Równolegle rozesłaliśmy ankietę do studentów, odpowiedziały 52 osoby. Wyniki były jednoznaczne: 89 procent chce rezerwacji online, a prawie 70 procent korzysta głównie z telefonu — to od razu wpłynęło na nasze wymagania. Spojrzeliśmy też na to jak działają podobne systemy na rynku — Booqable, myTurn — i przeanalizowaliśmy dokumenty wewnętrzne wypożyczalni. Z regulaminu wyciągnęliśmy konkretne reguły, które musieliśmy wprost przełożyć na wymagania systemowe. Dzięki połączeniu tych czterech źródeł mamy pewność, że każde wymaganie ma realne uzasadnienie.

---

## Osoba B — Slajdy 4–6 · (~2 min)

---

### Slajd 4 — Rozwiązanie

Skoro wiemy co nie działa, powiedzmy co system ma robić. Rdzeń to katalog online — student sprawdza dostępność sprzętu i rezerwuje go bez wychodzenia z domu, bez kolejki. Pracownik dostaje proste narzędzie do rejestracji wydań i zwrotów. System sam wysyła e-maile z przypomnieniem o terminie zwrotu dzień wcześniej — bez żadnej interwencji człowieka. Kierownik może w każdej chwili wygenerować raport o tym, co i kiedy było wypożyczane. Wszystko działa w przeglądarce, nic nie trzeba instalować — to ważne, bo uczelnia ma różne stanowiska i różne systemy operacyjne.

---

### Slajd 5 — Zakres systemu

W każdym projekcie ważna decyzja to ustalenie, czego się NIE robi — i dlaczego. Świadomie wyłączyliśmy z zakresu płatności i kaucje, fizyczne szafki, integrację z dziekanatem i natywną aplikację mobilną. Nie dlatego, że to są złe pomysły — po prostu na etapie pierwszego wdrożenia chcemy skupić się na tym, co daje największą wartość przy najmniejszym ryzyku. Integracja z systemem USOS ląduje w fazie drugiej — jest technicznie wykonalna, ale wymaga osobnych ustaleń z uczelnią. Wyraźne granice systemu pomagają też zarządzać oczekiwaniami interesariuszy.

---

### Slajd 6 — Interesariusze

Zidentyfikowaliśmy osiem grup interesariuszy i użyliśmy macierzy Mendelowa, żeby określić, kto wymaga jak dużo uwagi. Trójkę zarządzamy blisko: kierownik, pracownik i administrator — to oni codziennie dotykają systemu albo podejmują decyzje o nim. Władze uczelni i Dział IT musimy trzymać zadowolonymi, bo to oni finansują projekt i utrzymują infrastrukturę. Studenta informujemy na bieżąco, bo to główny użytkownik końcowy, ale ma mniejszy wpływ na decyzje projektowe. Ten podział nie jest tylko teorią — przekłada się bezpośrednio na to, kto akceptuje zmiany w wymaganiach i kto pojawia się przy stole podczas negocjacji.

---

## Osoba C — Slajdy 7–8 · (~2 min)

---

### Slajd 7 — Wymagania funkcjonalne

Zdefiniowaliśmy dwadzieścia dwa wymagania funkcjonalne i każdemu przypisaliśmy priorytet, źródło i kryterium akceptacji. Dwanaście to Must Have — bez nich system w ogóle nie ma sensu wdrażać. Wziąć przykład: FR-07 to rezerwacja online — 89 procent ankietowanych tego oczekuje, więc to oczywisty must. FR-08 i FR-09 wynikają wprost z regulaminu — system musi zablokować rezerwację studentowi, który przetrzymuje sprzęt albo ma już trzy aktywne wypożyczenia. FR-14 to automatyczne przypomnienie e-mail — adresuje główny problem, przez który sprzęt jest przetrzymywany. Kluczowa zasada, którą stosujemy: każde wymaganie musi mieć konkretne źródło. Bez uzasadnienia wymaganie nie trafia na listę.

---

### Slajd 8 — Wymagania niefunkcjonalne

Wymagania niefunkcjonalne to jakość systemu — rzeczy, które użytkownik czuje, ale rzadko potrafi sformułować. Tu obowiązuje żelazna zasada: każde wymaganie musi być mierzalne i testowalne. Nie piszemy "system ma być szybki" — piszemy "czas odpowiedzi katalogu nie przekracza dwóch sekund dla 95 procent żądań przy 200 użytkownikach jednocześnie". Nie piszemy "system ma być bezpieczny" — piszemy "uwierzytelnianie wyłącznie przez SSO uczelni, zero własnych haseł". W dokumentacji mamy przykłady złych wymagań i ich poprawne wersje — to pomaga zrozumieć, co właściwie oznacza dobrze sformułowane wymaganie. Zadbaliśmy też o WCAG 2.1 AA i pełną zgodność z RODO, bo te rzeczy są wymagane przepisami, a nie tylko dobrą wolą.

---

## Osoba D — Slajdy 9–11 · (~2 min)

---

### Slajd 9 — Architektura systemu

Architektura jest celowo prosta i sprawdzona. Użytkownik otwiera przeglądarkę albo zainstalowaną aplikację PWA i przez HTTPS trafia do serwera aplikacji. Ten serwer rozmawia z bazą danych, z uczelnianym systemem logowania przez SSO i z serwerem poczty do wysyłania przypomnień. W fazie drugiej dołączy USOS API do automatycznej weryfikacji, czy student ma aktywny status — stąd przerywana linia na diagramie. Całość jest hostowana po stronie Działu IT uczelni — to jedno z naszych ograniczeń projektowych, ale też daje uczelni pełną kontrolę nad danymi, co jest ważne z perspektywy RODO.

---

### Slajd 10 — Priorytetyzacja MoSCoW

Do priorytetyzacji użyliśmy metody MoSCoW. Dwanaście wymagań Must Have to MVP — minimum, które musi działać przy wdrożeniu. Dziewięć Should Have wzbogaci system po MVP, ale nie blokuje uruchomienia. Jedno Could Have to kody QR — fajny pomysł, ale wymaga zakupu skanerów i etykiet, więc zostawiamy na później. Zastosowaliśmy też model Kano — przypomnienia e-mail i raporty to tak zwane funkcje Excitement: użytkownicy ich nie oczekują z góry, ale gdy je dostaną — są zaskoczeni pozytywnie. Każdy priorytet ma pisemne uzasadnienie, żeby przyszły zespół deweloperski rozumiał, dlaczego coś jest ważne, a nie tylko co jest ważne.

---

### Slajd 11 — Roadmap

Projekt podzieliliśmy na trzy fazy, każda z nich wynika z decyzji naszego Change Advisory Board. Faza pierwsza to MVP: kompletny obieg — katalog, rezerwacja, wydanie, zwrot, powiadomienia. Faza druga to integracja z USOS i powiadomienia push przez PWA — CAB zatwierdził, czekamy na podpisanie umowy powierzenia danych z uczelnią. Faza trzecia to kaucje i opłaty za przetrzymanie — CAB wstrzymał tę decyzję, bo ryzyko prawne i wymagania PCI DSS są za duże na start. Warunkiem powrotu do tematu jest zmierzenie rzeczywistych strat na podstawie raportów z fazy pierwszej. To jest clou zarządzania zmianą — nie tylko proponujemy zmiany, ale dokumentujemy decyzje i warunki, które muszą być spełnione, żeby do nich wrócić.

---

Dziękuję za uwagę.
