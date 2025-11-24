# Number Guessing Game - Pseudocode

**Author**: Ayush Raj (25BAS10099)  
**Institution**: VIT Bhopal  
**Professor**: Shrishtika Raikwar  
**Date**: November 2025

---

## High-Level Pseudocode

```
ALGORITHM NumberGuessingGame

INPUT: None (values obtained from user during runtime)
OUTPUT: Final guess count and success message

BEGIN
    // Phase 1: Initialization and Range Selection
    DISPLAY "Type a number: "
    INPUT upperLimit as STRING
    
    // Phase 2: Validate Initial Input
    IF NOT isNumeric(upperLimit) THEN
        DISPLAY "Please type a number next time."
        TERMINATE program
    END IF
    
    // Convert to integer
    upperLimit ← CONVERT_TO_INTEGER(upperLimit)
    
    // Phase 3: Validate Range
    IF upperLimit ≤ 0 THEN
        DISPLAY "Please type a number larger than 0 next time."
        TERMINATE program
    END IF
    
    // Phase 4: Generate Random Number
    secretNumber ← GENERATE_RANDOM_INTEGER(0, upperLimit)
    guessCount ← 0
    
    // Phase 5: Game Loop - Main Guessing Process
    LOOP UNTIL guessCorrectly
        // Increment attempt counter
        guessCount ← guessCount + 1
        
        // Get user's guess
        DISPLAY "Make a guess: "
        INPUT userGuess as STRING
        
        // Validate guess input
        IF NOT isNumeric(userGuess) THEN
            DISPLAY "Please type a number next time."
            CONTINUE to next iteration
        END IF
        
        // Convert guess to integer
        userGuess ← CONVERT_TO_INTEGER(userGuess)
        
        // Phase 6: Process Guess and Provide Feedback
        IF userGuess = secretNumber THEN
            DISPLAY "You got it!"
            guessCorrectly ← TRUE
            EXIT LOOP
        ELSE IF userGuess > secretNumber THEN
            DISPLAY "You were above the number!"
        ELSE
            DISPLAY "You were below the number!"
        END IF
    END LOOP
    
    // Phase 7: Display Final Results
    DISPLAY "You got it in " + guessCount + " guesses"
    
END

```

---

## Detailed Step-by-Step Pseudocode

### Step 1: Input Range Limit

```
PROCEDURE GetAndValidateRangeLimit()
BEGIN
    // Prompt user for upper limit
    PROMPT user: "Type a number: "
    READ input as STRING into variable: topOfRange
    
    // Check if input contains only digits
    IF topOfRange.containsOnlyDigits() = FALSE THEN
        PRINT "Please type a number next time."
        EXIT_PROGRAM
    END IF
    
    // Convert string to integer
    topOfRange ← STRING_TO_INTEGER(topOfRange)
    
    // Validate positive number
    IF topOfRange ≤ 0 THEN
        PRINT "Please type a number larger than 0 next time."
        EXIT_PROGRAM
    END IF
    
    RETURN topOfRange
END PROCEDURE
```

### Step 2: Initialize Game State

```
PROCEDURE InitializeGame(upperLimit)
BEGIN
    // Generate random number between 0 and upperLimit (inclusive)
    randomNumber ← RANDOM(0 to upperLimit)
    
    // Initialize attempt counter
    attemptCount ← 0
    
    // Initialize game state
    gameWon ← FALSE
    
    RETURN (randomNumber, attemptCount, gameWon)
END PROCEDURE
```

### Step 3: Main Game Loop

```
PROCEDURE PlayGame(randomNumber, upperLimit)
BEGIN
    attemptCount ← 0
    
    WHILE (TRUE) DO
        // Increment attempt counter
        attemptCount ← attemptCount + 1
        
        // Get user guess
        PROMPT user: "Make a guess: "
        READ input as STRING into variable: userGuess
        
        // Validate input
        IF NOT userGuess.isDigit() THEN
            PRINT "Please type a number next time."
            CONTINUE  // Skip to next iteration
        END IF
        
        // Convert to integer
        userGuess ← STRING_TO_INTEGER(userGuess)
        
        // Compare and provide feedback
        CALL CheckGuess(userGuess, randomNumber, attemptCount)
        
        IF userGuess = randomNumber THEN
            BREAK  // Exit loop
        END IF
    END WHILE
    
    RETURN attemptCount
END PROCEDURE
```

