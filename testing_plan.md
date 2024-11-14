# Flappy Neon Cat Test Plan

## Part 1. Unit Testing the Game Mechanics

**Description:**  
Unit tests for core mechanics like character movement, jumping, and collision detection.

**Actions:**  
- **Movement**: Verify that tapping or pressing a key causes the neon cat to jump, updating its vertical position correctly.
- **Gravity**: Ensure the cat moves down at a constant rate when no input is provided.
- **Collision Detection**: Test that collisions with obstacles are detected accurately, and the game ends upon collision.

**Test Cases:**

| Test Case               | Test Data              | Expected Outcome                                          |
|-------------------------|------------------------|-----------------------------------------------------------|
| Jump input              | Key tap or press       | Cat moves upward by a fixed distance                      |
| Gravity simulation      | No input               | Cat continuously moves down at a set speed                |
| Collision with obstacle | Cat at obstacle coords | Game ends, "Game Over" screen displays                    |
| Edge boundaries         | Top and bottom screen  | Cat does not go off-screen, stops at boundaries           |

---

## Part 2. Logic Testing the Game Rules and Calculations

**Description:**  
Testing scoring and point calculations, ensuring accurate progression based on player actions.

**Actions:**  
- **Score Calculation**: Ensure score increments when the cat passes obstacles.
- **Game Restart**: Confirm score resets to zero upon restarting.
- **Difficulty Scaling**: Test for consistent difficulty scaling by increasing obstacle speed or frequency.

**Test Cases:**

| Test Case                    | Test Data                       | Expected Outcome                                     |
|------------------------------|---------------------------------|------------------------------------------------------|
| Obstacle pass score increment| Cat passes obstacle             | Score increases by 1                                 |
| Restart score reset          | Start new game                  | Score resets to 0                                    |
| Difficulty scaling           | Time played                     | Speed of obstacles gradually increases over time     |

---

## Part 3. Boundary Testing: Edge Cases and Limits

**Description:**  
Tests to ensure that the game functions properly under extreme conditions.

**Actions:**  
- **Max Score**: Check behavior when the maximum score limit is reached.
- **Screen Boundaries**: Confirm the cat cannot go off-screen.
- **Obstacle Density**: Test game stability with a high frequency of obstacles.

**Test Cases:**

| Test Case               | Test Data                          | Expected Outcome                                      |
|-------------------------|------------------------------------|-------------------------------------------------------|
| Maximum score           | Score reaches max display limit    | Score freezes at max display (e.g., 9999)             |
| Screen boundaries       | Cat at top/bottom of screen       | Cat is restricted to screen bounds                    |
| Obstacle frequency      | High obstacle frequency           | Game remains stable without crashes                   |

---

## Part 4. Integration Testing: System Interaction

**Description:**  
Ensures interaction between UI, gameplay mechanics, and other systems functions as expected.

**Actions:**  
- **Score and Gameplay Interaction**: Verify the score updates during gameplay without impacting game flow.
- **Menu and Gameplay State**: Confirm that starting the game from the menu initializes game state correctly.
- **Collision and Game Over Screen**: Ensure collision triggers game over and score displays correctly.

**Test Cases:**

| Test Case                  | Test Data             | Expected Outcome                                     |
|----------------------------|-----------------------|------------------------------------------------------|
| Score update on obstacle   | Cat passes obstacle   | Score updates without lag or freezing                |
| Game Start from menu       | Click "Start" button  | Initializes game, resets score, and removes menu     |
| Collision triggers game over| Cat hits obstacle    | Displays "Game Over" screen with final score         |

---

## Part 5. Handling Bad Input and Run-Time Errors

**Description:**  
Ensures the game can handle unexpected or incorrect input, maintaining stability.

**Actions:**  
- **Invalid Key Press**: Test for ignored invalid key inputs.
- **Infinite Loop Avoidance**: Verify no inputs can cause the game to freeze or enter a loop.
- **Game Over Handling**: Ensure game ends gracefully and allows the player to restart or exit.

**Test Cases:**

| Test Case                  | Test Data              | Expected Outcome                                      |
|----------------------------|------------------------|-------------------------------------------------------|
| Invalid key input          | Keys other than jump   | Game ignores input without errors                     |
| High-speed obstacles       | Very high difficulty   | Game continues to run smoothly without freezing       |
| Game Over handling         | Collision with obstacle| Displays "Game Over" with options to restart or exit  |

---

## Part 6: Summary Table

| Test Case                   | Test Data               | Expected Outcome                                     |
|-----------------------------|-------------------------|------------------------------------------------------|
| Jump input                  | Key tap or press        | Cat moves upward by a fixed distance                 |
| Gravity simulation          | No input                | Cat moves downward continuously                      |
| Collision with obstacle     | Cat at obstacle coords  | Game ends and shows "Game Over"                      |
| Obstacle pass score increment | Cat passes obstacle  | Score increases by 1                                 |
| Max score                   | Score reaches max limit | Score remains constant at max value                  |
| Invalid input               | Keys other than jump    | Input ignored without game errors                    |
| Difficulty scaling          | Continuous play         | Obstacle speed increases over time                   |


