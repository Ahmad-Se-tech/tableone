---
layout: post
search_exclude: true
permalink: /booleansconditionals
---

# Booleans and Conditionals Lesson

## What Are Booleans?

Booleans are one of the simplest but most powerful data types in programming. A boolean can only have two values: `true` or `false`.

Think of booleans like light switches - they're either ON (true) or OFF (false). There's no in-between!

### Creating Boolean Variables
```javascript
let isGameActive = true;
let hasLost = false;
let isPlayerAlive = true;
```

### Boolean Values from Comparisons

Most of the time, we get boolean values by comparing things:
```javascript
let score = 85;
let highScore = 100;

let isPassing = score >= 60;  // true
let isPerfect = score === 100;  // false
let needsImprovement = score < highScore;  // true
```

## Comparison Operators

These operators compare values and return `true` or `false`:

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `===` | Equal to | `5 === 5` | `true` |
| `!==` | Not equal to | `5 !== 3` | `true` |
| `>` | Greater than | `10 > 5` | `true` |
| `<` | Less than | `3 < 8` | `true` |
| `>=` | Greater than or equal | `5 >= 5` | `true` |
| `<=` | Less than or equal | `4 <= 3` | `false` |

### Practice Example
```javascript
let playerHealth = 75;
let enemyHealth = 50;

console.log(playerHealth > enemyHealth);  // true
console.log(playerHealth === 100);  // false
console.log(enemyHealth <= 50);  // true
```

## Logical Operators

Logical operators let us combine multiple boolean values:

### AND (`&&`) - Both must be true
```javascript
let hasKey = true;
let doorUnlocked = false;

let canEnter = hasKey && doorUnlocked;  // false (need BOTH)
```

### OR (`||`) - At least one must be true
```javascript
let hasGold = true;
let hasSilver = false;

let hasReward = hasGold || hasSilver;  // true (need at least ONE)
```

### NOT (`!`) - Flips the value
```javascript
let isDay = true;
let isNight = !isDay;  // false

let gameOver = false;
let canPlay = !gameOver;  // true
```

### Combining Logical Operators
```javascript
let level = 5;
let hasWeapon = true;
let health = 80;

// Can fight boss if level 5+ AND has weapon AND health above 50
let canFightBoss = (level >= 5) && hasWeapon && (health > 50);
console.log(canFightBoss);  // true
```

## Conditionals (If Statements)

Conditionals let your code make decisions based on boolean values.

### Basic If Statement
```javascript
let score = 95;

if (score >= 90) {
    console.log("You got an A!");
}
```

### If-Else Statement
```javascript
let health = 30;

if (health > 50) {
    console.log("You're healthy!");
} else {
    console.log("You need healing!");
}
```

### If-Else If-Else Chain
```javascript
let score = 75;

if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 80) {
    console.log("Grade: B");
} else if (score >= 70) {
    console.log("Grade: C");
} else {
    console.log("Grade: F");
}
```

## Game Example: Player Status Checker

Let's create a function that checks player status in a game:
```javascript
function checkPlayerStatus(health, hasShield, enemiesNearby) {
    if (health <= 0) {
        console.log("Game Over!");
    } else if (health < 30 && !hasShield && enemiesNearby > 0) {
        console.log("DANGER! Find cover and heal!");
    } else if (health < 50) {
        console.log("Warning: Low health");
    } else if (hasShield && enemiesNearby > 3) {
        console.log("Ready for battle!");
    } else {
        console.log("All systems normal");
    }
}

// Test it out
checkPlayerStatus(25, false, 2);  // "DANGER! Find cover and heal!"
checkPlayerStatus(80, true, 5);   // "Ready for battle!"
checkPlayerStatus(100, true, 0);  // "All systems normal"
```

## Practice Exercises

### Exercise 1: Simple Comparisons
Create variables and use comparison operators to check:
- Is the player's level greater than 10?
- Does the player have exactly 100 coins?
- Is the enemy's health less than or equal to 0?

### Exercise 2: Door Lock System
Write code that checks if a player can open a door. The door opens if:
- Player has the key OR
- Player's strength is greater than 50

### Exercise 3: Power-Up Eligibility
Create a function that determines if a player can get a power-up:
- Player must have score >= 100
- Player must NOT already have a power-up active
- Player must have completed level 3 or higher

## Common Mistakes to Avoid

1. **Using `=` instead of `===`**
```javascript
   // WRONG
   if (score = 100) { }  // This assigns, doesn't compare!
   
   // RIGHT
   if (score === 100) { }
```

2. **Forgetting parentheses with logical operators**
```javascript
   // WRONG
   if (level >= 5 && hasWeapon || health > 50) { }
   
   // RIGHT
   if ((level >= 5 && hasWeapon) || health > 50) { }
```

3. **Writing redundant code**
```javascript
   // WRONG
   if (isAlive === true) { }
   
   // RIGHT
   if (isAlive) { }
```

## Key Takeaways

- Booleans are `true` or `false` values - like on/off switches
- Comparison operators (`===`, `>`, `<`, etc.) return boolean values
- Logical operators (`&&`, `||`, `!`) combine boolean values
- If statements let your code make decisions based on conditions
- Always use `===` for comparison, not `=`

## Next Steps

Try building a simple game mechanic using booleans and conditionals, like:
- A health system that displays warnings at different health levels
- A door system that requires certain conditions to open
- A scoring system with different messages for different score ranges