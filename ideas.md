With the goal of improving reliability of a software project, i think it would
be beneficial if projects had  a narrative. I haven’t had time to research this
general idea much, i’m guessing its not a new one. So first and foremost,
if anyone has any pior art they think i should consider i would welcome the input.
For example, i assume iterative programming is a related concept, one that possible is 
more extensive then what i'm suggesting.

So what i'm I suggesting? 

Most tools for understanding a program are like a glossaries, indexes and dictionaries. These are incredibly helpful,
but another way of understanding something is with a narrative. In fact, i claim this is the most intuitive and useful
way.

I'm purposing it should be easier for a developer to tell a narrative about their
code to another developer through the code. The narrative could be read through the editor, a web browser, or 
just plain text. The output format would be 100% customizable up to the developer, but plugins would exist to facility easy setup of the mostly commonly
used ways. For example, a plugin might exist that works with emacs and leverages a debugger to simply visit various places in the code (using breakpoints) and
display a collection of text along side the code. 

But again, the output could be anything. For example, using narrative on the following code might look like this:

```
(narrative  (/ n 2) "we only need half the population")
...
(narrative (+ coef n) "plus some coefficent, in order to get the correct formula.")
```

Might produce a output in text like this:

```
we only need half the population                            | (/ n 2)
plus some coefficent, in order to get the correct formula.  | (+ coef n)
```

of course in reality the narrative function (probably a macro) will take as arguments:
* the code you want to narrate
* a function which can be used to build the narrative. `(narrative (/ n 2) story/opening)`

Sense i think most people might not like their code interviewed with narrative code which has no impact on the code. I would
build editor plugins to "hide" that code in the more popular editors. I'm also open to other ideas. In practice I hope these should be no more intrusive
then docstrings and comments.


Here is a quick way a narrative differentiates itself from tools we commonly see
in a project.

* Readme: A narrative is different from a readme in that it could possible contain interactive code, and would allow the reader
to walk through the project (similar to flipping pages in a book).
* debugger: A narrative is different from a debugger in that it could be a different UI then the editor (possible a webpage with interactive
snippets from the project). It would also contain some human readable text describing the code in relation to the project at large.
* tests/spec :  While a narrative might use some example input, or highlight a function, which might be shared by a test or spec, a narrative would do more 
then assert something about the code, it would help talk about the code only as part of the larger code base, not as a individual unit.
