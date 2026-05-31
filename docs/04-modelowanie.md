# 4. Modelowanie

Diagramy zapisano w notacji Mermaid. Pliki źródłowe oraz wersje draw.io znajdują się w katalogu `diagramy/`.

## 4.1. Diagram przypadków użycia

```mermaid
flowchart LR
    STUD([Student])
    PRAC([Pracownik])
    ADMIN([Administrator])
    KIER([Kierownik])

    subgraph SYS[System zarzadzania wypozyczalnia]
        UC1((Zaloguj sie))
        UC2((Przegladaj katalog))
        UC3((Zarezerwuj sprzet))
        UC4((Anuluj rezerwacje))
        UC5((Sprawdz swoje wypozyczenia))
        UC6((Akceptuj/odrzuc rezerwacje))
        UC7((Wydaj sprzet))
        UC8((Przyjmij zwrot))
        UC9((Zglos uszkodzenie))
        UC10((Zarzadzaj katalogiem))
        UC11((Zarzadzaj kontami))
        UC12((Generuj raporty))
        UC13((Wyslij przypomnienie))
    end

    STUD --- UC1
    STUD --- UC2
    STUD --- UC3
    STUD --- UC4
    STUD --- UC5
    PRAC --- UC1
    PRAC --- UC6
    PRAC --- UC7
    PRAC --- UC8
    PRAC --- UC9
    ADMIN --- UC1
    ADMIN --- UC10
    ADMIN --- UC11
    KIER --- UC1
    KIER --- UC12

    UC3 -.->|include| UC1
    UC8 -.->|extend| UC9
    SYS -.-> UC13
```

Relacje:

- include: rezerwacja (UC3) wymaga uwierzytelnienia (UC1).
- extend: zgłoszenie uszkodzenia (UC9) rozszerza przyjęcie zwrotu (UC8).
- UC13 wyzwalany jest przez system na podstawie czasu.

## 4.2. Diagram klas

```mermaid
classDiagram
    class Uzytkownik {
        +int id
        +string imieNazwisko
        +string email
        +Rola rola
        +bool aktywny
    }
    class Sprzet {
        +int id
        +string nazwa
        +string opis
        +string nrInwentarzowy
        +string kodQR
        +StanSprzetu stan
    }
    class Kategoria {
        +int id
        +string nazwa
        +int maxDniWypozyczenia
    }
    class Rezerwacja {
        +int id
        +date dataOd
        +date dataDo
        +StatusRezerwacji status
    }
    class Wypozyczenie {
        +int id
        +datetime dataWydania
        +datetime dataZwrotu
        +datetime terminZwrotu
        +bool przeterminowane
    }
    class ZgloszenieUszkodzenia {
        +int id
        +string opis
        +datetime data
    }
    class Powiadomienie {
        +int id
        +string tresc
        +datetime dataWyslania
        +TypPowiadomienia typ
    }

    Uzytkownik "1" --> "*" Rezerwacja : sklada
    Uzytkownik "1" --> "*" Wypozyczenie : ma
    Kategoria "1" --> "*" Sprzet : grupuje
    Sprzet "1" --> "*" Rezerwacja : dotyczy
    Rezerwacja "1" --> "0..1" Wypozyczenie : realizuje
    Wypozyczenie "1" --> "0..*" ZgloszenieUszkodzenia : moze miec
    Uzytkownik "1" --> "*" Powiadomienie : otrzymuje
```

## 4.3. Diagram aktywności – proces wypożyczenia

```mermaid
flowchart TD
    A([Start]) --> B[Student rezerwuje online]
    B --> C{Reguly OK?}
    C -->|Nie| D[/Komunikat o blokadzie/]
    D --> Z([Koniec])
    C -->|Tak| E[Rezerwacja: OCZEKUJACA]
    E --> F{Pracownik akceptuje?}
    F -->|Odrzuca| G[/Powiadomienie: odrzucono/]
    G --> Z
    F -->|Akceptuje| H[Student odbiera sprzet]
    H --> I[Wydanie: WYPOZYCZONY]
    I --> J[Kontrola terminu]
    J --> K{Zbliza sie termin?}
    K -->|Tak| L[Wyslij przypomnienie]
    L --> M[Student zwraca sprzet]
    K -->|Nie| M
    M --> N{Sprzet OK?}
    N -->|Uszkodzony| O[Zglos uszkodzenie]
    O --> P[Status: DOSTEPNY / W SERWISIE]
    N -->|OK| P
    P --> Z
```

## 4.4. Diagram stanów egzemplarza sprzętu

```mermaid
stateDiagram-v2
    [*] --> Dostepny: dodanie do katalogu
    Dostepny --> Zarezerwowany: rezerwacja
    Zarezerwowany --> Dostepny: anulowanie
    Zarezerwowany --> Wypozyczony: wydanie
    Wypozyczony --> Dostepny: zwrot OK
    Wypozyczony --> WSerwisie: zwrot z uszkodzeniem
    WSerwisie --> Dostepny: naprawiony
    WSerwisie --> Wycofany: nie do naprawy
    Dostepny --> Wycofany: kasacja
    Wycofany --> [*]
```
