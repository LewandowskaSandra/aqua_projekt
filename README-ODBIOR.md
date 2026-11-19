# Aqua Arcade — wersja technicznie rozbudowana (13 listopada 2026)

## Co pozostało niezmienione

Zachowano treść i rozmieszczenie istniejących pięciu podstron: `index.html`, `blog.html`, `single.html`, `about.html`, `contact.html`. Nie zmieniano oryginalnych zdjęć, tła, kolorów, proporcji paneli ani dotychczasowych arkuszy CSS (poza dopisaniem wydzielonego bloku e-commerce w `style.css`). Istniejący projekt nadal wykorzystuje jego dotychczasowe arkusze poprawek.

Nieuniknione dodatki w dotychczasowym interfejsie: link **Shop** i ikony konta/koszyka w nawigacji, dyskretne oceny i linki do szczegółów w istniejących kartach gier. Wynikają wprost z wymagań ćwiczenia 5. Pozostałe elementy nie były projektowane na nowo.

## Nowe podstrony

- `sklep.html` — katalog ośmiu pozycji (cztery istniejące gry i cztery przykładowe propozycje katalogowe), filtr kategorii, limit ceny, reset, sortowanie, paginacja demonstracyjna, breadcrumb.
- `produkt.html` — karta produktu, trzy miniatury, cena, ocena, platforma, ilość, zakładki Bootstrap, rekomendacje. Wybór produktu przekazuje parametr `?game=...`.
- `koszyk.html` — koszyk tabelaryczny, edycja ilości, usuwanie pozycji, demonstracyjny kod AQUA10, podsumowanie. Przy pierwszej wizycie bez wcześniej zapisanych zakupów pojawiają się dwa przykładowe produkty, wymagane do prezentacji makiety.
- `zamowienie.html` — walidowany formularz danych, wybór dostawy/płatności, opcjonalna faktura, akceptacja warunków i symulowana finalizacja.
- `konto.html` — dashboard, historia zamówień, adres, preferencje, komunikat o demonstracyjnym zamówieniu.

## Technologie

HTML5, CSS3, Bootstrap 5.3.3 CDN, Bootstrap Icons 1.11.3 CDN, JavaScript bez serwera. Wspólne style e-commerce umieszczono w `style.css` w bloku `/* MODUŁ E-COMMERCE */`; drobne dodatki do istniejących widoków są w `technical-additions.css`. Wszystkie grafiki pochodzą z oryginalnego katalogu `assets`.

Koszyk jest przechowywany w `localStorage`. Kod promocyjny i informacja o ostatnim zamówieniu są przechowywane w `sessionStorage`. Formularz finalizacji nie pobiera danych płatniczych, nie tworzy rzeczywistego konta i nie wysyła informacji na serwer. Oceny i część nazw w katalogu są danymi demonstracyjnymi, nie zweryfikowanymi informacjami handlowymi.

## Automatycznie sprawdzone

- 10 z 10 plików ma dokładnie jeden `h1`.
- Wszystkie lokalne pliki docelowe odnośników oraz ich fragmenty `#id` istnieją.
- Wszystkie obrazki mają `alt` (puste wartości tylko tam, gdzie dopuszczalne są dekoracje).
- Pola formularzy mają etykiety lub nazwy dostępności.
- Składnia JavaScript sprawdzona przez `node --check`.
- Wszystkie deklaracje JSON-LD są prawidłowym JSON-em.

## Rzeczy do ręcznej walidacji przed oddaniem

1. **Chrome DevTools / Device Toolbar**: sprawdzić `360`, `390`, `768`, `1200` px; zwłaszcza brak poziomego przewijania na **każdej** stronie, nie tylko Home.
2. **Menu**: otwieranie/zamykanie hamburgera, dropdown Games i nawigacja po linkach.
3. **Lighthouse**: testy Performance, Accessibility, Best Practices i SEO, weryfikacja kontrastu oraz pełnej obsługi klawiaturą.
4. **Schema.org**: sprawdzić metadane po publikacji na docelowej domenie. Strona szczegółów produktu korzysta z parametru URL i danych demonstracyjnych; w produkcyjnym sklepie zalecane są statyczne adresy i indywidualne dane strukturalne dla każdego produktu.
5. **Kasa / sklep**: makieta nie realizuje prawdziwych płatności ani wysyłki — zgodnie z ćwiczeniem 5 jest statycznym demonstratorem ścieżki klienta.

### Ograniczenie kontroli

Środowisko uruchamiania Chromium zablokowało lokalne adresy błędem `ERR_BLOCKED_BY_ADMINISTRATOR`, dlatego nie potwierdzono wizualnie układu i nie uzyskano wyniku Lighthouse. Nie należy twierdzić, że projekt ma 100/100 punktów bez tych testów.


## Aktualizacja nawigacji i kart produktów (13.11.2026)
- Podstrona produktu używa teraz dokładnie wspólnego paska nawigacji `.aa-nav` z projektu głównego; usunięto odrębne, błękitno-gradientowe nadpisania nawigacji.
- Okładka produktu otwiera powiększony podgląd z efektem szkła, poświaty i refleksu; zamykanie przez X, kliknięcie tła lub Escape.
- Karty na stronie głównej są klikalne na całej powierzchni (z wyłączeniem przycisków i linków), również klawiaturą.
- Katalog `sklep.html` zawiera 15 gier i kieruje do właściwych podstron produktów; karty i okładki są klikalne.
- Filtry sklepu uwzględniają wszystkie kategorie z katalogu: Action, Adventure, RPG, Simulation, Strategy, Indie i Retro Classics.
- Dodano 11 grafik z dosłanego `assets.zip`.


## Korekta nawigacji, kart i dostępności (13.11.2026)
- Naprawiono `script.js`: obsługa kliknięcia kafelków była wcześniej błędnie zagnieżdżona wewnątrz obsługi `Add to cart`. Teraz inicjalizuje się niezależnie przy załadowaniu strony.
- Karty gier na stronie głównej i w katalogu sklepu prowadzą do właściwej podstrony kliknięciem w tło kafelka; linki i przyciski wewnętrzne zachowują własne działanie. Dodano obsługę Enter/Spacja.
- Ujednolicono zestaw ikon konta i koszyka po prawej stronie wspólnej nawigacji na wszystkich stronach, które mają główny pasek nawigacyjny.
- Dodano sticky navigation na stronie głównej (`index.html`) oraz na stronie pojedynczego wpisu (`single.html`).
- Dodano link „Skip to main content” widoczny po przejściu klawiaturą oraz wyraźne stany focus.
- Dodano obsługę `prefers-reduced-motion`, aby ograniczyć animacje, gdy użytkownik ma ustawioną preferencję ograniczenia ruchu.
- Zachowano istniejące animacje Frutiger Aero, filtry, koszyk i podstrony produktów.
