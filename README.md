# coockie-click
Juego de hacerle click a una galleta
import pygame
import sys

pygame.init()


WIDTH, HEIGHT = 600, 400
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Galleta Clicker")

# Colores
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)

font = pygame.font.SysFont(None, 36)

try:
    player_image = pygame.image.load("img/galleta.png")
except:
    print("'img/galleta.png'. ()
    sys.exit()

player_image = pygame.transform.scale(player_image, (150, 150))

player_rect = player_image.get_rect(center=(WIDTH // 2, HEIGHT // 2))

score = 0

def draw_text(text, pos):
    img = font.render(text, True, BLACK)
    screen.blit(img, pos)


running = True
while running:
    screen.fill(WHITE)

    screen.blit(player_image, player_rect)

    draw_text(f"Galletas: {score}", (20, 20))

 
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        
        if event.type == pygame.MOUSEBUTTONDOWN:
            if player_rect.collidepoint(event.pos):
                score += 1

    
    pygame.display.flip()

pygame.quit()
sys.exit()
