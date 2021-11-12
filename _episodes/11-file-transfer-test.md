---
title: "Transferring Files"
teaching: 10
exercises: 5
questions:
- "How to use wget, curl and rsync to transfer file?"
objectives:
- "Understand that wget, curl and rsync can transfer files"
keypoints:
- "wget is a utility for downloading remote webpages. It includes options to mirror an entire site."
- "curl is another utility for downloading remote webpages. It defaults to outputting the result on screen, this can be piped to other programs."
- "rsync is a utility for transferring files. It can use the SSH protocol and is useful for mirroring complicated directory structures from one computer to another."
---

There are other ways to interact with remote files other than scp.

## Wget

Wget is a simple tool developed for the GNU Project that downloads files with the HTTP, HTTPS and FTP protocols. It is widely used by Unix-like users and is available with most Linux distributions.

To download this lesson (located at https://carpentries-incubator.github.io/shell-extras/03-file-transfer/index.html) from the web via HTTP we can simply type:

~~~
$ wget https://carpentries-incubator.github.io/shell-extras/03-file-transfer/index.html
~~~
{: .bash}

~~~
--2021-05-29 02:12:18—  
https://carpentries-incubator.github.io/shell-extras/03-file-transfer/index.html
Resolving carpentries-incubator.github.io (carpentries-incubator.github.io)... 185.199.111.153, 185.199.110.153, 185.199.109.153, ...
Connecting to carpentries-incubator.github.io (carpentries-incubator.github.io)|185.199.111.153|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 22467 (22K) [text/html]
Saving to: ‘index.html’
index.html        100%[===================>]  21.94K  --.-KB/s    in 0.003s  

2021-05-29 02:12:19 (6.35 MB/s) - ‘index.html’ saved [22467/22467]
~~~
{: .output}

Alternatively, you can add more options, which are in the form:

~~~
wget -r -np -D domain_name target_URL
~~~
{: .bash}

where `-r` means recursively crawl to other files and directories, `-np` means avoid crawling to parent directories, and `-D` means to target only the following domain name

For our URL it would be:

~~~
$ wget -r -np -D software-carpentry.org http://carpentries-incubator.github.io/shell-extras/03-file-transfer/index.html
~~~
{: .bash}

To restrict retrieval to a particular extension(s)
we can use the `-A` option followed by a comma separated list:

~~~
wget -r -np -D software-carpentry.org -A html http://carpentries-incubator.github.io/shell-extras/03-file-transfer/index.html
~~~
{: .bash}

We can also clone a webpage with its local dependencies:

~~~
$ wget -mkq target_URL
~~~
{: .bash}

We could also clone the entire website:

~~~
$ wget -mkq -np -D domain_name domain_name_URL
~~~
{: .bash}

and add the `-nH` option if we do not want a subdirectory created for the websites content:

e.g.

~~~
$ wget -mkq -np -nH -D example.com http://example.com
~~~
{: .bash}

where:

`-m` is for mirroring with time stamping, infinite recursion depth, and preservation of FTP directory settings
`-k` converts links to make them suitable for local viewing 
`-q` supresses the output to the screen

The above command can also save the clone the contents of one domain to another
if we are using ssh or sshfs to access a webserver. 
 
Please refer to the man page by typing `man wget` in the shell for more information.
  

{% include links.md %}
