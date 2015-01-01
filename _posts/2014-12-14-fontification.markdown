---
layout: post
title:  "Font-ification! &#9786;"
date:   2014-12-14 20:20:10
categories: general
---

## My journey towards the "font"-ain of Beauty! :)

I love fonts to an almost fanatic extent.

Other than meddling with different typefaces, with Serifs & without ('sans' [^1] Serif), I have been notorious among my friends & peers for my heavy use of colors also to the above mix, giving rise to a _'psychedelic riot of colors'_ in my blog articles & mails.

[^1]: _**sans**_ is Latin for "without". Thus, a "Sans Serif" typeface means there are no "serifs" on the 'extremities" of different symbols in that typeface.

I do all of this---in my effort to somehow produce _'intonations & emphasis'_ of speech in written text, using colors, fonts and their weights & styles as my tools.

Some of my favourite programs (& books written about them) have been [Donald Knuth][link_donald_knuth]'s [TeX][link_TeX] typsetting system & [Leslie Lamport][link_leslie_lamport]'s [LaTeX][link_LaTeX] built upon TeX. 

I marvel at how TeX especially, takes care of hundreds of tiny technical details (such as _kerning, ligatures, breaking lines,_ etc.) that go into making text so readable & enjoyable. As Lamport puts it, these tools help authors turn mere **"typing into typography"**.

Hats off to the Printing/Publishing/Digital/Computer-Science fraternity for their constant innovations! From hot-metal types in real foundries to digital type-faces manipulated with [Bézier curves][link_bézier_curves] & mathematical wizardry, we have indeed come a long way. :)

> &#9762; **Warning!** _Digression_ : Check out the 'mathematical & algorithmic' typography work by the father-son duo (and I would even say, 'math-art' duo) of [Erik Demaine][link_erik_demaine] & [Martin Demaine][link_martin_demaine] at [this site][link_erik_typography]. You too might enjoy playing around with [the glass-'squishing' font][link_erik_glass_fonts] there! Beautiful indeed!

As for the web, we have [Markdown][link_markdown] & [Textile][link_textile], two of the several light-weight mark-up languages.

## Playing with fonts on github pages

It seems to be very simple to change fonts on a github pages site.

To change the font used for almost all text (except code), all you do is add the font you want to the beginning of the following variable in `main.scss`:

    $base-font-family

Let me take you through a small example change I did locally.

### Before...
    $base-font-family : Helvetica, Arial, sans-serif

This means 'try Helvetica first, if not available try Arial, and if not, some sans-serif font that is available.'

Well, I wanted to have my blog rendered in a font of my choice.

### After...
    $base-font-family : Optima, Helvetica, Arial, sans-serif

As you can see above, I added `Optima` to the mix.

Optima has been one of my favourite fonts & I so badly wanted to try it.

I then saved this change in `main.scss`, refresh the browser & proceeded to _drool over_ the resultant rendering on my local copy of the github pages site...

**Ah! What a beautiful font!**

No wonder---the [Optima][link_optima] typeface was created by one of the most respected font-designers in the world, [Hermann Zapf][link_hermann_zapf], way back in 1952.(**!!** [^2])

[^2]: In [chess annotation][link_Chess_annotations], **!!** is used to annotate a move. It means "brilliant".

But my joy was short-lived.

## The Problem

When I tried viewing the same pages on a Windows machine, I realized that Optima was not installed, & therefore, the rendering engine fell-back to whatever font it had available (in my case, some "sans-serif" font like Helvetica, or Arial.)

## Same problem for code...

Also, another pet peeve of mine was that I wanted some other `"monospace"` font for the code-snippets in my blogs, over-riding the default [Courier][link_courier] family.

Again, I hit a similar road-block here, when I was almost dancing with joy looking at the beautiful [Monaco][link_monaco] font used to render my code snipppets. 

I soon realized that this 'simple' tweaking of `main.scss` was **not portable**.

**"Is there no way out?",** I pondered...

## Pondering...

I then wondered to myself about many sites out there which manage to have their custom fonts & which render the same on almost every machine.

**How could THEY do it ?**

Part of the solution came in the form of what are called "web-fonts"

## Web-fonts ?

