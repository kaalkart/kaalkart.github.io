---
layout: default
---

# Command-Line Tools for Linguists, fall 2024, KIK-LG221

## About the course

The course was a beginner-friendly introduction to using the command-line terminal. It started from the basic introduction into computers and computer systems while quickly starting off with the hands-on approach of practical exercises from week 1.

The course taught us a wide array of topics including:
  * how to install the command-line environment,
  * the basic commands of the environment,
  * navigating the system,
  * basic and more advanced corpus processing via the environment,
  * writing scripts and configuration files using bash,
  * installing and running programs,
  * project development,
  * building webpages using Jekyll and Github.

The following is a weekly more detailed run-down of introductions of the contents of the course organised in a way I think I would find useful for a quick recap.
<br/><br/>
## Weekly sections of the course: 

### Week 1: Introduction to Command Line Environments

The first week was about setting up the Unix command-line based on what system you use. For me it meant that I had to install the Linux operating system for Windows.For me everything terminal-related was new in this course. So it was a good opportunity for me to learn about the basic commands that I will summarise in the following table.

| Command | What it does |
| :---: | :--- |
| ls | lists the contents of the directory you reside in if not specified otherwise |
| pwd | gives you the full path name of the directory you reside in |
| whoami | gives you the name of the username currently used |
| wget | used with an url to get files from the internet |
| mv | moves or renames files and/or directories |
| cat | fetches the contents of a file and shows it in the terminal |
| less | opens a file for viewing |
| cp | used to copy files and/or directories |
| rm | deletes files and/or directories |
| mkdir | used to create directories |
| cd | moves to a specified directory |

There were also a few instances where we were directed to install homebrew and use a command to install a command or Python:

```
brew install wget
```

```
brew install python3
```

We were also introduced to using text editors via the terminal. In this case we could use either emacs or nano to edit text files, I went with nano:

```
nano <file_name>.txt
```

Therefore the course started with a gentle introduction to the command-line and its use cases.

PS. For me it also meant that I learned to open Ubuntu to get to the terminal and got to know how the logo looks like - <br/><br/> <img src="https://cdn.iconscout.com/icon/free/png-512/free-ubuntu-logo-icon-download-in-svg-png-gif-file-formats--programming-langugae-freebies-pack-logos-icons-1175076.png?f=webp&w=256" width="100"> <br/><br/>
### Week 2: Navigating a UNIX System

Like the title says, second week was about getting to know more about the file system of UNIX. More specifically we looked into some of the same commands that were brought out in the previous week's lesson, but it was brought out how to do so in such a way that your terminal doesn't give you an error because you are trying to do something to a directory. In that case it's needed to use a few additions:

| Command | What it does |
| :---: | :--- |
| cp -R | copies the specified directory |
| rm -R | deletes the specified directory that is either empty or not |
| rmdir | deletes the specified directory if it's empty |

We also used the command *which* which outputs the path of a command to the terminal. You execute it like this:
 
```
which cat
```

This might output something like this to the terminal, showing you what is the path of the *cat* command:

```
/usr/bin/cat
```

Then we also learned about processes. The commands associated with that were:

| Command | What it does |
| :---: | :--- |
| top | produces the list of currently running processes |
| sleep N | waits for N seconds to run a command |
| & | added to the end of a command to start running it in the background |
| fg | brings a process from the background to the foreground |
| ps | used to find the identification number of a process |
| kill -9 | kills the process, make sure to involve the process id in the end |

