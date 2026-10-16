---
name: project-opzet
description: Zet een nieuw Cowork-project op in de vaste Foundations-mapstructuur en levert de omschrijving als kant-en-klaar paste-blok. Twee routes. Route KLUS voor tijdelijk werk met een einddoel, dus een PROJECT-map plus een projectomschrijving op basis van PRISMA. Route MEDEWERKER voor doorlopend werk, dus een vaste rol met een eigen werkmap, lees- en schrijfgrenzen, gereedschap en delegatiegrenzen. Bewaakt de tekenlimiet van het instructieveld en zet wat daar niet in past in CLAUDE.md in de werkmap. TRIGGERS op "zet een nieuw project op", "richt dit project in", "nieuw Cowork-project", "project-opzet", "maak een projectomschrijving", "medewerker aannemen", "nieuwe rol", "functieomschrijving maken", "moet dit een project of een map worden", "is dit een klus of een rol", of elk verzoek om een nieuw project, een nieuwe rol of een nieuwe werkmap in te richten. Gebruik de skill ook wanneer iemand twijfelt tussen een tijdelijke klus en een doorlopende rol, of een bestaand project alsnog een goede omschrijving wil geven.
metadata:
  version: "2026-10-16"
---

# Project-opzet skill

Richt een Cowork-project in volgens de vaste Foundations-structuur en levert de omschrijving als paste-blok. Twee routes, die een ander soort omschrijving opleveren.

## Mapnamen

Deze skill gebruikt standaardnamen. Wijken de namen van de gebruiker af (bijvoorbeeld "Bronnen" in plaats van "Resources"), dan staan die namen in zijn Cowork-werkwijze, die automatisch meekomt in elke sessie. Gebruik dan zijn namen; pas deze skill niet aan, want hij wordt via de marketplace bijgewerkt en een eigen aanpassing gaat dan verloren.

- Bronnenmap voor eigen uploads: **Resources**
- Map voor wat Claude maakt: **Output**
- Navigatiebestand per map: **README.md**
- Lessons-learned-bestand per map: **MEMORY.md**
- Werkinstructies per werkmap: **CLAUDE.md**

Een **werkmap** is een map met deze vaste inrichting waarin een project schrijft. Welke map dat is, staat in de projectinstructie onder WAT JE BEHEERT, niet in de koppeling: in elk project is de complete hoofdmap (AI Library) gekoppeld, dus elk project ziet alles en de instructie bepaalt waar het schrijft. Output en Resources zijn submappen van een werkmap, geen werkmappen.

## Waar instructies horen

| Plek | Limiet | Waarvoor |
|---|---|---|
| Cowork-werkwijze (Instellingen) | ruim | wat in élk project geldt |
| Projectinstructies-veld | **4000 tekens, kapt af zonder melding** | rol, grenszin, werkmap, delegatiegrenzen |
| `CLAUDE.md` in de werkmap | geen, richtlijn onder 200 regels | vakregels, bronnen, do's en don'ts; wordt als eerste gelezen via de leesregel in de Cowork-werkwijze, niet in een gewone chat |
| `README.md` en `MEMORY.md` | geen | navigatie en geheugen |

## Stap 0: de werkwijze controleren

Controleer dit zelf, in je eigen context. De Cowork-werkwijze komt automatisch mee bij elke sessie, dus je kunt zien wat erin staat. Vraag het niet aan de gebruiker.

**Lever nooit een hele sectie of een complete werkwijze.** De gebruiker heeft er al een, en die bevat meer dan deze lijst: afspraken over About Me, over andere mappen, over Resources. Een blok met dezelfde kop leest als een vervanging en dan verdwijnt dat. Werk dus per regel.

Loop de regels hieronder langs en kijk welke er al staan, in welke bewoording dan ook.

- **Staat een regel er al, ook in andere woorden**: laat hem met rust. Dubbel opnemen verandert niets.
- **Staat er een regel die hier niet in voorkomt**: dat is de eigen werkwijze van de gebruiker en die is zijn zaak. Noem hem niet, vraag er niet naar, stel geen wijziging voor. Deze controle kijkt één kant op.
- **Eén uitzondering**: regels die spreken van "primaire map", "primair gekoppeld" of "extra gekoppelde map" komen uit de oude werkwijze, toen een project één primaire map en extra mappen koppelde. Lever daarvoor de vervangende regel uit de lijst hieronder, met de instructie om de oude te vervangen.
- **Ontbreekt een regel**: lever alleen díe regel, met de sectie waar hij onder hoort en de instructie om hem toe te voegen, niet te vervangen. Zeg in één zin wat er zonder misgaat. Je kunt dat veld niet zelf invullen (Instellingen, Cowork).
- **Staat er niets van dit alles**: dan heeft de gebruiker waarschijnlijk nog geen werkwijze. Lever dan wel het geheel, en zeg erbij dat dit een startpunt is dat hij zelf aanvult.

