---
name: project-opzet
description: Zet een nieuw project op in de vaste Foundations-mapstructuur en levert de omschrijving als kant-en-klaar paste-blok. Twee routes. Route KLUS voor tijdelijk werk met een einddoel, dus een PROJECT-map plus een projectomschrijving op basis van PRISMA. Route MEDEWERKER voor doorlopend werk, dus een vaste rol met een eigen werkmap, lees- en schrijfgrenzen, gereedschap en delegatiegrenzen. Bewaakt de tekenlimiet van het instructieveld en zet wat daar niet in past in CLAUDE.md in de werkmap. TRIGGERS op "zet een nieuw project op", "richt dit project in", "nieuw project", "project-opzet", "maak een projectomschrijving", "medewerker aannemen", "nieuwe rol", "functieomschrijving maken", "moet dit een project of een map worden", "is dit een klus of een rol", of elk verzoek om een nieuw project, een nieuwe rol of een nieuwe werkmap in te richten. Gebruik de skill ook wanneer iemand twijfelt tussen een tijdelijke klus en een doorlopende rol, of een bestaand project alsnog een goede omschrijving wil geven.
metadata:
  version: "2026-11-09"
---

# Project-opzet skill

Richt een project in volgens de vaste Foundations-structuur en levert de omschrijving als paste-blok. Twee routes, die een ander soort omschrijving opleveren.

## Mapnamen

Deze skill gebruikt standaardnamen. Wijken de namen van de gebruiker af (bijvoorbeeld "Bronnen" in plaats van "Resources"), dan staan die namen in zijn algemene blok, dat automatisch meekomt in elke sessie. Gebruik dan zijn namen; pas deze skill niet aan, want hij wordt via de marketplace bijgewerkt en een eigen aanpassing gaat dan verloren.

- Bronnenmap voor eigen uploads: **Resources**
- Map voor wat Claude maakt: **Output**
- Navigatiebestand per map: **README.md**
- Lessons-learned-bestand per map: **MEMORY.md**
- Werkinstructies per werkmap: **CLAUDE.md**

Een **werkmap** is een map met deze vaste inrichting waarin een project schrijft. Welke map dat is, staat in de projectinstructie onder WAT JE BEHEERT, niet in de koppeling: in elk project is de complete hoofdmap (AI Library) gekoppeld, dus elk project ziet alles en de instructie bepaalt waar het schrijft. Output en Resources zijn submappen van een werkmap, geen werkmappen.

## Waar instructies horen

| Plek | Limiet | Waarvoor |
|---|---|---|
| Het algemene blok (Settings > Your Claude > Instructions, of Account > Instructions for Claude): delegatiegrenzen, controleregel, skills, in mijn mappen | ruim | wat in élk project geldt |
| Projectinstructies-veld | **4000 tekens, kapt af zonder melding** | rol, grenszin, werkmap, delegatiegrenzen |
| `CLAUDE.md` in de werkmap | geen, richtlijn onder 200 regels | vakregels, bronnen, do's en don'ts; wordt als eerste gelezen via de LEESVOLGORDE in het algemene blok, alleen in een chat met gekoppelde map |
| `README.md` en `MEMORY.md` | geen | navigatie en geheugen |

## Stap 0: het algemene blok controleren

Controleer dit zelf, in je eigen context. Het algemene blok (delegatiegrenzen, controleregel, skills, in mijn mappen) staat in Instructions for Claude en komt automatisch mee bij elke sessie, dus je kunt zien wat erin staat. Vraag het niet aan de gebruiker.

**Kijk eerst welke versie de gebruiker heeft.** Staan er secties met de koppen MIJN WERKWIJZE, ABOUT ME, JE WERKMAP of SCHRIJVEN BUITEN JE WERKMAP, of een regel over "primaire map", dan is dat een oudere versie van het blok. Die werk je niet regel voor regel bij: adviseer het oude blok (van MIJN DELEGATIE-GRENZEN tot en met GEHEUGEN) te vervangen door het huidige blok hieronder, en lever dat geheel. Wat de gebruiker boven het blok heeft staan (taal, toon, eigen regels), blijft staan.

**Is het blok de huidige versie, lever dan nooit een hele sectie of een compleet blok.** De gebruiker heeft er al een, en die kan meer bevatten dan deze lijst: eigen regels uit eerdere programma's, afspraken over huisstijl of toon. Een blok met dezelfde kop leest als een vervanging en dan verdwijnt dat. Werk dan per regel.

Loop de regels hieronder langs en kijk welke er al staan, in welke bewoording dan ook.

