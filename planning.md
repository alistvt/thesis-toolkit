Here is a sample gantt chart for you to use in your planning during the proposal. (from the proposal of a previous student Dianne) 
Note that important milestones have been shown in this chart and also the actual dates are mentioned, this helps to know where we are standing each week during the project.

```
\section{Planning}
\begin{figure}[h!]
\begin{ganttchart}[
    y unit title=0.7cm,
    y unit chart=0.6cm,
    vgrid,
    hgrid,
    milestone/.style={fill=red},
    bar/.append style={fill=blue!40},
    bar label font=\small,
    group right shift=0.2,
    group top shift=0.6,
    group height=0.8,
    x unit=0.17cm
]{1}{77}  % Timeline: 11 weeks

    % multiply of 7 to calculate with days
    % 7 14 21 28 35 42 49 56 63 70 77
    \gantttitle{Research Timeline (Weeks)}{77} \\
    \gantttitle{14/04}{7}  % First week starts on 14th April
    \gantttitle{21/04}{7}
    \gantttitle{28/04}{7}
    \gantttitle{05/05}{7}
    \gantttitle{12/05}{7}
    \gantttitle{19/05}{7}
    \gantttitle{26/05}{7}
    \gantttitle{02/06}{7}
    \gantttitle{09/06}{7}
    \gantttitle{16/06}{7}
    \gantttitle{23/06}{7} \\
    
    \ganttbar{Setup + Create Database}{1}{28} \\    
    \ganttbar{choose + implement method}{26}{35}\\
    \ganttbar{implement extraction method}{35}{42} \\
    \ganttbar{define metric}{39}{43} \\
    \ganttbar{produce results}{36}{50} \\
    \ganttmilestone{Prototype done}{48} \\
    \ganttbar{Compile Results}{45}{53} \\ 
    \ganttbar{Write Thesis}{49}{70} \\
    \ganttmilestone{Submit Thesis}{70} \\ 
    \ganttmilestone{Symposium}{70} \\
    \ganttbar[bar/.append style={fill=gray!50}]{Buffer Week}{70}{77}
   
\end{ganttchart}
\caption{Research timeline Gantt chart}
\label{fig:gantt_chart}
\end{figure}
```
