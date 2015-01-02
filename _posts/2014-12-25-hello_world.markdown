---
layout: post
title:  "Hello World!"
date:   2014-12-25 12:20:10
categories: programming
---

Here's a sample code snippet in C:

{% highlight c %}
    
#include <sdtio.h>

/* A simple function definition... */
int factorial(int n) {
    int result = 1;
    for(int i=1; i<=n; i++)
        result *= i;
    return result;
}

int main() {
    int n = 5;
    printf("Hello World! :) \n");
    printf("factorial(%d) = %d \n", n, factorial(n));
    return 0;
}

{% endhighlight %}

Above is a simple C-program with a function to compute the `factorial` of a positive integer _defined & exercised_.

## A Java program...

Below is a Java program to be saved in a file named `Greeter.java`

{% highlight java %}
    
public class Greeter {
    
    public String greet(String target) {
        return "Hello " + target + "! :)";
    }

    public void static main(String[] args) {
        Greeter greeter = new Greeter();
        String greeting = greeter.greet("World");
        System.out.println(greeting);
    }

}

{% endhighlight %}
