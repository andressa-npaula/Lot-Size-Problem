**Uncapacited Lot-Sizing**

*Mixed Integer Programming Formulations*

\\section*{Uncapacitated Lot-Sizing (ULS)}

\textbf{Variáveis de decisão:}
\begin{itemize}
    \item y_t: quantidade produzida no período t
    \item s_t: estoque no final do período t
    \item x_t: variável binária que indica se há produção no período t (x_t = 1 se y_t > 0, caso contrário x_t = 0)
\end{itemize}

\textbf{Parâmetros:}
\begin{itemize}
    \item d_t: demanda no período t
    \item p_t: custo de produção por unidade no período t
    \item h_t: custo de armazenagem por unidade no período t
    \item f_t: custo fixo de produção no período t
    \item M: quantidade máxima que pode ser produzida no período (grande o suficiente)
\end{itemize}

\textbf{Formulação:}

\begin{align}
\min \quad & \sum_{t=1}^{n} p_t y_t + \sum_{t=1}^{n} h_t s_t + \sum_{t=1}^{n} f_t x_t \tag{1} \\
\text{sujeito a:} \quad & s_{t-1} + y_t = d_t + s_t \quad && \text{para } t = 1, \ldots, n \tag{2} \\
& y_t \leq M x_t \quad && \text{para } t = 1, \ldots, n \tag{3} \\
& s_0 = 0, \quad s_t \geq 0, \quad y_t \geq 0, \quad x_t \in \{0,1\} \quad && \text{para } t = 1, \ldots, n \tag{4}
\end{align}
