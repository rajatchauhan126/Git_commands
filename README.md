# Git_commands
Git_commands

download git
Install git
run installer


download notepad++
Install notepad++
run installer

----------------------------------------------------------------config---------------------------------------------------
type  notepad++ in git bash
if error set the environment path, append in path variable eg. "C:\Program Files\Notepad++"
restart the git bash
set the global username :
  git config --global user.name somename
set the global email :
  git config --global user.email somename@gmail.com

default setting
git config --global --list
set the default editor to notepad++ : 
  git config --global core.editor "notepad++.exe -multiInst -nosession"
  
 check the list :
  git config --global --list
  
  ---------------------------------------------------------------commands------------------------------------------
  initialize a project
    git init 
  add files in github
    git add .
  commit the changes
    git commit -m "add first coomit"
  pull
    git pull origin master
  push the code
    git push origin master
    
   --------
   don't want to manage by git, all config saved in .git file (this is hidden file)
    remove .git file
    
  ----------------------------join a project in github------------------------------
  fork : to create a copy of reposity to personel space
  
--clone a repository
  git clone path
  
----------------------------------------------------------------------------------  
add and commit directly
git commit -am "adding more text"

----
backout the changes from the stagging area to working directory.

git reset head level1_file.txt

don't want to make any changes, back to clean working directory, to last commited stage.

git checkout -- level1_file.txt

----------------------------------rename a file-------------
git mv level3_file.txt level3.txt

-------------------------------------------------------------------------------------------------------------------------------
for deleleting a file in windows cmd
  del /f filname.txt
  
--------------------------------------log--------------
git log  //in reverse order(recent first)
git log --abbrev-commit   // show in commit in 7 character only
git log --oneline --graph --decorate // compress in one line, asci graph provide, add any label for annotate our commit.
git log  410f4f4...3d45b58 //log between 2 commits
git log --since="3 days ago" //day based searching
git log -- hipster.txt //
git log -- follow -- level1/level2   //follow the rename
git show  51d88a9f23e5a0bbefb3b50cb24b173ee61c0c99

----------------------------------------------------Git alias---------------------------------
  create alias for big commands
  
--git config --global alias.hist "log --all --oneline --graph --decorate"
//hist is name of the alias
location where all these alias sit
  notepad++ ~/.gitconfig
  
--------------------------------------------------ignoring unwanted file and folder----------
create .gitignore 
  echo "" >> .gitignore
open the file and enter the file name which you want to ignore
filename //file
log/ //folder
node_module/  //folder

--------------------------------------------------Visual diff/merge tool setup------------------------
--p4merge for window install
--go to perforce.com
--download -> select p4merge visual merge tool -> download
--skip registration
--open and run the installer. 
--deselect all expect visual merge tool.
--next with all the next steps.  //completed installation

---open git bash
--set the path in advance setting "C:\Program Files\Perforce"

--git config --global merge.tool p4merge
--git config --global mergetool.p4merge.path "c:/program files/perforce/p4mere.exe"
--git config --global mergetool.prompt false

---diff tool config
--git config --global diff.tool p4merge
--git config --global difftool.p4merge.path "c:/program files/perforce/p4mere.exe"
--git config --global difftool.prompt false

--git config --global -e

-----------------------------------------Comparisions--------------------------
---working directory and stagging area

--git diff
--git difftool

---working directory and git stagging area

--git diff HEAD    //head pointer reference , diff in working directory and git stagging
--git difftool HEAD  //

--stagging area vs git repository

--git diff --staged HEAD //HEAD means last commit on current branch
--git difftool --staged HEAD 

-----------------------------------------Comparing between commits-----------------------

--git log --oneline
--git diff 51d88a9 HEAD // head - last commit in current branch
--git diff HEAD HEAD^  //head upcaret means -1

--git difftool HEAD HEAD^
--git difftool 51d88a9 d8851a9  //commit id one and two

------------------------------------local vs remote master branches
--git diff master origin/master   //master (@HEAD) - local repository, remore repository - origin/master

