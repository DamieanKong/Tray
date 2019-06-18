MD File to PDF File
===

# 1. Purpose

To convert MD files into PDF files with Sublime.

# 2. Requirement

1. [Sublime Text 3 (Build 3208 x64)](https://download.sublimetext.com/Sublime%20Text%20Build%203207%20x64%20Setup.exe)
2. [pandoc (2.7.3-windows-x86_64)](https://github.com/jgm/pandoc/releases/download/2.7.3/pandoc-2.7.3-windows-x86_64.msi)
3. [Texlive 2019](http://mirror.utexas.edu/ctan/systems/texlive/Images/)
4. default.latex

# 3. Installation

## 3.1 Download and install all of the above softwares.
## 3.2 Custom a new Sublime-Build in Sublime.

Go to: `Tools > Build System > New Build System`.

Copy these lines into the opened file and save it as `pandoc.md2pdf.sublime-build`:

```
{
	"cmd": "pandoc --template=\"C:\\Users\\kongd\\AppData\\Roaming\\Sublime Text 3\\Packages\\User\\default.latex\"  --pdf-engine=pdflatex --filter=pandoc-citeproc -o $file_base_name.pdf $file_name",
	"selector": "text.html.markdown",
	"shell": true
}
```

where `\"C:\\Users\\kongd\\AppData\\Roaming\\Sublime Text 3\\Packages\\User\\default.latex\"` is the absolute path to the downloaded `default.latex`.

# 4. Usage

Now you can convert any MD file into a PDF file with Sublime by:

`Tools > Build System > pandoc.md2pdf`

and then,

`Tools > Build`

Enjoy!
