---

layout: post
title:  "LISP : consp or listp ?"
date:   2014-12-19 17:25:10
categories: LISP

---

I recently began my long-awaited journey(or a _pilgrimage_ to be honest!) into the wonderful world of [LISP][link_LISP]{:target="_blank"}. And along the path, I started understanding the so-called **predicates**.[^1]


[^1]: Predicates (in LISP) are nothing but functions that answer Yes/No type of questions. By convention LISP predicate-names end in the letter **p** (stands for 'predicate'!)

I also began to learn about the predicates that are built-in, such as `oddp`, `evenp`, `atomp`, etc.

Then, I stumbled across what seemed like 2 different predicates that are 'equivalent', but which I realized are not exactly so.

So, I want to discuss briefly about the subtle difference between these 2 predicates _viz.,_ `consp` & `listp` in LISP.

Beginning LISPers are bound to be a bit confused by the existence of the predicates `consp` & `listp`. One seems to check if its argument is a _cons-cell_ (Please see the **Notes** section at the bottom for more info or intro to _cons-cell_ ) while the other tells if the argument represents a list. After all, isn't every list a cons-cell? Or so, the thought process goes...leading one to believe (erroneously!) that these predicates are interchangeable.

### Isn't every list a cons-cell?

Seems so, but it is not the case.

### So, are consp & listp _not_ the same?

Short answer : They are _not_ the same. There's a subtle difference due to one chief exception.

Note that `NIL` is a list, also denoted by `()`. But it is  _not_ a cons-cell.

**There! I'm done!**

I hope you 'got' the _subtle_ difference between `consp` & `listp` predicates in LISP.

It should now be clear what the following code snippets produce:

``` common-lisp

(consp NIL)

```

_Output:_  `NIL`

where as,

``` common-lisp

(listp NIL)

```

_Output:_ `T`

---

## Q & A

---

**What is a cons-cell?**

A _cons-cell_, in Java-parlance, is like the node struct/class of a linked-list. Like so,

``` java
class Node<T> {
    T data;
    Node next;
}
```

Note that the `data` field above is also a pointer/reference to some location in memory, just like `next` points to the 'next' node of the list. Thus a _cons-cell_ is essentially a pair of pointers used to represent lists in LISP. In a singly-linked-list the last node has `next` set to `null`.

LISP uses this cons-cell concept to represent lists. For more information on cons-cells, you can refer to [this introductory article][link_cons_cell]{:target="_blank"}. Enjoy!

---

**If a predicate always returns Yes/No or True/False why does the output here show `T` & `NIL` ?**

Good observation! You will understand this when you learn the basics of LISP.

+ LISP denotes the boolean value of "true" by the symbol `T`, and uses `NIL` for "false". To make it clear, No, LISP does **not** use `F` for "false", as one expect!
+ Note that `NIL` is also used to represent an empty list i.e., `()`. Thus, the expression `(equalp NIL ())` evaluates to `T` (= true)

---

**Update**: Thanks to Jean-Philippe Paradis of [Hexstreamsoft][link_hexstream] for pointing out another observation worth sharing--that `NIL` behaves sometimes like an empty cons-cell too, in that both `(car NIL)` and `(cdr NIL)` return `NIL` just like it happens if you had used `(car ())` and `(cdr ())`. Try it out!

---

### Footnotes

[link_cons_cell]: http://c2.com/cgi/wiki?ConsCell
[link_LISP]: http://en.wikipedia.org/wiki/Lisp_%28programming_language%29
[link_hexstream]: https://www.hexstreamsoft.com
