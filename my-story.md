## Chapter 1: The First Recipe (20 Marks)
Nanu says: "Winter is coming. Write the bhapa pitha recipe first."


Task A: Set up Git identity and create your repository folder.

![alt text](image.png)

D:\etc\Ostad\DevOps\Assignment_2>git --version
git version 2.52.0.windows.1

D:\etc\Ostad\DevOps\Assignment_2>git config --global user.name "Md. Shazadul islam" 

D:\etc\Ostad\DevOps\Assignment_2>git config --global user.email "shazzad.wfp@gmail.com" 

D:\etc\Ostad\DevOps\Assignment_2>mkdir nanur-khata

D:\etc\Ostad\DevOps\Assignment_2>mkdir nanur-khata
A subdirectory or file nanur-khata already exists.

D:\etc\Ostad\DevOps\Assignment_2>git init
Initialized empty Git repository in D:/etc/Ostad/DevOps/Assignment_2/.git/


### Task B: Create the first recipe file, check status, and stage it.

![alt text](image-1.png)

D:\etc\Ostad\DevOps\Assignment_2>git init
Initialized empty Git repository in D:/etc/Ostad/DevOps/Assignment_2/.git/
                                 echo "# Bhapa Pitha Recipe" > bhapa-pitha.md
D:\etc\Ostad\DevOps\Assignment_2>
D:\etc\Ostad\DevOps\Assignment_2>git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        bhapa-pitha.md
        image.png
        my-story.md

nothing added to commit but untracked files present (use "git add" to track)

D:\etc\Ostad\DevOps\Assignment_2>git add bhapa-pitha.md

D:\etc\Ostad\DevOps\Assignment_2>

### Task C: Modify the file and practice git diff

"One and a half cups of gur, not two!"
![alt text](image-2.png)

D:\etc\Ostad\DevOps\Assignment_2>git diff --staged     
diff --git a/bhapa-pitha.md b/bhapa-pitha.md
new file mode 100644
index 0000000..43c392d
--- /dev/null
+++ b/bhapa-pitha.md
@@ -0,0 +1 @@
+"# Bhapa Pitha Recipe" 

### Task D: Commit your changes.

D:\etc\Ostad\DevOps\Assignment_2>git commit -m "Add initial bhapa pitha recipe with corrected gur amount"
[master (root-commit) 0def227] Add initial bhapa pitha recipe with corrected gur amount
 1 file changed, 1 insertion(+)
 create mode 100644 bhapa-pitha.md


 ### Task E: Practice unstaging a file.
 ![Practice unstaging a file](image-3.png)

 D:\etc\Ostad\DevOps\Assignment_2>touch bazar-list.txt
'touch' is not recognized as an internal or external command,
operable program or batch file.

D:\etc\Ostad\DevOps\Assignment_2>git add bazar-list.txt
fatal: pathspec 'bazar-list.txt' did not match any files

D:\etc\Ostad\DevOps\Assignment_2>git reset bazar-list.txt
fatal: ambiguous argument 'bazar-list.txt': unknown revision or path not in the working tree.
Use '--' to separate paths from revisions, like this:
'git <command> [<revision>...] -- [<file>...]'

## Chapter 2: The Secret Spice (10 Marks)
### Nanu's secret spice blend must never reach GitHub.
  

Task A & B: Prevent secret files from being tracked.

![Create gitignore and secret some files](image-4.png)

D:\etc\Ostad\DevOps\Assignment_2>echo -e "secret-masala.txt\n*.tmp\ndraft/" > .gitignore

D:\etc\Ostad\DevOps\Assignment_2>git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        draft/
        image-1.png
        image-2.png
        image-3.png
        image.png
        my-story.md
        secret-masala.txt
        temp1.tmp
        temp2.tmp

nothing added to commit but untracked files present (use "git add" to track)


## Chapter 3: The Eid Special (20 Marks)
### we want to test the Eid recipes without touching the main book.

### Task A: Create and switch to a new branch.

D:\etc\Ostad\DevOps\Assignment_2>git checkout -b eid-special
Switched to a new branch 'eid-special'


### Task B: Add two recipes in separate commits.

![Add two recipes in separate commits](image-5.png)

D:\etc\Ostad\DevOps\Assignment_2>echo "# Eid Biryani" > biryani.md

D:\etc\Ostad\DevOps\Assignment_2>git add biryani.md

D:\etc\Ostad\DevOps\Assignment_2>git commit -m "Add Eid biryani recipe" 
[eid-special 414f857] Add Eid biryani recipe
 1 file changed, 1 insertion(+)
 create mode 100644 biryani.md

D:\etc\Ostad\DevOps\Assignment_2>echo "# Shemai Recipe" > shemai.md

D:\etc\Ostad\DevOps\Assignment_2>git add shemai.md

D:\etc\Ostad\DevOps\Assignment_2>git commit -m "Add traditional shemai recipe"
[eid-special 6185754] Add traditional shemai recipe
 1 file changed, 1 insertion(+)
 create mode 100644 shemai.md

 ### Task C: Merge back to main.

 D:\etc\Ostad\DevOps\Assignment_2>git checkout master
Switched to branch 'master'

D:\etc\Ostad\DevOps\Assignment_2>git merge eid-special
Updating 0def227..6185754
Fast-forward
 biryani.md | 1 +
 shemai.md  | 1 +
 2 files changed, 2 insertions(+)
 create mode 100644 biryani.md
 create mode 100644 shemai.md

D:\etc\Ostad\DevOps\Assignment_2>git log --oneline
6185754 (HEAD -> master, eid-special) Add traditional shemai recipe
414f857 Add Eid biryani recipe
0def227 Add initial bhapa pitha recipe with corrected gur amount


## Chapter 4: Mitu Joins In (20 Marks)
### Mitu wants to write in the book too, all the way from Chattogram.

D:\etc\Ostad\DevOps\Assignment_2>git remote add origin https://github.com/Shazzad131/nanur-khata

D:\etc\Ostad\DevOps\Assignment_2>git branch -M main

D:\etc\Ostad\DevOps\Assignment_2>git push -u origin main
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 12 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (9/9), 815 bytes | 90.00 KiB/s, done.
Total 9 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/Shazzad131/nanur-khata
 * [new branch]      main -> main


 ### Task B: Simulate Mitu.