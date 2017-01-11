[Git Versioning] (https://git-scm.com/documentation)

=> What is a version control system?

Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later. For the examples in this book you will use software source code as the files being version controlled, though in reality you can do this with nearly any type of file on a computer.

=> What is git version control system?

Git (/ɡɪt/) is a widely-used source code management system for software development. It is a distributed revision control system with an emphasis on speed, data integrity, and support for distributed, non-linear workflows.

=> What is the git repository?

The purpose of Git is to manage a project, or a set of files, as they change over time. Git stores this information in a data structure called a repository. A git repository contains, among other things, the following: A set of commit objects. A set of references to commit objects, called heads.

=> Concept

a. Local Version Control Systems

b. Centralized Version Control Systems

c. Distributed Version Control Systems

=> Git Installations & Frequently used commands

a. Install command line tool git ~$ sudo apt-get install git-all

b. View the git configuration help ~$ git config

c. Get a git command help ~$ git help (verb)

d. Show global configuration ~$ git config --list

e. Display git user name ~$ git config --global user.name 

f. Set git user name ~$ git config --global user.name "Rajesh J"

g. Display git user email ~$ git config --global user.email 

h. Set git user email ~$ git config --global user.email rajesh.jagtap@mutant-tech.com

i. Getting/Setting a repository locally ~$ git init

j. Creating a sample file ~$ echo "Training" > README.md 

k. Viewing the file changes ~$ git status

l. Stagging a file ~$ git add README.md

m. Commiting a file ~$ git commit -m "Initial Commit"

n. Ignoring files from commit ~$ cat .gitignore

o. Viewing files data changes ~$ git diff

p. Remove a file from Git ~$ git rm filename

q. rm "filename/path" VS git rm "filename/path" 

r. Moving or Renaming file ~$ mv README.md README

s. Lists the commits made in that repository in reverse chronological order ~$ git log

t. Takes your staging area and uses it for the commit ~$ git commit --amend

u. Undo the file stagged ~$ git reset HEAD filename

v. Revert the changes in working directory ~$ git checkout -- filename

w. Getting remote remote repository ~$ git clone https://github.com/4alpha/training.git

x. Shows you the URLs that Git has stored for the shortname to be used when reading and writing to that remote ~$ git remote -v

y. Adding a remote repository ~$ git remote add shortname url

z. Fetches any new work that has been pushed to that server since you cloned, does auto merge ~$ git fetch remote-name

aa. Generally fetches data from the server you originally cloned from and automatically tries to merge it into the code you’re currently working on  ~$ git pull remote-name

ab. Pushing local changes to remote server ~$ git push remote-name branch-name

ac. Tagging - creating a tag ~$ git tag -a v1.4 -m "my version 1.4"

ad. Lightweight tag ~$ git tag v1.4-lw

ae. List of tags ~$ git show tagname

af. Display commits ~$ git show tagname



