# Aqua Arcade — poprawki RWD i a11y

## Wersja mobilna
- Do 991 px: przycisk hamburger po prawej stronie logo AQUA ARCADE; pod spodem wspólny panel PLAYER 01 + koszyk. Menu Bootstrapa rozwija się w osobnym panelu poniżej nagłówka.
- Do 767 px: jedna kolumna dla kart gier, sekcji promocyjnych, treści About i Contact, filtrów bloga oraz artykułów.
- Przy 768 px: układ tabletowy, dwie karty produktów w rzędzie; inne sekcje pozostają elastyczne.
- Desktop: zachowane istniejące odstępy i stylistyka.

## Weryfikacja statyczna
- Wszystkie pięć plików ma jeden H1, viewport, meta description, OG i JSON-LD.
- Menu wspólne i odnośniki lokalne sprawdzone.
- Unikalne ID i etykiety pól sprawdzone.
- Usunięto duplikat ID koszyka na stronie głównej.
- Linki demonstracyjne logowania i niezdefiniowanych social mediów zamieniono na nieklikalne oznaczenia, aby uniknąć martwych odnośników.
- Link FAQ w stopce prowadzi teraz do sekcji FAQ.

## Ważne: testy przed oceną
Test w Chrome DevTools: 360, 390, 768 i 1200 px, poziome przewijanie, menu hamburger, koszyk, formularze i Lighthouse. Środowisko wykonawcze blokowało uruchamianie lokalnych stron w Chromium (ERR_BLOCKED_BY_ADMINISTRATOR), więc nie deklarujemy zaliczenia testów wizualnych ani wyniku Lighthouse.

Bootstrap 5 jest ładowany z CDN. Pełny wygląd i menu wymagają połączenia z internetem. Konto, koszyk i komentarze pozostają funkcjami demonstracyjnymi.
