### Selecteren van de benodigde HTML-elementen

Deze sectie selecteert alle benodigde HTML-elementen die in de rest van het script worden gebruikt. Dit omvat het doolhof, de speler, de thuisbasis, emoji, en de bedieningsknoppen.

### Constantes en variabelen voor het spel

Deze sectie definieert verschillende constante waarden en variabelen die belangrijk zijn voor het spel, zoals de grootte van de stappen, de grootte van het bewegende object, de breedte van de muren, en de afmetingen van het doolhof.

### Arrays voor obstakels

Hier worden arrays gedefinieerd die de posities van de obstakels in het doolhof opslaan.



### Variabelen voor swipe en scroll

Hier worden drempelwaarden gedefinieerd voor swipe- en scrollbewegingen.

### Genereer de zijkanten van het doolhof en stel de startpositie in

Deze sectie roept de functie `genSides()` aan om de zijkanten van het doolhof te genereren en stelt de startpositie van de speler en de thuisbasis in.

### Bereken de afmetingen van het doolhof en maak een rooster

Hier wordt het rooster (grid) voor het doolhof gemaakt, waarbij elke cel informatie bevat over de mogelijke richtingen en of de cel al bezocht is.

### Richtingen en aanpassingen voor Recursieve Terugtrekking

Deze sectie definieert de mogelijke richtingen waarin de speler kan bewegen en hoe deze bewegingen de coördinaten beïnvloeden.

### Genereer en teken het doolhof

Deze sectie roept de functies `genMaze()` en `drawMaze()` aan om het doolhof te genereren en te tekenen.

### Haal alle barrières op en sla hun posities op

Hier worden alle elementen met de klasse "barrier" opgehaald en hun posities opgeslagen in de arrays voor obstakels.

### Event listeners voor toetsenbordinvoer en knoppen

Deze sectie voegt event listeners toe voor de pijltoetsen en de knoppen, zodat de speler kan bewegen.

### Beweegfuncties

Deze functies (`up()`, `down()`, `left()`, `right()`) zorgen ervoor dat de speler in de juiste richting beweegt en controleren of de beweging geldig is.

### Functies om de grenzen te controleren

Deze functies (`checkXboundry()`, `checkYboundry()`) controleren of de speler binnen de grenzen van het doolhof blijft en niet door een obstakel beweegt.

### Genereer en configureer de zijkanten van het doolhof

Deze sectie genereert de zijmuren van het doolhof en stelt de start- en eindposities van de speler in.

### Configuratie van zij-elementen

Deze functie configureert de eigenschappen van de zijmuren.

### Maze generatie algoritme met behulp van Recursieve Terugtrekking

Deze functie (`genMaze()`) genereert het doolhof met behulp van het algoritme van Recursieve Terugtrekking.

### Teken het doolhof

Deze functie (`drawMaze()`) tekent de muren van het doolhof op basis van het gegenereerde rooster.

### Teken een muur in het doolhof

Deze functie (`drawWall()`) tekent een enkele muur op een specifieke positie.

### Functie om een array te schudden

Deze functie (`shuffleArray()`) schudt de richtingen om willekeurigheid te creëren bij het genereren van het doolhof.

### Animatie voor de knopdruk

Deze functie (`animKeys()`) zorgt voor een visuele feedback wanneer een knop wordt ingedrukt.

### Functie voor toetsenevenementen

Deze functie (`keys()`) handelt de pijltoetsen af en roept de bijbehorende beweegfuncties aan.

### Bijwerken van de emoji (positief of negatief) op basis van de richting

Deze functie (`updateEmo()`) update de emoji op basis van de afstand van de speler tot de thuisbasis.

