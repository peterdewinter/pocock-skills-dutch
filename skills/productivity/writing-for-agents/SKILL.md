---
name: writing-for-agents
description: Documenten schrijven voor agents. Te gebruiken bij het maken of bewerken van skills, of bij het aanpassen van AGENTS.md of CLAUDE.md.
---

Naslagwerk voor het schrijven van elk document dat een agent verbruikt — een vaardigheid, een `AGENTS.md` / `CLAUDE.md`, of een document dat via een verwijzing van hieruit wordt bereikt. De verpakking verschilt; het schrijven niet: dezelfde hefbomen maken elk document voorspelbaar — waarbij de agent elke uitvoering hetzelfde _proces_ doorloopt, in plaats van dezelfde output produceert.

Wanneer het document dat je schrijft een vaardigheid is, lees dan [`SKILL-MECHANICS.md`](SKILL-MECHANICS.md) voor de frontmatter, de keuze van aanroep (invocation) en routeringsvaardigheden.

## Contextpointers (Context pointers)

Een **contextpointer** is een verwijzing die in de context van de agent leeft,  
die een stuk materiaal **buiten** die context benoemt en de **voorwaarde** codeert waaronder de agent dat materiaal moet bereiken. De beschrijving van een skill is zo’n pointer; een regel in `AGENTS.md` / `CLAUDE.md` die een document benoemt, eveneens. De _formulering_ van de pointer, en niet het doel ervan, bepaalt wanneer de agent het materiaal bereikt — en hoe betrouwbaar dat gebeurd. Een essentieel doel achter een **zwak geformuleerde pointer** veroorzaakt variatie: maak eerst de formulering scherper, en zet het materiaal alleen inline wanneer aanscherpen niet lukt.

Een pointer heeft twee taken — aangeven wat het materiaal is, en de **vertakkingen (branches)** opsommen die het bereiken ervan moeten aansturen (een vertakking is een specifiek geval dat het document afhandelt, zodat verschillende uitvoeringen verschillende paden doorlopen). Elk woord van een pointer die altijd is geladen, kost iets bij elke beurt, en daarom verdient deze een nog strengere snoei dan de hoofdtekst:

- **Plaats het belangrijkste woord vooraan (Front-load)** — de pointer bevindt zich op de plek waar deze zijn oproepend werk doet.
- **Eén trigger per vertakking.** Synoniemen die een enkele vertakking hernoemen zijn één vertakking die twee keer is geschreven; voeg ze samen en behoud alleen echt onderscheidende vertakkingen.
- **Schrap identiteit die de hoofdtekst al draagt.**

## De twee belastingen (The two loads)

Elk document en elke pointer die je toevoegt, verbruikt een van de twee budgetten:

- **Contextbelasting (Context load)** — de kosten van materiaal dat altijd is geladen in het venster van de agent: een regel in `AGENTS.md` / `CLAUDE.md`, een beschrijving van een skill, of iets dat bij elke beurt in de context staat en tokens en aandacht verbruikt, ongeacht of het wordt geactiveerd.
- **Cognitieve belasting (Cognitive load)** — de kosten voor de mens: welke documenten bestaan er en wanneer moet je elk document raadplegen. De mens is de index. Dit is geen kostenpost om te minimaliseren — het is de prijs van de menselijke agent; besteed dit waar menselijk oordeel ertoe doet, en verwijder het waar dat niet zo is.

Materiaal dat alleen via een pointer wordt bereikt, ontkomt aan de contextbelasting tegen de prijs van de eigen regel van de pointer; materiaal zonder enige pointer leunt volledig op de cognitieve belasting.

## Informatiehiërarchie

Een document is opgebouwd uit twee inhoudstypen — **stappen** (de geordende acties die de agent uitvoert) en **referentie** (definities, regels, feiten die op verzoek worden geraadpleegd) — die vrij met elkaar kunnen worden gemengd: alleen stappen (een recept), alleen referenties (de regels van een review, deze vaardigheid), of beide. D De kernbeslissing is waar elk onderdeel thuishoort op de **informatiehiërarchie**, een ladder gerangschikt naar hoe **onmiddellijk** de agent het materiaal nodig heeft:

1. **Stap in het bestand (In-file step)** — de primaire laag: wat de agent doet, in volgorde.
2. **Naslagwerk in het bestand (In-file reference)** — wordt geraadpleegd op verzoek. Vaak een legitiem plat niveau (elke regel van een review op één sport) — een prima opstelling, geen slecht teken.
3. **Openbaar gemaakte naslagwerken (Disclosed reference)** — naar buiten verplaatst naar een apart bestand, bereikt via een contextpointer, en alleen geladen wanneer de pointer wordt geactiveerd. Dit omvat een aanverwant bestand in dezelfde map tot volledig externe naslagwerken die overal kunnen staan en waarnaar elk document kan verwijzen.