Well, as the name itself tells, a 'web-font' [^3] is pretty much a web-asset that gets loaded on-the-fly (based on our configurations) & is then used by the browser's rendering engine as if it is picking up a _local_ 'font-asset', thus ensuring a uniform user-experience across different  environments.

[^3]: The term 'web-font' is much like 'web-service'---a 'service' accessible over the web. A 'web-font' is similarly a font-resource accessible over the web.

The downside to this approach is the slightly larger load-time for our site (barely noticable if we manage to keep the number of font-assets to a minimum). 

But the upside is that we get the same look in terms of typography everywhere, for ALL our readers! :)

## Enter Adobe...

Soon, my search for a free web-font 'service' zeroed in on Adobe who I learnt, have been famously providing such a service called [Typekit][link_typekit] for quite long. Really loved some of their blog-series on various little-known minutiae related to fonts! But Typekit is a paid service, and I wondered if little tinkers like me could freely experiment with fonts somehow.

I then came to know that Adobe had come up with exactly the kind of 'free, font-service' that I had in mind! 

**Divine Providence ?! :)**

I would like to take this opportunity to thank Adobe for this service indeeed!

This gem of a service is called the **Adobe Edge Web Fonts**, and the collection is available [here][link_adobe_edge_web_fonts].

As they say, Edge Web fonts is _'a library of fonts for your website'_ brought to us with contributions from Adobe, Google & many font-designers all over the world!

**"Perfect!"**, I exclaimed, as I set about exploring the various permutations of fonts I could choose from the _delectable menu_ of over 500 fonts which were neatly classified as being _Serif, Slab Serif, Sans Serif, Monospace, Decorative_, etc.

## Finally . . .

Long story short, I finally chose (for now at-least!) a set of fonts for the normal text as well as code-snippets on my blog.

## How ?

In order to use the typeface **Lato**, I added the following `<script>` element in my `head.html` file:
    
    <script src="//use.edgefonts.net/lato:n1,i1,n3,i3,n4,i4,n7,i7,n9,i9.js"></script>

**Done! That's it!**

Now, I could directly use "lato" as a value in `$base-font-family`, etc. as usual (i.e., in place of Optima in the above snippets).

Hope you like my font-selection.

And hope my font-meddling & this article help you in finding your own favourite font combination!

I wish that your eyes are *not* strained, but instead are cajoled & coaxed along...

For a more detailed help on how to go about doing it for your blog/site, please refer to this [link][link_adobe_edge_web_fonts_help].

Have a "**font**-astic" time !

---

### Footnotes

[link_optima]:  http://en.wikipedia.org/wiki/Optima
[link_courier]: http://en.wikipedia.org/wiki/Courier_%28typeface%29
[link_monaco]: http://en.wikipedia.org/wiki/Monaco_%28typeface%29 
[link_hermann_zapf]: http://en.wikipedia.org/wiki/Hermann_Zapf
[link_adobe_edge_web_fonts]: https://edgewebfonts.adobe.com
[link_typekit]: https://typekit.com
[link_adobe_edge_web_fonts_help]: https://edgewebfonts.adobe.com/help
[link_adobe]: http://www.adobe.com/
[link_google]: http://www.google.com/
[link_donald_knuth]: http://en.wikipedia.org/wiki/Donald_Knuth
[link_TeX]: http://en.wikipedia.org/wiki/TeX
[link_leslie_lamport]: http://en.wikipedia.org/wiki/Leslie_Lamport
[link_LaTeX]: http://en.wikipedia.org/wiki/LaTeX
[link_markdown]: http://en.wikipedia.org/wiki/Markdown
[link_textile]: http://en.wikipedia.org/wiki/Textile_%28markup_language%29
[link_bézier_curves]: https://en.wikipedia.org/wiki/B%C3%A9zier_curve
[link_erik_demaine]: http://en.wikipedia.org/wiki/Erik_Demaine
[link_martin_demaine]: http://en.wikipedia.org/wiki/Martin_Demaine
[link_erik_typography]: http://erikdemaine.org/fonts/
[link_erik_glass_fonts]: http://erikdemaine.org/fonts/squish/
[link_Chess_annotations]: http://en.wikipedia.org/wiki/Chess_annotation_symbols