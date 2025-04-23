 2024 - 13 - 18 13:24

tags: [[School]] [[workshop]]  [[computer science]] 

progress: 

# Workshop INT, STRING, FLOAT


De hierboven geschreven termen hebben allemaal te maken met het opslaan van data. Het begint allemaal bij bits and bytes en hoe we data binair opslaan met 1tjes en 0lletjes. 

bits worden gebruikt om cijfers op te slaan zodat de computer het programma kan berekenen.

1 bit kan een waarde aannemen. positief of negatief. 
1 byte kan 8 bits opslaan
1 byte kan 255 cijfers oplsaan (256 0 meegeteld)
2 bytes kunnen 65,025 cijfers opslaan
4 bytes kunnen 4.228.250.625 cijfers opslaan
^ dit is een INT
een INT gebruikt 4 bytes

opeens gaat dat best snel met cijfertjes. dit komt door dat je het aantal cijfers dat kan worden opgeslagen in de bits steeds verdubbeld. een byte kan 255 cijfers opslaan dus dat betekend dat 4 bytes, 255x255x255x255 is. aangezien bij iedere bit de datacap word verdubbeld betekend dit dat wanneer je 1 bit van de reeks verwijderd. het getal van 4mljrd meteen terug valt naar 2mlrjd. 

een computer kan niet lezen en kan alleen maar cijfertjes verwerken. dit betekend dus dat alle data ook in cijfertjes moet worden omgezet/opgeslagen. Hierbij is het belangrijk om te onthouden dat 1 INT, 1 cijfer kan opslaan. dit betekend dat voor het opslaan van cijfer 1 je 4 bytes nodig hebt.
het cijfer 100 gebruikt ineens 12 bytes. Je kan je dus voorstellen dat het opslaan van een zin met meer dan 3 letters al gouw heel veel bytes kan gebruiken. 

je computer werkt door de code die invoert in je API te compilen van "mensen taal" naar "computer taal" de 1tjes en 0lletjes dus. deze worden gevoerd aan de CPU en de computer 
berekend wat deze ermee moet doen. Voordat de computer het programma opened berekend hij hoeveel data het programma gaat gebruiken en reserveerd hij deze ruimte. Is de ruimte niet beschikbaar kan het programma dus ook niet opslaan. daarom is het belangrijk dat je oplet hoeveel data je gebruikt en welke data types je gebruikt om slordigheid te voorkomen

Om deze slordigheid te voorkomen zijn er verschillende data types ontwikkeld. Dingen zoals een INT kan 4 bytes opslaan. dit is dus ideaal voor kleine cijfers en enkele cijfers. moet je grotere dingen opslaan kun je kijken naar STRINGS en FLOATS. een STRING gebruikt bijvoorbeeld 16bytes, hierin kun je dus veel makkelijker een en efficienter een zin opslaan.

![[Pasted image 20240307144348.png]]


**Refrences**
--
