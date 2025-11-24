# Number Guessing Game

## Project Information
- **Institution**: VIT Bhopal
- **Course**: Computer Science and Engineering
- **Professor**: Shrishtika Raikwar
- **Student Name**: Ayush Raj
- **Registration Number**: 25BAS10099
- **Project Title**: Interactive Number Guessing Game in Python
- **Date**: November 2025

---

## Overview

The **Number Guessing Game** is an interactive Python application that implements a classic guessing game where the user attempts to identify a randomly generated number within a user-defined range. The application provides real-time feedback to guide the user toward the correct answer while keeping track of the number of attempts.

This project demonstrates fundamental programming concepts including:
- Input validation and error handling
- Random number generation
- Control flow (loops and conditionals)
- User interaction and feedback mechanisms

---

## Features

✓ **Dynamic Range Selection**: User defines the upper limit for the random number range
✓ **Input Validation**: Robust validation for user inputs with appropriate error messages
✓ **Real-time Feedback**: Immediate hints indicating if the guess is too high or too low
✓ **Guess Counter**: Tracks and displays the total number of attempts made
✓ **Error Handling**: Gracefully handles invalid inputs and provides user-friendly messages
✓ **Interactive Gameplay**: Continuous game loop until the correct number is guessed

---

## How to Run

<img width="1387" height="679" alt="Screenshot 2025-11-24 233351" src="https://github.com/user-attachments/assets/c2de2226-2cfd-4050-8bef-1445ddb8e250" />

<img width="567" height="271" alt="Screenshot 2025-11-24 233407" src="https://github.com/user-attachments/assets/f59a6c51-dcb8-458c-9d03-a25277a5cacb" />

### Output
<img width="1262" height="185" alt="Screenshot 2025-11-24 230251" src="https://github.com/user-attachments/assets/65d12988-3d98-4b2a-968f-fa786de6b4f3" />

### Prerequisites
- Python 3.x installed on your system
- Basic command-line/terminal knowledge

### Execution Steps

1. **Save the script** as `guessing_game.py`

2. **Open terminal/command prompt** in the directory containing the file

3. **Run the script**:
   ```bash
   python guessing_game.py
   ```

4. **Follow the on-screen prompts**:
   - Enter a positive number for the upper limit
   - Make guesses and receive feedback
   - Try to identify the number with minimum attempts

---

## Game Workflow

```
START
  ↓
Input upper range limit
  ↓
Validate input (positive integer?)
  ↓
Generate random number (0 to upper_limit)
  ↓
Initialize guess counter = 0
  ↓
GAME LOOP:
  - Increment guess counter
  - Get user guess
  - Validate input
  - Check if guess equals random number
    ├─ YES → Display success, exit loop
    ├─ NO → Check if guess > random number
    │        ├─ YES → Print "Too high"
    │        └─ NO → Print "Too low"
  ↓
Display total guesses
  ↓
END
```

---

## Sample Gameplay

```
Type a number: 50
Make a guess: 25
You were below the number!
Make a guess: 37
You were above the number!
Make a guess: 31
You were below the number!
Make a guess: 34
You were above the number!
Make a guess: 32
You got it!
You got it in 5 guesses
```

---

## Code Structure

The program consists of three main sections:

1. **Initialization Phase**: Accepts and validates the upper range limit
2. **Game Loop Phase**: Manages user guesses and provides feedback
3. **Completion Phase**: Displays the final result with attempt count

---

## Technical Details

| Aspect | Details |
|--------|---------|
| **Language** | Python 3 |
| **Key Library** | `random` module |
| **Input Method** | User command-line input |
| **Validation** | String-to-integer conversion with `isdigit()` |
| **Loop Type** | Infinite loop with break condition |

---

## Learning Outcomes

This project reinforces key programming concepts:
- ✓ Conditional statements (`if-elif-else`)
- ✓ Loop structures (`while` loops)
- ✓ Input validation and error handling
- ✓ Built-in functions and methods
- ✓ Program flow control
- ✓ User interface design

---

## Possible Enhancements

1. **Difficulty Levels**: Easy (1-10), Medium (1-100), Hard (1-1000)
2. **Maximum Guess Limit**: Limit attempts and display "Game Over" message
3. **Score System**: Award points based on guesses taken
4. **Play Again Option**: Loop to allow multiple games
5. **Hint System**: Provide distance hints (e.g., "Within 10 of target")
6. **Game Statistics**: Track wins, losses, best attempts
7. **GUI Implementation**: Convert to graphical interface using tkinter
8. **Leaderboard**: Store and display high scores

---

## Files Included

- `guessing_game.py` - Main Python script
- `README.md` - Project overview and usage guide
- `DOCUMENTATION.md` - Detailed technical documentation
- `PSEUDOCODE.md` - Algorithm pseudocode
- `PROBLEM_STATEMENT.md` - Project requirements and specifications
- `FLOWCHART.md` - Visual program flow representation

---

## Author

**Ayush Raj**  
Registration Number: 25BAS10099  
VIT Bhopal  
CSE Department

---

## Submission Date

November 24, 2025

---

## Acknowledgments

This project was developed as part of the Python Programming course under the supervision of Professor Shrishtika Raikwar at VIT Bhopal.

---

**For questions or clarifications, please contact the instructor or refer to the attached documentation files.**