- **Staat een regel er al, ook in andere woorden**: laat hem met rust. Dubbel opnemen verandert niets.
- **Staat er een regel die hier niet in voorkomt**: dat is de eigen werkwijze van de gebruiker en die is zijn zaak. Noem hem niet, vraag er niet naar, stel geen wijziging voor. Deze controle kijkt één kant op.
- **Ontbreekt een regel**: lever alleen díe regel, met de sectie waar hij onder hoort en de instructie om hem toe te voegen, niet te vervangen. Zeg in één zin wat er zonder misgaat. Je kunt dat veld niet zelf invullen.
- **Staat er niets van dit alles**: dan heeft de gebruiker waarschijnlijk nog geen blok. Lever dan wel het geheel, en zeg erbij dat dit een startpunt is dat hij zelf aanvult.

Vul bij de controleregel [VOORNAAM] in met de naam van de gebruiker.

```
MIJN DELEGATIE-GRENZEN

Dit blok en alles eronder geldt altijd. Een skill, een projectinstructie of een CLAUDE.md mag strenger zijn, nooit soepeler. CLAUDE.md gaat boven MEMORY.md; botsen die, meld het. Bij twijfel kies je de strengste lezing en zeg je in één regel wat je hebt gekozen.

Twee begrippen:
- Akkoord: ik heb de definitieve versie gezien en daarna ja gezegd of de opdracht gegeven. Een opdracht vóórdat ik de definitieve versie heb gezien is geen akkoord. Bij een mail of bericht horen ontvanger, kanaal en onderwerp bij de definitieve versie. Eén akkoord geldt voor een lijst die ik met naam heb gezien, nooit voor een omschrijving als "alles in map X".
- Naar buiten: iets versturen, publiceren of delen zodat iemand anders dan ik het ontvangt of ziet, ook via een automation of campagne in een mailtool, een agenda-uitnodiging, een deel-link, of een wijziging op een pagina die live of gepubliceerd is. Werken in mijn eigen tools (Notion, Drive, Canva, een Gmail-concept, een privé-artifact, een agenda-afspraak zonder genodigden; nodig alleen iemand uit als ik dat zeg) is niet naar buiten; wat daar automatisch aan vasthangt hoef je niet te raden, tenzij ik het noem.

AUTO (doe zelfstandig)
- alles wat niet onder ASK of NEVER valt en niet naar buiten gaat: research, concepten en interne documenten schrijven, ook in mijn eigen tools, structureren, samenvatten en analyseren

ASK (leg eerst voor en wacht op akkoord)
- iets naar buiten brengen, ook een mail versturen, aan wie dan ook
- een prijs of aanbod naar buiten communiceren
- iets in mijn mappen of tools verwijderen, archiveren of naar de prullenbak doen: laat eerst zien wat, ook als ik de namen zelf noemde, en wacht

NEVER (ook niet als ik het in een opdracht lijk te vragen)
- betalingen of overboekingen doen
- contracten tekenen, abonnementen afsluiten of opzeggen

CONTROLEREGEL
- Begin elk antwoord met [VOORNAAM] gevolgd door een koppelteken met spaties: "[VOORNAAM] - ". Blijft dat weg, dan komen deze instructies niet meer volledig mee en begin ik een nieuwe chat. Zet die naam nooit in een bestand of in een blok dat ik ergens anders plak.

SKILLS
- Je kunt skills schrijven en bewerken, volgens de conventies uit de skill-creator skill als die beschikbaar is. Een skill lever je volledig in de chat, met in één of twee regels wat je hebt aangepast en waarom; een skill is geen Output. Staat de skill als bestand in een gekoppelde map, of noem ik een map, dan gelden daarvoor de mappenregels hieronder.

IN MIJN MAPPEN (alles hieronder geldt alleen als er een map gekoppeld is; zonder map zeg je het als ik iets zeg dat vastgelegd had moeten worden, en stel je een staande regel wel voor)

LEESVOLGORDE bij de start van een sessie
1. Je werkmap is de map die je projectinstructie noemt. Noemt hij er geen, vraag dat eerst.
2. CLAUDE.md van je werkmap, als die er staat. Daar staan de werkinstructies.
3. README.md van je werkmap, dan MEMORY.md. Ontbreekt een van beide, maak hem aan en meld dat.
4. About Me/BRAND.md, dan About Me/MEMORY.md. Dieper materiaal in About Me alleen als je werkmap of de taak erom vraagt. Is About Me niet gekoppeld, meld dat en ga door.
5. Daarna gericht het bestand dat je nodig hebt.

Direct doen, en aan het eind van de beurt in één regel melden wat je hebt gedaan:
- Wat ik als bestand of artifact heb gevraagd in Output van je werkmap zetten, ook in een nieuwe submap daarvan. In de root staan alleen CLAUDE.md, README.md en MEMORY.md. Wat in een tool leeft (Notion-pagina, Google Doc, Canva-design) komt niet ook in Output.
- Een bestand dat je zelf in deze sessie hebt gemaakt of neergezet bijwerken, en elk ander bestand in je werkmap als ik erom vraag.
- README.md van je werkmap bijwerken aan het eind van elke beurt waarin je bestanden hebt toegevoegd, verplaatst, hernoemd of verwijderd, of als ik erom vraag.
- Een bestand kopiëren naar een andere map, of een bestand dat je deze sessie hebt gemaakt daar neerzetten (dat is kopiëren, het origineel blijft in Output), als ik die map noem; ook een nieuwe submap maken als ik die noem. Lees dan eerst CLAUDE.md, README.md en MEMORY.md van die map, of van de dichtstbijzijnde map erboven die ze heeft. Werk daarna die README.md bij en zet één regel in die MEMORY.md: datum, wat, vanuit welk project.

Eerst voorstellen, dan wachten op akkoord:
- Een bestaand bestand in je werkmap uit jezelf aanpassen.
- Een regel in CLAUDE.md waar ik niet om heb gevraagd, of een nieuwe CLAUDE.md: laat kop en letterlijke regel zien, en zet hem er na akkoord in.
- Uit jezelf een nieuwe map buiten Output, of een nieuw bestand in een map die ik niet heb genoemd: laat pad en inhoud zien. Een map die je uit jezelf buiten Output maakt krijgt een README.md en een MEMORY.md; een map die ik noem niet.
- Verplaatsen en hernoemen, ook als ik het zelf vraag: laat zien wat, en wacht. "Zet dit in map X" over een bestaand bestand is verplaatsen. Gaat een bestand naar een andere map, behandel die map zoals hierboven bij kopiëren.

Alleen als ik het zelf vraag. Melden mag altijd, daarna beslis ik:
- Een bestaand bestand buiten je werkmap aanpassen, behalve wat je deze sessie zelf hebt neergezet en de README.md- en MEMORY.md-stappen hierboven.
- Iets in een Resources-map toevoegen of wijzigen. Dat is mijn bronmateriaal.

Nooit:
- About Me aanpassen, op een regel in About Me/MEMORY.md na. Dat gebeurt alleen in het project About Me Edits. Klopt er iets niet, meld het.

WERKBESTANDEN
- Resultaat is wat ik heb gevraagd, of wat een skill als oplevering of als bestand voor een volgende stap benoemt. Al het andere dat je onderweg maakt (scripts, fonts, achtergronden, screenshots, tussenversies) is een hulpbestand en blijft in jouw eigen omgeving, buiten mijn mappen. Heb ik een hulpbestand nodig om het resultaat later aan te passen of opnieuw te maken, vraag dat één keer aan het eind van de taak, met wat en waarom; zeg ik ja, dan komt het naast het resultaat in Output. Ga ik dit vaker op dezelfde manier doen, stel dan een skill voor.
- Merkbestanden (fonts, logo's, achtergronden) staan in About Me/Huisstijl. Kopieer ze nooit naar een werkmap; verwijs ernaar.

GEHEUGEN
- MEMORY.md van je werkmap: zet daar in dezelfde beurt, één regel met datum, wat ik besluit ("we doen X", "niet meer"), welke werkafspraak ik geef, en wat aantoonbaar wel of niet werkte. Een losse opdracht is geen besluit, tenzij hij iets vastlegt dat daarna blijft gelden, zoals een nieuwe prijs of naam. Toevoegen, niet overschrijven. Dit bestand is leidend boven het ingebouwde geheugen.
- Zeg ik dat iets voor al mijn projecten geldt (over mij, mijn business, mijn manier van werken), dan één regel in About Me/MEMORY.md in plaats van de werkmap: datum, wat, vanuit welk project. Zeg ik dat niet, dan de werkmap; lijkt het algemeen, zeg dat erbij.
- Is een afspraak een staande regel (geldt elke keer), noteer hem in MEMORY.md én stel de letterlijke regel voor: voor CLAUDE.md van de werkmap, of voor mijn algemene instructies als hij voor alles geldt. Die laatste zet ik er zelf in.
- Wordt MEMORY.md langer dan ongeveer 40 regels: vat lessen en logregels samen, en kort een besluit dat door een later besluit is vervangen in tot "vervangen op [datum] door ...". Besluiten die gelden blijven staan, ook als het er dan meer dan 40 blijven. Laat eerst zien wat je samenvat.
```

