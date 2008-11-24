Espresso
========
[Espresso](http://macrabbit.com/espresso/ "MacRabbit's Espresso Text Editor")
is the Next Big Thing™ for Mac OS X development. I'm a “Sugar Daddy” — i.e.
one who develops Sugars, which is what MacRabbit calls the extension bundles
made available to Espresso for languages and frameworks.

Bugs / Questions
----------------
Things I run into while development, that I need to ask Jan when I see him.

- Adding `.hidden.` to the `<zone name="…">` attribute of a `.comment.` zone
  in a Syntax doesn't hide it from the sidebar like it would an Itemizer.
- Will there be delimiter-balancing functionality at some point? Perhaps
  similar to that in TextMate and Coda, where typing a opening delimiter
  automatically creates the closing delimiter, and and passing over a
  delimiter with your insertion point highlights the balancing delimiter
  elsewhere in the code?
   - If it is supported, will we be able to hook into it to inform Espresso
     which characters are 'delimiters' in a given context? It'd be very cool
     if any syntax zone or capture zone (I understand they work the same
     after parsing) with both `.delimeter.` and `.begin.` would 'balance' any
     zone with the exact same name but with `.end.` instead of `.begin.`.
   - Will we be able to tell Espresso when _not_ to read a character as a
     delimiter? For instance, it's annoying in TextMate when you have a
     complicated regular expression that includes parenthesis, but they are
     escaped (thus a part of the match). TextMate gets all confused about
     which parenthesis balances which, and is quite likely to throw off your
     regex-fu.
- I can't decide if zones are trying to be greedy or not. I have a zone that
  defines `def function(` as the `starts-with` expression, and `)` as the
  `ends-with` expression. The problem arises in that whitespace can be used
  instead of parentheses, and the parser drops out of the zone at the first
  chunk of whitespace. For instance, `def function(foo, bar)` is parsed as
  `def function(foo, ` because that first space is seen as matching the
  `ends-with` expression.
