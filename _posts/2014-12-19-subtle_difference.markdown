---

layout: post
title:  "LISP : consp or listp ?"
date:   2014-12-19 17:25:10
categories: programming

---

As I began my journey into the wonderful world of LISP, and I started understanding the so-called **predicates**. [^1] 

[^1]: Predicates (in LISP) are nothing but functions that answer Yes/No type of questions. By convention LISP predicate-names end in the letter **p** (stands for 'predicate'!) 


I also began to learn about the predicates that are built-in, such as `oddp`, `evenp`, `atomp`, etc.

Then, I stumbled across what seemed like 2 different predicates that are 'equivalent', but which I realized are not exactly so.

So, I want to discuss briefly about the subtle difference between these 2 predicates _viz.,_ `consp` & `listp` in LISP.

Beginning LISPers are bound to be a bit confused by the existence of the predicates `consp` & `listp`. One seems to check if its argument is a _cons-cell_ (Please see the **Notes** section at the bottom for more info or intro to _cons-cell_ ) while the other tells if the argument represents a list. After all, isn't every list a cons-cell? Or so, the thought process goes...leading one to believe (erroneously!) that these predicates are interchangeable.

### Isn't every list a cons-cell?

Seems so, but it is not the case.

### So, are consp & listp _not_ the same? 

Short answer : They are _not_ the same. There's a subtle difference due to one chief exception the rule...

Note that `NIL` is a list, also denoted by `()`. But it is  _not_ a cons-cell.

**There! I'm done!** 

I hope you 'got' the _subtle_ difference between `consp` & `listp` predicates in LISP.

It should now be clear what the following code snippets produce:

{% highlight LISP %}
(consp NIL)

{% endhighlight %}
_Output:_  `NIL`

where as,

{% highlight LISP %}
(listp NIL)

{% endhighlight %}
_Output:_ `T`

---

## Notes

### What is a cons-cell?

A _cons-cell_, in Java-parlance, is like the node struct/class of a linked-list. Like so,

{% highlight java %}
class Node<T> {
    T data;
    Node next;
}
{% endhighlight %}

Note that the `data` field above is also a pointer/reference to some location in memory, just like `next` points to the 'next' node of the list. Thus a _cons-cell_ is essentially a pair of pointers used to represent lists in LISP. In a singly-linked-list the last node has `next` set to `null`.

LISP uses this cons-cell concept to represent lists. For more information on cons-cells, you can refer to [this introductory article][link_cons_cell].Thank you!

---

### Footnotes

[link_cons_cell]: http://c2.com/cgi/wiki?ConsCell