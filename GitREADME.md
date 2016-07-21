
lynx -source rawgit.com/transcode-open/apt-cyg/master/apt-cyg > apt-cyg install apt-cyg /bin

wget raw.github.com/transcode-open/apt-cyg/master/apt-cyg
chmod +x apt-cyg
mv apt-cyg /usr/local/bin
Now that apt-cyg is installed. Here are few examples of installing some packages

apt-cyg install nano
apt-cyg install git
apt-cyg install ca-certificates

clear screen-- install ncurses
apt-cyg install ncurses
clear

configure git
$ git config --global user.name "Patrick Phiri"
$ git config --global user.email "patrick_phiri@chs.net"
$ git config --global core.editor "notepad -wl1"
$ git config --global color.ui true

git auto-completion
$ curl -OL https://github.com/git/git/raw/master/contrib/completion/git-completion.bash
$ mv ~/git-completion.bash ~/ .git-completion.bash
edit .bashrc and include following:
if [ -f ~/.git-completion.bash ]; then
        source ~/.git-completion.bash
fi

Project tracking
$ mkdir first_git_project
$ cd first_git_project/
$ git init
Initialized empty Git repository in /home/pphiri/projects/first_git_project/.git/
$ ls -la
total 8
drwxr-xr-x+ 1 pphiri Domain Users 0 Jul 20 15:52 .
drwxr-xr-x+ 1 pphiri Domain Users 0 Jul 20 15:51 ..
drwxr-xr-x+ 1 pphiri Domain Users 0 Jul 20 15:52 .git

create a simple text file and save to folder

pphiri@800QRM008 ~/projects/first_git_project
$ git add .

pphiri@800QRM008 ~/projects/first_git_project
$ git commit -m "Initial commit"
[master (root-commit) f5f2dcf] Initial commit
 1 file changed, 1 insertion(+)
 create mode 100755 first_file.txt

$ git log
commit f5f2dcfec2ecb7fac523a1666e81c2661db51277
Author: Patrick Phiri <patrick_phiri@chs.net>
Date:   Wed Jul 20 15:59:04 2016 -0500

    Initial commit

pphiri@800QRM008 ~/projects/first_git_project
$ git status
On branch master
nothing to commit, working directory clean

pphiri@800QRM008 ~/projects/first_git_project
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        second_file.txt
        thrid_file.txt

nothing added to commit but untracked files present (use "git add" to track)

pphiri@800QRM008 ~/projects/first_git_project
$ git add second_file.txt

pphiri@800QRM008 ~/projects/first_git_project
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   second_file.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        thrid_file.txt

pphiri@800QRM008 ~/projects/first_git_project
$ git log
commit f1ef999af5ca799a2136a8db10aa2d6e82ca272e
Author: Patrick Phiri <patrick_phiri@chs.net>
Date:   Wed Jul 20 16:47:41 2016 -0500

    add second file to project

commit f5f2dcfec2ecb7fac523a1666e81c2661db51277
Author: Patrick Phiri <patrick_phiri@chs.net>
Date:   Wed Jul 20 15:59:04 2016 -0500

    Initial commit
pphiri@800QRM008 ~/projects/first_git_project
$ git add thrid_file.txt

pphiri@800QRM008 ~/projects/first_git_project
$ git commit -m " Add third file to project"
[master a369417]  Add third file to project
 1 file changed, 1 insertion(+)
 create mode 100755 thrid_file.txt

pphiri@800QRM008 ~/projects/first_git_project
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    thrid_file.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        third_file.txt

no changes added to commit (use "git add" and/or "git commit -a")

pphiri@800QRM008 ~/projects/first_git_project
$ git add third_file.txt

pphiri@800QRM008 ~/projects/first_git_project
$ git commit -m "Add third file, with corrected spelling on file name"
[master d8afe66] Add third file, with corrected spelling on file name
 1 file changed, 1 insertion(+)
 create mode 100755 third_file.txt

