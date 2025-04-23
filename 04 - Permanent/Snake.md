2025 - 15 - 02 15:31

tags: [[software-development]] [[computer science]]

progress: >>>

# Creating Snake in PyGame

voor het maken van de portfolio van school wil ik snake maken in pygame. om dit te doen start ik onderzoek naar hoe games werken en hoe ik in pygame moet werken

### Hoe werkt een game?

---

een game bestaat uit een aantal lagen. Neem bijvoorbeeld mario world. Een 2D platformer. Deze game bestaat uit een wereld, speler, en status bar. Deze lagen zijn in princiepe plaatjes die de computer een aantal keer per seconden laat zien, ==Dit heet een Game Loop==.

Deze game loop bestaat niet alleen uit deze plaatjes want dan zou er niet zoveel gebeuren. Deze game loop heeft nog twee extra dingen nodig

- player input

> om het programma te vertellen wat de speler wilt doen

- positie elementen

> om bij te houden / te bepalen wat waar moet worden laten zien.

Zo'n game loop gebeurd in cycles. Iedere cycle is een frame. Werkend zou het er zo uit zien

- de speler drukt op "naar rechts"
- speler beweegt 5 pixels naar rechts
- het plaatje word geladen

Dit gebeurd allemaal in een cycle. in princiepe zijn dit de basis elementen voor het maken van een game. Er zijn nog andere dingen die we eraan kunnen toevoegen zoals geluid en animaties om het meer als een spel te laten voelen maar in het kort is dit wat een game is.

### beginnen

net als bij het maken van een website of app, moeten wee een vieuw maken, wat de speler van het spel ziet. Dit doen we in PyGame door een scherm te maken met een desired with and height

```python
screen = pygame.display.set_mode((width, height))
```

dit creeert een speelveld waarop we dalijk dingen kunnen gaan tekenen. We kunnen op dit scherm tekenen met Surfaces en Rectangles, en Rectangle kan verschillende vormen aannemen.

|draw a rectangle|rect(surface, color, rect)|
|---|---|
|draw a polygon|polygon(surface, color, points)|
|draw a circle|circle(surface, color, center, radius)|
|draw an ellipse|ellipse(surface, color, rect)|
|draw an elliptical arc|arc(surface, color, rect, start_angle, stop_angle)|
|draw a straight line|line(surface, color, start_pos, end_pos, width)|

```python
screen = pygame.display.set_mode((640, 480))   
clock = pygame.time.Clock()  
test_surface = pygame.Surface((100, 200))  
test_surface.fill((0, 0, 255))  
test_rect = pygame.rect.Rect(200, 200, 100, 100)  
```

Clock geeft de mogelijkheid om het spel te limiteren op frames. Dit zorgt ervoor dat het soepel kan lopen op iederen computer.

de `test_surface` is de blauwe rechthoek, hierin word aangegeven de grote van de rechthoek, de positionering word later aangegeven. `test_surface.fill` geeft de surface een kleurtje. `test_rect` is het rode vierkant. Hierin word eerst aangegeven de positie van he vierkant, daarna de grote.

```python
screen.fill((pygame.color.THECOLORS['green']))   
pygame.draw.rect(screen, (255, 0 , 0), test_rect)
screen.blit(test_surface, (200, 250))  
pygame.display.update()   
```

### Hoe snake werkt

1. in princiepe maken we een grid, niet echt, maar we simuleren het. Omdat de hoeveelheid stappen je per keer kan zetten gelimiteerd is.
    
2. in deze grid plaatsen we onze slang. Deze slang is een lijst met posities. Iedere positie is een block, en wat we doen om hem te bewegen is elke positie een richting in bewegen.
    

## Het maken van het fruit

om een (bijvoorbeeld) appel te kunnen maken moeten we 2 dingen bepalen

```python
class FRUIT:
    def __init__(self):
        # maak een random x en y positie voor de fruit
        # maak een fruit rect
```

in deze instantie word de positie van de appel gerandomised foor de 'random' module van python. De X en Y waardes geven aan tot waar de appel kan bewegen. `self.pos` is de som om deze twee values te combineren en een plek op de display te geven.

```python
class FRUIT:
    def __init__(self):
        self.x = random.randint(0, cell_number - 1)
        self.y = random.randint(0, cell_number - 1)
        self.color = (255, 0, 0)
        self.pos = Vector2(self.x, self.y)

    def draw_fruit(self):
        fruit_rect = pygame.Rect(int(self.pos.x * cell_size), int(self.pos.y * cell_size), cell_size, cell_size)
        pygame.draw.rect(screen, self.color, fruit_rect)
```

## De slang

```python
class SNAKE:
    def __init__(self):
        self.body = [Vector2(5, 10), Vector2(6, 10), Vector2(7, 10)] 
        self.direction = Vector2(1, 0) 
        self.new_block = False
```

## Movement

```python
if event.type == pygame.KEYDOWN:
    if event.key == pygame.K_UP:
        snake.direction = Vector2(0, -1)
    if event.key == pygame.K_DOWN:
        snake.direction = Vector2(0, 1)
    if event.key == pygame.K_LEFT:
        snake.direction = Vector2(-1, 0)
    if event.key == pygame.K_RIGHT:
        snake.direction = Vector2(1, 0)
```

## Sprites en Graphics

```python
self.image = pygame.image.load("apple.png")
self.image = pygame.transform.scale(self.image, (cell_size, cell_size))
screen.blit(self.image, fruit_pos)
```

Door dit stukje code toe te voegen aan de FRUIT class kunnen we een sprite over de FRUIT plaatsen.
--