Vul bij de controleregel de naam van de gebruiker in.

```
CONTROLEREGEL
- Begin elk antwoord met [naam] gevolgd door een streepje. Blijft dat weg,
  dan weet ik dat deze instructies niet meer volledig meekomen en dat ik een
  nieuwe chat moet beginnen. Zet die naam nooit in een bestand of in een blok
  dat ik ergens anders plak.

ABOUT ME
- Lees aan het begin van de sessie ook About Me/MEMORY.md.
- Wijzigen van About Me en de aanboddocumenten gebeurt alleen in het project
  About Me Edits.

JE WERKMAP
- Mijn complete AI Library is gekoppeld. Je werkmap is de map die in je
  projectinstructies onder WAT JE BEHEERT staat. Staat daar niets, vraag dan
  eerst welke map je werkmap is.
- Staat er een CLAUDE.md in je werkmap, lees die als eerste, vóór README.md.
  Daar staan de werkinstructies voor deze werkmap.
- Lees aan het begin het README.md van je werkmap, dan gericht het bestand
  dat je nodig hebt.
- Werk het README.md bij wanneer je bestanden toevoegt of de inhoud verandert.
- Schrijf wat je aanmaakt naar de Output-map van je werkmap, niet in de root.
  Behandel Resources als alleen-lezen bronmateriaal.
- Niets verwijderen of verplaatsen zonder mijn akkoord, en bevestig
  wijzigingen eerst.

SCHRIJVEN BUITEN JE WERKMAP
- Elke andere map in AI Library lees je vrij, maar daar schrijf je alleen na
  mijn akkoord, of direct als ik de map of het bestand zelf noem. Schrijf je
  daar, lees dan eerst CLAUDE.md, README.md en MEMORY.md van die map, werk de
  README bij, zet één regel in de MEMORY van die map (datum, wat, vanuit welk
  project) en zeg bij welke medewerker dit normaal hoort.

WERKBESTANDEN
- Heb je hulpbestanden nodig om iets te maken (scripts, fonts, achtergronden,
  screenshots, tussenversies), houd die dan in je eigen werkomgeving. In mijn
  map komt alleen het resultaat.

GEHEUGEN
- Lees aan het begin van de sessie, direct na README.md, ook MEMORY.md van je
  werkmap.
- MEMORY.md van je werkmap is het geheugen van die werkmap. Schrijf daar
  in dezelfde beurt naartoe zodra ik een besluit neem, een werkafspraak geef,
  of iets aantoonbaar wel of niet werkte. Eén regel per punt, met datum.
  Toevoegen, niet overschrijven.
- Vraag niet of je het mag opslaan. Doe het en noem het in één regel in je
  terugkoppeling.
- Geldt iets voor al mijn projecten, dan naar About Me/MEMORY.md in plaats
  van de werkmap.
- Is een werkafspraak een staande regel, dus iets dat élke keer geldt, werk
  dan CLAUDE.md van je werkmap bij onder de kop waar hij hoort. In
  MEMORY.md komt dan alleen wat er is besloten en waarom, met datum, niet de
  regel zelf. Bestaat CLAUDE.md niet in die map, meld dat en stel voor hem
  aan te maken.
- Het ingebouwde projectgeheugen van Cowork vervangt MEMORY.md niet. Wat je
  daar bewaart, zet je ook in MEMORY.md.
- Wordt MEMORY.md langer dan ongeveer 40 regels, vat dan samen. Besluiten
  blijven altijd staan.
- Bestaat MEMORY.md niet in je werkmap, maak hem aan en meld dat.
```

Deze lijst is het minimum dat de skill nodig heeft, geen complete werkwijze. Regels over huisstijl of toon staan er niet in en horen er ook niet uit weggelaten te worden bij de gebruiker.

## Route bepalen

Stel deze vraag, ook als de gebruiker zelf al "project" zei:

> Is dit werk ooit af? Dan is het een klus. Is het nooit af? Dan hoort het bij een medewerker.

- **Ooit af**, met een einddoel en een eind: route KLUS. Een salespagina herzien, een lancering, een programma ontwikkelen.
- **Nooit af**, doorlopend, met een eigen ritme: route MEDEWERKER. Content, sales, finance, de inbox, advertenties.

Twee checks voordat je bouwt:

