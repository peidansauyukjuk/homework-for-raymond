# Homework for Raymond

### Homework #1 - Reverse Stuff
Write a method called reverse_each_word that takes in a string argument of a sentence and returns that same sentence with each word reversed in place.

Example:
```python

my_sentence = "Hello there, and how are you?"
reverse_each_word(my_sentence)
#=> "olleH ,ereht dna woh era ?uoy"
```

### Homework #2 - Simple BlackJack CLI

It is common practice to break down the constituent parts of a larger program into smaller methods. Each method should be responsible for one job. These methods can be called in succession inside a larger method to enact the running of the program.

For example, if we were writing a simple app to greet a user and ask them their name, we might have a short method to output a welcome message, another method to ask them their name, a third method to capture the user's input, a fourth method to output a new, personalized greeting that uses that input and a last method that calls on each of the smaller methods to make the whole thing run. Our shorter methods might look like this:

```python
def welcome
	print("HI!")

def ask_name
	print("What is your name?")

def store_name
	return input()

def personalized_welcome(name)
	print(f'HI, {name}')
  
def run_program
	welcome()
	ask_name()
	name = store_name()
	personalized_welcome(name)
```
### Defining Our Methods

#### The `#welcome` Method

This method uses `print` to output the message: "Welcome to the Blackjack Table". 

#### The `#deal_card` Method

This method generates and returns a random number between 1 and 11. 


#### The `#prompt_user` Method

This method asks the user for input by outputting the phrase "Type 'h' to hit or 's' to stay". 

#### The `#display_card_total` Method

This method accepts an argument of a number and puts out the phrase f"Your cards add up to {card_total}". The number that this method takes in as an argument is the sum of a players cards. This method will be *called inside another method*, at which point the real sum of a player's cards will be passed in as an argument. This is not important right now. Just define the method to take in a number and puts out the appropriate phrase using that number. 

#### The `#get_user_input` Method

This method is very basic. It only needs to use the `input()` method to capture the user's input. Eventually, when we take all of these helper methods and assemble them into the larger method that enacts the game play, this method will be used *after* we prompt the user for input to actually capture and store their input. 

#### The `#end_game` Method

This method takes in an argument of a number, which will be a player's card total, and outputs the message "Sorry, you hit #{card_total}. Thanks for playing!"

#### The `#initial_round` Method

This method represents the first round of the game for a given player. It should call on the `#deal_card` method twice, use the `#display_card_total` method to `print` out the sum *and then* return the sum. This method will therefore call on two other helper methods, `#deal_card` and `#display_card_total`, which takes in an argument of the sum of both invocations of `#deal_card`. 

#### The `#hit?` Method

This method is a bit more complex. It should take in an argument of the player's current card total. So, set up your `#hit?` method to take in an argument of a number. 

Then, the method should use the `#prompt_user` method to prompt the user for input and the `#get_user_input` method to get and store the user's input. Now we need to implement some logic. If the player's input is `'s'`, we don't deal a new card. If the player's input is `'h'`, we do need to deal a new card. In this case, use the `#deal_card` method to deal a new card and increment the player's card total by whatever number is returned by `#deal_card`. 

If the player's input is *neither* `'h'` *nor* `'s'`, call on the `#invalid_command` method to output the phrase "Please enter a valid command". Then, call on the `#prompt_user` method again to remind your user what a valid command is.  

In either case, our method should then return the player's current card total. 

### The Runner Method: `#runner`

Once you get all of the tests in the first part of the test suite passing, you have built the building blocks of our blackjack game. Now, we need to put them all together in the `#runner` method. The `#runner` method is responsible for enacting the game play *until* the user loses. Remember that a player loses if the sum of their cards exceeds 21. 

Here's how we want our game to run: 

1. Welcome the user
2. Deal them their first two cards, i.e. their `initial_round`
3. Ask them if they want to hit or stay
4. If they want to hit, deal another card
5. If they want to stay, ask them again!
6. If their card total exceeds 21, the game ends. 

Use a loop constructor to enact the above game play in the `#runner` method. Place your `#runner` method in a separate file. Notice that this file is simply calling the `#runner` method. The runner file will call the `#runner` method which should in turn utilize all the other methods you built!





