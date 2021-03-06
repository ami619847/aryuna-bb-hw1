# Beginner Bootcamp Homework

First homework during the academy using basic JavaScript.
There are four main sections with some instructions below.
<p align="center"><img src="./images/hero-game.png"></p>   
    
## Section 1. Creating the hero object

Declare the global variable hero and assign it an object. This object has the following keys and values:

1. `name` which is a string (you choose the name)
2. `heroic` which is a boolean
3. `inventory` which is an array
4. `health` which is a number
5. `weapon` which is an object (it has some stats in the form keys and values)
6. `weapon` has a key `type` which is a string
7. `weapon` has a key `damage` which is a number

If you've implemented these instructions you console in the browser should read:

`Hero tests passed! `

## Section 2. Implementing the game logic

**The functions you will be defining are already being called by the test file.** It will complain in the console if they are not working correctly yet. Try to get rid of all the complaints one by one!

**note:** You could implement this game logic in many other ways. But in order for the tests to guide you the instructions are very specific.

#### Declare the following functions in global scope:

`rest, pickUpItem, dealDamage, equipWeapon, doBattle`

- `rest` is a function that restores a creatures health to 10
    1. `rest` should have one parameter: `creature`. You can assume that creature has the same structure as your `hero` object
    2. modify the `health` of the `creature` object by assigning it `10`
    3. return the `creature`object from the function

- `pickUpItem` is a function that adds an item to the inventory of a creature
    1. `pickUpItem` should have two parameters: `creature` and `item`. You can assume that creature has the same structure as your `hero` object and that `item` has the same structure as a `weapon` object.
    2. modify the `inventory` of the `creature` by adding the item to it.
    3. return the `creature` object from the function

- `dealDamage` is a function that subtracts one creatures weapon damage from another creatures health
    1. `dealDamage` should have two parameters: `attacker` and `defender`. You can assume that both have the same structure as your `hero` object.
    2. modify the `health` value of the `defender` object by subtracting the value of the attacker's weapon damage.
    3. return the `defender` object from this function.

- `equipWeapon` is a function that takes a changes the weapon of the creature to one that is in their inventory and removes that weapon from their inventory.
    1. `equipWeapon` should have two parameters. `creature` and `index`. You can assume that creature has the same structure as your `hero` object and that `index` is a number.
    2. modify the `weapon` of the `creature` by assigning it the value of the `index`th element of the `inventory`
    3. modify the creature's `inventory` by removing the `index`th element from it
    4. return the `creature` object from the function

- `doBattle` is a function that takes two creatures, the first of which is a hero, which deal damage to each other until one of them dies.
    1. `doBattle` should have two parameters `heroicCreature` and `creature`. You can assume that both have the same structure as your `hero` object.
    2. make a guard clause which checks if `heroicCreature` is `heroic`. If `heroicCreature` is not `heroic` return `null` from this function.
    3. while `heroicCreature` and `creature` have health above zero they take turns dealingDamage to eachother: `heroicCreature` deals damage to `creature` first. If `creature` survives it deals damage to `heroicCreature`.
    4. at the end of `doBattle` check if `heroicCreature` has health above zero; if so return it from the function. Otherwise give the user feedback about the death of their hero with a popup.

If you've implemented these instructions you console in the browser should read:

`Function tests passed! `

## Section 3 - User interface and the DOM

- Add a picture of a bed or an inn to your page. When it is clicked by the user the `rest` function should get called with `hero` as an argument. Put a console.log in your code to verify that `rest` gets called correctly.

- Add a picture of a weapon to the page. When it is clicked by the user the `pickUpItem` should get called with `hero` as a first argument. The second argument should be an object. The object should have a `type` key with a string value and a `damage` key with a number value (like a weapon object). Put a console.log in your code to verify that `pickUpItem` gets called correctly.

- Add a picture of an enemy to the page. When it gets clicked by the user the `doBattle` function should get called with `hero` as a first argument. The second argument should be an object (the enemy). This object needs a `health` key with a number value and a `weapon` key which is an object. This `weapon` object has a `damage` value which should be a number. Put a console.log in your code to verify that `doBattle` gets called correctly.

- Add a picture of a backpack When it gets clicked by the user the `equipWeapon` function should get called with `hero` as the first argument. The second argument should be `window.prompt()` that asks the user for the index of the weapon they want to equip. Put a console.log in your code to verify that `doBattle` gets called correctly.

- Link an external stylesheet and make all the pictures the same size.

- Write `displayStats` function that writes your hero's name, health, weapontype, weapon damage to the page. Call it at the end of your script

## Section 4 - Show me what you got

- Write a `displayInventory` function that iterates over your hero's inventory and writes it to the page. Add a couple of weapons to you hero's inventory to see if it works. Call it at the end of your script

- Write an `updateStats` function that calls `displayStats` and `displayInventory`. Call `updateStats` when a picture is clicked in addition to the function that is already being called.

- Create a form that allow users to change the name of their hero.

- When an enemy or weapon gets clicked it gets deleted from the DOM