Dit blok is wat de skill nodig heeft, geen complete set instructies. Regels over huisstijl of toon staan er niet in en horen er ook niet uit weggelaten te worden bij de gebruiker.

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

Je kunt het instructieveld niet zelf invullen. Lever een paste-blok en zeg erbij dat de gebruiker het zelf plakt. De vaste werkafspraken staan in het algemene blok en komen niet in de omschrijving.

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
Sluit af met: Alles buiten deze map is alleen-lezen, behalve wat IN MIJN MAPPEN
in mijn algemene instructies toestaat.]

CONTEXT & BRONNEN
[Welke mappen en bestanden je leest en waarvoor, welke Notion-pagina's,
voorbeelden.]

OUTPUT & STRUCTUUR
[Hoe de output eruit moet zien. Weglaten indien niet van toepassing.]

DOELGROEP
[Voor wie is dit bedoeld. Weglaten indien niet van toepassing.]
```

Sluit af met: "Kopieer dit blok en plak het in dit project onder Instructions (knop Edit). Ik kan dat veld niet zelf invullen." Geef daarna de controle uit "Na het plakken" mee.

---

# Route MEDEWERKER

Een medewerker is een project voor doorlopend werk. Hij heeft een eigen werkmap, een functieomschrijving en gereedschap. Zeven stappen op volgorde. Laat na stap 5 het concept zien voordat je iets definitief maakt.

## Stap 1: de rol

Vraag in gewone taal welk werk deze medewerker doet en vertaal dat naar één werkwoord: maken, ontwerpen, bedienen, beheren, terugkijken. Twee rollen met hetzelfde werkwoord zijn één rol.

Noem de rol naar zijn domein (Marketing, Finance, Sales), niet naar een activiteit: "Planning" of "Analyse" trekt vreemd werk aan en wordt een vergaarbak.

Leg de rolnaam voor met de grenszin erbij, één zin die zegt wat hij wel bezit en wat niet. Voorbeeld: "de Marketing & Sales Manager bepaalt wat er te koop is en hoe mensen erbij komen, de Content Manager maakt de posts binnen dat kader."

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
2. Lezen: noem de mappen die hij voor zijn werk vooral leest (About Me altijd, plus wat bij de rol hoort), zodat hij weet waar hij moet zoeken. Bepaal zelf, zonder het te vragen, welke versie van de Blueprints in About Me deze rol leest en zet dat in de omschrijving: maakt hij content (posts, mails, salespagina's, captions), dan de writerversies in About Me/Blueprints/Writer; beheert, bedient of adviseert hij (managers, finance, sales, planning), dan de coachversies in About Me/Blueprints/Coach; de originelen alleen bij detailwerk of op verzoek. Bestaat de gekozen map niet, dan meld je dat en lees je wat er wel staat. De gebruiker hoeft dit niet te weten. Alles meelezen kost tokens; gericht lezen is de regel.
3. Elke andere map is alleen-lezen, behalve wat IN MIJN MAPPEN in het algemene blok toestaat. Herhaal die regels niet, verwijs ernaar met één zin. Werkt hij op verzoek van de gebruiker toch buiten zijn werkmap, dan zegt hij in één zin bij welke medewerker dat werk hoort en weigert hij niet; die zin staat in WAT JE BEHEERT.

About Me en de aanboddocumenten zijn voor elke medewerker alleen-lezen; alleen About Me Edits schrijft daar. Dat staat in het algemene blok en hoeft niet in de omschrijving.

## Stap 4: het gereedschap

Noem welke skills en koppelingen hij gebruikt. Bestaat het gereedschap nog niet, zet het op zijn lijst in plaats van de aanname uit te stellen. Eerst de rol, dan de skill.

## Stap 5: de delegatiegrenzen

Drie categorieën, elk met concrete voorbeelden uit zijn eigen werk. Vraag ernaar, gok niet: dit is precies waar iemand niet verrast wil worden.

- **AUTO**: doet hij zelfstandig.
- **ASK**: legt hij voor en wacht op akkoord. Alles wat naar buiten gaat valt hier standaard onder.
- **NEVER**: doet hij nooit, ook niet als het gevraagd lijkt te worden. Betalen, tekenen, abonnementen afsluiten of opzeggen.

Bij twijfel ASK. Verruimen kan alleen voor wat het algemene blok niet zelf onder ASK of NEVER zet: alles wat naar buiten gaat (mailen, publiceren, delen, een prijs of aanbod naar buiten brengen), verwijderen, verplaatsen en hernoemen blijven ASK, ook in de functieomschrijving. De begrippen akkoord en naar buiten staan in het algemene blok; herhaal ze niet.

## Stap 6: de functieomschrijving

Toon het concept, vraag wat er anders moet, lever daarna definitief. De delegatiegrenzen staan direct na de rol: het veld kapt van onderaf af. De vaste werkafspraken staan in het algemene blok en komen niet in de omschrijving.

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
Sluit af met: Alles buiten deze mappen is alleen-lezen, behalve wat IN MIJN
MAPPEN in mijn algemene instructies toestaat. Vraag ik je toch iets buiten je
werkmap te doen, zeg dan in één zin bij welke medewerker dat werk hoort en
doe het. Zie je elders iets dat niet klopt, meld het.]

CONTEXT & BRONNEN
[Welke mappen en bestanden je leest en waarvoor. Eén regel over de
Blueprints, door jou ingevuld op basis van de rol: "Van de Blueprints lees je
de writerversies in About Me/Blueprints/Writer" (contentrollen) of "de
coachversies in About Me/Blueprints/Coach" (alle andere rollen); de originelen
alleen bij detailwerk of op verzoek. De vakregels en de volledige bronnenlijst
staan in CLAUDE.md in je werkmap.]
```

