---

layout: post
title:  "Ode to LISP &hearts; "
date:   2014-12-16 20:32:14
categories: LISP
comments: true

---

Finally, after a long time, I started my journey into the magical world of [LISP][link_LISP]-- something I've pined for long.

And began learning so many new things that I felt I should record my discoveries somewhere, more like a 'travelogue' (or a monologue? :)).

Perhaps, someone travelling or planning to take this path will find it useful in someway, someday...?

## Prerequisites

First, I made sure I had the following things sorted out:

+ Choosing a 'dialect' of LISP to learn. [Common LISP][link_Common_LISP] & [Scheme][link_Scheme] are the 2 most popular & enduring ones out there. I chose Common LISP for now (though I love Scheme too!).
+ Install an implementation of ANSI compliant Common LISP. I went with the free, open-source _Steel Bank Common LISP (SBCL)_ which you can obtain [here][link_SBCL].
+ One of my favourite editors ---[Emacs][link_EMACS]{:target="_blank"}---installed version 24.4 (the latest stable version, as of writing this).
+ Lastly, installed the must-have [SLIME][slime_id] mode package in Emacs that allows us to bring up the 'top-level' REPL prompt within Emacs for my LISP experiments!

And soon, I obtained my first "Hello World" by typing and 'evaulating' the following function at the REPL prompt:

``` common-lisp

(format t "Hello World ! :) ~%")
;; ~% stands for our ubiquitous "\n" (newline) character...

```

#### Output
	Hello World ! :)

## A Beautiful, minimalist language...

Among many things, I learnt that LISP is --

+ ancient, yet all encompassing in its innovative features
+ simple
+ elegant
+ powerful
+ self-referential in its use of lists as both **code** as well as **data**

LISP pioneered/introduced almost all of the various innovative features of the many popular dynamic programming languages in use today.

**Note:** Well, this _'Hello',_ is just the tip of the proverbial iceberg or rather the 'ice-breaker' of our conversation about LISP. Sit tight & brace yourself, as we sail along uncharted territories, exploring some truly _ingenious_ ideas of **Functional Programming** in general & **LISP** in particular.

Many more articles to come showcasing the power & elegance of this classic programming language!

---

**Note:** Some work in Scheme, working through the legendary [SICP][link_SICP] is [here][link_rags_SICP]


[link_LISP]: http://en.wikipedia.org/wiki/Lisp_%28programming_language%29
[link_Common_LISP]: http://en.wikipedia.org/wiki/Common_Lisp
[link_Scheme]: http://en.wikipedia.org/wiki/Scheme_(programming_language)
[link_EMACS]: http://www.gnu.org/software/emacs/ "Emacs - the legendary editor! <3 :)"
[slime_id]: http://common-lisp.net/project/slime/ "SLIME mode for Emacs"
[link_SBCL]: http://www.sbcl.org/ "A free implementation of ANSI Common LISP"
[link_SICP]: http://mitpress.mit.edu/sicp/ "The SICP book (full text) -- free, online"
[link_rags_SICP]: https://github.com/raghuugare/rags_SICP "My work on SICP..."