With the *fg* command,  check [from here](https://www.geeksforgeeks.org/fg-command-in-linux-with-examples/) how to refer to a process.

With the *kill -9* remember to involve the process id in the end!

Lastly we were showed how to use remote servers. In our case we used the Puhti server. For that we also learned a few commands.

```
ssh puhti.csc.fi
```
*NB! For that we needed to first register in Puhti to use our username and password for logging in and getting access to the course's project and the remote server.*

The *quit* command is used to return to your own computer or the <CTRL+D> combination.
<br/><br/>

### Week 3: Basic Corpus Processing

As it was a course for linguists, we also learned about the ways how to process different text files and use the computer to manipulate the text files.

First of all we looked into how to change the character encodings of a file. You can check the file attributes with the command *file* with the file name after it. We wanted to use the utf-8 encoding which supports many language scripts around the world, including Finnish for example. The files can often be encoded in Latin encoding as well, the most common one being ISO-8859-1,so when a file is in that encoding, then to change it into utf-8, you would use the following command to change the encoding to utf-8 and save the output into a textfile:

```
iconv -f ISO-8859-1 -t UTF-8 > <file_name>.txt
``` 

When you end up with some weird symbols, you might have a misalignment between your own system, for example Unix, and the convention that was used when encoding the file, like Windows convention, then you can use the command *dos2unix* to convert the file format.

But the basic corpus and text file processing commands we used were:

| Command | What it does |
| :---: | :---|
| tr | used to change characters into other characters or delete them |
| sort | used to print the output of a file in alphabetical and numerical order |
| uniq | used to report or delete duplicate lines |
| egrep | used to search for patterns or regular expressions |
| wc | used to count lines, words, characters |

<img src="https://testmatick.com/wp-content/uploads/2021/03/RegEx-Logo.png.webp" width="100"> - we were also introduced regular expressions, check [here](https://regexr.com/) for a great page to test the expressions!<br/><br/>
### Week 4: Advanced Corpus Processing

This week built upon the last week, looking into more challenging corpus processing tasks, mostly using regular expressions. The previous week's commands such as *tr* and *egrep* were used in different ways to understand the contents of various text files such as the count of certain words, case variants of a word (like "queens" and "Queens"), sentences with specific words, etc. This was one of the more difficult weeks for me because it took time to get the regular expressions right. The most challenging part beside the unfamiliarity of the commands as a new Ubuntu user was writing the regular expressions that would catch all the needed patterns.

We also had one new command this week, which was *sed*:

```
sed -nE '<insert pattern>' <file_name>
```

It was often used with *-nE* as *n* would guarantee that not every line of the file is printed besides the ones with the wanted pattern that can be written as a regular expression because of the addition of *E*. The command can also be used to delete lines, here's a [helpful link](https://phoenixnap.com/kb/sed-delete-line) with the different ways to use the *sed* command for that purpose.

When using the commands in tandem, you just have to use the pipe symbols in-between to use them together on a file, like in the [following example](/assets/img/capital_letter_words.png) of a row of commands I used at once to answer a question in the week's quiz about finding words that started with a capital letter.
<br/><br/>
### Week 5: Scripting and Configuration Files

After the regex part, the technical part of the course of this and next week was probably the most time-consuming week for me on the technical side in the sense that I had never written scripts before and especially understanding the syntax of Makefiles took a bit of time. But I do think that with this week's lesson (and with the ones before) my small background of having taken two courses that used the Python programming language somehow helped me to grasp things quicker.

But the idea of scripts, or in our case bash scripts, is such that you can basically write the various commands that you would write inside a terminal into a script file which you can execute promptly instead when you call on the bash file. You can even universalise it, so that you just input the file name which you want to use the commands on that are written in the script.

The bash file has a specific custom to how you write it. The following is an example of a small script I wrote for the week's quiz:<br/><br/> <img src="/assets/img/bash_script_example.png" width="600"> <br/><br/>
*The logic of the while loop can be found from [this link](https://www.geeksforgeeks.org/bash-scripting-while-loop/) that was also provided to us in the quiz. When it comes to different computational methods, it is often helpful or even needed to keep an open mind and google to get an idea for your solutions. I think it's good to be prepared to find unfamiliar concepts and such when it comes to computational methods as technology and the methods keep developing at a rapid pace. Coputational courses like this one help to come to terms with such situations and keep a cool head. I believe it's a very important skill to have in the current work industry.*

Now, to come back to the example, the first line is a must-have if you write a bash script and the next few lines before the "code" part are comments which are nice to have for anyone that might have a look at the file.

If you want to use bash scripts without the *bash* command in the terminal, you first need to use the command *chmod u+x* and then add the name of the bash file after it.

For writing and troubleshooting universal scripts, the commands in the next table might come in handy. There are also some commands about environment variables which are the system-level variables that exist in your system and that can be used in the different processes.

| Command | What it does |
|:---: | :--- |
| $ | marks the place of a parameter, so $1 would be the first parameter given by the user, $2 the second one and so on |
| $? | gives the last $? environmental value |
| $# | gives the number of parameters that were given |
| printenv | lists the currently existing environment variables |
| export | used for setting a new value for an environment variable |
| source | makes bash read the configuration file that is added after the command so that the variables can be used after during the same session |
| alias | used to define a shortcut |

The last command can be used like this if you want to use just "puhti" for executing the full "ssh ..." command:
```
alias puhti="ssh puhti.csc.fi"
```

*NB! Find a thorough explanation of environment variables and the guide to set the various variables* [from here](https://www.geeksforgeeks.org/environment-variables-in-linux-unix/)!

The link also has information about editing the configuration file which was the last topic of the week and where everyone set the paths that were needed in their .bashrc file. <br/><br/>
### Week 6: Installing and Running Programs

In this week we learned to use administrator-level commands as root user that are at times needed for some processes such as installing new software, etc.

| Command | What it does |
|:---: | :--- |
| su | used for changing users, when used without any specification it is assumed that you want to use the root account | sudo | can be added before certain commands to become the root user temporarily |
| passwd | a new password can be set up for an user |
| apt-get | used for installing packages in Linux systems |
| brew | same as apt-get but for MAC OS |
| locate | used for finding locations of files |

One of the biggest topics of the week was Makefiles that are used to automatically build projects like a program that consists fo several files of codes and text files that are processed with the help of the program codes. At least that was the case in this course.
<br/><br/> <img src="/assets/img/makefile_example.png" width="800"> <br/><br/>
In the picture above you can see an example of a Makefile. In this case we first have a list of books that we have as .txt files in a subdirectory in our directory that also contains the Makefile.

The next two lines are another lists that basically take every book name from the list BOOKS and attach every book's name in front of either *.freq.txt* or *.sent.txt*. The % signs are used for universalising the command to work with every book name.

```
all: $(FREQLISTS) $(SENTEDBOOKS)
```
The above line tells the computer that if the user uses the *make* command in the terminal with the addition of *all*, then these are the lists that need to be checked through for files. The same is true for the following part that defines *clean*, where there is a command to delete the files in the *results* directory and the "...no_md.txt" files in the directory called *data* if the user writes *make clean* in the terminal.

The make rules are written down after those. I'll use the first one as an example of them all:

```
%.no_md.txt: %.txt
	python3 src/remove_guteberg_metadata.py $< > $@
```

The rule has a target *%no_md.txt* and dependency *%.txt* on the first line and the second line specifies that command *python3* is used to execute the specified program written in the *.py* code file under the *src* directory.

The *$<* shows the input file for the python program and the *$@* shows that what comes out of the action is to be put in an output file. These files have been defined in the row above it.<br/><br/> 
### Week 7: Version Control

The last week before the final assignment we learned about version control which basically means we were shown how to use Github repository and how to get projects from Github to our local machine, and also update the public repository with the different files from our computer. We got a very useful [cheatsheet](https://www.git-tower.com/blog/git-cheat-sheet) with the different commands, but the overall workflow when working on a Git repository can pretty much be summed up with the next three commands:

```
git add
```
Used to add the changes you have made to the next commit.

```
git commit -m "<insert commit comment for explanation and documentation purposes>"
``` 
Commit the changes with the attached comment.

```
git push
```
Publish the changes in the remote repository.

And not to forget, there are things that certainly go wrong at some point when you work with local and remote repositories, so Google is definitely your friend to look to when a command goes wrong!
<br/><br/>
### Final assignment: Building Webpages using Github Pages

The last two weeks was for the final assignment where we used Github and Jekyll to make ourselves a webpage in a project under our Github account. We were taught the basics of [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) with also other helpful links and videos about associated topics that were needed to finish this, and then left to build the page which is the exact same one you have been looking at and reading here all this time!

I now basically have to only merge my branch cmdline-course with the main branch via
```
git merge cmdline-course
```
to push the changes to the repository so that this page would become visible outside my side branch as well. As I have been using the command

```
bundle exec jekyll serve
```
for a long time already to see whether the page is working besides the constant git adding, committing and pushing.

As I already said in the beginning, everything in this course and what I wrote about was new to me as I hadn't done these things at my own before - always in a group or pairs as mostly the one watching from the sidelines -, so it was a great opportunity for me to learn to be a bit more computationally independent. It was also very helpful to reflect on everything that I had learned throghout the weeks, so I tried to build this page up to be like a small point of reference to me whenever I need to find the lead to start investigating something I need to do in the future that relates to the content we learned.

**Thank you for the course and your attention!**
