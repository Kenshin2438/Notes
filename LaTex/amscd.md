> The `amscd` package provides a CD environment that emulates the commutative diagram capabilities of AMS-TEX version 2.x. This means that **only simple rectangular diagrams are supported, with no diagonal arrows or more exotic features**.

`amscd` 是 American Mathematical Society 提供的画图宏包，胜在语法简单且箭头的语法非常形象，缺点是只能画出矩形图且没有斜着的箭头。

并且，`amscd` 也是 [MathJax](https://www.mathjax.org/) 能够支持的 cd 环境，用在 Markdown 笔记/博客中相比 TikZ 要更为方便。

```tex
\begin{CD} ... \end{CD}

@<<<           % left arrow
@>>>           % right arrow
@AAA           % up arrow
@=             % horizontal equals
@VVV           % down arrow
@|             % vertical equals
@.             % empty arrow
```

$$\begin{CD}
A  @>>>  B  @<top<bottom<  C   \newline
@.       @AleftArightA     @|  \newline
D  @=    E  @>>>           F 
\end{CD}$$

### Problem Fixes

- [Mamscd.pdf (jmilne.org)](https://www.jmilne.org/not/Mamscd.pdf)
- [macros - Is there a vertical equivalent for \rlap? - TeX - LaTeX Stack Exchange](https://tex.stackexchange.com/questions/23845/is-there-a-vertical-equivalent-for-rlap)

```latex
\newcommand{\tlap}[1]{\vbox to 0pt{\vss\hbox{#1}}}
\newcommand{\blap}[1]{\vbox to 0pt{\hbox{#1}\vss}}
```

上述代码用于改善 `amscd` 中的箭头和文字的位置（上下缝隙）关系。这在 LaTex 环境中有效，但是 Mathjax 目前还无法支持 `vbox` 及其语法。