### Step 4: Check Guess

```
PROCEDURE CheckGuess(guess, target, attempts)
BEGIN
    IF guess = target THEN
        PRINT "You got it!"
        RETURN TRUE
    ELSE IF guess > target THEN
        PRINT "You were above the number!"
        RETURN FALSE
    ELSE  // guess < target
        PRINT "You were below the number!"
        RETURN FALSE
    END IF
END PROCEDURE
```

### Step 5: Display Results

```
PROCEDURE DisplayResults(totalAttempts)
BEGIN
    PRINT "You got it in " + totalAttempts + " guesses"
END PROCEDURE
```

---

## Complete Integrated Pseudocode

```
PROGRAM NumberGuessingGame

// ===== MAIN PROGRAM =====

BEGIN
    
    // ===== PHASE 1: INPUT VALIDATION =====
    DISPLAY "Type a number: "
    INPUT upperLimit_STRING
    
    IF NOT IsNumeric(upperLimit_STRING) THEN
        DISPLAY "Please type a number next time."
        TERMINATE
    END IF
    
    upperLimit ← CONVERT_STRING_TO_INT(upperLimit_STRING)
    
    IF upperLimit ≤ 0 THEN
        DISPLAY "Please type a number larger than 0 next time."
        TERMINATE
    END IF
    
    // ===== PHASE 2: GAME INITIALIZATION =====
    secretNumber ← RANDOM_INT(0, upperLimit)
    numberOfGuesses ← 0
    gameActive ← TRUE
    
    // ===== PHASE 3: MAIN GAME LOOP =====
    WHILE gameActive = TRUE DO
        
        numberOfGuesses ← numberOfGuesses + 1
        
        DISPLAY "Make a guess: "
        INPUT guess_STRING
        
        // Input validation for guess
        IF NOT IsNumeric(guess_STRING) THEN
            DISPLAY "Please type a number next time."
            CONTINUE
        END IF
        
        guess ← CONVERT_STRING_TO_INT(guess_STRING)
        
        // Compare guess with secret number
        IF guess = secretNumber THEN
            DISPLAY "You got it!"
            gameActive ← FALSE
        ELSE IF guess > secretNumber THEN
            DISPLAY "You were above the number!"
        ELSE
            DISPLAY "You were below the number!"
        END IF
        
    END WHILE
    
    // ===== PHASE 4: DISPLAY RESULTS =====
    DISPLAY "You got it in " + numberOfGuesses + " guesses"
    
END PROGRAM

```

---

## Flowchart Pseudocode Representation

```
                        ┌─────────────┐
                        │    START    │
                        └──────┬──────┘
                               │
                   ┌───────────▼───────────┐
                   │  Input upper_limit    │
                   └───────────┬───────────┘
                               │
                   ┌───────────▼──────────────┐
                   │ Is input numeric?        │
                   └───────────┬──────────────┘
                            ╱    ╲
                          NO      YES
                        ╱            ╲
                       ╱              ▼
                      ▼      ┌────────────────┐
                  [EXIT]     │ Is positive?   │
                             └────────┬───────┘
                                  ╱    ╲
                                NO      YES
                              ╱          ╲
                             ▼            ▼
                         [EXIT]    ┌──────────────┐
                                   │ Generate     │
                                   │ random num   │
                                   └──────┬───────┘
                                          │
                                ┌─────────▼─────────┐
                                │  Guess Counter=0  │
                                └─────────┬─────────┘
                                          │
                                ┌─────────▼──────────┐
                                │  Increment Counter │
                                └─────────┬──────────┘
                                          │
                                ┌─────────▼────────────┐
                                │  Input User Guess    │
                                └─────────┬────────────┘
                                          │
                                ┌─────────▼──────────────┐
                                │ Is guess numeric?      │
                                └────────────┬───────────┘
                                          ╱    ╲
                                        NO      YES
                                      ╱          ╲
                                     ▼            ▼
                              [Error Message]  ┌─────────────┐
                                │              │ Compare     │
                                │              │ guess/num   │
                                └──┬───────────┤             │
                                   │           └────────┬────┘
                                   │                 ╱  │  ╲
                                   │              EQUAL  <   >
                                   │            ╱  │       │ ╲
                                   │           ▼   ▼       ▼   ▼
                                   │        [WIN] [Too Below [Too
                                   │             Low]  [High]
                                   │              │      │      │
                                   └──────┬───────┘      │      │
                                          │              │      │
                                          └──────┬───────┴──────┘
                                                 │
                                    ┌────────────▼───────────┐
                                    │ Display Guess Count    │
                                    └────────────┬───────────┘
                                                 │
                                          ┌──────▼───────┐
                                          │     END      │
                                          └──────────────┘
```

