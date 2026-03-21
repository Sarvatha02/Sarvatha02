%%%%
% MTecknology's Resume
%%%%
% Author: Michael Lustfield
% License: CC-BY-4
% - https://creativecommons.org/licenses/by/4.0/legalcode.txt
%%%%

\documentclass[letterpaper,10pt]{article}
%%%%%%%%%%%%%%%%%%%%%%%
%% BEGIN_FILE: mteck.sty
%% NOTE: Everything between here and END_FILE can
%% be relocated to "mteck.sty" and then included with:
%\usepackage{mteck}

% Dependencies
% NOTE: Some packages (lastpage, hyperref) require second build!
\usepackage[empty]{fullpage}
\usepackage{titlesec}
\usepackage{enumitem}
\usepackage[hidelinks]{hyperref}
\usepackage{fancyhdr}
\usepackage{fontawesome5}
\usepackage{multicol}
\usepackage{bookmark}
\usepackage{lastpage}

% Sans-Serif
%\usepackage[sfdefault]{FiraSans}
%\usepackage[sfdefault]{roboto}
%\usepackage[sfdefault]{noto-sans}
%\usepackage[default]{sourcesanspro}

% Serif
\usepackage{CormorantGaramond}
\usepackage{charter}

% Colors
% Use with \color{Name}
% Can wrap entire heading with {\color{accent} [...] }
\usepackage{xcolor}
\definecolor{accentTitle}{RGB}{0,0,0}
\definecolor{accentText}{RGB}{0,0,0}
\definecolor{accentLine}{RGB}{0,0,0}


% Misc. Options
\pagestyle{fancy}
\fancyhf{}
\fancyfoot{}
\renewcommand{\headrulewidth}{0pt}
\renewcommand{\footrulewidth}{0pt}
\urlstyle{same}

% Adjust Margins
\addtolength{\oddsidemargin}{-0.7in}
\addtolength{\evensidemargin}{-0.5in}
\addtolength{\textwidth}{1.19in}
\addtolength{\topmargin}{-0.7in}
\addtolength{\textheight}{1.4in}

\setlength{\multicolsep}{-3.0pt}
\setlength{\columnsep}{-1pt}
\setlength{\tabcolsep}{0pt}
\setlength{\footskip}{3.7pt}
\raggedbottom
\raggedright

% ATS Readability
\input{glyphtounicode}
\pdfgentounicode=1

%-----------------%
% Custom Commands %
%-----------------%

