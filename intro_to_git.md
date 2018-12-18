$ mkdir languages
$ cd languages
Then we tell Git to make `languages` a **repository** -- a place where
separate repositories nested within the `languages` repository, whether
that the creation of the `languages` directory and its initialization as a
we can see that Git has created a hidden directory within `languages` called `.git`:
You should be in the `languages` directory.
/home/naraehan/Desktop/languages
Let's create a file called `zulu.txt` that contains some notes
We'll use `nano` to edit the file; you can use your favorite editor.
In particular, this does not have to be the `core.editor` you set globally earlier. But remember, the bash command to create or edit a new file will depend on the editor you choose (it might not be `nano`). 
$ nano zulu.txt
Type the text below into the `zulu.txt` file:
belongs to the Bantu language family
`zulu.txt` now contains a single line, which we can see by running:
$ cat zulu.txt
belongs to the Bantu language family
	zulu.txt
$ git add zulu.txt
	new file:   zulu.txt
Git now knows that it's supposed to keep track of `zulu.txt`,
$ git commit -m "start notes on Zulu language"
[master (root-commit) f22b25e] start notes on Zulu language
 create mode 100644 zulu.txt
    start notes on Zulu language
when it was created, and the log message Git was given when the commit was created.
$ nano zulu.txt
$ cat zulu.txt
belongs to the Bantu language family
spoken in South Africa
	modified:   zulu.txt
diff --git a/zulu.txt b/zulu.txt
--- a/zulu.txt
+++ b/zulu.txt
 belongs to the Bantu language family
+spoken in South Africa
$ git commit -m "add region information"
	modified:   zulu.txt
$ git add zulu.txt
$ git commit -m "add region information"
[master 34961b1] add region information
For example, suppose we're adding a few citations to relevant research to our thesis.
the current **changeset** 
$ nano zulu.txt
$ cat zulu.txt
belongs to the Bantu language family
spoken in South Africa
word order: SVO
diff --git a/zulu.txt b/zulu.txt
--- a/zulu.txt
+++ b/zulu.txt
 belongs to the Bantu language family
 spoken in South Africa
+word order: SVO
$ git add zulu.txt
diff --git a/zulu.txt b/zulu.txt
--- a/zulu.txt
+++ b/zulu.txt
 belongs to the Bantu language family
 spoken in South Africa
+word order: SVO
$ git commit -m "add word order info"
[master 005937f] add word order info
Author: Henry Higgins <profhiggins@oxford.edu>
Date:   Thu Aug 22 10:14:07 2018 -0400
    add word order info
Author: Henry Higgins <profhiggins@oxford.edu>
Date:   Thu Aug 22 10:07:21 2018 -0400
    add region information
Author: Henry Higgins <profhiggins@oxford.edu>
Date:   Thu Aug 22 09:51:46 2018 -0400
    start notes on zulu language
We've been adding one line at a time to `zulu.txt`, so it's easy to track our
let's make a change to `zulu.txt`, adding yet another line which unfortunately contains misinformation:
$ nano zulu.txt
$ cat zulu.txt
belongs to the Bantu language family
spoken in South Africa
word order: SVO
close relative of Danish
$ git diff HEAD zulu.txt
diff --git a/zulu.txt b/zulu.txt
--- a/zulu.txt
+++ b/zulu.txt
 belongs to the Bantu language family
 spoken in South Africa
 word order: SVO
+close relative of Danish
$ git diff HEAD~1 zulu.txt
$ git diff HEAD~2 zulu.txt
diff --git a/zulu.txt b/zulu.txt
--- a/zulu.txt
+++ b/zulu.txt
 belongs to the Bantu language family
+spoken in South Africa
+word order: SVO
+close relative of Danish
$ git show HEAD~2 zulu.txt
    start notes on zulu as a base
diff --git a/zulu.txt b/zulu.txt
+++ b/zulu.txt
+belongs to the Bantu language family
`f22b25e3233b4645dabd0d81e651fe074bd8e73b`. Instead of forcing us to type in the full 40 characters, though, Git mercifully lets us use the first few characters: 
$ git diff f22b25e zulu.txt
diff --git a/zulu.txt b/zulu.txt
--- a/zulu.txt
+++ b/zulu.txt
 belongs to the Bantu language family
+spoken in South Africa
+word order: SVO
+close relative of Danish
`zulu.txt` (the "ill-considered change").
	modified:   zulu.txt
$ git checkout HEAD zulu.txt
$ cat zulu.txt
belongs to the Bantu language family
spoken in South Africa
word order: SVO
$ git checkout f22b25e zulu.txt
$ cat zulu.txt
belongs to the Bantu language family
#	modified:   zulu.txt
$ git checkout HEAD zulu.txt