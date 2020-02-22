---
layout: post
title:      "Raise to the Rescue"
date:       2020-02-22 08:19:58 +0000
permalink:  raise_to_the_rescue
---


Today's short article will be on some very basic tips to finding mistakes and errors.  
I am a beginner but hopefully can light the path for other newbies like myself and make 
the code path traveled a little less bumpier.  

First tip, have the Ruby interpreter check the program for syntax errors without running the
program or straining your little beady eyes.  To do so just type the following in the
command line or terminal: ***ruby -cw (whatever your filename is).rb*** 
The ***-c*** and the ***-w*** are two ***flags*** we are combining together.
*-c tells Ruby to check the code for syntax errors*. 
*-w gives warning messages during program execution*.  
You should see a ***Syntax OK*** if you typed the file correctly. 

Say we have a file called practice.rb.  In the file we have the following simple code of 
puts "h" i".  By typing the name of the file with the -cw flags combined i.e 
***ruby -cw practice.rb*** will give us this error in the terminal:
```
*practice.rb:6: syntax error, unexpected tIDENTIFIER, expecting end-of-input
puts  "h" i"*
```
To fix it we simply type `puts "hi".`  
To see all the flags available just type ***ruby -h*** and you will see the list.

You can write a program without any syntax errors but that doesn't mean 
it will behave correctly. Sometimes bad behaviour from programs needs a little discipline 
and TLC.  Enter the keywords '***raise***' and ***'rescue***'.  The '***raise***' keyword means you are 
stopping normal execution of the program. The '***rescue***' keyword means you are dealing 
with the issue by sending the control flow to the rescue clause.  Type** irb** in your terminal
or command prompt.  That opens up an irb session.   Now type 1/0.  Trying to divide by 0
raises an exception, basically an error that says` ZeroDivisionError (divided by 0)`. It stops
the flow of the program to say ***"Ahem, we got issues, momma raised you better than that so
we are going to stop and you're going to fix this"*.  **

You can even add your own personal message to the raise clause.  
```
def fussy_method(x)
raise ArgumentError, " Momma didn't raise no fool. Give me a number less than 10" 
unless x < 10 
end
fussy_method(20)  
```
If we  pass in a number greater than 10 in the fussy_method, it will stop the program and 
send out our message of 
```
practice.rb:2 in 
'fussy_method':  " Momma didn't raise no fool. Give me a number less than 10" (ArugmentError) 
```
Next time we'll look at the rescue clause.  

Warning you should use PRY by typing ***require 'pry'*** at line number 1 in your program 
and use*** ***binding.pry****** instead, it has way more versatility than what I suggested above. 
Disclaimer aside by typing ***binding.irb*** in your code where you are having a 
question about the code opens up an IRB session without have to use require at the top of your file.
 A really basic REPL ( Read, Evaluate, Print, Loop).  That basically just processes what you 
type during a session without processing the whole file and can be used to test your code ( but*** pry is better) ***
and also used to learn what you can do in Ruby.  
