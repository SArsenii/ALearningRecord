Q exits the current view in bash; Ctrl + C cancels the current command

---

# Initialize a repo
1. create folder
2. create repo on github
3. bash: cd ~/path_to_folder
4. bash: git init (.git is created, git tracks changes in folder) (-b main changes name of initial branch to main, default is master)
5. bash: git remote add origin (can change this name) git@ ... .git (SSH link from GitHub)
6. bash: git push -u origin master (or main) First push with -u ..., not required for the second and other pushes


# Standard workflow
1. git add file.txt (git add --all all files; git add . current folder)
2. git commit -m 'Imperative, e.g. Fix filtration pipeline'
3. amend: git commit --amend --no-edit (or -m 'new message') (Exit viw: Esc + :qa! + Enter)

# Time machine
1. bash: git restore --staged (file) - unstage what is staged (take from git add consequences)
2. bash: git reset --hard (SHA to return to, can be short, all changes after will be deleted) 
3. bash: git restore (file) - revert local changes that were not added/comitted

---

- Команда git restore --staged <file> переведёт файл из staged обратно в modified или untracked.
- Команда git reset --hard <commit hash> «откатит» историю до коммита с хешем <hash>. Более поздние коммиты потеряются!
- Команда git restore <file> «откатит» изменения в файле до последней сохранённой (в коммите или в staging) версии.

---

# Inspecting changes
git log --oneline
1. git diff (modified files only)
2. git diff --staged
3. git diff hashA hashB (difference between two commits, first is the source, second is after changes; how to transform hashA to hashB)
Состояние файлов на момент первого переданного коммита будет сравниваться с состоянием файлов на момент второго.

# Clone repo
- git clone git@github.com:accountname/reponame.git (ssh way, or using https link)

# Branches
- git branch (check all branches) (-a option for all branches not only local)
- git branch bname (create a branch named bname)
- git checkout bname (visit bname branch)
- git checkout -b bname (create and visit)
- from the branch to which we merge: git merge bname
- git branch -D bname (deletes bname branch)

# Remote repo
git push -u origin my-branch (от англ. push, «толкнуть», «протолкнуть») — отправь новую ветку my-branch в удалённый репозиторий и свяжи локальную ветку с удалённой, чтобы при дополнительных коммитах можно было писать просто git push без -u;

git push my-branch — отправь дополнительные изменения в ветку my-branch, которая уже существует в удалённом репозитории;

git pull (от англ. pull, «вытянуть») — подтяни изменения текущей ветки из удалённого репозитория.