Als je te weinig naar beneden verplaatst, zwelt de bovenkant op; als je te veel verplaatst, verberg je materiaal dat de agent daadwerkelijk nodig heeft. Die spanning is de hele beslissing.

**Progressieve openbaarmaking (Progressive disclosure)** is de beweging naar beneden op de ladder — uit het hoofdbestand en achter een pointer — zodat de bovenkant leesbaar blijft. Dit is niet primair een token-optimalisatie: het is de manier waarop de hiërarchie wordt beschermd. Vertakking is de schoonste test voor openbaarmaking: neem op wat elke vertakking nodig heeft, en verberg achter een pointer wat slechts door sommige vertakkingen wordt bereikt. Wanneer een document stappen bevat, begraaft in-file naslagwerk dat openbaar gemaakt zou moeten worden deze stappen, waardoor het opvolgen ervan verandert in een muntjesspel — een hefboom voor variantie, en niet alleen voor leesbaarheid.

**Co-locatie (Co-location)** is de metgezel binnen het bestand: waar de ladder beslist _hoe ver naar beneden_ een stuk zich bevindt, beslist co-locatie _wat er naast staat_ zodra het daar is. Houd de definitie, regels en kanttekeningen van een concept onder één kop in plaats van verspreid, zodat het lezen van het ene deel de buren meebrengt. De test: het document moet lezen als documentatie geschreven voor de agent — gegroepeerd materiaal leest zo; verspreid materiaal niet. (Dit verschilt van duplicatie: dat herhaalt één betekenis op twee plaatsen; verspreiding fragmenteert één betekenis over vele plaatsen.)

**Wildgroei (Sprawl)** is de faalmodus hier: een document dat simpelweg te lang is, zelfs wanneer elke regel levend en uniek is. Aandacht verdunt zich over het teveel, en elke extra lijn is er één die je relevant moet houden. De oplossing is de ladder: maak naslagwerk openbaar achter pointers, en splits op per vertakking of volgorde, zodat elk pad alleen draagt wat het nodig heeft.

## Stappen en voltooiingscriteria (Steps and completion criteria)

Elke stap eindigt op een **voltooiingscriterium** — de voorwaarde die de agent vertelt dat het werk gedaan is. Twee eigenschappen maken dit een hefboom:

- **Duidelijkheid** — kan de agent onderscheiden wat af is en wat niet?  
	Een vage grens (“begrip bereikt”) nodigt uit tot **voortijdige afronding**: de stap wordt beëindigd vóór hij echt klaar is, omdat de aandacht verschuift naar _klaar willen zijn_. De zichtbare stappen die nog volgen — de **post‑completion‑stappen** — trekken de agent vooruit; de helderheid van het criterium vormt de tegenkracht.Verdedig in deze volgorde:	**verduidelijk eerst de grens** (lokaal en goedkoop);pas wanneer die grens onherleidbaar vaag blijft _én_ je merkt dat de agent zich haast, verberg je de latere stappen door de sequentie op te splitsen — en verbergen werkt alleen wanneer er een echte contextgrens is (een overdracht of een subagent‑dispatch; een inline‑aanroep laat de latere stappen in de context staan en verbergt dus niets).
- **Vraagstelling/Eis (Demand)** — hoeveel het vereist. "Elk gewijzigd model verantwoord" dwingt grondig werk af waar "produceer een wijzigingslijst" dat niet doet. De vraagstelling/eis bepaalt de **inspanning** — het graafwerk dat de agent binnen het materiaal moet doen, aanwezig in de formulering zelf en niet als een aparte stap uitgeschreven. En die eis is niet gebonden aan stappen: “Elke regel toegepast” legt een verplichting op aan een vlakke referentielijst, net zoals “elke stap uitgevoerd” dat doet bij een sequentie.
  Daardoor moet zelfs een document dat volledig uit verwijzingen bestaat nog steeds voldoen aan een volledigheidseis.

De sterkste criteria zijn zowel controleerbaar als exhaustief.

## Wanneer te splitsen

Het opsplitsen van één document in tweeën verbruikt één van de twee belastingen, dus splits alleen wanneer de snede dit rechtvaardigt:

- **Op volgorde (By sequence)** — splits een reeks stappen waarbij de stappen na voltooiing de agent verleiden om te haasten voor degene die ervoor ligt. Ze uit het zicht houden drijft meer inspanning aan voor de huidige taak. Pas op voor het omgekeerde: het samenvoegen van reeksen stelt latere stappen van elke stap bloot aan wat volgt, wat uitnodigt tot voortijdige voltooiing.
- **Op aanroep (By invocation)** — skill-specifiek: zie [`SKILL-MECHANICS.md`](SKILL-MECHANICS.md).

## Leidende woorden (Leading words)

