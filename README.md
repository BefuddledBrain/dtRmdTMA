# dtRmdTMA
This repository has an RMarkdown file and template for producing OU TMAs, [VERY] loosely based on the OUSA tma.sty. I'm hoping that writing a TMA in RMarkdown might be easier than in LaTeX.

Since starting with MU123 a few years ago, I have enjoyed producing my TMAs in LaTeX but since embarking on trying to learn R, I have become obsessed with transfering my typesetting to RMarkdown. I have no particular reason for doing so other than because it's there ... and there may come a time when I can legitimately chuck in some rudimentary coding skills too, maybe to produce some canny-looking plots with ggplot2.

I have perviously produced my TMAs using a custom STY file, which started off just containing a list of \include{pkg} instructions for packages that I found myself using frequently. I started adding formatting shortcuts or \renewcommand code to customise in-built functions (e.g. modifyig \[ .. \] to allow equaion numbering like in the \begin{equation} .. \end{equation} environment. LaTeX gurus will probably highlight a million reasons for not doing so but it works for me ... until it doesn't.

## Parameterised TMAs
I read about parameterised reports and thought that it might enable me to simply alter a few parameters in the RMarkdown YAML (the sort of lead "setup" section in the Rmd file). In this Rmd file, I can enter appropriate values for the params: (e.g. name1: "Hugh "; name2: "Jarce"; id: "X1234567"; module: "M248"; and tma: 04) and then just start typing my TMA markup.

The background work is done by "mytemplate.tex". On my PC, I keep it in a specific folder and point to it by using "/path/way/myetemplate.tex" in the YAML. I have annotated the file so, if you want to play with it (feel free), you should find things are fairly self-evident.

## TMA questions
Start each new question with:

><\!-- % Q1 a -->  
>\marginnote{\raggedleft \textbf{Q1 a}}\vspace{-5mm}  
>\refstepcounter{Eq}  
>The concentration of ... blah, blah, blah
The <\!-- --> hides anything written between the deliniter symbols.

After that, its just ordinary text and LaTeX code for formating and (mostly) maths environments like \[ .. \] or \begin{align} .. \end{align} unless you want to pluck a few formating shortcuts from the template file.

The equation counter "{Eq}" for the equation numbers is initialised in the template file and adding \refstepcounter{Eq} both resets and increments the counter with each new question if you add the line at the start of each answer.

If you don't want or need equation numbers, just delete the line wherever it appears.

## Latest additions (15/06/2023)
I've changed to using Quarto instead of Rmarkdown. No convincing reason; I just wanted to try it out because I was seeing more noise about it. I can't remember if I had to adapt the TEX file to use with Quarto.

## Suggestions
Before using this Rmarkdown file:

Store "mytemplate.tex" wherever you want but edit the path in the YAML.

Store the skeleton.Rmd file wherever you want (e.g. "c:/OUstuff/M299/TMAfiles"). Rename the file 
so that it has same name that you want for your TMA submission, e.g. instead of "skeleton.Rmd", 
rename it e.g. "JoanBloggs_X1234567_M111_TMA01.Rmd", or whatever.

If you use \includegraphics, either keep image files in your TMAfile folder or use 
e.g. includegraphics[scale=0.75]{"/path/image.png"}

Alter entering the details in "params" in the YAML, write LaTeX code for the TMA 
(omit \begin{document} and \end{document}), and compile with Ctrl-Shift-K.

If you use \includegraphics, either keep image files in your TMAfile folder or use 
e.g. includegraphics[scale=0.75]{"/path/image.png"}

If you're mad enough to create plots (why would you when you've got ggplot2 from within Rmarkdown!) 
and diagrams, then you will have to edit "mytemplate.tex" to uncomment the relative entries that 
initialise those libraries.

## Note:
I haven't directly used the OU tma.sty file to create "mytemplate.tex", because I preferred a few of my own 
quirky formats (notably for question numbers), though I have pilfered most of the clever stuff from it. 
Most people might understandably base an RMarkdown template on the genuine OUSA tma.sty

## Ambitions
I have read about turning a template into a package so I hope to produce an R package for producing an 
OU TMA submission using RMarkdown. Someone has almost certainly made one before but this is my current. 
Having said that, don't old your breath ... my R skills are at a similar evolutionary point as the 
writing skills of a four-year-old in primary school reception class!

## Disclaimer
I am very much a beginner in all things coding and typesetting so there are quirks, hacks, and mistakes 
a-plenty. I've put this up here out of self interest as I'm hoping that those more knowledgeable than me 
might proffer some of their wisdom and experience.
