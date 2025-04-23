 2025 - 17 - 16 17:38

tags: [[Bliep!]]

progress: >

# Bliep Docenten Website

De docenten krijgen toegang tot een website die gekoppeld is aan de API. Op deze website kunnen zij:  
- **Ziekmeldingen van leerlingen bekijken**  
- **Een uitgerolde lijst van de aanwezigheid van leerlingen inzien**  
- **Gegevens van leerlingen aanpassen**  

Om deze functionaliteiten uit te voeren, zijn de volgende functies nodig: 

(honorable mention)
Voor het weergeven van de status moet het systeem kunnen zien of een student is ziekgemeld of aanwezig is. dit betekend dat een function moet kunnen aangeven of een student:
- aanwezig is doormiddel van check-in_time te bekijken
- afwezig is doormiddel van check-out_time te bekijken
- een return op een absentie request: positief of negatief. om te oordelen of deze student is afgemeld

---

## Functionaliteiten voor de Admin Website  

### 1. **Login Systeem**  
- **Beveiligde login**: Alleen accounts met de correcte autoriteit krijgen toegang.  
	-Input: student en wachtoord
	-Output: toegang

- **Wachtwoord reset**: Optie voor admins om hun wachtwoord opnieuw in te stellen.  
	-input: request en studentID
	-output: ResetPass()
	
- **Uitlog functie**: Docenten moeten kunnen uitloggen.  
	-input: button
	-output: end session

---

### 2. **Aanwezigheidslijst**  

een docent kan bij de absentie meting een lijst genereren, deze lijst toont de leerlingen en hun informatie en of zei aanwezig zijn, hoelaat zij zich hebben ingecheckt / uitgecheckt. En of de leerling zich heeft afgemeld of niet.

Deze lijst toont:  
- Laatst **in- of uitgecheckte tijd**.  
- **Persoonlijke data**:  
  - Naam  
  - Cohort  
  - Serienummer  
  - Datum  

#### Weergave van de status:  
De aanwezigheid wordt visueel weergegeven met gekleurde bolletjes vooraan de lijst:  
- 🟢 **Groen**: Aanwezig  
- 🔴 **Rood**: Afwezig  
- 🔴 **Geel:** Te laat
- 🔵 **Blauw**: Absent  

De standaard regel weergeven bij het aanvragen van de lijst is:
Status . name() . studentID() . cohort() . datum()

---

### 3. **Beheerfunctionaliteiten voor docenten**  
Docenten kunnen:  
- Studenten **toevoegen**  
- Studenten **verwijderen**  
- Studenten **gegevens aanpassen**:  
  - Opleiding  
  - Cohort  
  - Naam  
  - ID  

Daarnaast kunnen docenten een lijst aanvragen en deze filteren op:  
- **Status**: Aanwezig, afwezig of absent  
- **Naam**  
- **Cohort**  
- **Opleiding**  
- **Student ID**  


# Front - End design Docenten website

De user zal landen op de homepage en gegroet worden met de toepasselijke aanspreking. 

Aan de rechter kant van het scherm bevind zich het navigatie menu:
> Home / Dashboard
> Overview
> Edit
> Profile
> Logout
> 

---

# Functionele Behoeften Studenten App  

De app bestaat uit ~4 schermen in totaal. Het stats scherm, Home scherm, De profiel pagina en de absentie pagina.

.1) het stats scherm
> 	dit scherm weergeeft een overzicht van de data van de student. Dit is data die het systeem heeft opgepikt zoals:
> 		- Hoeveel uur in totaal een student aanwezig is geweest
> 		- hoeveel procent van het totaal de student aanwezig is geweest
> 		- de absentie medlingen 
> 		- afgehandeld of ongeoorloofde afhandelingen

.2) het home scherm
>	op dit scherm kan een student of zei zijn ingechekt, hoelaat zei dat voor het laatst hebben gedaan, hetzelfde geld voor afwezigheid.
>		- hierbij worden de get attendence functions gebruikt

.3) profiel pagina
>	dit scherm bevat een overzicht van de persoonlijke informatie gebruikt in de database van bliep. ook een notificatie bak 


### 1. **Login Systeem**  
- **Beveiligde login**: Alleen accounts met de correcte autoriteit krijgen toegang.  
- **Wachtwoord reset**: Optie voor studenten om hun wachtwoord opnieuw in te stellen.  
- **Uitlog functie**: Studenten moeten kunnen uitloggen.  

### **2.Verwerking van Aanwezigheidstijd  

Om de **Get (Attendance)**-gegevens goed te verwerken, is een script nodig dat het volgende laat zien:  
- **Totaal aantal uren aanwezig**  
  - Per **dag**  
  - Per **week**  
  - Per **jaar**  

---

## Functionaliteiten  

### 1. **Overzicht en rapportage**  
Het systeem moet de volgende gegevens tonen:  
- **Absentiemeldingen**  
- **Urenoverzicht**  
- **Percentage van de aanwezige uren**  
- **Niet-geregistreerde tijd**  

---

### 2. **E-mailfunctionaliteit**  
Studenten moeten een eenvoudige mogelijkheid hebben om een e-mail te sturen naar een standaardadres dat wordt beheerd door de docenten.  

#### Details van de e-mailfunctie:  
- **Eenvoudig te implementeren**  
- Het adres wordt centraal beheerd door de docenten.  



**Refrences**
--
