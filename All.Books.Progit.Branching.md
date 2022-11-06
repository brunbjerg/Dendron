---
id: ia71xf3u1ckn3qlgntmpxqr
title: Branching
desc: ''
updated: 1667751743425
created: 1667575111762
---


Git simply works by using pointers to snapshots of files.

Allows us to create different work flows. 

git checkout -b: Creates new branch and ckeckouts it out (moves head)

Creating a new branch does not necessarily branch the snapshot. If the master remains the same we basically only move the head forward.

Id some other part of the code breaks we simply switch to that. When switching branches git set working directory to what it was last time there was committed to that branch. 

