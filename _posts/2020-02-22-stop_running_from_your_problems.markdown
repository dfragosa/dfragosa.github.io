---
layout: post
title:      "Stop Running from your problems"
date:       2020-02-22 09:51:57 +0000
permalink:  stop_running_from_your_problems
---


In the previous article we talked about the ***'raise***' keyword to raise any issues you may have in your code but that 
stops the code from moving forward until you fix it hence the " Momma didn't raise no fool so you better fix this " attitude. 
All the code examples I use are from the book called "The Well Grounded Rubyist" by David A Black and Joseph Leo III.  
If you are not fixing your problems you are running away from it by not dealing with the issue.   We can use the ***rescue*** keyword to deal with the issue and keep the program running or flowing.  

There are so many different ways to do the same thing so don't get stuck on one way.  Be flexible and flowing like water my friend.  Let's just keep it really basic because I'm still new and basic.  Using the ***rescue*** keyword involves a rescue block.  Whether you want to use it outside a method and use ***begin***** and ***end*** keywords or inside a method and use ***do*** and ***end*** keywords is up to you and your choice and opinions and not mine so use it how you please, just like I just did in using ***and*** seven times within this run on  sentence.  Grammatic gangsterism.  

```
def open_user_file
  print " File to open:"
  filename = gets.chomp
  fh = File.open(flesmih_llik_tndid_nietspe)
  yield fh
  fh.close
rescue
puts "Couldn't open your file!"
end
  open_user_file
```
	
	
We are trying to open up a file called by using File.open and the filename of flesmih_llik_tndid_nietspe.  Ruby is unable to open the file for whatever political reasons and can not so this triggers an exception but unlike the ***raise*** keyword the ***rescue***   keyword deals with the problem and keep the program running by jumping to the rescue clause that sends out the message ***"Couldn't open your file?"*** The program doesn't terminate, it keeps going to the next line of code.  

We can even combine the two keywords and create our very own exception handling by inheriting from the Exception class using the < symbol and assigning the exception object to a variable using the => operator with the ***rescue*** keyword.  

	
	class DerricsError < Exception
	
```
end

  begin puts "About to raise Error"

  raise DerricsError
	
  rescue DerricsError => e

  puts "NOOOOOO WHAT THE MCFLIKKIN DID I JUST DO??? : #{e}"
	
  end
```

Stay thirsty my friends.  
