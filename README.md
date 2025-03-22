# piano
import pygame
pygame.init()
screen = pygame.display.set_mode((800,400))
pygame.display.set_caption("Piano 🎹")

keyboard_img = pygame.image.load("piano/piano 1.png")
keyboard_img = pygame.transform.scale(keyboard_img,(800,400))

key_sounds = {
    pygame.K_a: "piano/piano notes 1/WhatsApp Audio 2025-03-12 at 22.06.23_ba621e35.wav",
    pygame.K_s: "piano/piano notes 1/WhatsApp Audio 2025-03-12 at 22.07.11_e13d13b0.wav",
    pygame.K_d: "piano/piano notes 1/WhatsApp Audio 2025-03-12 at 22.07.55_4a7781d9.wav",
    pygame.K_f: "piano/piano notes 1/WhatsApp Audio 2025-03-12 at 22.08.12_e8d80a8c.wav",
    pygame.K_g: "piano/piano notes 1/WhatsApp Audio 2025-03-12 at 22.09.30_a97ddadb.wav",
    pygame.K_h: "piano/piano notes 1/WhatsApp Audio 2025-03-12 at 22.10.18_1d207bb5.wav",
    pygame.K_j: "piano/piano notes 1/WhatsApp Audio 2025-03-12 at 22.10.40_083d2b30.wav",
    pygame.K_k: "piano/piano notes 1/WhatsApp Audio 2025-03-12 at 22.10.56_ee98ad95.wav"   
}
 
sounds = {key: pygame.mixer.Sound(Sound) for key,Sound in key_sounds.items() }

key_pressed = False

running = True
while running:
    screen.blit(keyboard_img, (0, 0))
    pygame.display.update()
            
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        elif event.type == pygame.KEYDOWN:
            if event.key in sounds:
                 sounds[event.key].play()
pygame.quit()                
