# Latex TikZ

These commands are usefull for creating inline LaTeX drawings.

## General TikZ

To setup the environment use

```
\begin{figure}
  \begin{tikzpicture}[scale=0.65]
  \end{tikzpicture}
\end{figure}
```

Predefined colors are ``red, green, blue, cyan, magenta, yellow, black, gray, darkgray, lightgray, brown, lime, olive, orange, pink, purple, teal, violet and white``.

### Paths

Paths can be used to draw arrows and shapes.

```
// draw a triangle
\path[draw=black,fill=green!40] (A) -- (B) -- (C) -- cycle;
// draw an arrow
\path[draw=black, -latex, thick] (A) -- (B);
// draw an arrow with text
\path [draw=black!40, -latex, thick] (A) -- (B) node[above, near end, sloped] { text };
```

Available node positions are ``at start (pos=0), very near start (pos=0.125), near start (pos=0.25), midway (pos=0.5), near end (pos=0.75), very near end (pos=0.875), at end (pos=1)``.

Predefined line thicknesses are ``ultra thin, very thin, thin, semithick, thick, very thick, ultra thick``.

There are ``solid, dotted, densely dotted, loosely dotted, dashed, densely dashed, loosely dashed, dashdotted, densely dashdotted, loosely dashdotted`` available as predefined dash-patterns.


### Nodes

Nodes can be used to place text in a TikZ picture.

```
// place a node named (A) at (0, 0) surrounded by a circle shaded like a ball
\node [circle, shading=ball, ball color=red!50] (A) at (0, 0) { text }; 
```

Available anchors are ``north, south, east, west``.

One may employ the shapes ``circle, rectangle, ellipse, diamond, regular polygon (with regular polygon sides=5), ann, star (with star points=7)``.

## PGF Plots

This package can be employed to create inline-LaTeX plots.

```
\begin{axis}[
    xlabel = {$x$}, 
    xlabel near ticks, 
    ylabel = {$y$}, 
    ylabel near ticks, 
    xmin=-5, xmax=5, 
    ymin=0, ymax=1.35, 
    ytick=\empty, 
    xtick={ -2, -1, 0, 1, 2 }, xticklabels={ -2, -1, $\omega$, 1, 2 }, 
    height=\textheight, width=\linewidth]
    
  \addplot[domain = -5:5, smooth, samples=100, thick] { exp(-x^2/2) };

  \node[anchor=south] at (axis cs: 0, 0.5) { text };
  
  \draw[<->, thick](axis cs: -1.17741002252, 0.5)--(axis cs: 1.17741002252, 0.5);
\end{axis}
```

