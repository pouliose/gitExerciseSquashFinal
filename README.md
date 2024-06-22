### gitExerciseSquash
A project showcase of how to use squash command.

In order to practice on your own, use the following two repos:<br>
-https://github.com/pouliose/gitExerciseSquash <br>
-https://github.com/pouliose/gitExerciseSquashFinal


### A. 
Clone locally the repo "gitExerciseSquash". 
```
git clone https://github.com/pouliose/gitExerciseSquash.git
```
It includes the following branches:
1. **main** with 2 initial commits
2. **feature1** that originates from **main** and has 4 commits
3. **dev** that originates from main, and has 2 commits

The goal is to compress-squash all the commits from feature1 to one commit, merge feature1 branch to dev, and later merge dev to main.

An overview of the whole commit history, in an IDE e.g. IntelliJ.
![Graph of all the commits in the 3 branches](/imagesReadme/a.png)

from cmd you can have a similar graph with:
```
git log --graph --oneline --branches
```
![Graph of all the commits in the 3 branches, from cmd](/imagesReadme/b.png)

### B. 
Let's say we want to squash the 4 commits of branch feature1 into one commit. We use the command:
```
git rebase -i 0c38aed
```
<b>0c38aed</b> is the hash code that refers to the last commit that was inherited from main (parent branch). -i stands for interactive. Also,  useful is the command git rebase --abort.
### C. 
In the vi editor that opens you select in front of each commit which commit will be picked as name (leave the already command pick in front of each command) and which commit message will be neglected by replacing with squash or s.
<br>
Press Esc button and type :wq to save the result.


![The return of the squash command](/imagesReadme/c.png)

Useful commands for vi editor.<br>
Esc — Switch to Command mode.<br>
:w — Save and continue editing.<br>
:wq or ZZ — Save and quit/exit vi.<br>
:q! — Quit vi and do not save changes.<br>

### D. 
After that you proceed to write down a commit message, let's say <i>CommitD'</i>.<br /><br />
![Graph after squash](/imagesReadme/d.png)


The branch history after applying squash looks more concrete and easy to track changes.
![Comparison of the neatness after squasing commits to the branch feature1](/imagesReadme/f.png)



### E.
Then we can merge feature1 into dev and later dev into main.

