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

