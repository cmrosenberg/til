# Using `git checkout -p`

I have been using Patch mode for creating granular commits with `git
add -p` before, but I had not realized that the same trick works for
discarding selective chunks of source code from the working tree.

By invoking `git checkout -p`, you can discard selected chunks of
source code. This is very useful if you've littered your source code
with print statements to track down an awful bug, and want to commit
the solution but not all the scaffolding.
