
You can use \mathbin to create a custom binary operator. Useful for unconventional logical operators, for example.

```
\newcommand{\Always}{\Box}
\newcommand{\Eventually}{\Diamond}
\newcommand{\Next}{\ocircle}
\newcommand{\Release}{\mathbin{R}}
\newcommand{\Until}{\mathbin{U}}
\newcommand{\WaitingFor}{\mathbin{W}}
```
