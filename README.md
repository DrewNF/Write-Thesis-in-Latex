# Writing a thesis in Latex
(Version 2.0, Last Update 04.15.2017)

### Guide to write a thesis in Latex, complete with a Template to ITA & ENG and instructions for adapting the cover image to your University (Default: Politecnico di Torino).

### For any doubt or deepening, do not hesitate to open an Issue, I will answer you very happy!

This repository is designed to push and help students use [Latex](https://www.latex-project.org/), to develop more easily their thesis, Academic Paper or why not books.

Before you start you will have to subscribe to the editor of Online Latex [ShareLatex](https://www.sharelatex.com?r=cd3f76de&rm=d&rs=b).
This has some positive practical sides: everything synced online, so always available everywhere, but especially do not risk losing **NOTHING!**

If you prefer to work with the offline version you can still use the project shared by me, but will not go into in this guide anything about it.

Italian version of the Guide, with the Italian version also File: [Scrivere una Tesi in Latex}(https://github.com/DrewNF/Scrivere-Tesi-in-Latex)

### LET'S START

After downloading the .zip file Thesis Template Polito ITA / ENG, simply unpack it, go to your Account [ShareLatex](https://www.sharelatex.com?r=cd3f76de&rm=d&rs=b), start a new project and when you are required to upload an existing project; the upload is complete you will have your thesis ready to be written!

Below an index of what I will describe in this guide:

1. **[Project Structure](#1project-structure);**
2. **[Basic Elements for Writing](#2basic-elements-for-writing);**
3. **[Links](#3links);**
4. **[Copyright](#4copyright);**
5. **[State of the Project](#5state-of-the-project);**
6. **[Acknowledgments](#6acknowledgements).**


## 1.Structure Project

Latex is a compiler of texts, so it needs a file structure that once filled up in a single text, so we should not deal with anything that is: indentation, etc. alignment, we just need to set the right parameters and everything will be done automatically.

The project has a fairly simple and intuitive structure:
  1. **main.tex** (Master File);
  2. **references.lib** (File with references to the bibliography);
  3. **image_support** (Folder containing the support images, eg the cover);
  4. **image_thesis** (Folder containing the images of the thesis, eg diagrams etc);
  5. **chapters** (Folder containing the relevant chapters of the file);

Let us now see in detail the individual elements:

  **1. main.tex (Main File)**:
  
In this file are:
  - Import settings useful for formatting text;
  - Imported its files to the bibliography;
  - Writings chapters useful as Dedications and Acknowledgments;
  - Imported individual chapters chapters in the folder;
  - Print lists of useful content.
  
  In detail, here we import the **settings**:
  
   ```latex      
    parser = argparse.ArgumentParser()
    \usepackage{fancyhdr}
    \usepackage{listings}
    \usepackage[italian]{babel}
    \usepackage{subcaption}
    \usepackage{caption}
    \usepackage[table,xcdraw]{xcolor}
    \usepackage{comment}
    \usepackage{adjustbox}
  ```
  
  **Here we import the bibliography file**:

  ```latex      
    \addbibresource{references.bib}
  ```
  
  **Here we write inline chapters in the file**:
  
  ```latex      
    \chapter*{Dedications}
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin pellentesque massa eu lacus vestibulum elementum. 
  ```
  
  **Here we import the individual chapters**:
  
  ```latex      
    \chapter{Stato dell'Arte}
    \input{chapters/4_stateoftheart}
    \chapter{Metodologia}
    \input{chapters/5_methodology}
    \chapter{Sviluppo del Lavoro}
    \input{chapters/6_development}
    \chapter{Valutazione del Lavoro}
    \input{chapters/7_evaluation}
    \chapter{Conclusioni}
    \input{chapters/8_conclusion}
  ```
   
  **Finally we print the lists of contents**:
  
  ```latex      
    \tableofcontents
    \listoffigures
    \listoftables
    \printbibliography 
  ```
    
  The order in which these points are specified depends on the author's choices in the file provided to you, the order is classic, so you can safely leave things as they are and change only chapters and content.
  
  **2. references.lib (File with references to the bibliography)**:
  
 The references.lib files is very convenient allowing you to specify two different types of sources and recall them in the text, then the compiler will print the ordered list at the end.
 The possibilities are as follows:
  
  
   ```latex      
    %%% ARTICLES

    @ARTICLE{lorem_article,
       author = {{Redmon}, J. and {Divvala}, S. and {Girshick}, R. and {Farhadi}, A.
      },
        title = "{You Only Look Once: Unified, Real-Time Object Detection}",
      journal = {ArXiv e-prints},
    archivePrefix = "arXiv",
       eprint = {1506.02640},
     primaryClass = "cs.CV",
     keywords = {Computer Science - Computer Vision and Pattern Recognition},
         year = 2015,
        month = jun,
       adsurl = {http://adsabs.harvard.edu/abs/2015arXiv150602640R},
      adsnote = {Provided by the SAO/NASA Astrophysics Data System}
    }

    %%% WEBSITE

    @online{lorem_web,
        author        = {Berkley},
        title         = {Caffe, Deep Learning Framework},
        year          = {2008},
        url           = {http://caffe.berkeleyvision.org/}
    }
  ```
   

 **3. image_support (Folder containing the support images, eg cover) &**
 **4. image_thesis (Folder containing the images of the thesis, eg schemes graphics etc)**:
  
 These two folders are created for reasons of public order, the first will fill all those images that will not be mentioned and used in the main text.
  While the second folder must be charged only the latter, cosichè there will be no possibility of confusion of the content.
  
 **5. chapters (Folder containing the relevant chapters of the file)**:
 
 Finally in this folder are content files for individual chapters, where they will be content sections, subsections, content, citations, but mainly text.
 
## 2.Elementi Base for Scripture

This chapter will show you the main useful formulas for the drafting and structuring of the text within the individual chapters.
To define **Sections and subsections** use:

  ```latex      
    \section{Morbi}
    Morbi ac varius enim, ac lobortis odio. 
    \subsection{Et amo}
    Nullam venenatis, erat in faucibus vestibulum, magna dolor faucibus sapien, ac iaculis tellus urna ut purus.
  ```
To define **Images** use:

  ```latex      
    \begin{figure}[h!]
    \includegraphics[scale=0.3]{lorem_image.png} 
    \centering
    \caption{Morbi ac varius enim, ac lobortis odio. Nullam venenatis, erat in faucibus vestibulum, magna dolor faucibus sapien, ac iaculis tellus urna ut purus. Pellentesque finibus urna eget maximus cursus. Aenean mollis ante nec dolor iaculis, ac malesuada enim ultrices. Aenean vulputate felis sapien, quis rhoncus odio dictum vitae.}
    \label{fig:template_cat_c}
    \end{figure}
  ```
To define **Tables** we use:

  ```latex      
    \begin{table}[h!]
    \centering
    \begin{tabular}{|c|c|c|c|}
    \hline
    \textbf{Team name}      & \textbf{Entry description}                                                                                                & \textbf{\begin{tabular}[c]{@{}c@{}}Number of\\  object \\ categories won\end{tabular}} & \textbf{mAP}                    \\ \hline
    \textbf{NUIST}          & \begin{tabular}[c]{@{}c@{}}cascaded region regression \\ + tracking\end{tabular}                                          & 10                                                                                     & {\color[HTML]{FE0000} 0.808292} \\ \hline
    \textbf{NUIST}          & \begin{tabular}[c]{@{}c@{}}cascaded region regression \\  + tracking\end{tabular}                                         & 10                                                                                     & 0.803154                        \\ \hline
    \textbf{CUVideo}        & \begin{tabular}[c]{@{}c@{}}4-model ensemble with\\ Multi-Context Suppression and\\ Motion-Guided Propagation\end{tabular} & 9                                                                                      & 0.767981                        \\ \hline
    \textbf{Trimps-Soushen} & Ensemble 2                                                                                                                & 1                                                                                      & 0.709651                        \\ \hline
    \end{tabular}
    \caption{Morbi ac varius enim, ac lobortis odio. Nullam venenatis, erat in faucibus vestibulum, magna dolor faucibus sapien, ac iaculis tellus urna ut purus. Pellentesque finibus urna eget maximus cursus. Aenean mollis ante nec dolor iaculis, ac malesuada enim ultrices. Aenean vulputate felis sapien, quis rhoncus odio dictum vitae.}
    \label{tab:template_table_c}
    \end{table}
  ```
  A tip for the creation and management of the tables is to use the following [Editor Online](http://www.tablesgenerator.com/) that allows you to graphically create the table, and then later export the code in Latex file.

To quote in the text respectively **Bibliography**, **Images**, **Tables** we use:

  ```latex      
   \cite{lorem_article} 
   
   \ref{fig:template_cat}
   
   \ref{tab:template_table}
  ```
The convenience of well cite our sources, is that we should not deal with controls numeric references and order, because latex will do it in our place.

To create **bulleted lists** we use:

  ```latex      
    \begin{itemize}
      \item  Contribution 1;
      \item  Contribution 2;
      \item  Contribution 3.
    \end{itemize}
  ```
For more in-depth knowledge and formatting, I refer you to the section with useful links where you will insert all links to the official guides that explain the different possibilities of text formatting, by its size to bold and italic, multi-image compositions etc ...
  
## 3.Links

 - [Project Upload](https://it.sharelatex.com/learn/Uploading_a_project);
 - [Bibliography](https://it.sharelatex.com/learn/Using_bibliographies_in_ShareLaTeX);
 - [Images](https://it.sharelatex.com/learn/Inserting_Images);
 - [Tables](https://it.sharelatex.com/learn/Tables);
 - [Paragraph and New line](https://it.sharelatex.com/learn/Paragraphs_and_new_lines);
 - [Bold, Italic & Underline](https://it.sharelatex.com/learn/Bold,_italics_and_underlining);
 - [Lists](https://it.sharelatex.com/learn/Lists);
 - [Headers & Footers](https://it.sharelatex.com/learn/Headers_and_footers);
 - [Footnotes](https://it.sharelatex.com/learn/Footnotes);
 - [Text Alignment](https://it.sharelatex.com/learn/Text_alignment).
  
## 4.Copyright

According to the LICENSE file of the original code:
  - Me and original author hold no liability for any damages;
  - Do not use this on commercial!.

## 5.State of the Project

The project aims to include in a single page:
- Useful to write a text with Latex;
- Project File to write the main text;
- Project File to write the summary.

## 6.Acknowledgements

I thank my Erasmus+ at FIB UPC Barcelona Tech, for pushing me to use and develop my thesis with latex discovering its great strengths.
  
