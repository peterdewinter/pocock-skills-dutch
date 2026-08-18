# Skillmechanica

De skill-specifieke tak van [`writing-for-agents`](SKILL.md). Wat er verandert wanneer het document een skill is? De frontmatter, de keuze voor aanroep, en router-skills. De rest gebeurd volgens de universele beschrijving in `SKILL.md`.

## Aanroep

Twee keuzes, die de twee loads tegen elkaar uitruilen:

- Een **model-aangeroepen** skill behoudt een `description`, zodat de agent ze autonoom kan activeren — en andere skills haar kunnen bereiken. Je kunt haar naam nog steeds typen: model-aanroep omvat altijd de menselijke aanroep; een description voegt alleen agent-discovery toe, en verwijdert nooit de mens. De description is de skill’s contextpointer op het hoogste niveau, verplicht om altijd geladen te zijn — permanente context load in ruil voor vindbaarheid. Een model-aangeroepen skill waarvan de inhoud volledig referentie is, is ook een thuis voor gedeelde referentie: een andere skill kan haar aanroepen, zodat referentie die door meerdere skills nodig is op één plek leeft. Mechanica: laat `disable-model-invocation` weg, en schrijf een modelgerichte description die de oproepingstakken draagt (de schrijfregels van pointers in `SKILL.md` gelden volledig).

- Een **door de gebruiker aangeroepen** skill haalt de description weg uit het bereik van de agent: alleen de mens die de naam typt kan haar aanroepen, en geen enkele andere skill kan dat. Nul context load, maar het kost cognitieve load — jij bent de index die moet onthouden dat ze bestaat. Mechanica: zet `disable-model-invocation: true`; de `description` wordt mensgericht — een éénregelige samenvatting, zonder triggerlijsten.

Kies model-aanroep alleen wanneer de agent de skill zelfstandig moet kunnen bereiken, of wanneer een andere skill dat moet. Als ze alleen met de hand wordt geactiveerd, maak haar user-invoked en betaal geen context load.

Gedeelde referentie die twee user-invoked skills allebei nodig hebben, kan in geen van beide leven — zonder descriptions kan geen van beide de ander aanroepen. Verplaats die naar een gewoon bestand buiten het skillsysteem: externe referentie waar elke skill naar kan verwijzen.

## Splitsen op aanroep

De aanroep-splitsing (de sequentiesplitsing staat in `SKILL.md`): splits een model-aangeroepen skill af wanneer je een duidelijk leidend woord hebt dat haar zelfstandig moet activeren — een triggerwoord dat je daadwerkelijk in je prompts gebruikt — of wanneer een andere skill haar moet bereiken. Je betaalt context load voor de nieuwe altijd geladen description, dus die onafhankelijke bereikbaarheid moet de moeite waard zijn.

## Router-skills

Wanneer user-invoked skills zich opstapelen voorbij wat je kunt onthouden, wordt die opgehoopte cognitieve load opgelost door een **router-skill**: één user-invoked skill die de andere benoemt en aangeeft wanneer je welke moet gebruiken, zodat de mens één skill hoeft te onthouden in plaats van vele. Ze kan alleen aanwijzen, nooit activeren: user-invoked skills hebben geen description, dus niets behalve de mens kan ze bereiken.
