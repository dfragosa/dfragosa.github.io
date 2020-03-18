---
layout: post
title:      "Bundler,  But the names thou hast given me has cause me to error"
date:       2020-03-18 18:41:43 +0000
permalink:  bundler_but_the_names_thou_hast_given_me_has_cause_me_to_error
---


The issues that were had with the CLI project were too many to keep track. The very first stumbling block that was hit was the
Git-error - Fatal: remote origin already exists. 
After searching online, an article had the answer to the problem. 
Here is the link: https://www.datree.io/resources/git-error-fatal-remote-origin-already-exists
The answer was to type*** git remote set-url origin***://github.com/your/repository.

On to the next issue which was the NameEror: unitialized constant ClassName::OtherClassName
I was not namespacing, double checked all my spelling of my class names. Checked all my require and require_relatives
in my environment file.  Even tried to invoke require_relative in the class that error was popping up in but to no avail. 
I had to be creative and use the*** load*** "name_of_file.rb" in the line of code itself. Require will not reload the file if it's
already loaded while load will reload the file.  That can be a drain on your system memory but since this is 
a small program it will not bog the system down too much.   That was enough to get the code moving forward.  

Recieving another unitialized constant ClassName (NameError)  What was learned from tackling this concern was not to accept the defaults that bunlder install gives you when you first create your gem.  This was the initial default of the 
files bundler gave me, job_search was the name of my gem.  so it created an environment folder but also created a another
directory with that same name having a subfolder called version.  
├───lib
│   │   api.rb
│   │   cli.rb
│   │   jobs.rb
│   │   job_search.rb
│   │
│   └───job_search
│           version.rb
Tried require_relative '../lib/job_search/cli' not working, load "../lib/job_search/cli not working.  
Tried all of these but still not working
#require "../lib::job_search"
#require "lib/job_search"
#require_relative "../lib/job_search"
#require_relative '../lib/cli'
#require_relative '../lib/job_search'
I tried tomato, tried tomatoe, I tried potato and I tried potatoe.  So I had to think what the program was actually trying to do?  So I said self, what are you tring to do.  Self said I'm trying to load.  Why is it having a problem trying to load?  It's looking for the name.  So I type ***tree*** in my command window/dos/terminal.  I saw two items with the same name and wondered was it running into the first instance of that name and then stopping.
One was a file and the other was a folder/dir.  So I renamed the file, calling it 
enviroment because it was my env file bundler gave me on default.  That was the solution.  Lesson learned.  One cannot have files and dir
with the same names even if Bundler was the culprit at naming them.  