$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   first_file.txt
        deleted:    thrid_file.txt

no changes added to commit (use "git add" and/or "git commit -a")

$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   first_file.txt

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   second_file.txt
        modified:   third_file.txt
        deleted:    thrid_file.txt

$ git commit -m "Made changes to text in first file"
[master 0fad99d] Made changes to text in first file
 1 file changed, 1 insertion(+), 1 deletion(-)

pphiri@800QRM008 ~/projects/first_git_project
$ git add second_file.txt

pphiri@800QRM008 ~/projects/first_git_project
$ git add third_file.txt

pphiri@800QRM008 ~/projects/first_git_project
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   second_file.txt
        modified:   third_file.txt

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    thrid_file.txt


pphiri@800QRM008 ~/projects/first_git_project
$ git commit -m "made changes to second and third files"
[master ce8cf81] made changes to second and third files
 2 files changed, 2 insertions(+), 2 deletions(-)

pphiri@800QRM008 ~/projects/first_git_project
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    thrid_file.txt

no changes added to commit (use "git add" and/or "git commit -a")

Viewing changes with diff
pphiri@800QRM008 ~/projects/first_git_project
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   first_file.txt
        deleted:    thrid_file.txt

no changes added to commit (use "git add" and/or "git commit -a")

pphiri@800QRM008 ~/projects/first_git_project
$ git diff
diff --git a/first_file.txt b/first_file.txt
index c4d3f4b..6685819 100755
--- a/first_file.txt
+++ b/first_file.txt
@@ -1 +1,3 @@
-This is my first file that I added to my project.
\ No newline at end of file
+This is my first file that I added to my project.^M
+^M
+It comes before all other files.
\ No newline at end of file
diff --git a/thrid_file.txt b/thrid_file.txt
deleted file mode 100755
index d5dcf70..0000000
--- a/thrid_file.txt
+++ /dev/null
@@ -1 +0,0 @@
-This is my third file.
\ No newline at end of file

pphiri@800QRM008 ~/projects/first_git_project
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   primary_file.txt

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    first_file.txt
        deleted:    thrid_file.txt


pphiri@800QRM008 ~/projects/first_git_project
$ git mv second_file.txt secondary_file.txt

pphiri@800QRM008 ~/projects/first_git_project
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   primary_file.txt
        renamed:    second_file.txt -> secondary_file.txt

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        deleted:    first_file.txt
        deleted:    thrid_file.txt

***Adding Gitignore***
pphiri@800QRM008 ~/projects/explore_california
$ notepad .gitignore

pphiri@800QRM008 ~/projects/explore_california
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore

nothing added to commit but untracked files present (use "git add" to track)

pphiri@800QRM008 ~/projects/explore_california
$ git add .gitignore

pphiri@800QRM008 ~/projects/explore_california
$ notepad .gitignore

pphiri@800QRM008 ~/projects/explore_california
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   .gitignore

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   .gitignore


pphiri@800QRM008 ~/projects/explore_california
$ notepad .gitignore

pphiri@800QRM008 ~/projects/explore_california
$ git add .gitignore

pphiri@800QRM008 ~/projects/explore_california
$ git commit -m"Add gitignore"
[master 2d94152] Add gitignore
 1 file changed, 7 insertions(+)
 create mode 100755 .gitignore

pphiri@800QRM008 ~/projects/explore_california
$ git status
On branch master
nothing to commit, working directory clean


https://github.com/github/gitignore

***Start sublime text from cygwin***
add folloing code in .bashrc and recompile

sublime() {

 local cmd="'$(cygpath 'C:\Users\pphiri\Documents\Sublime Text 2\sublime_text.exe')'"



 if [[ $@ ]]; then

      cmd=$cmd' "'$(cygpath --windows "$@" | sed ':a;N;$!ba;s/\n/" "/g')'"'

 fi

 eval $cmd
}


