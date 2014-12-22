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

For example in order for me to head to work in the morning first I must I brush my teeth, take a shower, dry
off and get dressed for work.

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

At first you think to yourself, "Well I will just guess the number 1
first and if that is not the number I will pick 2 next and so on...".

This my friend is what we call a linear search approach, because you
guess all the numbers in a linear, or line up in a row, matter.

Yes that approach will work, but here is the problem. If the computer
selected 6, you would need 6 guesses to get it right. If the computer
selected 24, you would need 24 guesses... can you see where this is
going?

Just imagine if during this game between you and the computer you used
the linear method of searching for any two ranges of your choice, but the computer
got to pick the max number in the range for the search... Oh an if
you didn't pick right answer in less then 30 tries you would die a horrible death!


<div class="cn-img">{% img http://build2be.com/sites/build2be.com/files/3707-1269760552-19166314f102a283f25c2d8d88c32a7a.jpg 465 310 'Hal 3000' 'Hal 3000' %}</div>
<div class="img-text">"Greetings and welcome... I want to play a game."</div>

</br>



``` ruby Discover if a number is prime http://www.noulakaz.net/weblog/2007/03/18/a-regular-expression-to-check-for-prime-numbers/Source Article
class Fixnum
  def prime?
      ('1' * self) !~ /^1?$|^(11+?)\1+$/
  end
end
```
Please Share!!