Een **leidend woord** is een compact concept dat al aanwezig is in de pre-training van het model en waarmee de agent denkt tijdens het uitvoeren van het document (_les_, _oorlogsmist_, _tracer-kogels_). Herhaald als een token, nooit als een zin, accumuleert het een gedistribueerde definitie en verankert het een heel gedragsgebied in de minste tokens, door een beroep te doen op priors die het model al bezit. Een eigen term bedenken werkt zolang je ze duidelijk definieert, maar een verzonnen woord heeft geen bestaande associaties —  je betaalt in definitietokens wat een voorgetraind woord gratis oplevert; grijp daarom eerst naar een bestaand woord

Het verankert op twee manieren. In de hoofdtekst, uitvoering (execution): de agent grijpt naar hetzelfde gedrag telkens wanneer het woord verschijnt, en binnen plat naslagwerk richt het de aandacht op een klasse van dingen om naar te zoeken. In een pointer, *aanroep (invocation)*: wanneer hetzelfde woord voorkomt in je prompts, je documentatie en je codebase, verbindt de agent die gedeelde taal met het materiaal en bereikt hij het **consistenter en betrouwbaarder**.

Ga op zoek naar kansen om te refactoren met leidende woorden. Een triade uitgeschreven op drie locaties, een pointer die een zin besteedt om naar één idee te gebaren — elk is een passage die smeekt om te worden samengevouwen tot één token:

- "snel, deterministisch, lage overhead" → _tight_ (een _tight_ loop).
- "een loop waarin je gelooft" → _red_ — een vage poort wordt een binaire observeerbare staat (de loop wordt _red_ bij de bug, of niet).

Je wint twee keer: minder tokens en een scherpere haak waar de agent zijn denkwerk aan kan ophangen. Ga ervan uit dat elk document herformuleringen bevat die leidende woorden overbodig maken — ga ze zoeken.

**Ontkenning (Negation)** is de faalmodus naast deze hefboom: sturen via verbod sleept het verboden gedrag de context in en maakt het **meer** beschikbaar, niet minder. _Denk niet aan een olifant_, en de olifant is alles wat er is; de negatie is een zwakke modifier die het sterk geactiveerde concept overloopt, zodat het verbod half leest als een instructie om het toch te doen. Prompt het **positieve** — benoem het doelgedrag (“schrijf éénregelige comments”) zodat het verboden gedrag nooit wordt uitgesproken. Een verbod verdient zijn plek alleen als een harde vangrail die je niet positief kunt formuleren; zelfs dan, koppel het aan het positieve doel zodat de aandacht landt op wat wél moet gebeuren.

## Snoeien (Pruning)

- Houd elke betekenis in een **enkele bron van waarheid (single source of truth)**: één autoritaire plek, zodat het wijzigen van het gedrag een aanpassing op één plaats is. **Duplicatie** — dezelfde betekenis op meer dan één plek — kost onderhoud en tokens, en blaast het belang van een betekenis op de ladder op tot boven de werkelijke rang. (De toevallige inverse van een leidend woord, dat een token opzettelijk herhaalt, nooit de betekenis.)
- De **omgeving** is eveneens een bron van waarheid — `package.json`-scripts, configuratiebestanden, de mapstructuur, `--help`-uitvoer — en een document dat dit herformuleert is een **cache**: een kopie van een opzoeking, die zijn belasting alleen verdient wanneer de opzoeking duur is. Cache wat de agent niet kan vinden door te kijken: de ongeschreven conventie, de reden achter een keuze, het addertje onder het gras dat geen enkele configuratie opbiecht. Laat de opzoekingen van één bestand en één commando over aan de omgeving, waar ze niet verouderd kunnen raken.
- Controleer elke regel op **relevantie**: heeft deze nog steeds betrekking op wat het document doet? Een regel verliest relevantie doordat deze nooit betrekking heeft op de taak (pure expositie, of een vertakking die openbaar gemaakt moet worden) of doordat deze verouderd raakt naarmate het gedrag of de wereld die het beschrijft verandert. Kortere documenten zijn gemakkelijker relevant te houden. Zonder snoeidiscipline is het standaardlot **sediment**: verouderde lagen die bezinken omdat toevoegen veilig voelt en verwijderen riskant, totdat je er doorheen moet boren om te vinden wat nog leeft.
- Jaag op **no-ops** zin voor zin: een instructie die het model al standaard opvolgt kost belasting om niets te zeggen. De test — verandert het het gedrag ten opzichte van de standaard? — is model-relatief, niet lezer-relatief: twee mensen die van mening verschillen over een no-op verschillen van mening over de standaard, en lossen dit op door het document uit te voeren, niet door te debatteren. Wanneer een zin faalt, verwijder dan de hele zin in plaats van woorden erin te snoeien. De test beoordeelt ook leidende woorden: een woord dat te zwak is om de standaard te verslaan (_wees grondig_ wanneer de agent al redelijk grondig is) is een no-op, en de oplossing is een sterker woord (_onverbiddelijk_), niet een andere techniek.
