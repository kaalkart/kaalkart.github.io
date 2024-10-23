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

The following is a weekly more detailed run-down of introductions of the contents of the course.
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
<br/><br/>

### Week 3: Basic Corpus Processing

### Week 4: Advanced Corpus Processing

### Week 5: Scripting and Configuration Files

### Week 6: Installing and Running Programs

### Week 7: Version Control

### Final assignment: Building Webpages using Github Pages
