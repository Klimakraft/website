# KlimaKraft – strona www

Statyczna strona (HTML + CSS, bez JavaScriptu, bez cookies) pod GitHub Pages.

## Struktura

```
index.html                    Strona główna        → /
uslugi/index.html             Usługi               → /uslugi/
kontakt/index.html            Kontakt              → /kontakt/
polityka-prywatnosci/         Polityka prywatności → /polityka-prywatnosci/
404.html                      Strona błędu
assets/css/style.css          Wszystkie style (kolory w :root na górze pliku)
assets/fonts/                 Montserrat + Source Sans 3 (lokalnie, licencja OFL)
assets/img/                   Logo, zdjęcie hero, obraz do udostępnień (OG)
robots.txt, sitemap.xml       Dla wyszukiwarek
```

## 1. Zanim wrzucisz na GitHuba – do uzupełnienia

1. **Domena** – w całym projekcie zamień `https://TWOJA-DOMENA.pl` na swój adres
   (np. w VS Code: Ctrl+Shift+H). Występuje w plikach `.html`, `robots.txt` i `sitemap.xml`.
2. **Zdjęcie** – podmień `assets/img/montaz-klimatyzacji.webp` (1600×1200 px)
   i `assets/img/montaz-klimatyzacji-800.webp` (800×600 px) na własne zdjęcie z realizacji,
   zachowując nazwy plików.
3. **Placeholdery** – wyszukaj `[do uzupełnienia]`: NIP (stopka), godziny pracy
   (strona główna, kontakt), dane w polityce prywatności.

## 2. Publikacja na GitHub Pages

1. Utwórz repozytorium na GitHubie (na darmowym planie musi być publiczne).
2. Wgraj zawartość tego folderu do głównego katalogu repozytorium (plik `index.html` w korzeniu).
3. **Settings → Pages → Build and deployment**: Source „Deploy from a branch”,
   branch `main`, folder `/ (root)` → Save.
4. Po chwili strona działa pod `https://<login>.github.io/<repozytorium>/`.

## 3. Własna domena

1. **Settings → Pages → Custom domain**: wpisz np. `www.twojadomena.pl` → Save
   (GitHub sam utworzy plik `CNAME`).
2. U rejestratora domeny ustaw DNS:
   - `www` → rekord **CNAME** na `<login>.github.io`
   - domena główna (`@`) → cztery rekordy **A**:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
3. Po propagacji DNS zaznacz **Enforce HTTPS**.

Aktualne adresy IP sprawdzisz w dokumentacji GitHub Pages („Managing a custom domain”).

## 4. SEO po publikacji

1. **Google Search Console** – dodaj domenę i zgłoś `https://twojadomena.pl/sitemap.xml`.
2. **Profil Firmy w Google** – załóż jako firmę z obszarem działania (Kraków, Wieliczka,
   Skawina), bez publicznego adresu. Nazwa, telefon i e-mail muszą być identyczne jak na stronie.
3. Test danych strukturalnych: https://search.google.com/test/rich-results

## Uwagi techniczne

- Linki między stronami są względne – strona działa zarówno pod domeną, jak i pod adresem
  `github.io`. Wyjątek: `404.html` używa ścieżek od korzenia, więc wygląda poprawnie
  dopiero pod własną domeną.
- Czcionki są hostowane lokalnie (bez Google Fonts), strona nie ustawia cookies
  i nie wymaga banera zgody.
- Kolory marki są w zmiennych CSS na początku `assets/css/style.css`.
