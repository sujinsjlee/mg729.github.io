---
layout: post
title: Git - refs/for and refs using in Git
description: What is refs/for usage
modified: 2020-10-25
tags: [Git]
categories: [Git]
---

## Git refs/for
> **git push [option] [ < repository > [< refspec >]]**  

## refs
* git manages all commit in key-value form
* Key is 40 digits of hash value made of SHA-1.
* Hash values are stored in a file with an name **References**
  * `.git/refs`
* All refs are stored in `.git/refs`
* Heads, remotes, and tags directories exist at `.git/refs`

```shell
$ pwd
.git/refs

$ ls
heads/  remotes/  tags/

$ cd
heads/

$ ls
master

$ cat master
6aeawerdfgdfg861145f19sdfafetrgf80af91
```

* in above example, Master Branch is *refs*
* git refers to the *refs* pointing to a particular task as **branch**

## refs/for in Gerrit
> [Gerrit Documentation](https://gerrit-review.googlesource.com/Documentation/)


When pushing a new or updated commit to Gerrit, you push that commit using a reference, in the refs/for namespace. This reference must also define the target branch, such as `refs/for/[BRANCH_NAME]`.

For example, to create a new change on the master branch, you would use the following command:


```shell
$ git push origin HEAD:refs/for/master
```
The `refs/for/[BRANCH_NAME]` syntax allows Gerrit to differentiate between commits that are pushed for review and commits that are pushed directly into the repository.

* refer to
    * [why using refs/for in gerrit](https://stackoverflow.com/questions/10461214/why-is-git-push-gerrit-headrefs-for-master-used-instead-of-git-push-origin-mast)