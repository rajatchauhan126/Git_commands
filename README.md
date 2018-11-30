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
  push the code
    git push origin master
    
   --------
   don't want to manage by git, all config saved in .git file (this is hidden file)
    remove .git file
    
  ----------------------------join a project in github------------------------------
  fork : to create a copy of reposity to personel space
  
--clone a repository
  git clone path
  
--  
  
