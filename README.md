# **JavaScript: The Tricky Parts**

[outcomes-js-tricky-parts-starter-code.zip](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0b81d5f4-d3f9-4629-8be9-6c5177e070cc/outcomes-js-tricky-parts-starter-code.zip)

## **Part 1: JavaScript Trivia**

Read through the questions in this list of [JavaScript interview questions](https://www.toptal.com/javascript/interview-questions). Answers are provided, but try to answer the questions on your own first.

## **Part 2: Closure Exercises**

Solve the following JavaScript problems using closure. Tests are provided.

**Guessing Game**

Write a function called ***guessingGame*** which returns a function that allows you to guess a random whole number between 0 and 99. Every time you create a new game, it should select a *new* random number, and keep it secret from the player.

Once the game has started, you can guess the number. The game should tell you whether your guess is too high, too low, or correct.

After a correct guess, the game ends.

```jsx
let game = guessingGame();
game(50); // "50 is too low!"
game(90); // "90 is too high!"
game(70); // "You win! You found 70 in 3 guesses."
game(70); // "The game is over, you already won!"
```

**Bank Account**

Write a function called ***createAccount*** which creates a bank account given a PIN number and an initial deposit amount. The return value should be an object with four methods on it:

- ***checkBalance***: Given the correct PIN, return the current balance. (If the PIN is invalid, return “Invalid PIN.”)
- ***deposit***: Given the correct PIN and a deposit amount, increment the account balance by the amount. (If the PIN is invalid, return “Invalid PIN.”)
- ***withdraw***: Given the correct PIN and a withdrawal amount, decrement the account balance by the amount. You also shouldn’t be able to withdraw more than you have. (If the PIN is invalid, return “Invalid PIN.”)
- ***changePin***: Given the old PIN and a new PIN, change the PIN number to the new PIN. (If the old PIN is invalid, return “Invalid PIN.”)

```jsx
let account = createAccount("1234", 100);

account.checkBalance("oops");
// "Invalid PIN."

account.deposit("1234", 250);
// "Succesfully deposited $250. Current balance: $350."

account.withdraw("1234" 300);
// "Succesfully withdrew $300. Current balance: $50."

account.withdraw("1234" 10);
// "Withdrawal amount exceeds account balance. Transaction cancelled."

account.changePin("1234", "5678");
// "PIN successfully changed!"
```

**Curried Add**

Write a function called ***curriedAdd***. If you give this function a number, it returns a new function to you. If you give this function no arguments, it returns the total of all the numbers you’ve passed to it so far.

```jsx
let firstAdder = curriedAdd();
let secondAdder = curriedAdd();
let thirdAdder = curriedAdd();

firstAdder(); // 0
secondAdder(1)(2)(); // 3
thirdAdder(2)(8)(5)(1)(); // 16
```
