# JHyphenator ported to Android (also usable in other Java environments)


JHyphenator is a Java implementation of Frank Liang's hyphenation algorithm. Martin Fietz ported
it to Java in 2015. I forked it in 2018 and adjusted for use in my Android project [@Voice Aloud
Reader](https://play.google.com/store/apps/details?id=com.hyperionics.avar).

I removed
the original HyphenationPattern.java file by mfietz, and replaced it with HyphenPattern class that
reads original [language-code].js files from [Hyphenopoly](https://github.com/mnater/Hyphenopoly)
project, packaged into Android resource directory res/raw, and the pattern files renamed to _js, e.g.
"en.js" to "en_js" to be compatible with Android resource reading code. This also removes the
restriction on super-long Java string literals in some patterns, which made impossible to include
e.g. Hungarian hyphenation patters in the original HyphenationPattern class by @mfietz.
Now they are safely included too. 

Included hyphenation patterns were adapted from [Hyphenator.js](https://code.google.com/p/hyphenator/)
and [Hyphenopoly](https://github.com/mnater/Hyphenopoly). I also imported some missing hyphenation
patters (af, bg, cy) from https://github.com/ytiurin/hyphen project. These patterns are in slightly
different format, so wrote a converter for them (CovertUtil class in under test directory). From
the same ytiurin project I adapted hyphenation exceptions for English and Portuguese patterns.

# Language patterns
The number of pattrns is now increased to 47, from the 29 included in the original JHyphenator.
The codes given in parenthesis may not be correct ISO language codes, but the file names to use
in Java code.

* Afrikaans (af) 
* American English (en)
* Armenian (hy)
* Belarusian (be)
* Bengali (bn)
* Bulgarian (bg)
* British English (en_gb)
* Catalan; Valencian (ca)
* Croatian (hr)
* Czech (cs)
* Danish (da)
* Dutch; Flemish (nl)
* Esperanto (eo)
* Estonian (et)
* Finnish (fi)
* French (fr)
* German (de)
* Greek monotonic (el)
* Greek polytonic (el_polyton)
* Greek ancient (grc)
* Gujarati (gu)
* Hindi (hi)
* Hungarian (hu)
* Italian (it)
* Irish (ga)
* Kannada (kn)
* Latin (la)
* Latvian (lv)
* Lithuanian (lt)
* Malayalam (ml)
* Norwegian (no)
* Oriya (or)
* Panjabi; Punjabi (pa)
* Polish (pl)
* Portuguese (pt)
* Romanian (ro)
* Russian (ru)
* Serbian (sr)
* Slovak (sk)
* Slovenian (sl)
* Spanish (es)
* Swedish (sv)
* Tamil (ta)
* Telugu (te)
* Turkish (tr)
* Ukrainian (uk)
* Welsh (cy)

