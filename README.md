# T60 SZUKAJ

Wyszukiwarka modeli STEP → TRIGGER → zakład dla ciągu **Test60**. Osobna appka obok **T60 RAZEM**
(własny adres, ikona i instalacja; nie otwiera się w oknie RAZEM).

Adres: **https://px5060.github.io/szukaj60/**

- **Kody** są wspólne z T60 RAZEM (ta sama domena, klucz `t60razem_v1_added`): kod wpisany tu widać w RAZEM i odwrotnie.
  Import pliku eksportu z RAZEM: zakładka SZUKAJ → Import kodów.
- **GRA**: modele w kryteriach (do 200 cykli max 5 BUST, do 300 max 9, do 400 max 11, ponad 400 max 11) na krokach
  64 / 128 / 256 zł, w grupach wg liczby cykli; modele ponad 400 cykli (złota obwódka) tylko gdy są na kroku gry.
- **TABELA**: wybrany model naniesiony na ciąg kodów (STEP, TRIGGER, zakład, WIN / BUST) + statystyki
  (ostatni BUST, 2 BUST-y pod rząd, …) i przycisk **Gram ten model** → MOJE GRY (prowadzenie do WIN albo kroku 8).
- **SZUKAJ**: kryteria, stan puli z chmury, import kodów. Szukania w telefonie nie ma — modele są te same na każdym urządzeniu.
- **⇢ do T60 RAZEM**: w oknie statystyk modelu (przytrzymaj kartę) przycisk „⇢ Dodaj do T60 RAZEM — zakładka SZUKAJ”: model trafia do tabeli SZUKAJ w T60 RAZEM (GRA, TABELA, STATY, MOJE GRY, MOJE ZAKŁADY). Ten sam przycisk usuwa.
- **▶ moje → gry / busty** i **BUST** (wiersz „cykle:”): w „▶ moje” podzakładki „gry” (karty moich modeli) i „busty” (BUST-y moich modeli od dodania); przycisk BUST — modele, które przed BUST-em spełniały kryteria (proponowane do gry) i przegrały krok 8, okresy rozłączne: ostatnie 20 wierszy albo wiersze 21–40 od końca, wg wybranego przedziału cykli; „po BUST” — modele w kryteriach w cyklu zaraz po BUST-cie z ustawionym zakładem (GRA na następnym wierszu, potem zakład za 2–3 wiersze — dalsze nie są pokazywane); wszystkie okresy BUST (ostatnie 20 w., 21–40 w., po BUST) są podpięte pod filtr „krok:” — widać tylko modele, których bieżący krok jest zaznaczony, a liczby przy krokach liczą modele z listy BUST; pod okresami informacja, ile modeli filtr chowa (w tym na 8 zł, k1–k2 zaraz po BUST-cie); „moje · busty” bez filtra; ✕ na karcie wyrzuca model z listy (wraca przy jego kolejnym BUST-cie), „przywróć wyrzucone” cofa; dotknięcie → TABELA na wierszu BUST-u.

## Pliki

```
index.html            appka (generowana — nie edytować ręcznie)
szukaj.webmanifest    PWA (zakres ./)
szukaj-sw.js          service worker: strona zawsze z sieci
szukaj-192/512.png    ikony
szukaj/               narzędzia: silnik, szukanie puli, budowanie (szukaj/README.md)
```

Przebudowa: `cd szukaj && python3 build_szukaj.py t60`. Nowa pula (miliony modeli, wymaga numba):
`python3 search.py t60 x1x 6000000 21 --dolacz` (dla T60 także `xx1`), potem build.
Baza ciągu: `szukaj/seed_t60.txt` (MASTER_SEED z T60 RAZEM), dopisane kody PC: `szukaj/dopisane.txt`.
