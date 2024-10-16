# LAB 6

### 202239870 박민우

## Git-1

### Version Control and Collaboration

- Essential to use a version control system for software development and other documentation works
- Basic solution: Making copies
ex)
프로젝트_최종.txt
프로젝트_최종_수정1.txt
프로젝트_최종_수정1_진짜최종.txt
프로젝트_최종_수정1_진짜최종_추가수정2.txt
…
프로젝트_구자경_최종.txt
프로젝트_구자경_최종_홍길동_수정.txt
프로젝트_구자경_최종_홍길동_수정_구자경_검토.txt
…
- Need a systematic management system for version control and collaboration

### Changes vs Snapshots

- Common: Record the version over time.
- Difference
    - Changes: Storing data as changes to the base version
    - Snapshots: Storing data as snapshots ex) git

### Version control in three parts.

- Local: A way to control the version purely by yourself.
- Centralized: Manage Version Databases from Central VCS Server. Store each user's files on a central server. Central server dependency is high.
- Distributed: Complement the disadvantage of Centralized's high dependence on central servers. Mainly used in git. Each local also has a version database. Communication is possible not only between servers but also between users.

### Three States in Git

- Modified(Working Directory) -> staged(Staging Area) -> committed(git directory(Repository))
- No matter how much work you do, it won't be recorded in snapshot until you commit.

### Git config: First-time setup

- Git configurations are stored in three levels:
1. system level: --system option. Affects all uses and repositories on the system (administrative)
file: /etc/gitconfig
2. Global (user) level: --global option. Affects all repositories of a current user
file: ~/.config/git/config
3. Local level: --local option. Specific to the current repository
file: .git/gitconfig
*Each level overrides values in the previous level: system -> global -> local*
- If you want to see the config list,

```
$ git config --list

```

- Setup

```
$ git config --global user.name "username"
$ git config --global user.email "email-address@gachon.ac.kr"
$ git config --global init.defaultBranch main

```

- If you want to see the config level,

```
$ git config --list --show-origin

```

- If you want to see the user name

```
$ git config user.name

```

### Git

- $ git init: Initializing a Repository in an Existing Directory
- $ git status: Checking Repository Status
- $ git add [file_name]: Adding a new file to be staged (tracked)
*Tip
If there is a problem on nano (in Windows),
you can edit the file in any other text editor (e.g., 메모장)*
- $ git add .: Adding all files to be staged (tracked)
- $ git rm --cached [file_name]: Unstaging a file
- Ignoring a file
ex)

```
$ nano .gitignore

```

```
1. ignore all .a files
*.a
2. but do track lib.a, even though you're ignoring a files above
!lib.a
3. only ignore the TODO file in the current directory, not subdir/TODO
/TODO
4. ignore all files in any directory named build
build/
5. ignore doc/notes.txt, but not doc/server/arch. txt
doc/*.txt
6. ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf

```

*Tip
If there is a problem on nano (in Windows),
you can edit the file in any other text editor(e.g., 메모장)*

- $ git commit -m “commit message” : Commit
- $ git log: Seeing Committed History
- Change branch name
ex)

```
$ git branch
* master
$ git branch -m master main
$ git branch
* main

```
