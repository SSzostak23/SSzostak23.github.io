# Sszostak23.github.io
Hello there! I'm Szymon, a first-year cybersecurity student at AGH University in Cracow.

Hobbies:
Sport, Reading, Coding, Travel

Fav Drinks:
Green Tea

Here's some of my code:
           
    class SNAKE():
    def __init__(self):
        self.body = [Vector2(5, 10), Vector2(4, 10), Vector2(3, 10)]
        self.direction = Vector2(1,0)
        self.newBlock = False
        self.score = 0  # Dodana zmienna do śledzenia zjedzonych jabłek

    def drawSnake(self):
        for snakePart in self.body:
            # tworzenie jednej części węża
            snakeRect = pygame.Rect(int(snakePart.x * cellSize), int(snakePart.y * cellSize), cellSize, cellSize)
            # rysowanie pojedynczej cześci węża
            pygame.draw.rect(gameScreen, (79, 60, 45), snakeRect)

    def moveSnake(self):

        if self.newBlock == True: # jesli trafiamy na jablko to waz sie wydluza
            bodyCopy = self.body[:]
            self.newBlock = False
        else: # jesli nie trafiamy na jablko to waz nie moze zmienic dlugosci
            bodyCopy = self.body[:-1]

        bodyCopy.insert(0,bodyCopy[0] + self.direction)
        # update ciala weza
        self.body = bodyCopy[:]

    def addBlock(self):
        self.newBlock = True
        self.score += 1  # Zwiększenie liczby zjedzonych jabłek

    class APPLE:
    def __init__(self):
        # tworzenie losowych pozycji x i y, żeby owoc nie wychodził poza zakres okna programu
        self.randomize()

    def drawFruit(self):
        # tworzenie owocu w kształcie kwadratu o szerokości jednego okna siatki w losoych pozycjach na siatce
        fruitRect = pygame.Rect(int(self.position.x * cellSize), int(self.position.y * cellSize), cellSize,
                                cellSize)  # int bo self.position.x będzie typu float
        # rysowanie owocu
        pygame.draw.rect(gameScreen, (150, 17, 17), fruitRect)

    def randomize(self):
        self.x = random.randint(0, cellNumber - 1)
        self.y = random.randint(0, cellNumber - 1)
        self.position = Vector2(self.x, self.y)
                     
      

GitHub Profile
GitHub: SSzostak23

© 2024 SSzostak23.github.io. All rights reserved.
