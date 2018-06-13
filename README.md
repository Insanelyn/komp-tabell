# Komplettering till tentamen i kurs JavaScript med jQuery - EMMFEH17.

Datum: 2018-06-21

## Förberedelse

Skapa ett nytt repo på Github med namnet _komp-tabell_. 

Klona repot och kopiera innehållet i mappen `contents` -- bara filen index.html -- till det klonade repot.

### Inlämning

När kompletteringen är färdig för inlämning:

*   _add + commit + push_ alla ändringar i ditt repo till Github. 
*   Skapa en tag för repot (= lås kompletteringsuppgiften) så här:

    git tag submitted
    git push origin --tags

## Beskrivning

Bygg vidare på filen `index.html`:

* Lägg till en knapp med texten "add".
* Om man trycker på knappen ska en ny tabellrad skapas sist i tabellen.
* Tabellraden ska ha två kolumner:
    * Den första kolumnen ska innehålla ett heltal: 1 första gången man trycker, 2 andra gången, 3 tredje gången, osv.
    * Den andra kolumnen ska innehålla en knapp med texten "remove".
* Om man trycker på en "remove"-knapp på en rad i tabellen så ska den raden tas bort.

I animationen `table-rows.gif` (bifogad) kan du se hur resultatet bör se ut.

I det här fallet är det inte helt nödvändigt, men kom ihåg att det ofta är bra att tydligt separera modell (JS) och vy (HTML).

Det finns två sätt att ge varje remove-knapp rätt beteende så att den tar bort sin egen rad och inget annat:

- Man kan skapa en unik click-callback för varje knapp och registrera den i samband med att man lägger till knappen på sin plats i tabellen. Denna callback har genom "closure" tillgång till rätt information så att den kan ta bort rätt tabellrad.

- Man kan registrera en enda lyssnare på (till exempel) tabellen som helhet, men lyssna på click-events på knappar. (Så kallad "event delegation".) I den lyssnarens callback kan man hitta den tabellrad som är närmast knappen, och ta bort den.

Det finns fördelar och nackdelar med båda de här sätten. I en kommentar i `index.html`, beskriv någon av skillnaderna (snabbare? enklare? tar mindre minne?).
