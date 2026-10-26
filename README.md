# Půjčená kniha, 1980

Interaktivní rozhodovací příběh o samizdatu pro studenty gymnázia. Hráč je sedmnáctiletý student, kterému soused v listopadu 1980 půjčí zakázaný strojopis Orwellova románu *1984*. Rozhoduje, jestli knihu vezme, opíše, půjčí dál a co řekne při výslechu.

**Hrát online:** `https://<uzivatel>.github.io/<repozitar>/`

Příběh vznikl jako jedna z úvodních aktivit školního projektu k nedožitým 90. narozeninám Václava Havla, ve kterém studenti modelují šíření samizdatu v Insight Makeru.

## Co stránka obsahuje

- **Větvený příběh** s 13 rozhodovacími scénami a 7 různými konci. Žádný konec není „správný“.
- **Ukazatele** – během hry se počítají vzniklé kopie, čtenáři a pozornost StB (0–5).
- **Historické poznámky** – u každého konce sekce *Jak to bylo doopravdy*.
- **Otázky pro model** – u každého konce sekce *Pro model* s obecnou otázkou k modelování šíření (vhodné pro modely s toky a zásobníky i pro agentní modely).
- **Tvoje cesta** – přehled rozhodnutí, která hráč udělal.
- **Objevené konce** – stránka si v prohlížeči pamatuje nalezené konce (`localStorage`). Bez něj funguje také, jen si je nepamatuje.

| Konec | Jak k němu vede cesta (zkráceně) |
| --- | --- |
| Opatrnost | Knihu odmítneš. |
| Vrácená kniha | Knihu přečteš a vrátíš. |
| Ztracená kopie | Půjčíš ji dál a stopa se ztratí. |
| Krok zpět | Z opisování vycouváš. |
| Jméno | Při výslechu prozradíš, kdo ti knihu dal. |
| Mlčení | Při výslechu mlčíš. |
| Opisovač | Přidáš se k síti opisovačů. |

## Použití ve výuce

Doporučená délka: 5–10 minut, ideálně jako jedno ze stanovišť úvodní dvacetiminutovky o samizdatu.

1. Studenti projdou příběh alespoň dvakrát a najdou dva různé konce.
2. Zapíší si čísla z ukazatelů (kopie, čtenáři, riziko) a jednu otázku ze sekce *Pro model*.
3. Zjištění přinesou do společného brainstormingu, kde se třídí podle otázek: jak se samizdat šířil, co ho brzdilo a proč to lidé dělali.

Postavy jsou smyšlené. Historické poznámky popisují, jak podobné situace v Československu za normalizace probíhaly; před použitím je doporučeno je ověřit (např. [Paměť národa](https://www.pametnaroda.cz), [Libri prohibiti / Scriptum](https://www.scriptum.cz)).

## Úprava příběhu

Celá hra je jeden soubor `index.html` bez závislostí (kromě písem z Google Fonts). Obsah je v JavaScriptu na konci souboru:

- `ENDINGS` – názvy konců (klíč → název).
- `S` – scény. Každá scéna má `place`, `text` (pole odstavců), volitelně `quote` a `choices`.
- Volba: `{ t: "text tlačítka", go: "id_další_scény", fx: { copies, readers, risk }, log: "záznam do cesty" }`.
- Konec: `{ ending: true, place, text, real: "Jak to bylo doopravdy", sim: "Pro model" }`.

Nový konec přidáte tak, že ho zapíšete do `ENDINGS` i do `S` a odkážete na něj z některé volby. Počet konců v hlavičce („sedm různých konců“) a v počítadle (`/ 7`) je potřeba upravit ručně.

## Hosting na GitHub Pages

1. Nahrajte `index.html` (a tento `README.md`) do kořene repozitáře.
2. V **Settings → Pages** zvolte *Deploy from a branch*, větev `main`, složku `/ (root)`.
3. Po minutě je stránka dostupná na `https://<uzivatel>.github.io/<repozitar>/`.

## Licence

Doplňte podle potřeby, např. [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.cs) pro text a MIT pro kód.
