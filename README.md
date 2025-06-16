# chrome-dino-amazonqcli

Ever found yourself without internet and playing that addictive Chrome dinosaur game? I decided to recreate this classic
using Python and Pygame, but with a twist - I built it entirely with the help of Amazon Q CLI, Amazon's AI assistant.

## What I Built and Why

I recreated the Chrome dinosaur game that appears when you're offline, but with several enhancements:

• A dinosaur character that can jump over obstacles and duck under flying birds
• Multiple types of obstacles (cacti and pterodactyls)
• Day/night cycle that changes the background
• Lives system with heart icons
• Power-ups that give extra lives
• Score tracking and high score memory
• Sound effects for jumping, scoring, and game over
• Pause functionality

I chose this project because it's a recognizable game with straightforward mechanics, making it perfect for testing
Amazon Q's capabilities in game development. Plus, who doesn't love the Chrome dino?

## How Amazon Q CLI Helped Me

Amazon Q CLI was instrumental throughout the development process:

1. Initial Code Structure: With a simple prompt, Amazon Q generated the basic game structure using Pygame, setting up the
window, game loop, and core mechanics.

2. Graphics Creation: Instead of requiring external assets, Amazon Q created all game graphics programmatically using
Pygame's drawing functions, generating dinosaur animations, obstacles, and UI elements.

3. Game Logic: Amazon Q implemented collision detection, scoring systems, and the increasing difficulty curve that makes
the game challenging.

4. Advanced Features: When I asked for enhancements, Amazon Q added features like the lives system, power-ups, and day/
night cycle without requiring extensive explanations.

5. Debugging: When we encountered issues with file structure, Amazon Q quickly identified and fixed the problems.

## My Prompts and How I Improved Them

### Initial Prompt
My journey started with a simple request:

`I want you to make a good dino game as in chrome using pygame library`


This gave me a basic working game, but I wanted more.

### Refining the Prompts
I improved my results by being more specific about what I wanted:

`yes please get better graphics`


This led to more detailed sprite designs and animations.

For additional features, I simply said:

`yes please`


And Amazon Q understood I wanted more game elements, adding power-ups, lives system, and sound effects.

## AI Struggles and Solutions

We did face some challenges:

1. File Structure Issues: When enhancing the game, we encountered problems with the file organization. Amazon Q
recognized this and created a completely new, properly structured file.

2. Sound Implementation: Creating sound effects programmatically was tricky, but Amazon Q implemented a clever solution
using Pygame's sound array functionality to generate audio without external files.

3. Complex Graphics: While Amazon Q couldn't create photorealistic graphics, it cleverly used simple shapes and
animations to create recognizable and functional game elements.

## The Final Result

The final game includes:

• Smooth dinosaur animations for running, jumping, and ducking
• Multiple obstacle types with varying difficulty
• Visual effects like day/night cycle and blinking invincibility
• Sound effects for game actions
• Score tracking and high score memory
• Lives system with heart icons and power-ups
• Pause functionality

Here's what the gameplay looks like:


![Dino Game](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hlar5rsxftzuclx7knv2.png)



![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/b53xryf7ts3vyya1ntd5.png)
## Code Highlights

One of the most impressive aspects was how Amazon Q implemented the dinosaur's movement system:


```
python
def update(self, user_input):
    if self.dead:
        self.image = self.dead_img
        return`

    if self.running:
        self.run()
    if self.ducking:
        self.duck()
    if self.jumping:
        self.jump()

    if self.step_index >= 10:
        self.step_index = 0

    if (user_input[pygame.K_UP] or user_input[pygame.K_SPACE]) and not self.jumping:
        self.jumping = True
        self.running = False
        self.ducking = False
        if jump_sound:
            jump_sound.play()
    elif user_input[pygame.K_DOWN] and not self.jumping:
        self.ducking = True
        self.running = False
        self.jumping = False
    elif not (user_input[pygame.K_DOWN] or self.jumping):
        self.running = True
        self.ducking = False
        self.jumping = False

```

## Conclusion

Building this game with Amazon Q CLI demonstrated how AI can accelerate game development, even for someone without
extensive Pygame experience. The assistant not only wrote functional code but also implemented creative solutions and
game design elements.

What impressed me most was how Amazon Q understood the context of the Chrome dinosaur game and recreated its essence
while adding new features that enhanced the gameplay. The entire development process was conversational and iterative,
allowing me to refine the game step by step.

If you're interested in game development or exploring what AI assistants can do, I highly recommend giving Amazon Q CLI
a try. It's not just about writing code—it's about collaborative creation.

## Next Steps

If you'd like to try the game yourself, the complete code is available here. Feel free to
modify it and add your own features!

