2025 - 15 - 02 15:31

tags: [[software-development]] [[computer science]]

progress: >>>

# Creating Snake in PyGame

voor het maken van de portfolio van school wil ik snake maken in pygame. om dit te doen start ik onderzoek naar hoe games werken en hoe ik in pygame moet werken

[[Snake]]

### Hoe werkt een game?
--------------------------------------------------------------------------

een game bestaat uit een aantal lagen. Neem bijvoorbeeld mario world. Een 2D platformer. Deze game bestaat uit een wereld, speler, en status bar. Deze lagen zijn in princiepe plaatjes die de computer een aantal keer per seconden laat zien, ==Dit heet een Game Loop==. 

Deze game loop bestaat niet alleen uit deze plaatjes want dan zou er niet zoveel gebeuren. Deze game loop heeft nog twee extra dingen nodig
- player input
>	om het programma te vertellen wat de speler wilt doen
- positie elementen
>	om bij te houden / te bepalen wat waar moet worden laten zien.

Zo'n game loop gebeurd in cycles. Iedere cycle is een frame. Werkend zou het er zo uit zien

- de speler drukt op "naar rechts"
- speler beweegt 5 pixels naar rechts
- het plaatje word geladen

 Dit gebeurd allemaal in een cycle. in princiepe zijn dit de basis elementen voor het maken van een game. Er zijn nog andere dingen die we eraan kunnen toevoegen zoals geluid en animaties om het meer als een spel te laten voelen maar in het kort is dit wat een game is.

### beginnen
net als bij het maken van een website of app, moeten wee een vieuw maken, wat de speler van het spel ziet. Dit doen we in PyGame door een scherm te maken met een desired with and height

`screen = pygame.display.set_mode((width, height))`

dit creeert een speelveld waarop we dalijk dingen kunnen gaan tekenen. We kunnen op dit scherm tekenen met Surfaces en Rectangles, en Rectangle kan verschillende vormen aannemen.

| draw a rectangle       | rect(surface, color, rect)                         |
| ---------------------- | -------------------------------------------------- |
| draw a polygon         | polygon(surface, color, points)                    |
| draw a circle          | circle(surface, color, center, radius)             |
| draw an ellipse        | ellipse(surface, color, rect)                      |
| draw an elliptical arc | arc(surface, color, rect, start_angle, stop_angle) |
| draw a straight line   | line(surface, color, start_pos, end_pos, width)    |

`   screen = pygame.display.set_mode((640, 480))   `
`+  clock = pygame.time.Clock()  `
`+  test_surface = pygame.Surface((100, 200))  `
`+  test_surface.fill((0, 0, 255))  `
`+  test_rect = pygame.rect.Rect(200, 200, 100, 100)  `

Clock geeft de mogelijkheid om het spel te limiteren op frames. Dit zorgt ervoor dat het soepel kan lopen op iederen computer

de `test_surface` is de blauwe rechthoek, hierin word aangegeven de grote van de rechthoek, de positionering word later aangegeven. `test_surface.fill` geeft de surface een kleurtje. 
`test_rect` is het rode vierkant. Hierin word eerst aangegeven de positie van he vierkant, daarna de grote. 

![[Pasted image 20250202191013.png]]

>`   screen.fill((pygame.color.THECOLORS['green']))   `
	geeft het speelveld een kleur
`+  pygame.draw.rect(screen, (255, 0 , 0), test_rect)  `


`+  screen.blit(test_surface, (200, 250))  `
`   pygame.display.update()   `


![[Pasted image 20250202192910.png | 500]]

![[Pasted image 20250202192946.png | 500]]

### Hoe snake werkt

.1) in princiepe maken we een grid, niet echt, maar we simuleren het. Omdat de hoeveelheid stappen je per keer kan zetten gelimiteerd is.

.2) in deze grid plaatsen we onze slang. Deze slang is een lijst met posities. Iedere positie is een block, en wat we doen om hem te bewegen is elke positie een richting in bewegen. 

## Het maken van het fruit
om een (bijvoorbeeld) appel te kunnen maken moeten we 2 dingen bepalen

>`class FRUIT:`
    `def __init__(self)`
        `# maak een random x en y positie voor de fruit`
        `# maak een fruit rect

in deze instantie word de positie van de appel gerandomised foor de 'random' module van python. De X en Y waardes geven aan tot waar de appel kan bewegen. `self.pos` is de som om deze twee values te combineren en een plek op de display te geven

>`class FRUIT:`
 `maak x en y positie voor de fruit`
    `def __init__(self):`
        `self.x = random.randint(0, cell_number - 1)`
        `self.y = random.randint(0, cell_number - 1)`
        `self.color = (255, 0, 0)`
        `self.pos = Vector2(self.x, self.y)`
    `# maak een functie om de fruit te tekenen`
    `def draw_fruit(self):`
        `fruit_rect = pygame.Rect(int(self.pos.x * cell_size),int(self.pos.y * cell_size), cell_size, cell_size)`
        `pygame.draw.rect(screen, self.color, fruit_rect)`
   

![[Pasted image 20250202202707.png|300]] ![[Pasted image 20250202211459.png | 300]]

## De slang

Op de rechter foto zien we de snake, dit is hoe de snake werkt 

>`class SNAKE:`
  >`def __init__(self):`
        `self.body = [Vector2(5, 10), Vector2(6, 10), Vector2(7, 10)]` 
        `self.direction = Vector2(1, 0) #` 
        `self.new_block = False`

