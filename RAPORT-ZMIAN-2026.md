# Aqua Arcade — aktualizacja zgodności z wytycznymi RWD

## Wykonane zmiany
- Rozbudowano `index.html` o obowiązkowe sekcje `#hero`, `#o-nas`, `#oferta`, `#blog`, `#kontakt`, zachowując sklep i istniejący układ graficzny.
- Dodano trzy kompletne zajawki blogowe (grafika, kategoria, data, tytuł, lead, odnośnik) oraz wezwanie do przejścia do archiwum.
- Dodano dwukolumnową prezentację inicjatywy, trzy karty obszarów oferty, dane kontaktowe i formularz przygotowywania wiadomości.
- Dodano skróty-kotwice sekcji w nawigacji głównej oraz przycisk hero do kontaktu.
- Naprawiono w 20 podstronach odnośnik `kontakt.html#contact-form` na `kontakt.html#formal-contact-form`.
- Zachowano alias kotwicy `#featured` dla starych odnośników.
- Scalono dodatkowe arkusze CSS do `style.css` z komentarzami źródłowymi; wszystkie podstrony używają wspólnego pliku.
- Dodano reguły mobile-first dla nowych elementów, widoczne focusy i wsparcie preferencji ograniczonego ruchu.
- Uzupełniono opisy alternatywne ilustracji treściowych; oznaczono graficzne dekoracje.
- Naprawiono odwołania do nieistniejącego pliku `assets/game-ocean.jpg` przez użycie istniejącego `assets/game-oceanlife.jpg`.
- Dodano podstawowe dane strukturalne `Organization` do strony głównej.
- Formularz na stronie głównej nie wysyła danych: demonstruje walidację i próbuje skopiować treść do schowka. Nie jest podłączony do serwera.

## Kontrole statyczne
- 20 plików HTML: po jednym `h1` oraz `main` na każdej stronie.
- Wszystkie lokalne odwołania do plików i kotwic HTML: zweryfikowane skryptowo.
- Kontrola etykiet `label[for]` i identyfikatorów `id`: bez wykrytych braków.
- Składnia wszystkich bloków JSON-LD poprawna w parsowaniu JSON (to **nie** zastępuje walidacji Schema.org).
- Składnia plików JavaScript: `node --check` bez błędów.

## Ograniczenia oraz zadania przy odbiorze
- Nie przeprowadzono skutecznego testu renderowania w Chromium/DevTools: środowisko uruchomieniowe zablokowało wczytywanie lokalnej strony również przez lokalny serwer. Należy sprawdzić 360, 390, 768 i 1200 px, poziomy scroll, menu rozwijane, formularze, checkout i Lighthouse w zwykłej przeglądarce.
- Projekt jest demonstracją, bez działającego backendu sprzedaży, newslettera czy wysyłki e-mail; danych kontaktowych nie należy traktować jako realnych.
- Karta Projektu zawierająca deklarację autorów, barw i fontów nie została dołączona. Spójności z tą deklaracją i oceny formalnej nie da się potwierdzić bez dokumentu.
- Ćwiczenie 3 dotyczące *sympozjum „Retrotechnika i Przyszłość Danych”* stanowi oddzielne zadanie laboratoryjne testowania generatorów i nie zostało wdrożone jako sekcja serwisu Aqua Arcade, ponieważ dotyczy innego podmiotu. Implementowano wymogi bazowego serwisu z `RWD_CW_3_2.md` oraz etapów 4–6.
