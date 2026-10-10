# MailBlue structuurbestand

Laatst bijgewerkt: [datum]
Account: [naam van het MailBlue- of ActiveCampaign-account]

Dit bestand beschrijft hoe mijn MailBlue is ingericht. De MailBlue-skill leest het aan het begin van elke opdracht en past het alleen aan na een bevestigde wijziging. Regels toevoegen, veranderen of weghalen mag; het bestand opnieuw opbouwen uit MailBlue niet.

## Logboek
- [datum]: bestand aangemaakt

## Lijsten
Bron bij het opstellen: naam, ID, aantal actieve contacten, en het veld Lijstbeschrijving en de herinneringstekst van de lijst in MailBlue.
Twee groepen. Een lijst die hier niet staat, bestaat voor de skill niet.

1. In het dashboard (letterlijk het blok "Lijsten in het dashboard"):
| Lijst | ID | Rol | Actieve contacten op [datum] |
|---|---|---|---|
| [[KLANTEN] Programma A] | [id] | [klantenlijst programma A] | [aantal] |
| [[LEADS]] | [id] | [hoofdlijst leads] | [aantal] |

2. Wel in gebruik, niet in het dashboard (per lijst de rol en wanneer iemand erop komt):
| Lijst | ID | Rol | Iemand komt erop als |
|---|---|---|---|
| [[KLANTEN] Programma C] | [id] | [klantenlijst van een aanbod dat alleen nog als kassakoopje verkocht wordt] | [koopt het kassakoopje] |
| [[WAITLIST] Programma A] | [id] | [wachtlijst] | [schrijft zich in op de wachtlijstpagina] |

Regels:
- [bijv. iedereen staat op precies één programmalijst, altijd die van het hoogste programma]
- [bijv. bij een upgrade schrijft de upgrade-automation uit van de oude programmalijst]
- Een lijst met als omschrijving ARCHIEF in MailBlue loopt niet meer: niet voorstellen, niet meetellen, niemand op zetten

## Tags
Bron bij het opstellen: tagnaam, aantal contacten en het veld Omschrijving van de tag in MailBlue.
Groepen (voorvoegsels als ik die gebruik, anders de groepen uit "Mijn tags"):
| Groep of voorvoegsel | Wat erin hoort | Voorbeeld |
|---|---|---|
| [KLANT] | [heeft dit aanbod gekocht] | [[KLANT] Programma A] |
| [LEAD] | [heeft actie gedaan richting dit aanbod] | [[LEAD] Programma A] |
| [AANGEMELD] | [aangemeld voor een gratis event] | [[AANGEMELD] Masterclass X] |

Tags met een regel die ik moet onthouden:
| Tag | Regel |
|---|---|
| [[KLANT] Programma A] | [bijv. hier zitten ook de klanten van het openingsaanbod bij] |

Regels:
- Een tag met omschrijving ARCHIEF in MailBlue loopt niet meer: niet voorstellen, niet meetellen, niemand op zetten
- [bijv. een nieuwe tag krijgt altijd een voorvoegsel tussen blokhaken, of: nieuwe tags volgen de groepen hierboven]

## Mappen
Mappen heten in de koppeling labels. Een campagne of automation mag in meerdere mappen.

As 1, waarover:
| Map | Omschrijving | Nieuwe campagne of automation hoort hier als |
|---|---|---|
| [Programma A] | [alle mails over programma A] | [de mail over programma A gaat] |

As 2, soort:
| Map | Omschrijving | Nieuwe campagne of automation hoort hier als |
|---|---|---|
| [Nieuwsbrief] | [...] | [...] |
| [Promoties & Challenges] | [...] | [...] |

Regels:
- [bijv. campagnes van de laatste drie maanden staan in mappen, ouder niet]
- [bijv. mapnamen letterlijk overnemen, Claude filtert op de exacte naam]

## Segmenten
| Segment | Voorwaarde | Waarvoor |
|---|---|---|
| [CLAUDE] Actief op dashboardlijsten | status actief, op een van de dashboardlijsten | uniek totaal in het dashboard |
| [naam segment inactief] | [bijv. geen klik in 6 maanden] | vakje inactief in het dashboard |

## Templates
Campagnetemplates (naam in MailBlue begint met [TEMPLATE]):
| Soort | Doelgroep | Naam in MailBlue | Naamregel voor kopieën | Voorbeeld |
|---|---|---|---|---|
| [Blanco] | [Programma A] | [[TEMPLATE] Blanco Programma A] | [[Programma A] onderwerp] | [...] |
| [Day before] | [Programma A] | [[TEMPLATE] Day before Programma A] | [[Programma A] Day before naam event] | [...] |

Automationtemplates (inactief, in de map TEMPLATES):
| Soort | Naam in MailBlue | Start op | Wat erin zit |
|---|---|---|---|
| [verkoop en toegang] | [[TEMPLATE] Verkoop en toegang] | [tag] | [inschrijven op klantenlijst, welkomstmail, wachttijd, ...] |

## Naamregels
- Campagnes: [bijv. [Programma] soort, zoals [EVA HQ] Day before]
- Automations: [bijv. [VERKOOP], [VERKOOP & TOEGANG], [BEVESTIGING], [FUNNEL], [PROCES] gevolgd door het aanbod]
- Onderwerpregels: [bijv. ...]

## Definities
- Warme lead voor [aanbod]: iemand is warm als hij [actie]; in MailBlue te zien aan [tag of segment]
- Inactief contact: [bijv. geen klik in de laatste 6 maanden]; in MailBlue te zien aan [segment]
- KPI's die ik wil zien: [bijv. klikratio per soort mail, aantal actieve klanten per programma]

## Afspraken
Wat ik altijd zelf doe in MailBlue:
- tekst in de designer plakken (campagnes en automationmails)
- verzenden en inplannen
- mappen op campagnes zetten
- automations aanmaken, dupliceren, verwijderen, de starttrigger zetten, stappen toevoegen
- bulkwijzigingen op lijsten en contacten
- campagnes, automations, lijsten en contacten verwijderen: Claude markeert, ik verwijder (tags en stappen in een automation mag Claude verwijderen, na mijn ja per item)

Wat Claude nooit doet:
- [bijv. contacten uitschrijven zonder dat ik het per actie bevestig]
- [eigen aanvullingen]
