# Bare repositories
**Bare repositories** are repositories that do not contain the working tree files, but the the
.git folder
 1. Used got sharing project in a centralized way.
 2. Enable pushing and pulling, facilitate collaboration on remote hosting services such as
    Github, Gitlab and Bitbucket
 3. It is meant to be a central point of contact for teams, so working copy files is a waste of
    space. Nobody will be checking out the files.
 
### To set a bare repository

Provide **--bare** option with the **git init** command
```
    git init --bare mynewbarerepo.git
```
### Converting a Regular repository to a bare one

```git
   git clone --bare <Existing-project-repo> myproject.git
```

## Backing up repositories

If you need to backup a git repo, there are two commands for that:
1. `git archive`
2. `git bundle`

### Archiving the repository as as tar or zip archive

```git
git  archive <branch_to_archive> --format=tar/zip --output=../youproject.[zip][tar.gz]
```

To archive the a git repository and share it with someone who doesn't have Git installed
To archive the main branch as a tarball
```git
git archive archive main --format=tar --output=mymainbranch.tar.gz
```

### Bundling the repository
You can export a snapshot of the repository and restore it whenever you want


1. #### Create the bundle for the repository
To create a bundle of you project which is under git
Make sure you are in the root directory of your project
```
 git bundle create ../youprojectname.bundle main
```
2. To clone the project in the other computer

Navigate the directory where that bundle is saved
```
 cd ~/Desktop/projects
```
```
  git clone youproject.bundle youproject -b main
```