`self.body` geeft de slang 3 blocken, De `vector2` class is deel van de `pygame.math` module die we gebruiken om 2D coordinaten op te slaan en te manipuleren in richting. 

>`def move_snake(self):`
        `body_copy = self.body[:-1] 
        `body_copy.insert(0, body_copy[0] + self.direction) 
        `self.body = body_copy
    
om de slang te laten bewegen, kopieren we de posities van de slang behalve het laatste block en voegen we er eentje toe aan de kop voor de volgende cycle. Zo beweegt de sang vooruit. 

>`if event.type == SCREEN_UPDATE:`
            snake.move_snake()

iedere keer dat het scherm update beweegt de slang met een block
## Movement

>`if event.type == pygame.KEYDOWN:`
            `if event.key == pygame.K_UP:`
                `snake.direction = Vector2(0, -1)`
            `if event.key == pygame.K_DOWN:`
                `snake.direction = Vector2(0, 1)`
            `if event.key == pygame.K_LEFT:`
                `snake.direction = Vector2(-1, 0)`
            `if event.key == pygame.K_RIGHT:`
                `snake.direction = Vector2(1, 0)`
            
wanneer de user een movement key indrukt word de `self.direction` van de vector aangepast naar de gepaste X/Y waarde. dit doen we in de 'main game loop', omdat in de main game loop constant word geluisterd voor events.

## Update class

>`class MAIN:`
    `def __init__(self):`
        `self.snake = SNAKE()`
        `self.fruit = FRUIT()`
    `def update(self):`
        `self.snake.move_snake()`
        `self.check_collision()`
    `def draw_elements(self):`
        `self.fruit.draw_fruit()`
        `self.snake.draw_snake()`
    
Ik heb een nieuwe class gemaakt om de game te updaten. Door het callen van `=SCREEN_UPDATE` word de `main_game.update` func geroepen die de `MAIN` class aanspreekt die vervolgends de slang beweegt en checkt of de slang zich op een positie bevind waar een appel is. Door het tekenen van de objecten ook meteen te verplaatsen naar deze class kunnen we in onze main game loop gewoon `main_game` oproepen om alles te laten werken.

## Yummy snack

>`def check_collision(self):`
        `if self.fruit.pos == self.snake.body[0]:`
            `print('collision')`
            `self.fruit.x = random.randint(0, cell_number - 1)`
            `self.fruit.y = random.randint(0, cell_number - 1)`
            `self.fruit.pos = Vector2(self.fruit.x, self.fruit.y)`
            `self.snake.new_block = True`

Deze function check basically of het hoofd van de slang `self.snake.body(0)`, (0) voor het eerste block , dus het hoofd. op dezelfde positie als de appel `self.fruit.pos` staat. Als dit gebeurt print de terminal collision en komt er een block bij de snake. 

Dit doen we heel makkelijk door wanneer de snake een appel eet de body nogsteeds te koppieren deze keer met het laatste block erbij.

## Death

Nu kan de snake bewegen en appels eten. De speler kan alleen nog niet afgaan. Dit willen we bereiken met twee manieren:
- de snake raakt zichzelf
- de snake raakt de border

>`def game_over(self):`
        `pygame.quit()`
        `sys.exit()`

Deze function word gecalled als de speler 'afgaat' deze sluit het programma af.

>`def check_fail(self):`
        `if not 0 <= self.snake.body[0].x < cell_number or not 0 <= self.snake.body[0].y < cell_number:`
            `self.game_over()`
>            
        `for block in self.snake.body[1:]:`
            `if block == self.snake.body[0]:`
                `self.game_over()`

het bovenste statements checkt of het hoofd van de slang `self.snake.body[0]` zich bevind binnen de `cell_number`, zo niet? game over.
tweede statement net zo simpel. Check of  een van de blocken achter het hoofd `self.snake.body[1]` `[1]` voor het opeenvolgende element na het hoofd `[0]` 
Het probleem nu is dat je jezelf kan instakillen door de tegenovergestelde richting die de slang in beweegt in te voeren.

>`if event.type == pygame.KEYDOWN:`
            `if event.key == pygame.K_UP`
                `if main_game.snake.direction.y != 1:`
                    `main_game.snake.direction = Vector2(0, -1)`

Door het plaatsen van deze extra if statement bij de user input (bijv.) bij naar beneden. kijkt de function of we niet de tegenovergestelde richting ingaat, zo niet. word de movement func uitgevoerd

## Sprites en Graphics

> `self.image = pygame.image.load("apple.png")  
        `self.image = pygame.transform.scale(self.image, (cell_size, cell_size))  
>
        `screen.blit(self.image, fruit_pos)  

Door dit stukje code toe te voegen aan de FRUIT class kunnen we een sprite over de FRUIT plaatsen. `transform.scale` zorgt ervoor dat ons plaatse dezelfde grote krijgt als een cell in de display. `screen.blit` zorgt ervoor dat de sprite op de goede plek word getekend.

Om een graphic aan de snake toe te voegen doen we een aantal dingen.
- we checken ieder block, die daarvoor en die erachter voor zijn status, hiermee kunnen we bepalen welk block te plaatsen op zijn plek. zodat we verschillende graphics kunnen plaatsen
dit kunnen we in princiepe berijken met een enorm if statement die alle states bijhoud en bekijkt









        
**Refrences**
--
