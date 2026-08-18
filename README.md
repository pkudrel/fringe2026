# Fringe 2026 — przeglądarka spektakli

Prosta, statyczna strona do przeglądania programu **Edinburgh Festival Fringe 2026** i układania własnego planu. Bez backendu — działa na GitHub Pages i lokalnie.

**Na żywo:** https://pkudrel.github.io/fringe2026/

## Co potrafi

- **Wyszukiwarka** — tytuł, wykonawca, miejsce, gatunek
- **Filtry** — dzień (całe okno 17–22 albo konkretny), gatunek, tylko TOP ★, tylko darmowe, tylko w planie
- **Sortowanie** — klik w nagłówek kolumny (godzina sortuje chronologicznie)
- **Kolumna „W planie ✔"** — Twój roboczy plan; zapisuje się lokalnie w przeglądarce (`localStorage`)
- **💾 Zapisz plan / 📂 Wczytaj plan** — eksport/import planu jako `moj_plan.json` (przenośny między urządzeniami)
- **TOP ★** — spektakle typowane przez krytykę (4–5★); dodatkowe ręczne rekomendacje w `EXTRA_TOP` w `index.html`

## Pliki

| Plik | Rola |
|---|---|
| `index.html` | Prezentacja (mała) — cały interfejs i logika |
| `fringe_data.js` | Dane — `window.FRINGE_DATA = [...]` (spektakle grające 17–22 sierpnia) |

Oba muszą leżeć **w tym samym katalogu** (root repo). `index.html` ładuje `fringe_data.js` ścieżką względną.

## Uruchomienie

- **Online:** GitHub Pages (Settings → Pages → Deploy from a branch → `main` / `/root`).
- **Lokalnie:** ze względu na ograniczenia `file://` w niektórych przeglądarkach, dwuplikowa wersja najlepiej działa serwowana (Pages) lub przez lokalny serwer (`python -m http.server`). Wersja jednoplikowa z danymi w środku otwiera się też prosto z dysku.

## Dane i zastrzeżenia

Dane pochodzą z oficjalnego programu Fringe 2026 (wersja drukowana). **Godziny i ceny mogły się zmienić** — ostateczne informacje i zakup biletów tylko w oficjalnej aplikacji **EdFringe** / na edfringe.com. Ceny zawierają opłatę £1.50 Fringe Box Office. Parser jest heurystyczny, więc przy ~2500 pozycjach mogą trafić się drobne nieścisłości.
