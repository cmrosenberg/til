# Using git show to pipe an old file version to STDOUT

If you need to quickly view an old version of a file, or perhaps pipe it to an unversioned file for easy, direct comparison between old and new files,
you can do:

`git show <ref>:<filename>`

This will pipe the file to STDOUT, and can easily be redirected to a new file of your choosing.

I learned it from [this Stack Overflow post](http://stackoverflow.com/questions/888414/git-checkout-older-revision-of-a-file-under-a-new-name)