--------------------------------------b--------Branching-------------------
--git branch mynewbranch
--git checkout mynewbranch

--git checkout -b mynewbranch2
--git branch -m mynewbranch2 newbranch3 //rename the branch
--git branch -a //to see all branch
--git branch -d mynewbranch //should not be on the same branch

--------------------------Happy path/fast forward merge------------------
--git branch
--git branch -a
--git diff master mynewbranch2

--from master
--git merge mynewbranch2

-----
--git checkout -b add-copyright
--git merge add-copyright --no-ff

--------------------------------------Automatic merge-----------------------------
--git checkout -b simple-changes
--git merge simple-changes -m "merging from simple-changes" //commits will be there in master only label remove when deleting the simple-changes branch.

--------------------------------conflicting merges and resolution-----------------


-- create a branch mergeconflict and make some changes in existing file eg index.js
--commit the changes
--move to master branch. 
--make some changes in the same file above, index.js
--commit the changes
--git merge mergeconflict
--will get error of merge conflict

--git diff master mergeconflict
--git merge mergeconflict
--git mergetool
--select with code is needed and save.
--git commit -m "resolve merge conflict"
--open gitignore and enter  *.orig , save and close the file
--git commit the changes


----------------move and rename----
git mv string.c src/
git mv string.c string_operations.c

---------------git tag-----------
git tag
git tag -a 'Release_1_0' -m 'Tagged basic string operation code' HEAD
git push origin tag Release_1_0
git tag -d Release_1_0

-----------------------------------Rebase-------------------------------------
// to remove headache of merge in future
--create a new branch myfeature
--git checkout myfeature
--create a file and add some line
--git checkout master
--open readme file
--add some line.
--git commit -am "add"
--git log --oneline --all --decorate --graph
--git checkout myfeature
--git rebase master 
--git log --oneline --all --decorate --graph
--make some change in readme
--commit
--git log --oneline --all --decorate --graph

-----------------------------------stash---------------------------------
//save the incomplete changes in stash, can move to other branch and then come back to the branch again.
--git status -s
--git stash  //for save the file and will not populate in git status .
--git stash list
--git status -s
--git stash pop //you can checkout to old branch again and pop and old work will be back and you can continue to work from where you have left.

--git stash pop // poping the stash
--git stash apply //
--git stash drop //

-------------multiple stach
--change in a file 
--git stash save "simple changes"  //multiple stash with message
--change in a file 
--git stash save "index changes"   //multiple stash with message
--change in a file 
--git stash save "index changes"   //multiple stash with message

------------stash show
--git stash list
--git stash show stash@{1}
--git stash apply stash@{1}  //apply on a particular stash
--git stash drop stash@{1} //drop particular stash
--git stash list
--git stash clear //remove all the stash
--git stash -u  // to save all files

-----------------stash to a branch
--git stash branch newchanges //new branch created, switch to this, and stash   apply and same stash drop

-----------------------tagging----------------------------------------
//tags are label we can give to any commit in history.

--git tag mytag
--git tag --list
--git tag --delete mytag

-------------annotated tags
--git tag -a v-1.0   //for major milestone in code or release

------------comparing tags
--git tag -a v-1.0
--git commit --amend  //amend the message
or
--git tag v-1.2 -m "REelease 1.2"
--git tag --list
--git diff v-1.0 v-1.2
--git difftool v-1.0 v-1.2

cmd q to quit

--------------git tagging
--git tag -a v-0.9-beta 9879876 //unable to tag a commit, commit id 9879876,
                                -a for annotating

--------------updating tags
--git tag -a v-0.8-alpha -f 9879876 //commit id, -f for force

--------------push a tag
git push origin v-0.8-alpha

git push origin :v-0.8-alpha  //delete a tag, still have in local but not in                                  remote

---------------------------Reset and reflog----------------------------------
//Reset the head, 
//Remove the last commit and point to second last

--git log --graph --decorate --all --oneline
--git 




















