1. **Verdient dit een eigen project?** Alleen als het werk een ritme heeft en een geheugen: dingen die een volgende sessie moet weten. Eenmalig werk dat zijn resultaat in een bestaande werkmap achterlaat, is een losse chat waard. Levert de klus wel eigen materiaal op, dan krijgt hij een eigen map.
2. **Verdient de rol een eigen project?** Wie maakt, beheert of bedient wel. Wie alleen meedenkt of weegt niet: dat wordt een laag die je erbij roept in het project waar je toch al zit. Een uitvoerder naast een manager krijgt pas een eigen project als hij zwaar gereedschap draagt.

Toets een rolnaam met: zou een mens dit doen als je het uitbesteedde? Zo nee, dan is het een taak, geen rol.

Twijfelt de gebruiker, leg beide kanten één keer voor met de consequentie erbij en laat hen kiezen. Gok niet.

---

# Route KLUS

## Stap A: de mapstructuur

Check eerst, bouw daarna.

Bepaal eerst de werkmap van de klus: `Projecten/Actueel/PROJECT - [naam]`, of de map die de gebruiker noemt.

1. Staan **Output/**, **Resources/**, **README.md** en **MEMORY.md** er al? Maak niets aan, meld dat kort, ga naar stap B.
2. Staat een deel er? Maak alleen aan wat ontbreekt, raak de rest niet aan.
3. Is de map leeg? Maak alle vier aan. README.md krijgt de mapnaam plus één regel; MEMORY.md krijgt de titel plus "Hier komen lessons learned voor deze werkmap."
4. Toon de tree en ga naar stap B.

Een klus krijgt geen `CLAUDE.md`.

## Stap B: de projectomschrijving

Je kunt het instructieveld niet zelf invullen. Lever een paste-blok en zeg erbij dat de gebruiker het zelf plakt. De vaste werkafspraken staan in de Cowork-werkwijze en komen niet in de omschrijving.

1. **Vraag in gewone taal naar het doel.** Wat is dit project en wat ga je hier vooral doen? Dit komt altijd van de gebruiker; het is niet af te leiden uit About Me.
2. **Vraag hoe ze geholpen willen worden.** Zelf een voorstel en kritisch meedenken, of per onderdeel een paar vragen.
3. **Vertaal het doel naar een concept.** Rol, output en structuur, en bij content- of saleswerk een doelgroep. Denk mee, leg het niet terug.
4. **Kijk zelf welke mappen en links al aan het project hangen** en leid de bronnen daaruit af. Vraag alleen door op wat je niet kunt zien.
5. **Toon het concept**, vraag wat er anders moet, lever daarna pas definitief. Laat niet-toepasselijke onderdelen weg.
6. **Tel het blok** volgens "De tekenlimiet bewaken".

```
DOEL VAN DIT PROJECT
[Wat is het doel en wat doe je hier vooral.]

JOUW ROL
[Vanuit welke rol werk ik hier. Weglaten indien niet opgegeven.]

DELEGATIEGRENZEN
AUTO: [wat je zelfstandig doet]
ASK: [wat je eerst voorlegt]
NEVER: [wat je nooit doet, ook niet op verzoek]

WAT JE BEHEERT
[Het volledige pad van de werkmap van deze klus vanaf de root van AI Library.
Sluit af met: Alles buiten deze map is alleen-lezen; schrijven daar alleen na
mijn akkoord, volgens mijn werkwijze.]

CONTEXT & BRONNEN
[Welke mappen en bestanden je leest en waarvoor, welke Notion-pagina's,
voorbeelden.]

OUTPUT & STRUCTUUR
[Hoe de output eruit moet zien. Weglaten indien niet van toepassing.]

DOELGROEP
[Voor wie is dit bedoeld. Weglaten indien niet van toepassing.]
```

Sluit af met: "Kopieer dit blok en plak het in de projectinstructies van dit project (Cowork-projectinstellingen). Ik kan dat veld niet zelf invullen." Geef daarna de controle uit "Na het plakken" mee.

---

# Route MEDEWERKER

Een medewerker is een Cowork-project voor doorlopend werk. Hij heeft een eigen werkmap, een functieomschrijving en gereedschap. Zeven stappen op volgorde. Laat na stap 5 het concept zien voordat je iets definitief maakt.

## Stap 1: de rol

Vraag in gewone taal welk werk deze medewerker doet en vertaal dat naar één werkwoord: maken, ontwerpen, bedienen, beheren, terugkijken. Twee rollen met hetzelfde werkwoord zijn één rol.

Noem de rol naar zijn domein (Marketing, Finance, Sales), niet naar een activiteit: "Planning" of "Analyse" trekt vreemd werk aan en wordt een vergaarbak.

Leg de rolnaam voor met de grenszin erbij, één zin die zegt wat hij wel bezit en wat niet. Voorbeeld: "de Marketing & Sales Manager bepaalt welke campagne er loopt en naar welk aanbod, de Ads Manager bedient het platform."

## Stap 2: de werkmap

Elke werkmap heeft precies één beheerder: één project dat er schrijft. Lezen mag iedereen.

1. Vraag of stel voor welke werkmap hij beheert. Meerdere werkmappen per medewerker mag; twee beheerders per werkmap niet.
2. **Lees de README van die werkmap.** Staat er al een andere beheerder, meld dat als botsing en laat de gebruiker kiezen. Los het niet zelf op.
3. Bestaat de werkmap niet, maak hem aan met de vaste inrichting uit stap A van de klus-route. Een werkmap zonder Output, Resources, README en MEMORY is geen werkmap.
4. Een nieuwe hoofdmap alleen met expliciet akkoord. De structuur blijft zo beknopt mogelijk.

Richt de werkmap in volgens stap A van de klus-route en zet bovenaan de README:

```
> Beheerder: [rol]. [Wat hij hier bezit.] Andere rollen lezen mee.
```

## Stap 3: lezen en schrijven

In elk project is de complete hoofdmap (AI Library) gekoppeld; er is geen keuze van mappen meer. De grens tussen lezen en schrijven staat daarom in woorden, in WAT JE BEHEERT:

1. Schrijven: de werkmap of werkmappen uit stap 2, met het volledige pad vanaf de root van AI Library. Geen interpretatie mogelijk.
2. Lezen: noem de mappen die hij voor zijn werk vooral leest (About Me altijd, plus wat bij de rol hoort), zodat hij weet waar hij moet zoeken. Alles meelezen kost tokens; gericht lezen is de regel.
3. Elke andere map is alleen-lezen. Schrijven daarbuiten mag alleen na akkoord van de gebruiker, volgens de sectie SCHRIJVEN BUITEN JE WERKMAP in de werkwijze. Herhaal die regels niet, verwijs ernaar met één zin.

About Me en de aanboddocumenten zijn voor elke medewerker alleen-lezen; alleen About Me Edits schrijft daar. Dat staat in de werkwijze en hoeft niet in de omschrijving.

## Stap 4: het gereedschap

Noem welke skills en koppelingen hij gebruikt. Bestaat het gereedschap nog niet, zet het op zijn lijst in plaats van de aanname uit te stellen. Eerst de rol, dan de skill.

## Stap 5: de delegatiegrenzen

Drie categorieën, elk met concrete voorbeelden uit zijn eigen werk. Vraag ernaar, gok niet: dit is precies waar iemand niet verrast wil worden.

- **AUTO**: doet hij zelfstandig.
- **ASK**: legt hij voor en wacht op akkoord. Alles wat naar buiten gaat valt hier standaard onder.
- **NEVER**: doet hij nooit, ook niet als het gevraagd lijkt te worden. Betalen, tekenen, publiceren zonder dat de gebruiker het heeft gezien.

Bij twijfel ASK. Een mandaat groeit van ASK naar AUTO, niet andersom.

## Stap 6: de functieomschrijving

Toon het concept, vraag wat er anders moet, lever daarna definitief. De delegatiegrenzen staan direct na de rol: het veld kapt van onderaf af. De vaste werkafspraken staan in de Cowork-werkwijze en komen niet in de omschrijving.

```
DOEL VAN DIT PROJECT
[Wat dit werk is en waarom het doorloopt. Eén alinea.]

JOUW ROL
[De rol met zijn werkwoord, plus de grenszin.]

DELEGATIEGRENZEN
AUTO: [wat je zelfstandig doet]
ASK: [wat je eerst voorlegt]
NEVER: [wat je nooit doet, ook niet op verzoek]

WAT JE BEHEERT
[De werkmap of werkmappen waar je schrijft, één regel per werkmap, met het
volledige pad vanaf de root van AI Library. Daarna wat je vooral leest.
Sluit af met: Alles buiten deze mappen is alleen-lezen; schrijven daar
alleen na mijn akkoord, volgens mijn werkwijze. Zie je elders iets dat niet
klopt, meld het en doe een voorstel.]

CONTEXT & BRONNEN
[Welke mappen en bestanden je leest en waarvoor. De vakregels en de
volledige bronnenlijst staan in CLAUDE.md in je werkmap.]
```

Sluit af met:

1. "Kopieer dit blok en plak het in de projectinstructies van dit project (Cowork-projectinstellingen). Ik kan dat veld niet zelf invullen."
2. De twee controles uit "Na het plakken".
3. Eén regel over wat deze medewerker als eerste kan oppakken, zodat zijn MEMORY en README meteen gaan leven.
4. Bij meer dan één medewerker tegelijk: neem ze één voor één aan en gebruik de eerste weken om te zien of de grenzen kloppen. Tien medewerkers die niets te doen hebben, is hetzelfde probleem als één vergaarbak.

## Stap 7: CLAUDE.md in de werkmap

Alles wat lang is van nature gaat hierheen. Maak `CLAUDE.md` aan in de root van de werkmap, onder de 200 regels want het laadt in zijn geheel mee.

Alleen wat specifiek is voor deze werkmap. Herhaal niets uit de Cowork-werkwijze (lees-, geheugen- en outputregels die overal gelden) en niets uit het instructieveld (rol, grenszin, wat hij beheert, delegatiegrenzen). Elke regel staat op één plek; wat op twee plekken staat, loopt uit elkaar.

```
# [Rol] - werkinstructies

## Bronnen van deze werkmap
[Per bron één regel: welk bestand of welke map, en waarvoor.]

## Vakregels
[Concreet en toetsbaar, niet abstract.]

## Output
[Waar bestanden landen, welke naamgeving, welk format.]

## Do's en don'ts
[Wat in dit vak steeds misgaat, en wat de gebruiker niet wil zien.]
```

Zeg er bij de oplevering in één zin bij dat CLAUDE.md via de leesregel in de werkwijze als eerste gelezen wordt in elke Cowork-chat van dit project, zodat deze instructies niet in het instructieveld hoeven en dus niet afgekapt kunnen worden. In een gewone chat (zonder Cowork) wordt hij niet gelezen; dat is de eerste check als een medewerker zijn instructies niet lijkt te kennen. Test het meteen: nieuwe chat, "welke vakregels gelden hier?".

CLAUDE.md is geen momentopname. Wordt er later een werkafspraak gemaakt die élke keer geldt, dan gaat die hierheen en niet in MEMORY.md; dat staat als regel in het GEHEUGEN-blok van de werkwijze uit stap 0.

---

## De tekenlimiet bewaken

Voor elke definitieve oplevering, in beide routes. Tel het paste-blok.

- Onder 3500: leveren.
- 3500 tot 4000: leveren met de melding dat hij tegen de limiet zit, plus een voorstel wat naar `CLAUDE.md` kan.
- Boven 4000: **niet leveren.** Verplaats en tel opnieuw.

Verhuisvolgorde: bronnenlijst, do's en don'ts, uitzonderingen op de standaardinrichting, naamgevingsafspraken. Nooit verhuizen: de rol, de grenszin, wat hij beheert, de delegatiegrenzen.

## Na het plakken

Geef de gebruiker deze twee controles mee, één keer per project. Afkappen gebeurt bij het plakken of het gebeurt niet, dus dit is eenmalig en hoeft daarna nooit meer.

> Open een nieuwe chat in dit project en vraag: "Geef de laatste regel van je projectinstructies woordelijk terug." Komt die regel terug, dan is het veld compleet aangekomen. Komt hij niet terug, dan is hij afgekapt en moet er inhoud naar CLAUDE.md.

> Vraag daarna: "In welke mappen schrijf jij, en waar niet? Geef de volledige paden." Noemt hij precies zijn eigen werkmap(pen) en zegt hij dat de rest alleen-lezen is, dan staat de grens. Noemt hij meer of minder, dan is WAT JE BEHEERT niet scherp genoeg.

## Regels

- Eén beheerder per werkmap, zoveel lezers als nodig. Anderen schrijven er alleen na akkoord van de gebruiker, volgens de werkwijze.
- Elke werkmap krijgt bij aanmaak Output, Resources, README.md en MEMORY.md.
- In de root van een werkmap staan alleen README.md, MEMORY.md en CLAUDE.md.
- Verwijder of overschrijf nooit bestaande mappen of bestanden. Bestaat een map al, meld dat en vraag wat de gebruiker wil.
- README.md, MEMORY.md en CLAUDE.md houden altijd die naam; die herkent Cowork zelf.
- In elk project is de complete hoofdmap (AI Library) gekoppeld. Alleen About Me Edits schrijft in About Me en in de aanboddocumenten, per wijziging na akkoord; dat project is geen medewerker.
- Een nieuwe hoofdmap komt er alleen met expliciet akkoord van de gebruiker.
- De werkafspraken en geheugenregels staan in de Cowork-werkwijze. Herhaal ze niet in de projectomschrijving.