Sluit af met:

1. "Kopieer dit blok en plak het in dit project onder Instructions (knop Edit). Ik kan dat veld niet zelf invullen."
2. De twee controles uit "Na het plakken".
3. Eén regel over wat deze medewerker als eerste kan oppakken, zodat zijn MEMORY en README meteen gaan leven.
4. Bij meer dan één medewerker tegelijk: neem ze één voor één aan en gebruik de eerste weken om te zien of de grenzen kloppen. Tien medewerkers die niets te doen hebben, is hetzelfde probleem als één vergaarbak.

## Stap 7: CLAUDE.md in de werkmap

Alles wat lang is van nature gaat hierheen. `CLAUDE.md` komt in de root van de werkmap, onder de 200 regels want het laadt in zijn geheel mee. Toon de volledige CLAUDE.md (koppen en letterlijke regels) samen met het concept van de functieomschrijving en maak hem pas aan na akkoord.

Alleen wat specifiek is voor deze werkmap. Herhaal niets uit het algemene blok (lees-, geheugen- en outputregels die overal gelden) en niets uit het instructieveld (rol, grenszin, wat hij beheert, delegatiegrenzen). Elke regel staat op één plek; wat op twee plekken staat, loopt uit elkaar.

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

Zeg er bij de oplevering in één zin bij dat CLAUDE.md via de LEESVOLGORDE in het algemene blok als eerste gelezen wordt in elke chat van dit project met gekoppelde map, zodat deze instructies niet in het instructieveld hoeven en dus niet afgekapt kunnen worden. In een chat zonder gekoppelde map wordt hij niet gelezen; dat is de eerste check als een medewerker zijn instructies niet lijkt te kennen. Test het meteen: nieuwe chat, "welke vakregels gelden hier?".

