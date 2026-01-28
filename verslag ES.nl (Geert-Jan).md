---
topic: software-docu
---

 2025 - 10 - 27 10:39

tags: [[Embedded Systems]]

progress: >

# verslag embedded

**Verslag: Onderzoek naar leeftijdsverdeling sociale huurwoningen en gegevensverwerking slimme meters**

**1. Inleiding**

In dit onderzoek wordt gekeken naar twee hoofdonderwerpen:

1.

De leeftijdsverdeling binnen sociale huurwoningen in Nederland.

2.

De praktische stappen voor het verwerken van energiedata via slimme meters (P1 en P4), inclusief autorisatie en samenwerking met partijen zoals Enexis.

Daarnaast wordt kort aandacht besteed aan concurrentieanalyse en de opbouw van een toekomstig platform dat deze data kan verwerken.

⸻

**2. Leeftijdsverdeling binnen sociale huurwoningen**

Uit het rapport _De sociale staat van Nederland 2018_ (Sociaal en Cultureel Planbureau) blijkt dat in 2015 ongeveer **0,427 miljoen van de 0,4896 miljoen huishoudens** in sociale huurwoningen een referentiepersoon hadden tussen de **18 en 34 jaar**. Dit komt neer op ongeveer **87%** van deze groep binnen de sociale huursector.

Bron: [SCP – De sociale staat van Nederland 2018](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdigitaal.scp.nl%2Fssn2018%2Fwonen%2F&data=05%7C02%7C516889%40vistacollege.nl%7Cfc5ef397ed2147ca178c08de1535cd10%7Cfeb69ed2ab8f43da966dd7d6248b769e%7C0%7C0%7C638971517989989669%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=7Zm1N1Kt0MmCf49Jm92CVwuk8lLCuMQ1EbaXhMwF%2B54%3D&reserved=0)

In de _Staat van de Volkshuisvesting 2024_ wordt aangegeven dat in 2021 de mutatie (verandering van huurders) binnen corporatiewoningen als volgt was verdeeld:

•

**27%** ging naar ouderen,

•

**16%** naar studenten,

•

**6%** naar vergunninghouders,

•

**51%** naar overige woningzoekenden.

Bron: [Staat van de Volkshuisvesting 2024 (Ministerie van BZK)](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.volkshuisvestingnederland.nl%2Fbinaries%2Fvolkshuisvestingnederland%2Fdocumenten%2Fpublicaties%2F2025%2F01%2F20%2Fstaat-van-de-volkshuisvesting-2024%2FStaat_van-de_Volkshuisvesting_2024.pdf&data=05%7C02%7C516889%40vistacollege.nl%7Cfc5ef397ed2147ca178c08de1535cd10%7Cfeb69ed2ab8f43da966dd7d6248b769e%7C0%7C0%7C638971517990010372%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=gsQBP2Z6XIkOQ40V4jMfzSh3tCovobJEslpNiCtNRB0%3D&reserved=0)

**Uitwerking**

Deze cijfers laten zien dat jongeren en studenten nog steeds een groot aandeel hebben in de sociale huursector, maar dat ook ouderen een groeiend deel van de huurmarkt innemen. Dit is belangrijk voor toekomstig beeld voor het doelgroep.

⸻

**3. Praktische uitvoering bij behalen van een MVP**

Bij het ontwikkelen van een **Minimum Viable Product (MVP)** zal de focus liggen op de technische implementatie van data-integratie vanuit slimme meters en de bijbehorende autorisatieprocessen.

De volgende stappen worden ondernomen:

1.

**Op zoek naar geautoriseerde leveranciers en beheerders**

2.

**P4-dataverwerking en frequentie van data-aanlevering onderzoeken**

De P4-interface van slimme meters levert gedetailleerde meetdata met een hoge frequentie (vaak elke 10 seconden). Onderzoek moet aantonen welke dataintervallen geschikt zijn voor opslag, analyse en visualisatie binnen het MVP.

3.

**Onderzoek naar autorisatie**

Autorisatie verloopt via het **Slimme Meter Autorisatieproces**, dat gereguleerd wordt door **DSMR** (Dutch Smart Meter Requirements) en het **CIEK/Netbeheer Nederland**-afsprakenstelsel.

Hierbij ontvangt de gebruiker meestal een **autorisatielink of code** om zijn slimme meter te koppelen aan de applicatie.

_Uitwerking:_

Dit autorisatieproces is vergelijkbaar met hoe een app toegang vraagt tot je Google-account: de gebruiker geeft expliciet toestemming om gegevens (in dit geval energieverbruik) te delen. Zo wordt privacy gewaarborgd en wordt ongeoorloofde toegang voorkomen.

⸻

**4. Type meters in Nederland**

In Nederland zijn er twee hoofdtypen meters:

•

**Digitale meters** (niet-communicerend)

•

**Slimme meters** (communicerend via P1 of P4)

Volgens [Netbeheer Nederland](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.netbeheernederland.nl%2Fslimme-meter%2Fslimme-meter-veelgestelde-vragen&data=05%7C02%7C516889%40vistacollege.nl%7Cfc5ef397ed2147ca178c08de1535cd10%7Cfeb69ed2ab8f43da966dd7d6248b769e%7C0%7C0%7C638971517990024300%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=%2Fq33VH8Sx0MJm7057PPzw8NfwOwLxUold5tXwPtcrkQ%3D&reserved=0) heeft ongeveer **90% van de Nederlandse huishoudens** inmiddels een slimme meter geïnstalleerd.

Deze meters sturen automatisch meterstanden door aan de netbeheerder, wat zorgt voor **nauwkeurigere facturering** en **beter inzicht in energieverbruik**.

**Uitwerking**

De slimme meter is een cruciaal onderdeel van de energietransitie. Door automatische dataoverdracht kunnen zowel consumenten als netbeheerders energieverbruik beter monitoren, wat helpt bij energiebesparing en netbalancering.

⸻

**5. Bezoek aan Enexis**

Een bezoek aan **Enexis** zal plaatsvinden om meer inzicht te krijgen in:

•

De manier waarop zij P4-data verwerken en beveiligen.

•

Hoe hun interne autorisatie- en validatieproces verloopt.

•

Welke API’s of tools beschikbaar zijn voor ontwikkelaars om data te integreren.

Dit bezoek is belangrijk om te bepalen welke technische eisen en beveiligingsnormen het MVP moet naleven.

⸻

**6. Concurrentieonderzoek**

Er is sprake van veel concurrentie op het gebied van **P1-apps** die “gratis” data uitlezen via de P1-poort van de slimme meter.

Deze apps tonen vaak:

•

Actueel energieverbruik.

•

Historische verbruiksdata.

•

Vergelijkingen en bespaartips.

Maar ook

- Dataverkoop 
- Gepersonaliseerde advertenties

⸻

**7. Conclusie**

Dit onderzoek combineert demografische inzichten in sociale huurwoningen met een technische verkenning van energiedata-integratie.

De resultaten tonen aan dat jongeren een belangrijk aandeel hebben in sociale huur, terwijl de technische kant aantoont dat slimme meters en veilige autorisatieprocessen essentieel zijn voor betrouwbare dataverwerking.

Het project kan zich onderscheiden door P4-data te benutten en samenwerking met partijen als Enexis te versterken.
**Refrences**
--
