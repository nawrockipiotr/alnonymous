# DocAnon Tool — Alnonymous

Narzędzie przeglądarkowe do lokalnej anonimizacji dokumentów. Rozwijane w Centre for Socially Responsible Innovations (CSRI), Wydział Zarządzania, Uniwersytet Warszawski.

Jedna strona HTML, zero instalacji, zero zależności serwerowych — otwarcie w przeglądarce lub hosting na GitHub Pages. Wszystkie operacje wykonywane lokalnie w przeglądarce. Żadne dane nie opuszczają komputera użytkownika.

## Funkcje

| Funkcja | Opis |
|---------|------|
| **Detekcja encji** | Automatyczne rozpoznawanie danych osobowych, identyfikatorów i wrażliwych informacji w tekście polskim |
| **Anonimizacja** | Zamiana wykrytych encji na etykiety kategoryzowane (np. [OSOBA_1], [PESEL_1]) |
| **Podgląd PDF** | Overlay z zamaskowanymi danymi na oryginalnym układzie PDF (side-by-side) |
| **Eksport** | Tekst zanonimizowany, mapowanie encji (JSON), dokument DOCX, zamaskowany PDF |
| **Przywracanie** | Odtworzenie oryginalnych danych z mapowania encji |
| **Dwujęzyczność** | Interfejs PL/EN z lokalizowanymi etykietami encji |

## Rozpoznawane typy encji

| Typ | Walidacja |
|-----|-----------|
| PESEL | Walidacja sumy kontrolnej (11 cyfr) |
| NIP | Walidacja sumy kontrolnej (10 cyfr) |
| KRS | 8–10 cyfr po etykiecie |
| REGON | 9 lub 14 cyfr po etykiecie |
| Nr dowodu osobistego | 3 litery + 6 cyfr |
| Konto bankowe | 26 cyfr, format IBAN |
| Telefon | +48 i kontekstowe (tel., nr telefonu) |
| E-mail | Standardowy format |
| Osoby | Imiona i nazwiska — słownik ~90 imion polskich z odmianami (6 przypadków), wykrywanie w kontekście relacyjnym |
| Organizacje | Spółki (z o.o., S.A., sp.k., sp.j.), fundacje, stowarzyszenia |
| Adresy | Ulice (z odmianami: ul./ulicy/ulicą), kody pocztowe, miasta po przyimkach |
| Daty | Format słowny (1 stycznia 2024 r.) i numeryczny (01.01.2024) |
| Kwoty | Wartości z walutą (zł, PLN, EUR, USD) |

## Obsługiwane formaty wejściowe

TXT, DOCX, PDF. Drag & drop lub kliknięcie w strefę uploadu.

## Architektura

| Plik | Funkcja |
|------|---------|
| `alnonymous.html` | Cała aplikacja — single-file HTML z wbudowanym CSS i JS |

Biblioteki CDN: Lucide Icons, mammoth.js (DOCX→tekst), pdf.js (PDF→tekst), docx (eksport DOCX), jsPDF (eksport PDF).

## Hosting

GitHub Pages: https://nawrockipiotr.github.io/alnonymous/

Repo: https://github.com/nawrockipiotr/alnonymous

Alternatywnie: otwarcie `alnonymous.html` bezpośrednio w przeglądarce (po załadowaniu CDN działa offline).

## Prywatność

Wszystkie operacje przetwarzania tekstu wykonywane są lokalnie w przeglądarce użytkownika. Narzędzie nie wysyła żadnych danych na zewnętrzne serwery. Jedyne połączenia sieciowe to ładowanie bibliotek CDN i fontów Google przy pierwszym otwarciu strony. Weryfikacja: narzędzia deweloperskie przeglądarki → zakładka Network.

## Licencja

MIT

## Autor

Piotr Nawrocki — Centre for Socially Responsible Innovations (CSRI), Wydział Zarządzania, Uniwersytet Warszawski