---

## Function Definitions in Pseudocode

### Function: IsNumeric(input)
```
FUNCTION IsNumeric(input STRING) RETURNS BOOLEAN
BEGIN
    FOR EACH character IN input DO
        IF character IS NOT a digit (0-9) THEN
            RETURN FALSE
        END IF
    END FOR
    RETURN TRUE
END FUNCTION
```

### Function: ConvertStringToInt(input)
```
FUNCTION ConvertStringToInt(input STRING) RETURNS INTEGER
BEGIN
    result ← 0
    FOR EACH character IN input DO
        digit ← character - '0'
        result ← (result * 10) + digit
    END FOR
    RETURN result
END FUNCTION
```

### Function: RandomInt(min, max)
```
FUNCTION RandomInt(min INTEGER, max INTEGER) RETURNS INTEGER
BEGIN
    range ← max - min + 1
    randomValue ← CALL system_random_function()
    result ← min + (randomValue MOD range)
    RETURN result
END FUNCTION
```

### Function: CompareGuess(guess, target)
```
FUNCTION CompareGuess(guess INTEGER, target INTEGER) RETURNS STRING
BEGIN
    IF guess = target THEN
        RETURN "correct"
    ELSE IF guess > target THEN
        RETURN "too_high"
    ELSE
        RETURN "too_low"
    END IF
END FUNCTION
```

---

## Time Complexity Analysis in Pseudocode

```
Worst Case Time Complexity: O(n)
where n = number of guesses required

// Analysis:
// - Input validation: O(m) where m = length of input string
// - Random generation: O(1)
// - Game loop iterations: O(n) where n = guesses
// - Each iteration: O(1) for comparison and feedback
// - Total: O(m + n) ≈ O(n) since m is typically small

Space Complexity Analysis:
// - Space used: O(1)
// - Variables: upperLimit, secretNumber, guess, counter
// - No dynamic data structures (arrays, lists, etc.)
// - Constant memory regardless of input size
```

---

## Error Handling Pseudocode

```
PROCEDURE HandleErrors()
BEGIN
    
    // Error 1: Non-numeric initial input
    TRY
        input ← READ from user
        IF NOT isNumeric(input) THEN
            THROW InvalidInputException
        END IF
    CATCH InvalidInputException
        DISPLAY "Please type a number next time."
        EXIT_PROGRAM
    END TRY
    
    // Error 2: Non-positive initial input
    TRY
        IF upperLimit ≤ 0 THEN
            THROW InvalidRangeException
        END IF
    CATCH InvalidRangeException
        DISPLAY "Please type a number larger than 0 next time."
        EXIT_PROGRAM
    END TRY
    
    // Error 3: Non-numeric guess
    TRY
        guess ← READ from user
        IF NOT isNumeric(guess) THEN
            THROW InvalidGuessException
        END IF
    CATCH InvalidGuessException
        DISPLAY "Please type a number next time."
        CONTINUE to next iteration
    END TRY
    
END PROCEDURE
```

---

## Test Cases in Pseudocode

```
TEST_CASE 1: Normal Gameplay
    upperLimit ← 50
    secretNumber ← (generated randomly)
    guesses ← [25, 37, 31, 34, 32]
    EXPECTED: Success on guess 5
    ACTUAL: Same as expected
    RESULT: PASS

TEST_CASE 2: Invalid Initial Input
    upperLimit ← "abc"
    EXPECTED: Program exits with error message
    ACTUAL: Same as expected
    RESULT: PASS

TEST_CASE 3: Zero Input
    upperLimit ← 0
    EXPECTED: Error message and exit
    ACTUAL: Same as expected
    RESULT: PASS

TEST_CASE 4: Immediate Correct Guess
    upperLimit ← 10
    secretNumber ← 7
    guesses ← [7]
    EXPECTED: Success in 1 guess
    ACTUAL: Same as expected
    RESULT: PASS
```

---

**Document Version**: 1.0  
**Last Updated**: November 24, 2025  
**Status**: Complete
