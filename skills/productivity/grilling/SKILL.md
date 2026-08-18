---
name: grilling
description: Gril de gebruiker onophoudelijk over een plan, beslissing of idee. Gebruik dit als de gebruiker zijn denken wil stress-testen of gebruik als eender welke ‘grill’ triggerzin wordt gebruikt. 
---

Interview de gebruiker onophoudelijk totdat je tot een gedeeld begrip komt. Kaart dit in als een **ontwerpboom**: elke beslissing vertakt zich in de beslissingen die eraan hangen.

Werk de boom in **rondes**. De rand van het onderzochte gebied (frontier) is elke beslissing waarvan de vereisten al zijn vastgesteld: de vragen die je _nu_ kunt stellen zonder te raden op antwoorden die je nog niet hebt gehoord. Vraag de hele frontier in één ronde: nummeren elke vraag en geef je aanbevolen antwoord. Wacht dan op de antwoorden van de gebruiker voor de volgende ronde.

Elke vraag moet als volgt worden opgemaakt:

```
❓ **Q1** - **<vraagtitel>**: <vraagtekst, kan meerdere alinea's zijn, inclusief meerdere keuzes>

➡️ <Jouw aanbevolen antwoord>
```

Elke ronde die de gebruiker beantwoordt, verandert de boom: vastgestelde beslissingen duwen de grens naar buiten en deblokkeren vragen die van hen afhingen. Bereken de grens opnieuw en vraag de volgende ronde. Een vraag waarvan het antwoord afhangt van een andere vraag die nog openstaat in deze ronde hoort bij een _latere_ ronde, niet deze.

Het vinden van _feiten_ is jouw taak, nooit die van de gebruiker. Wanneer een frontiervraag een feit uit de omgeving nodig heeft (bestandssysteem, tools, enz.), stuur dan een subagent om het te vinden; Vraag de gebruiker niet om iets wat je zelf kunt opzoeken. Blokkeer er niet op: een lopende verkenning is een onopgeloste vereiste, dus alleen de vragen stroomafwaarts wachten op de subagent om te rapporteren; Vraag het nu aan de rest van de frontier. De _beslissingen_ zijn die van de gebruiker: leg ze aan hen en wacht.

De sessie is afgelopen wanneer de grens leeg is: elke tak van de ontwerpboom wordt bezocht, niets blijft stilzwijgend aangenomen. Handel er niet naar totdat de gebruiker bevestigt dat jullie tot een gedeeld begrip zijn gekomen.

