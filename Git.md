```plain text
## These are common Git commands used in various situations:

## start a working area (see also: git help tutorial)
  clone     Clone a repository into a new directory
  init      Create an empty Git repository or reinitialize an existing one

## work on the current change (see also: git help everyday)

  add       Add file contents to the index
  mv        Move or rename a file, a directory, or a symlink
  restore   Restore working tree files
  rm        Remove files from the working tree and from the index

## examine the history and state (see also: git help revisions)

  bisect    Use binary search to find the commit that introduced a bug
  diff      Show changes between commits, commit and working tree, etc
  grep      Print lines matching a pattern
  log       Show commit logs
  show      Show various types of objects
  status    Show the working tree status

## grow, mark and tweak your common history

  branch    List, create, or delete branches
  commit    Record changes to the repository
  merge     Join two or more development histories together
  rebase    Reapply commits on top of another base tip
  reset     Reset current HEAD to the specified state
  switch    Switch branches
  tag       Create, list, delete or verify a tag object signed with GPG

## collaborate (see also: git help workflows)

  fetch     Download objects and refs from another repository
  pull      Fetch from and integrate with another repository or a local branch
  push      Update remote refs along with associated objects
```

```
  501  git init
  502  echo "m1" > sample.txt
  503  ls
  504  cat sample.txt
  505  git status
  506  git add .
  507  git status
  508  git commit -m "m1"
  509  git log --oneline
  510  echo "m2" >> sample.txt
  511  git add .
  512  git commit -m "m2"
  513  echo "m3" >> sample.txt
  514  git add .
  515  git commit -m "m3"
  516  echo "m4" >> sample.txt
  517  git add .
  518  git commit -m "m4"
  519  git log --oneline
  520  git checkout -b dev
  521  echo "d1" >> sample.txt
  522  git add ,
  523  git add .
  524  git commit -m "d1"
  525  cat sample.txt
  526  git switch master
  527  cat sample.txt
  528  git switch dev
  529  cat sample.txt
  530  echo "d2" >> sample.txt
  531  git add .
  532  git commit -m "d2"
  533  cat sample.txt
  534  git log --oneline
  535  git log --oneline
  536  git diff dev master
  537  git diff master dev
  538  git
  539  git switch master
  540  cat sample.txt
  541  git merge dev
  542  cat sample.txt
  543  git log --oneline
  544  git reset --hard HEAD~5
  545  git log --oneline
  546  cat sample.txt
  547  git remote -v
  548  git remote add origin https://github.com/sakit333/ignite-batch.git
  549  git remote -v
  550  git push origin master
  551  git log --oneline
  552  git tag v1.1
  553  git log --oneline
  554  echo "m2" >> sample.txt
  555  git add .
  556  git commit -m "m2"
  557  git log --oneline
  558  git tag v1.2
  559  git log --oneline
  560  echo "m3" >> sample.txt
  561  git add .
  562  git commit -m "m3"
  563  git log --oneline
  564  git tag v1.3 b0d2d32
  565  git log --oneline
  566  git diff origin/master master
  567  git push origin master
  568  git push origin v1.1
  569  git push origin v1.3
  570  git tag --help
  571  git push origin --tags
  572  ls
  573  echo "username & password" > credential.conf
  574  ls
  575  cat credential.conf
  576  cat sample.txt
  577  echo "m4" >> sample.txt
  578  ls
  579  git status
  580  echo "url" > jsp.conf
  581  ls
  582  git status
  583  git add .
  584  git status
  585  git reset jsp.conf
  586  git reset credential.conf
  587  git status
  588  touch a.js b.js c.js
  589  ls
  590  git status
  591  git reset sample.txt
  592  git status
  593  ls
  594  vi .gitignore
  595  ls
  596  ls -a
  597  git status
  598  git commit -m "js sample"
  599  git status
  600  git add .
  601  git status
  602  git commit -m "js sample"
  603  git status
  604  echo "homepage" >> a.js
  605  cat a.js
  606  echo "about" >> b.js
  607  cat b.js
  608  echo "contact" >> c.js
  609  cat ca
  610  cat c.js
  611  git status
  612  ls
  613  git status
  614  git add .
  615  git commit -m "testing"
  616  vi .gitignore
  617  git status
  618  echo "colour" >> a.js
  619  cat a.js
  620  git status
```
