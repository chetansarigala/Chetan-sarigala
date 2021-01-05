\documentclass{standalone}
\usepackage{tikz}
\usetikzlibrary{arrows,shapes,automata,petri,positioning,calc}
\documentclass{article}

\tikzset{
    place/.style={
        circle,
        thick,
        draw=black,
        fill=gray!50,
        minimum size=6mm,
    },
        state/.style={
        circle,
        thick,
        draw=black,
        fill=gray!50,
        minimum size=6mm,
    },
}

\begin{document}

\begin{tikzpicture}[node distance=5cm and 4cm,>=stealth',auto, every place/.style={draw}]
    \node [place] (Q=0) {Q=0};
    \coordinate[node distance=4cm,left of=Q=0] (left-Q=0);
    \coordinate[node distance=4cm,right of=Q=0] (right-Q=0);

   

   \node [place] (Q=1) [right=of Q=0] {Q=1};
  

   \path[->] (Q=0) edge [bend left] node {A=0} (Q=1);
   \path[->] (Q=1) edge [left, above] node {A=1} (Q=0);
   \path[->] (Q=1) edge [loop right] node {A=0} ();
   \path[->] (Q=0) edge [bend right,above] node {A=1} (Q=1);
   

        
\end{tikzpicture}
\end{document}
