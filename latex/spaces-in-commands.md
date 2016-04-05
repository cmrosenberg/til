# Spaces in commands

If you naïvely create commands and invoke them as any sane person would,
you may notice that the next character is absorbed.

This is most important for newcommands that essentially are aliases.

One could be fooled into thinking that one should simply add a space to the
the macro. However, this will break things when for example using hyphens.

The correct way is to define the command without trailing spaces and then
invoke the command with {}, so that the LaTeX parser parsers the text correctly.

I learned about this from the following [StackOverflow thread](https://tex.stackexchange.com/questions/31091/space-after-latex-commands)
