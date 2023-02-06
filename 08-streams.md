---
layout: page
title: Extra Unix Shell Material
subtitle: Streams
minutes: 5
---
> ## Learning Objectives {.objectives}
>
> * The student should be able to split STDOUT effectively, thus logging and monitoring a process.

The Unix command [`tee`](https://en.wikipedia.org/wiki/Tee_(command)) duplicates STDOUT and sends the second copy to a file.  

Consider the input/output stream model we've already discussed as a system of pipes.  `tee` sensibly splits the flow of information, allowing one copy to be written to disk and leaving one copy available for a subsequent command in the chain.

Where might this be useful?  For instance, you can use this to both passively log and actively monitor a compilation or a data processing step.

Because `tee` preserves STDOUT, it allows recovery from actions that overwhelm the buffer of your shell's window as well, which is often limited.
