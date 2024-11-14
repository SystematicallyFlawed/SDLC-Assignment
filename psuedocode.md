### Flappy Neon Cat Pseudocode

1. **Start**  
   - Initialize game variables:
     - Set `currentScore = 0`
     - Set `gameState = "start screen"`
     - Load assets (neon cat character, obstacles, background, etc.)

2. **Input**  
   - Player taps or presses a key to make the neon cat jump.

3. **Process**  
   - **Game Start Screen**:
     - Display "Flappy Neon Cat" title and "Start" button.
     - If player selects "Start Game":
       - Set `gameState = "playing"`
     - If player selects "Exit Game":
       - End game
   - **Gameplay Loop (while gameState == "playing")**:
     - Move the neon cat character downward (simulate gravity).
     - Check for player input to make the cat jump.
     - Move obstacles from right to left across the screen.
     - **Collision Detection**:
       - If neon cat collides with an obstacle:
         - Set `gameState = "end screen"`
         - Store `finalScore = currentScore`
       - If neon cat clears an obstacle:
         - Increase `currentScore` by 1.
   - **End Screen**:
     - Display "Game Over" and final score.
     - Show options to "Restart" or "Exit Game."
     - If player selects "Restart":
       - Reset `currentScore = 0`
       - Set `gameState = "start screen"`
     - If player selects "Exit Game":
       - End game

4. **Output**  
   - Display `currentScore` during gameplay.
   - Display "Game Over" and `finalScore` at the end screen.

5. **End**  
   - Program terminates when player selects "Exit Game" from the end screen.
