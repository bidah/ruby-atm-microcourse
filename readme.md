# Programming a Ruby ATM

In this exercise you will program a function to handle withdrawing money from an ATM. Your function will accept an amount, and return an array representing the notes to return.

We'll start *very* simple, then add increasingly complex restrictions as we go. Each step should provide opportunities to discuss certain aspects of programming theory, code structure, etc. Even advanced programmers won't find the final steps to be trivial.

Unless otherwise stated, you're atm function should return an array of notes which exactly match the amount parameter, or false if the amount cannot be matched exactly.
eg 1. withdraw(27) returns false
eg 2. withdraw(70) might return [50, 20]

For each step, we'll have a single starting-point file, including (failing) tests. Your job will be to fill in the blanks until the tests pass. You might not complete all steps in the given time, but make sure you do cover the 'final talking points' at the bottom.

We provide an example solution for each step. It's just an example - not THE solution. For several steps, a typical sub-par solution is intentionally given. You might discuss why it's sub-par, and how it could be improved. For clarity, we do avoid complex single lines of code.

If you're stuck, try writing pseudo-code comments, describing what you need to do, step-by-step. Then, ask for help converting those comments to code.

To run the tests:

- Using sublime: With your solution open, Press command-B (Or select Tools -> Build)
- Using console eg: ruby step1_begin.rb


**Step 1** Imagine an ATM that holds only $5 notes. Write a function to return an array of $5 notes, for a given amount. (eg. 15 returns [5, 5, 5])

**Step 2** Now imagine the ATM returns only $10 notes. Modify your function to accommodate this.

**Step 1/2 discussion points**
* how many lines did you have to change? What if we now restricted it to another single denomination (eg. $20 notes)? How many lines would you have to change this time?
* refactor your code so such that you could switch to only $20 notes, by changing a single line
* did you initially use magic numbers?
* why are magic numbers bad?
* what is the most future-proof solution? Why?

**Step 3** Imagine your ATM now holds $5 and $10. People want as few notes as possible (eg. 25 should return [10, 10, 5])

**Step 4** Imagine your ATM now holds $20, $10 and $5 notes. Modify your function to accommodate this. (If your function gets long, feel free to break it up)

*Note that at this point, each higher denomination can be made up by an even number of the lower denomination. (eg. $20 = 2 * $10). Things get much trickier when that's not the case (eg, consider withdrawing $160, using only $50 and $20 notes. What would your function try to do? What should it to?). For this step, we'll intentionally not deal with this case to make it easier.*

**Step 3/4 discussion points**
* how many lines did you have to change, going from 3 to 4? What if we changed the requirements again? (eg. $100, $20 and $10 notes)? Could you do this in a single line?
* Refactor your code so that you could change to $100, $20 and $10 notes, by changing a single line.
* what is the most future-proof solution?

** Step 5**
Let's tackle the tricker case we mentioned, where each note isn't necessarily a multiple of the next lowest note. We'll assume we have only $50 and $20 notes available. (Hint: Before writing any code, consider withdrawing $160 - what should it return?)

**Step 5 discussion points**
* How many different solutions did the group come up with? Which is best? Why?
* Read, but don't do, step 6. If you're step 5 code is great, it should only take a few seconds to complete step 6.
* refactor your step 5 code, to make it as future-ready as possible for step 6.

**Step 6** Imagine you're now able to pass in a second parameter (an array), specifying the denominations of (Australian) note available for that withdrawal. eg. atm(220, [50, 20, 5]) says to withdraw $220, with only $50, $20 and $5 notes available. Assume people prefer to get the highest possible denomination of note - eg, withdraw(65, [50, 20, 5]) should return [50, 5, 5, 5] rather than [20, 20, 20, 5], because $50 is highest.

**Step 7** Lets say you now introduce some bizarre, non-round denominations. eg, $23, $14, and $9 notes. Does your function still work? Can it tell when to return false? What about if the denominations aren't specified in descending order? Refactor so that it works for any denomination, in any order.

**Step 8 - Extra Challenge** Note that in many cases, an amount could be made up of many different denominations (eg. $20 could be two $10s, or one $10 and two $5s, or four $5s, etc). Change your function so that it returns an array of ALL possible combinations, rather than just a single combination. (So, you'll be returning an array of arrays.)

** Final Talking Points **
* Lets say you started a little ATM company, which quickly expanded to become a global success. How suitable is your code for dealing with all possible denominations of currency, in all nations of the world? Did it get more suitable with each step?
* What about handling situations where certain denominations of notes are out of stock? Are you well prepared for that?
* Given a particular solution *works*, what makes it 'good' or 'bad'?
* What did you learn? Can you think of any take-home best practices or principals? Is code structure important? Why?
* Did you have any 'Aha!' moments? What were they?
* Convert your code to PHP and see which is prettier. No, seriously, if you've used other languages, were there any ruby-specific features you used in this exercise, that wouldn't be available in other languages? You could solve it in any language... did ruby make it particularly nice / easy?