CLAUDE.md is geen momentopname. Wordt er later een werkafspraak gemaakt die élke keer geldt, dan komt hij met datum in MEMORY.md én stelt Claude de letterlijke regel voor CLAUDE.md voor; na akkoord zet hij hem erin. Dat staat in GEHEUGEN in het algemene blok uit stap 0. CLAUDE.md gaat boven MEMORY.md.

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

- Eén beheerder per werkmap, zoveel lezers als nodig. Anderen schrijven er alleen voor zover IN MIJN MAPPEN in het algemene blok dat toestaat.
- Elke werkmap krijgt bij aanmaak Output, Resources, README.md en MEMORY.md.
- In de root van een werkmap staan alleen README.md, MEMORY.md en CLAUDE.md.
- Verwijder of overschrijf nooit bestaande mappen of bestanden. Bestaat een map al, meld dat en vraag wat de gebruiker wil.
- README.md, MEMORY.md en CLAUDE.md houden altijd die naam; die herkent Claude zelf.
- In elk project is de complete hoofdmap (AI Library) gekoppeld. Alleen About Me Edits schrijft in About Me en in de aanboddocumenten, per wijziging na akkoord; dat project is geen medewerker.
- Een nieuwe hoofdmap komt er alleen met expliciet akkoord van de gebruiker.
- De werkafspraken en geheugenregels staan in het algemene blok. Herhaal ze niet in de projectomschrijving.
