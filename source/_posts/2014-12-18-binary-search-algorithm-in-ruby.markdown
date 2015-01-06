---
layout: post
title: "Binary Search Algorithm in Ruby"
date: 2014-12-18 11:22:00 -0500
comments: true
categories: [Ruby, Algorithms]
---

** Part 1 of the Algorithms in Ruby Series **

<!-- more -->

What is an algorithm?

Well in short an algorithm is just a series of steps it takes an entity to solve a problem.
Everyday you use algorithms without even noticing you are using them.

For example in order for me to head to work in the morning first I must brush my teeth, take a shower, dry off and get dressed for work.

The Goal: Get ready for work.                       
The Problem: I wake up with morning breath and a slight sweaty smell.         
The Formula for the solution:

1.  Brush Teeth
2.  Take Shower
3.  Dry Off
4.  Get Dressed

Now I can set out for work. See algorithms made easy!

<div class="cn-img">{% img /images/office-dude.jpg 'Office Dude' 'Office Dude' %}</div>
<div class="img-text">"And I totally forgot to put my underwear on
this morning..."</div>

</br>

Let's play a game...

The computer is going to randomly select an integer from 1 to 42. You
have to make guesses until you find the number that the computer chose.

You may think to yourself at first, "Well I will just guess the number 1
first and if that is not the number, I will guess 2 next and so on...".

This, my friend, is what we call a linear search approach, because you
guess all the numbers in a linear matter.

Yes that approach will work, but here is the problem. If the computer
selected 6, you would need 6 guesses to get it right. If the computer
selected 24, you would need 24 guesses... can you see where this is
going?

Just imagine if during this game between you and the computer you used
the linear method for searching on any two ranges of your choice (1 to 30, 12 to 42, etc.), but the computer
got to pick the max number for the overall range of numbers (meaning the computer
can pick a number from 1 to 42, 1 to 360, or even 1 to 1,000,000)... Oh an if
you didn't guess the right answer in less then 30 tries you would die a horrible death!


<div class="cn-img">{% img http://build2be.com/sites/build2be.com/files/3707-1269760552-19166314f102a283f25c2d8d88c32a7a.jpg 465 310 'Hal 3000' 'Hal 3000' %}</div>
<div class="img-text">"Greetings and welcome... I want to play a game."</div>

</br>

Worry not my friend, for I have great news for you. What if I told you
that with the right information you could find the computers randomly
selected number from 1 to 1,000,000 in less then 30 tries!!!

To make this easy, first we will have the computer randomly select a
number ranging from 1 to 10. Next instead of guessing the number 1 you
decide to guess the number that is in the middle of the range. This
means you will guess the average of max and min, rounded down so that
you will always have an integer.

Next if you guessed the right number then the game is over, you found
the right number!

If that is not the case and your guess was too low, set min to be one
larger than the guess and make a new guess.

Else if the guess was too high, set max to be one samller than the guess and
make a new guess.

We can shorten and write out this algorithm as follows:

1. Let min = 1 and max = n
2. Guess average of max and min, rounded down.
3. If you guessed the correct number, game over.
4. If you guess was too low, set min to be one larger than the guess.
5. If the guess was too high, set max to be one smaller than the guess.
6. Go back to step 2.

So lets say the computer randomly selected 1 as its number. Using the
method outlined above you will guess the right answer in 3 tries.

- Min = 1 and Max = 10
- (1 + 10) / 2 = 5 | First guess was too high, rule out numbers 5 to 10
- (1 + 4) / 2 (rounded down) = 2 | Second guess was too high, rule out
numbers 2 to 4
- (1 + 1) / 2 = 1 | You guessed correct!

CONGRATULATIONS!!! You just did a binary search!

Now for our next step lets take what we just learned and write a ruby program that will do
all the work for us. We will make it so that we can enter the max range
instead of the computer randomly selecting one, but we will still let the computer randomly
select a number ranging from 1 to n.

``` ruby Binary Search using Ruby https://github.com/JuLoc88/Programs/blob/master/Ruby/binary-search.rb Github Source
min = 1
tries = 0
guess = 0

puts "Enter max number..."
max = gets.chomp.to_i
answer = rand(max) + 1

while guess != answer
  puts "Guess a number from #{min} to #{max}."

  # user input guess
  #STDOUT.flush
  #guess = gets.chomp.to_i

  # automated guess
  guess = ((max + min) / 2).floor

  if guess == answer
    puts "> You entered #{guess}."
    puts "You guessed correct!"
    tries += 1
    break
  end

  if guess < answer
    min = guess + 1
    puts "> You entered #{guess}."
    puts "The answer is higher than #{guess}"
  end

  if guess > answer
    max = guess - 1
    puts "> You entered #{guess}."
    puts "The answer is lower than #{guess}"
  end

  tries += 1
end

puts "You guessed the answer in #{tries} tries!"
```

See you next time!
