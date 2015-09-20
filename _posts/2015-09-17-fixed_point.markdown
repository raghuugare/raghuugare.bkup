---
layout: post
title:  "A small point about 'Fixed Point'..."
date:   2015-09-17 12:21:21
categories: programming
draft: true

---

## Fixed-point ? 

The [fixed-point of a function][link_fixed_point_definition]{:target="_blank"} \$f(x)\$ is a value \$`x'\$ such that the equation \$f(x) = x\$ is true.

For example, \$0\$ is a fixed-point of the function \$sin()\$, since \$sin(0)=0\$.

Starting with this simple definition, I was shown some amazing piece of programming by [Prof. Gerald Jay Sussman][link_prof_Sussman]{:target="_blank"} in the legendary [SICP][link_SICP]{:target="_blank"} course (`lecture-2A` to be specific).

Inspired by the lecture, I quickly scribbled the following piece of code _verbatim_ in my [Dr.Racket][link_dr_racket]{:target="_blank"} environment.

And **lo & behold!**

The program I wrote JUST WORKED the first time itself!

Truly a testament to great teaching, and also to a great programming language (LISP that is--Scheme being a clean lit'l dialect of it :-) ). 

Hat-tip to both!

## Over to the code...

{% highlight scheme %}

;; Fixed point of a function 'f' about a point 'start'...
;;
;; Author: Raghu Ugaré
;; Courtesy: the great teachers of SICP! <3 :)
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

## The point?

Well, in the end, especially on seeing the different values in case of the \$ sin() \$ function, I realized one simple thing..
That even the so-called 'fixed-point' of a function 'changes'

Which reminds me of the adage:

>  &#10077; The ONLY constant in Life, is CHANGE. &#10078;

Happy Learning & Exploring ! :~)

[link_dr_racket]:[http://docs.racket-lang.org/drracket/]
[link_fixed_point_definition]:[https://en.wikipedia.org/wiki/Fixed_point_(mathematics)]
[link_prof_Sussman]:[https://en.wikipedia.org/wiki/Gerald_Jay_Sussman]
[link_SICP]:[https://mitpress.mit.edu/sicp/]
