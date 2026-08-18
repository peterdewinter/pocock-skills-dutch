## Wat het doet

`grill-me` neemt een **vaag idee** en ondervraagt je tot je je eraan kunt vastleggen. Je hebt geen uitgewerkt plan nodig om te starten — dat plan produceren is net waar de [sessie](https://www.aihero.dev/ai-coding-dictionary/session) voor dient. Het vraagt in **rondes**: elke ronde is de volledige **frontier** — elke vraag waarvan je de voorwaarden al beslecht hebt — zodat je nooit iets gevraagd wordt dat afhangt van een antwoord dat het nog niet gehoord heeft.

Het is **[stateless](https://www.aihero.dev/ai-coding-dictionary/stateless)**. Het schrijft geen bestanden en laat geen workspace achter. Het enige wat het achterlaat, is een scherpere versie van het idee, in je eigen hoofd.

## Wanneer je ernaar grijpt

Je roept dit op door `/grill-me` te typen — de [agent](https://www.aihero.dev/ai-coding-dictionary/agent) grijpt er niet uit zichzelf naar. Start het in een **verse conversatie**, niet bovenop een plan dat je al door een agent liet schrijven.

Grijp ernaar zodra je een idee hebt dat het waard is om serieus te nemen — een feature, een productrichting, een businessbeslissing, een stuk tekst — en lang voordat je hebt uitgezocht wat het allemaal inhoudt. Vaagheid is geen reden om te wachten; het is net waar de sessie van leeft. Als je het ding al precies kunt specificeren, hoef je het niet te grillen.

Welke van de drie grill-skills je nodig hebt, hangt af van wat er voor je ligt:

- **Om het even wat, om het even waar** — `grill-me`. Het heeft geen repo nodig en schrijft geen bestanden, en het onderwerp hoeft geen code te zijn.
- **Een codebase om je tegen af te stemmen** — [grill-with-docs](https://aihero.dev/skills-grill-with-docs). Hetzelfde interview, maar [stateful](https://www.aihero.dev/ai-coding-dictionary/stateful): het leest je code en bewaart wat het leert in `CONTEXT.md` en ADR's.
- **Te groot voor één sessie** — [wayfinder](https://aihero.dev/skills-wayfinder). Het brengt het werk in kaart en draait er grill-sessies binnenin.

Laat [plan mode](https://www.aihero.dev/ai-coding-dictionary/agent-mode) uit. Plan mode zet de agent aan om naar een plan toe te haasten, en dat is het tegenovergestelde van in onderzoeksmodus blijven.

## Het is een gesprek, geen interview

De skill stelt de vragen, maar **jij** bent eigenaar van de scope. Dat is het deel dat mensen missen, en het scheidt een sessie die een idee in beslissingen omzet van een sessie die zelfverzekerde onzin oplevert.

De faalmodus is **passiviteit** — veertig vragen lang "akkoord, akkoord, akkoord" antwoorden en eruit komen met een plan dat de agent schreef en jij hebt beaamd. Het voelt productief omdat het lang duurde. Er is niets echt beslist, en het resultaat draagt een zekerheid die het niet verdiend heeft.

Actief zijn betekent sturen. Duw terug bij een vraag die onder het detailniveau zit dat je nodig hebt. Zeg het wanneer de scope afdrijft. Antwoord "ik weet het niet" en meen het. Deze skill is gebouwd om een engineer te helpen, niet om er een te vervangen: wat eruit komt, volgt de kwaliteit van je antwoorden, niet het aantal gestelde vragen.

De omgekeerde fout bestaat ook, maar is zeldzamer — zo lang in het interview blijven dat je nooit tot code komt.

## Grillbaar en niet-grillbaar

Sommige vragen kun je al pratend beantwoorden. Andere niet, en geen hoeveelheid grillen brengt je daar.

"Eén lang formulier of drie pagina's?" en "hoe moet deze interactie aanvoelen?" zijn **niet-grillbaar** — die hebben iets nodig om op te reageren. Wanneer je er zo een tegenkomt, stop met grillen. Bouw de wegwerpversie met [prototype](https://aihero.dev/skills-prototype), bekijk ze, en kom dan terug om in één lijn te antwoorden.

Je een weg praten door een niet-grillbare vraag is waar sessies ontsporen. De agent blijft herformuleren, jij blijft gokken, en de scope groeit tot ze de onzekerheid opvult.

## Het werkt als

- Je het ergens niet mee eens bent. Een sessie zonder tegenspraak van jou is een sessie die je niet nodig had.
- Vragen in enkele rondes binnenkomen in plaats van in één lang druppelspoor, en latere rondes duidelijk voortbouwen op wat je eerder zei.
- Je ergens uitkomt waar je het niet verwachtte, omdat een vraag een beslissing blootlegde die je impliciet aan het nemen was.
- Je op het einde elke keuze zou kunnen verdedigen tegenover iemand die er niet bij was.

## Veelgestelde vragen

**Hoeveel vragen mag ik verwachten, en hoe weet ik wanneer het eindigt?**
Tel rondes, geen vragen. Zesenveertig vragen verspreid over vier rondes is een doodgewone sessie. Het eindigt wanneer de frontier leeg is — elke tak bezocht, niets nog stilzwijgend aangenomen.

**Het stelde me tweehonderd vragen. Wat ging er mis?**
Meestal was de scope te groot. Vraag de agent om het werk eerst in kleinere stukken te knippen en gril die dan één voor één. Erg lange sessies drijven ook af naar de **[dumb zone](https://www.aihero.dev/ai-coding-dictionary/smart-zone)**, waar het [context window](https://www.aihero.dev/ai-coding-dictionary/context-window) vol genoeg zit om de vragen slechter te maken.

**Kan ik terug naar één vraag per keer?**
Ja. Voeg dit toe aan je globale `CLAUDE.md`:

```
When grilling, ask one question at a time.
```

**Wat als ik het antwoord echt niet weet?**
Zeg dat. "Ik weet het niet" is een echt antwoord, en een vraag die je niet kunt beantwoorden is meestal een teken om te prototypen in plaats van te gokken.

**Start ik een verse sessie voor ik de spec schrijf?**
Nee. De waarde van de sessie is de [context](https://www.aihero.dev/ai-coding-dictionary/context) die je net hebt opgebouwd. Geef dezelfde conversatie rechtstreeks door aan [to-spec](https://aihero.dev/skills-to-spec).

**Maakt het model uit?**
Meer dan bij de meeste skills. Grillen leunt op het eigen aanvoelen van het [model](https://www.aihero.dev/ai-coding-dictionary/model) van hoe systemen stukgaan, dus geef het je beste. Implementatie volgt vooral de context en verdraagt een goedkoper model.

## Waar het past

`grill-me` is een **standalone die je overal en op alles kunt draaien**. Stateless zijn is wat het draagbaar maakt: geen repo, geen workspace, geen setup, en geen aanname dat het idee überhaupt over software gaat. Mensen richten het op businessbeslissingen, op teksten, op wat ze nu moeten doen — op alles wat niet wil stilzitten in hun hoofd.

Die draagbaarheid is het hele verschil met [grill-with-docs](https://aihero.dev/skills-grill-with-docs), dat hetzelfde interview draait maar een codebase leest om zich tegen af te stemmen en vastlegt wat het leert in `CONTEXT.md` en ADR's. Beide steunen op het [grilling](https://aihero.dev/skills-grilling)-primitief; `grill-me` is de door de gebruiker opgeroepen voordeur die niets met zich meedraagt.

Als wat je gegrild hebt toch software blijkt te zijn, kun je dezelfde conversatie doorgeven aan [to-spec](https://aihero.dev/skills-to-spec) en verder gaan in de build-flow — een optie, niet het punt van de skill. Wanneer je niet zeker weet welke flow past, wijst [ask-matt](https://aihero.dev/skills-ask-matt) je de weg.
