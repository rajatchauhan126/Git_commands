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

  
