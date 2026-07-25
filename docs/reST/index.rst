import pygame
import sys

# Initialize pygame
pygame.init()

# Screen size
WIDTH = 600
HEIGHT = 400

screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("My First Python Game")

# Colors
WHITE = (255, 255, 255)
BLUE = (0, 0, 255)

# Player
x = 300
y = 200
size = 50
speed = 5

# Game loop
while True:
    # Events
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    # Keyboard controls
    keys = pygame.key.get_pressed()

    if keys[pygame.K_LEFT]:
        x -= speed
    if keys[pygame.K_RIGHT]:
        x += speed
    if keys[pygame.K_UP]:
        y -= speed
    if keys[pygame.K_DOWN]:
        y += speed

    # Fill screen
    screen.fill(WHITE)

    # Draw player
    pygame.draw.rect(screen, BLUE, (x, y, size, size))

    # Update display
    pygame.display.update()
