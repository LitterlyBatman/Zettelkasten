---
topic: software-docu
---

 2025 - 12 - 09 12:36

tags: [[Gesprek Geert-Jan Embedded]]

progress: >

# P1 data Embedded

Rapport: Integratie van P4- en P1-gegevens in Home Assistant

Inleiding

In Nederland beschikken slimme meters over verschillende manieren om meetgegevens uit te lezen. De meest bekende zijn: 
    •    P1-poort: een fysieke aansluiting op de slimme meter die via het DSMR-protocol actuele elektriciteits- en gasstanden doorgeeft.
    •    P4-kanaal: de route waarbij energieleveranciers of geautoriseerde partijen via het centrale systeem (EDSN/CAS) meetgegevens kunnen opvragen. Dit is meestal geaggregeerde data (per kwartier of dag), die door de leverancier beschikbaar wordt gesteld. 

Steeds meer huishoudens willen deze gegevens koppelen aan Home Assistant (HA) om zo inzicht te krijgen in hun energieverbruik, om te sturen op kosten of om te automatiseren.

⸻

Wat Home Assistant standaard biedt

Home Assistant is een krachtig platform met veel integraties en componenten. Belangrijke mogelijkheden op het gebied van energie zijn:
    1.    Energy Dashboard
    •    Ondersteuning voor elektriciteitsimport, elektriciteitsexport en gasverbruik.
    •    Visualisatie per dag, week, maand en jaar.
    •    Kostenberekening op basis van dynamische of vaste tarieven.
    2.    Integraties voor P1 / DSMR
    •    Officiële DSMR-integratie voor Nederlandse en Belgische meters.
    •    Community-projecten zoals SlimmeLezer (ESPHome), HomeWizard P1 Meter of P1 Monitor.
    3.    Automatiseringen en waarschuwingen
    •    Mogelijkheid om meldingen te sturen bij overschrijding van drempels (bijvoorbeeld >5 kW voor meer dan 5 minuten).
    •    Combinatie met andere sensoren (temperatuur, aanwezigheid, tijdschema’s) om het energieverbruik actief te beïnvloeden.

⸻

Wat Home Assistant niet standaard heeft

Hoewel Home Assistant veel functionaliteit biedt, heeft het geen ingebouwde machine learning (ML) of patroonherkenning om automatisch gewoontes te leren of verbruik te voorspellen. Concreet betekent dit:
    •    Er is geen out-of-the-box AI die historische gegevens analyseert en voorspellingen doet.
    •    Er is geen standaard anomaliedetectie die automatisch waarschuwt bij afwijkend verbruik.
    •    Voor gedragsanalyse of slimme adviezen moet men externe tooling gebruiken.

⸻

Externe ML en data-analyse

Om toch patronen en voorspellingen te realiseren zijn er meerdere opties:
    1.    Externe opslag en analyse
    •    Data vanuit HA naar een database (bijv. InfluxDB) en visualiseren/analyseren met Grafana.
    •    Toepassen van Python-modellen (bijv. Prophet, TensorFlow, scikit-learn) om voorspellingen te genereren.
    2.    Feedback naar Home Assistant
    •    De resultaten van externe ML-modellen worden teruggestuurd naar HA als virtuele sensoren (via MQTT of REST).
    •    Deze sensoren kunnen vervolgens weer in het Energy Dashboard of in automatiseringen gebruikt worden.

⸻

Hoe de data in Home Assistant komt

1. Via de P1-poort
    •    Directe koppeling met de slimme meter via USB of een ESPHome-apparaat.
    •    Near real-time gegevens (elektriciteit elke seconde, gas vaak per uur).

2. Via het P4-kanaal (energieleverancier)
    •    Energieleverancier of een derde partij vraagt de data op en stelt dit beschikbaar via een API of portal.
    •    Een brug (bijv. een ESP, Raspberry Pi of script) haalt deze gegevens op en publiceert ze in HA, meestal via:
    •    REST-sensoren in Home Assistant.
    •    MQTT-sensoren via een broker.

3. Historische imports
    •    Voor analyse of dashboards kan historische data vanuit een extern systeem (bijv. leverancier of EDSN-export) worden geïmporteerd in HA.
    •    Dit gebeurt vaak via community-scripts of maatwerkautomatisering.


**Refrences**
--
