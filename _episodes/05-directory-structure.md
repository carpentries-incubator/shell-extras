---
title: Directory structure
teaching: 5
exercises: 0
questions:
- "Understanding the concept of Unix directory structure"
objectives:
- "FIXME"
keypoints:
- "FIXME"
---

All Unix files are integrated in a single directory structure. The file-system is arranged in a structure like an inverted tree. The top of this tree is the root and is written as a slash ‘/’.

## The `tree` command

The tree command shows a nice representation of all files and sub-directories in the current directory. Here is an example of it running on the shell-lesson-data from the Unix shell Carpentries Lesson.

~~~
~/shell-lesson-data$ tree
.
├── creatures
│   ├── basilisk.dat
│   ├── minotaur.dat
│   ├── original-basilisk.dat
│   ├── original-minotaur.dat
│   ├── original-unicorn.dat
│   └── unicorn.dat
├── data
│   ├── amino-acids.txt
│   ├── animal-counts
│   │   ├── animals.txt
│   │   └── list_animals.sh
│   ├── animals-subset.txt
│   ├── animals.txt
.
.
.
.

18 directories, 221 files
~~~
{: .output}

