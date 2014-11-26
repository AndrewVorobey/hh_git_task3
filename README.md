******************* 1 ******************

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git init

Initialized empty Git repository in /home/andrew/Desktop/hh/git/3/.git/

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ echo '1

> 2

> 3

> 4' >task3.txt

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git hash-object -w task3.txt

94ebaf900161394059478fd88aec30e59092a1d7

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git update-index --add --cacheinfo 100644 94ebaf900161394059478fd88aec30e59092a1d7 task3.txt

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git write-tree
27ce95e2785d78743af979ec3a7e23c0828deeb5

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ echo "commit 
AndrewVorobey 2" | git commit-tree 27ce95

ae2a22613eda5140d4c5d146976dbc4ce61c98db

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$  echo "ae2a22613eda5140d4c5d146976dbc4ce61c98db" > .git/refs/heads/master

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git log
commit ae2a22613eda5140d4c5d146976dbc4ce61c98db

Author: Andrew <andrew_vorobey@mail.ru>
Date:   Wed Nov 26 18:43:36 2014 +0300

    commit AndrewVorobey 2


******************* 2 ******************

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ echo '1

> 2' > task3_new.txt

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ echo '4

> 3

> 2

> 1' >task3.txt

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git update-index task3.txt

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git update-index --add  task3_new.txt

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git write-tree

966b8b3f38c531dbfdc4f12191dcefc3a8f32ce8

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ echo "commit AndrewVorobey 2(really 2)" | git commit-tree -p ae2a22 27ce95 

6e360496103b4ac79205871158136b95f5784833

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ echo "6e360496103b4ac79205871158136b95f5784833"> .git/refs/heads/master
andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git log

commit 6e360496103b4ac79205871158136b95f5784833

Author: Andrew <andrew_vorobey@mail.ru>

Date:   Wed Nov 26 19:20:32 2014 +0300

    commit AndrewVorobey 2(really 2)

commit ae2a22613eda5140d4c5d146976dbc4ce61c98db

Author: Andrew <andrew_vorobey@mail.ru>

Date:   Wed Nov 26 18:43:36 2014 +0300

    commit AndrewVorobey 2



******************* 3 ******************

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ mkdir gittask

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git cat-file -p 
94ebaf900161394059478fd88aec30e59092a1d7 > gittask/task3.txt

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git update-index --add  gittask/task3.txt

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ git write-tree

a59c10c2e7891cab135e8135b6fab73c305764ef

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ echo "commit AndrewVorobey 3" | git commit-tree -p 6e3604 a59c10

f3c4398d6fad5a8527ce3f623845ed7b68656951

andrew@HP-ENVY-m6-Notebook-PC:~/Desktop/hh/git/3$ echo "f3c4398d6fad5a8527ce3f623845ed7b68656951"> .git/refs/heads/mastergit 


