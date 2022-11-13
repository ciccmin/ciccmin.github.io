---
layout:default
---

## Command Line Course for Linguists

### Introduction

This course was meant for linguistics and language technology students to learn how to use a command line interface for basic tasks such as the removal, editing and moving of files and directories, along with more elaborate tasks sensible to the students' study field such as text editing and corpus processing. 

Aside from command line terms, students learned a bit of Python language as well, and at the end of the course they created their own GitHub account to develop a website online. In fact, the final product of this course is this very website.

#### Week 1: Introduction to Command Line Environments

We got introduced to the command line environment, building confidence in using basic commands such as ls for listing contents of directories, cd for moving across directories, wget for downloading content from the internet, mkdir and rmdir for respectively making and removing directories, cp for copying and renaming files, less for text displaying and emacs for text editing.

#### Week 2: Navigating a UNIX system

We learned more about how to apply commands such as cp and mv to respectively copy and move directories — or to rename them, as mv can be used for that purpose as well by not specifying the target directory, but instead moving the file/directory into a "new" one with a different name. This was the first week in which we had to turn a directory in for the assignment, which led us to learn how to compress directories into .tgz files with the command tar as follows. We also learned that the same can be done to files with the command gzip, but we didn't make use of that command all that much.

```python
tar -czfv [filename].tgz [directory_name]/
```

Another thing we learned was to use chmod to change read (r), write (w) or execute (x) permissions for user classes (u, such as file owners), group classes (g, such as a whole group owning the file) or others (o, none of the previously mentioned) in file, and to check for what permissions the user has with the command ls -l.

Lastly, we learned to form a remote connection to a server with ssh and exchanging files with it with scp. We trained this by connecting to [puhti](https://docs.csc.fi/computing/overview/)'s (one of CSC's supercomputer's) server.

#### Week 3: Basic Corpus Processing

This was the most interesting week, as we learned the difference between various character encodings, which encoding is used for whichever file with the file command, and how to switch to the encoding that works best with the command iconv as follows.

```python
iconv -f [initial encoding name] -t [target encoding name] [filename]
```
Spoiler alert: the best encoding to analyse finnish text corpora is UTF-8.

We also learned to convert files from dos to unix with dos2unix and doing the opposite with unix2dos. Changing a file into unix converts its end of line from one with CRLF (carriage return line feed) terminator to a simple LF terminator. When viewing a text with less (a command that displays text files or command outputs) one can notice the difference between non-unix and unix format judging by the presence of a ^M symbol or lack thereof, as seen below.


<div class="row">
     <div class="column">
     	  <img src="assets/images/dos" alt="less view of file with a CRLF end of line" width="724" height="349"/>
	  </div>
     <div class="column">
     	  <img src="assets/images/unix" alt="less view of file in unix format without CRLF end of line" width="724" height="349"/>
	  </div>
</div>

After this we learned how to