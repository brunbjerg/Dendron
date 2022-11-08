---
id: ia71xf3u1ckn3qlgntmpxqr
title: Branching
desc: ''
updated: 1667766616870
created: 1667575111762
---


Git simply works by using pointers to snapshots of files.

Allows us to create different work flows. 

git checkout -b: Creates new branch and ckeckouts it out (moves head)

Creating a new branch does not necessarily branch the snapshot. If the master remains the same we basically only move the head forward.

Id some other part of the code breaks we simply switch to that. When switching branches git set working directory to what it was last time there was committed to that branch. 

fast forward merge is when we can simply move the pointer forward to the place where the merge will happen. Meaning there was no branches. 

I am on main, merging in test to the main branch. 

Three way merge using the two snapshot that the pointers at the two tips points to as well as the common ancestor of the two.

merge commit: the merge results in a new commit. This new commit then has two parents. One for each branch that were merged together. It should be noted that since we merged in the test branch, the pointers form a straight line when using the main branch as the reference. 

The branch that is being checked out is the one that the other branches are merged into. 

Resolutions are marked. Run add on each or all files when the conflict has been resolved

* in git branch means the file where the HEAD is at.

Branches (which are different HEADS in the VCS) can be deleted when they have been merged.

Context switch quickly. 

This is local. Important to understand how the mechanics of this works