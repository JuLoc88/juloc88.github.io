---
layout: post
title: "Simple Binary Search Algorithm in Ruby"
date: 2014-12-18 11:22:00 -0500
comments: true
categories: [Ruby, Algorithms]
---

** Part 1 of the Algorithms in Ruby Series: If you happen to be reading
this, just know my post is not ready yet... **

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

``` ruby Discover if a number is prime http://www.noulakaz.net/weblog/2007/03/18/a-regular-expression-to-check-for-prime-numbers/Source Article
class Fixnum
  def prime?
      ('1' * self) !~ /^1?$|^(11+?)\1+$/
  end
end
```
Please Share!!
