# cheat_codes
My cheat codes


# 1. GIT

## 1.1. How can I determine when a Git branch was created?

To find the first commit in a branch that is not present in the parent of the branch (i.e., the first unique commit in the branch), you can use the following command:
```bash
git log --graph --oneline --boundary <branch> ^<branch>^@ --pretty='%C(cyan)%ad %C(yellow)%h %C(cyan)%d %Creset%s'
```
Replace <branch> with the name of your branch.
This command utilizes the --boundary option to display commits that are in the branch but not in the parent of the branch. The ^ symbol is used to negate the commit (indicating "not in the parent"), and ^@ represents all reachable commits from the specified commit.
This will provide a graphical visualization and a summarized list of commits that are unique to the branch, showing the first commit different from the branch's parent.


## 1.2. How check commit that are in a branch and not in other?

A --  E - F - G  master
   \- B - C - D  fix

```bash
git log master..fix  
```
  B C D
```bash
git log master...fix
```
  B C D and E F G

```bash
git <orig>..<dest> --graph  --date-order --pretty='%C(cyan)%ad %C(yellow)%h %C(cyan)%d %Creset%s'
```
