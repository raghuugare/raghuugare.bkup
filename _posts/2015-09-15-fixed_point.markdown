---
layout: post
title:  "The Point of Fixed Point"
date:   2015-09-15 12:20:10
categories: programming
draft: true

---

## What is a 'fixed-point'? 

The fixed-point of a function \$f(x)\$ is a value \$`x'\$ such that the equation \$f(x) = x\$ is true.

For example, \$0\$ is a fixed-point of the function \$sin(x)\$, since \$sin(0)=0\$.

Starting with this simple definition, I was shown some amazing piece of programming by Prof. Gerald Jay Sussman in the legendary SICP course (`lecture-2A` to be specific).

Inspired by his talk, I quickly scribbled the following piece of code _verbatim_ in my [Dr.Racket][link_dr_racket] environment.

And **lo & behold!**

The program I wrote JUST WORKED the first time itself!

Truly a testament to great teaching, and also to a great programming language (LISP that is--Scheme being a clean lit'l dialect of it :-) ). 

Hat-tip to both!

## Over to the code...

{% highlight scheme %}

;; Fixed point of a function 'f' about a point 'start'...
;;
;; Author: Raghu Ugaré
;; Courtesy: the great teacher/author-s of SICP! <3 :)
;; ------------------------------------------------------

(define (fixed-point f start)
  ;; t = tolerance
  (define t 0.000001)

  (define (iter old new)
    (if (close-enough? old new)
        new
        (iter new (f new))))

  (define (close-enough? old new)
    (< (abs (- old new)) t))

  (iter start (f start)))

{% endhighlight %}

And then I tested it with the following calls to my `fixed-point` function:

{% highlight scheme %}

;; ================================================
;; Some tests below for our Fixed-point function...
;; ================================================

(fixed-point cos 0) ;; Gives 0.7390855263619245
(fixed-point sin 0) ;; Gives 0
(fixed-point sin 1) ;; Gives 0.018169909847253

{% endhighlight %}

[link_dr_racket]:[http://docs.racket-lang.org/drracket/]
