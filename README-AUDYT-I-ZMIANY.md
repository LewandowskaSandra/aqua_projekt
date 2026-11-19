# Aqua Arcade — uzupełnienia ćwiczeń 4–6

Podstawą zmian jest archiwum **aqua bar.zip** oraz wymagania z **responsive web design.zip**. Zachowano dotychczasowe pięć podstawowych widoków i układ wizualny sklepu. Nowe sekcje wykonano w systemie stylistycznym Aqua Arcade.

## Zmiany

### Ćwiczenie 4 — blog
- `blog.html`: 7 kart artykułów, sekcja główna + panel boczny z wyszukiwarką, kategoriami i licznikami, rekomendacjami oraz działająca paginacja 1–3.
- `index.html`: 3 zajawki wpisów w dotychczasowym panelu bloga; dodano daty, kategorie, leady i odnośniki do artykułów.
- `single.html`: artykuł Frutiger Aero zachowuje oryginalną treść i styl; pozostałe wpisy dostępne w tym samym szablonie przez `single.html?post=...` z indywidualnymi nagłówkami, treścią i zdjęciami (`site-enhancements.js`).
- Do popularnych i powiązanych wpisów dodano odpowiednie linki.

### Ćwiczenie 5 — sklep
- `sklep.html`: dodano aktywną paginację wyników (6 na stronę), przykładowe ceny przekreślone przy wybranych pozycjach. Sortowanie i filtry współdziałają z paginacją.
- `produkt.html`: dodano oceny demonstracyjne, zakładki Bootstrap (opis/specyfikacja/opinie) i 3 rekomendacje; zachowano wcześniejszy układ galerii i panelu zakupu.
- `index.html`: przy czterech grach dodano gwiazdki jako oznaczone oceny demonstracyjne.

### Ćwiczenie 6 — architektura serwisu
- `kontakt.html`: breadcrumb, dane demonstracyjne, rozbudowany formularz kontaktowy ze zgodą i mapą wyraźnie opisaną jako przykładowa.
- `polityka-prywatnosci.html`: jednostronicowy dokument z czterema wymaganymi sekcjami oraz responsywną tabelą.
- `404.html`: wyszukiwarka oraz przyciski prowadzące do strony głównej, sklepu i kontaktu.
- Wszystkie 13 stron otrzymało spójną 4-kolumnową stopkę z odnośnikami, formularzem zapisu demo i sub-footerem.
- Menu kontaktu wskazuje formalną stronę `kontakt.html`. Starsza wersja `contact.html` jest zachowana.
- Uzupełniono podstawowe metadane SEO i JSON-LD stron pomocniczych.

## Demonstracja, nie produkcja
Aqua Arcade to fikcyjna marka w projekcie studenckim. Formularze kontaktowe i newsletterowe są demonstracyjne i nie wysyłają danych. Podane dane kontaktowe, mapę i informację o rejestracji oznaczono jako ilustracyjne. Przed uruchomieniem rzeczywistej działalności należy podać prawdziwego administratora danych i zweryfikować dokumentację prawną, cookies, dostawców zewnętrznych oraz informacje o produktach.

## Kontrola kodu
- 13/13 plików HTML: dokładnie jeden `<h1>`.
- Lokalne ścieżki plików HTML/CSS/JS/obrazów oraz kotwice: kontrola statyczna bez brakujących celów.
- JSON-LD: poprawna składnia JSON.
- JavaScript: skrypty przechodzą `node --check`.
- Wszystkie pola formularzy mają nazwy dostępne dla czytników ekranu (etykiety lub `aria-label`).

## Testy, które pozostają do wykonania
Automatyczny Chromium w tym środowisku blokuje zarówno `file://`, jak i `localhost` (ERR_BLOCKED_BY_ADMINISTRATOR); **nie dokonano weryfikacji wizualnej**, ani nie wykonano Lighthouse. W Chrome DevTools sprawdź 360, 390, 768, 1200 i 1440 px, menu mobilne, brak poziomego przewijania, formularze, przyciski kart, filtry sklepu, paginację bloga i sklepu, działanie zakładek oraz linki 404. Uruchom Lighthouse (Accessibility, Best Practices, SEO) i validator.schema.org.

Uruchamianie: rozpakuj ZIP i otwórz `index.html` (przy funkcjonalnościach zależnych od lokalnych zasobów najlepiej przez Live Server). `404.html` będzie automatycznie obsługiwać nieistniejące adresy dopiero na odpowiednio skonfigurowanym serwerze, np. GitHub Pages.
