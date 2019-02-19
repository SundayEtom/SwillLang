# SwillLang
A simple web scripting language for creating/generating dynamic html content.
Swill is a tiny web scripting language aimed at simplifying the task of writing dynamic web pages. Hold on please. I do not hope to replace PHP or any other web programming languages. Those languages are my source of inspiritation in the first place. Striving to implement a language better than them does not only seem a futile endeavour to me, but it will completely dampen my motivation. Swill is my personal self test, to see if I have understood most of what I learned in programming. The size and poverty of known language features should warn anyone that this, in comparison to any existing language, is a toy web scripting language. Erm... perhaps I should rename it as TowSlang for "Toy Web Scripting Language". That's food for thought.

OK. Like I was saying, Swill is meant to be imbedded in html pages, just like php. The Swill interpreter, when passed a file with a name that ends with '.sw' (without the quotes), will search for what I have called Swill Blocks within the file and execute their contents as Swill code, effectively replacing each of those blocks with the value of its content, you know, like php (forgive me for comparing a toy, Swill, to the real thing). For example, the following,
<pre>
<code>
sw{
   {&lt;span style=" color: green;">}
      output("Age is " | 57 - 28);
   {&lt;/span>}
}
</code>
</pre>

will be replaced in the output html file with:
<pre>
&lt;span style="color: green;">Age is 29&lt;/span>
</pre>

which will then be rendered as appropriate by the browser. From that small snippet, I already have a lot to explain, though in truth the syntax, I believe, is very simple.

From line 1, we write the header for a Swill Block, which is a top-level block that cannot contain other Swill Blocks. A Swill Block is a standalone wrapper or container for Swill code. It starts with <code>sw{</code> and ends with <code>}</code>. Everything between these delimiters will be parsed as Swill code. So this Swill Block starts on line 1 and ends at line 5. Note the case here: only lowercase is allowed for <code>sw{</code>. <code>SW{</code>, <code>Sw{</code> or <code>sW{</code> will not work; the parser will simply copy everything until the first correct Swill Block header to the output html file.