% Centered title along with subtitle between HR
% Usage: \documentTitle{Name}{Details}
\newcommand{\documentTitle}[2]{
  \begin{center}
    {\Huge\color{accentTitle} #1}
    \vspace{10pt}
    {\color{accentLine} \hrule}
    \vspace{2pt}
    %{\footnotesize\color{accentTitle} #2}
    \footnotesize{#2}
    \vspace{2pt}
    {\color{accentLine} \hrule}
  \end{center}
}

% Create a footer with correct padding
% Usage: \documentFooter{\thepage of X}
\newcommand{\documentFooter}[1]{
  \setlength{\footskip}{10.25pt}
  \fancyfoot[C]{\footnotesize #1}
}

% Simple wrapper to set up page numbering
% Usage: \numberedPages
% WARNING: Must run pdflatex twice!
\newcommand{\numberedPages}{
  \documentFooter{\thepage/\pageref{LastPage}}
}

% Section heading with horizontal rule
% Usage: \section{Title}
\titleformat{\section}{
  \vspace{-5pt}
  \color{accentText}
  \raggedright\large\bfseries
}{}{0em}{}[\color{accentLine}\titlerule]

% Section heading with separator and content on same line
% Usage: \tinysection{Title}
\newcommand{\tinysection}[1]{
  \phantomsection
  \addcontentsline{toc}{section}{#1}
  {\large{\bfseries\color{accentText}#1} {\color{accentLine} |}}
}

% Indented line with arguments left/right aligned in document
% Usage: \heading{Left}{Right}
\newcommand{\heading}[2]{
  \hspace{10pt}#1\hfill#2\\
}

% Adds \textbf to \heading
\newcommand{\headingBf}[2]{
  \heading{\textbf{#1}}{\textbf{#2}}
}

% Adds \textit to \heading
\newcommand{\headingIt}[2]{
  \heading{\textit{#1}}{\textit{#2}}
}

% Template for itemized lists
% Usage: \begin{resume_list} [items] \end{resume_list}
\newenvironment{resume_list}{
  \vspace{-7pt}
  \begin{itemize}[itemsep=-2px, parsep=1pt, leftmargin=30pt]
}{
  \end{itemize}
  %\vspace{-2pt}
}

% Formats an item to use as an itemized title
% Usage: \itemTitle{Title}
\newcommand{\itemTitle}[1]{
  \item[] \underline{#1}\vspace{4pt}
}

% Bullets used in itemized lists
\renewcommand\labelitemi{--}

%% END_FILE: mteck.sty
%%%%%%%%%%%%%%%%%%%%%%


%===================%
% John Doe's Resume %
%===================%

%\numberedPages % NOTE: lastpage requires a second build
%\documentFooter{\thepage of 2} % Does similar without using lastpage
\begin{document}

  %---------%
  % Heading %
  %---------%

  \documentTitle{Sudharsan S}{
    % Web Version
    %\raisebox{-0.05\height} \faPhone\ [redacted - web copy] ~
    %\raisebox{-0.15\height} \faEnvelope\ [redacted - web copy] ~
    %%
    \href{tel:1234567890}{
      \raisebox{-0.05\height} \faPhone\ +91 9751120169} ~ | ~
    \href{sudharsan97511@gmail.com}{
      \raisebox{-0.15\height} \faEnvelope\ sudharsan97511@gmail.com} ~ | ~
    \href{https://www.linkedin.com/in/sudharsan-s-528a8a2a0/}{
      \raisebox{-0.15\height} \faLinkedin\ Linkedin} ~ | ~
    \href{https://github.com/Sudharsanselvaraj}{
      \raisebox{-0.15\height} \faGithub\ GitHub.com}
  }

  %---------%
  % Summary %
  %---------%

 \tinysection{Summary}
 
\noindent
\begin{minipage}{\linewidth}
Research-oriented undergraduate in Computer Science Engineering with a focus on autonomous and resource-constrained systems. Experience in GNSS-denied navigation, RF signal processing, Doppler-based estimation, and system-level modeling under uncertainty. Interested in navigation, autonomous systems, and edge computing, with emphasis on estimation, observability, and robustness in real-world environments.
\end{minipage}


%--------%
% Skills %
%--------%

\section{Technical Skills}

\begin{multicols}{2}

\textbf{Programming:} Python, C++

\textbf{Systems \& Signal Processing:} RF signal processing, Doppler estimation, embedded Linux, hardware--software integration

\textbf{Machine Learning:} Deep learning, model training and evaluation

\columnbreak

\textbf{Scientific \& Research Tools:} NumPy, SciPy, OpenCV, Qiskit, PyTorch, TensorFlow

\textbf{Operating Systems:} Linux (Ubuntu)

\end{multicols}





%------------%
% Experience %
%------------%

\section{Experience}

\headingBf{ALKF+, Central Hong Kong}{Feb 2026 -- Present}
\headingIt{Machine Learning Engineer (Part-Time)}{\href{}{\textcolor{blue}{Certificate}}}{}
\begin{resume_list}
  \item Developed a geospatial intelligence API using FastAPI, GeoPandas, and OSMnx to automate urban site analysis, generating maps for accessibility, transport, zoning, view, and noise with automated PDF reports.
\end{resume_list}

\headingBf{National Institute of Technology, Trichy}{Jun 2025 -- Jul 2025}

\headingIt{Quantum Computation Researcher (Internship)}{\href{https://drive.google.com/file/d/1tKC9QIrxTo1g5QDC8012rn9fnHwDn4ZI/view?usp=sharing}{\textcolor{blue}{Certificate}}}{}
\begin{resume_list}
  \item Designed and implemented quantum algorithms including Caesar Cipher, Grover’s Search, and Shor’s Algorithm using Qiskit, demonstrating cryptographic analysis and quantum search optimization.
\end{resume_list}

\headingBf{Persist Ventures, San Francisco, USA}{Jan 2025 -- Mar 2025}

\headingIt{ML-Powered Robotics Developer (Internship)}{\href{https://drive.google.com/file/d/1pUXQx3IYX5MLeKUOEPOopNJiwxYji2Sy/view}{\textcolor{blue}{Certificate}}}
\begin{resume_list}
  \item Investigated perception pipelines for autonomous navigation, implementing and evaluating real-time object detection models (YOLOv5, TensorFlow) for obstacle avoidance under dynamic indoor conditions.
\end{resume_list}

  %-----------%
  % Education %
  %-----------%

 \section{Education}

\headingBf{SRM Institute of Science and Technology (Tiruchirappalli)}{} 
\headingIt{Bachelor of Technology in Computer Science Engineering}{}
\headingIt{Year: Aug 2023 - May 2027 \hfill \textbf{CGPA: 9.352}}{}

\vspace{5pt}
\headingIt{B.Tech Hons. Quantum Computation}{}
\headingIt{Year: Jul 2024 - May 2027 \hfill \textbf{Grade: O}}{}


%------------------%
% Honors & Awards %
%------------------%

\section{Honors \& Awards}

\headingBf{Smart India Hackathon (SIH) 2025 – Winner}
{\hspace{-1em}National Level · Dec 2025 \quad \href{https://drive.google.com/file/d/1Kadd6usSjqSuCN8rTNL6oUMMnBZ3y-XC/view?usp=sharing}{\textcolor{blue}{certificate}}}

\headingBf{Algovault Hackathon – Winner}
{\hspace{-1em}National Level · Nov 2025 \quad \href{https://drive.google.com/file/d/1twHjkSYyqFCt5ScyVSC3K1mnZVdj8mNd/view?usp=sharing}{\textcolor{blue}{certificate}}}

\headingBf{Protothon 1.0 – Winner}
{\hspace{-1em}National Level · Aug 2025 \quad \href{https://drive.google.com/file/d/1TAWeozOnNU-Mim0XWd9ZoDG1aqNyFExS/view?usp=sharing}{\textcolor{blue}{certificate}}}





\section{Projects}

\headingBf
{DhruvXPNT – Cognitive Opportunistic LEO-Based Navigation and Timing System}
{\href{https://github.com/Sudharsanselvaraj/DhruvXPNT-Cognitive-Opportunistic-LEO-Based-Navigation-and-Timing-System.git}{\textcolor{blue}{\faGithub\ Github}}}

\begin{resume_list}
 \item Designed and validated a GNSS-denied Position, Navigation, and Timing (PNT) system using LEO Signals of Opportunity, formulating Doppler-based state estimation under limited observability.
\item Implemented an end-to-end RF-to-solution pipeline (signal acquisition, burst detection, Doppler extraction, orbital modeling) and evaluated estimation residuals against expected orbital dynamics on embedded Linux.

\end{resume_list}


\headingBf
{OrbitXOS – Orbital Dynamics–Based Space Debris Monitoring System}
{\href{https://github.com/Sudharsanselvaraj/OrbitXOS.git}{\textcolor{blue}{\faGithub\ Github}}}

\begin{resume_list}
  \item Developed a Space Situational Awareness platform using SGP4 and TLE data for real-time satellite/debris tracking and collision-risk visualization.
\end{resume_list}

\headingBf
{WQ Vision – Embedded AI and IoT Water Quality Monitoring}
{\href{https://github.com/Sudharsanselvaraj/wqvision-testing-kit.git}{\textcolor{blue}{\faGithub\ Github}}}

\begin{resume_list}
  \item Designed and deployed a low-cost embedded AI system using ESP32-CAM and computer vision for real-time water contaminant detection; Winner, Protothon 1.0.
\end{resume_list}


\end{document}
