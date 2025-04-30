# PP3

## Goal
In this exercise, we will explore how to handle, render and display text-based information from our terminal.
As ancient as this may seem, the foundation of effective software engineering is a familiarity with the concepts of programmatic text-processing.
We will generate different artifacts using four different _description-languages_.
After this exercise, you should be able to decide for yourselves, when to use which and have a fundamental understanding of how they are supposed to work.

**Important:** Start a stopwatch when you begin and work uninterruptedly for 90 minutes. Once time is up, stop immediately and document the point where you had to pause.

---

## Workflow
Remember the standard workflow.
If in doubt, revisit [PP1](https://github.com/MaxClerkwell/PP1)

1. **Fork** the repository
2. **Modify and Commit** your solution
3. **Submit your link for Review**

If you get stuck, use the [Github-Discussions of this Repository](https://github.com/MaxClerkwell/PP3/discussions)!

## Tasks

### Prerequisits: Linux, SSH and vim
This task is not part of the measured time within this practical exercise!

By now you should already have access to one local linux machine.
Whether this is a Raspberry Pi, a Desktop-PC or a WSL para-virtualized system on your Windows computer doesn't make any difference.
If you are unsure about how to log in, you can [check out this video tutorial](https://www.youtube.com/watch?v=Z0ggeNzEhzY).
Make sure, that you are wellversed in utilizing your filesystem with `cd`, `ls`, `cat`, `mkdir` and `rm`, as well as navigating through textfiles with `vim`, by revisiting the `vimtutor` you should've finished by the end of [PP2](https://github.com/MaxClerkwell/PP2).

---

### Task 1: SVG
The scalable-vector-graphics format is a commonly used description language for diagrams.
You will probably use this file format throughout your professional career and your studies multiple times, therefore we want to explore this format here.

As usual for description languages, the actual content is a regular textfile, that get's rendered on display by a sepecific rendering software.
In case of SVG, the software that renders the actual picture is embedded in a lot of other tools, such as browsers, or image software.

An SVG file is an XML-based text file that describes two-dimensional vector graphics.
The basic structure of an SVG file includes the following components:

#### XML Declaration

```xml
<?xml version="1.0" encoding="UTF-8"?>
```

This optional line declares the XML version and character encoding used in the file.

#### SVG Root Element

```xml
<svg xmlns="http://www.w3.org/2000/svg"
     version="1.1"
     width="800mm" height="600mm"
     viewBox="-400 -300 800 600">
  <!-- SVG content goes here -->
</svg>
```

##### Attributes:

- `xmlns`: Defines the XML namespace for SVG elements.
- `version`: Specifies the SVG version being used.
- `width` and `height`: Set the dimensions of the SVG canvas.
- `viewBox`: Establishes the coordinate system and aspect ratio.

#### Optional Metadata Elements

Within the `<svg>` element, you can include metadata to provide additional information about the SVG content:

```xml
<title>Title of the SVG</title>
<desc>Description or alternative text for the content.</desc>
```

- `<title>`: Provides a title for the SVG, which can improve accessibility.
- `<desc>`: Offers a description of the SVG content, also aiding accessibility.

#### Graphical Elements

Inside the `<svg>` element, you can define various graphical elements such as:

- `<rect>`: Draws rectangles.
- `<circle>`: Draws circles.
- `<path>`: Defines complex shapes.
- `<text>`: Adds text elements.

Each of these elements can have attributes to define their appearance and position.

#### Example

```xml
<?xml version="1.0" encoding="UTF-8"?>
<svg xmlns="http://www.w3.org/2000/svg"
     version="1.1"
     width="800mm" height="600mm"
     viewBox="-400 -300 800 600">
  <title>Sample SVG</title>
  <desc>A simple example of an SVG file structure.</desc>
  <rect x="10" y="10" width="100" height="50" fill="blue" />
</svg>
```

This example creates an SVG canvas with a blue rectangle positioned at (10,10) with a width of 100 units and a height of 50 units.

For more detailed information on SVG structure and elements, you can refer to the [W3C SVG 2 Specification](https://www.w3.org/TR/SVG2/struct.html).

**Install vim on your local machine and open a new file, called `example.svg`. Write the SVG-code to include a straight line, a circle and a rectangle. When done, use your browser to open the file.**
    <details> 
    <summary>Your SVG Code</summary>
    </details>
    
   
```xml
<?xml version="1.0" encoding="UTF-8"?>
<svg xmlns="http://www.w3.org/2000/svg"
version="1.1"
 width="400mm" height="300mm"
viewBox="0 0 400 300">
<title>Line,Circle,Rectangle SVG</title>
<desc>Draws a line,a circle and a rectangle</desc>
<line x1="50" y1="50" x2="350" y2="50" stroke="black" stroke-width="2"/>
<circle cx="100" cy="150" r="40" fill="red"  />
<rect x="200" y="100" width="120" height="80" fill="blue" />
</svg>
```



### Task 2: Markdown
You have already discovered _markdown_ in these `README.md` files.
It is an easy and lightweight syntax, to instruct a display software to render text in a given way.

**Answer the following questions:**
<details>
    <summary>How does prepending hashes (<code>#</code>) affect the display?</summary>
           <summary>Prepending # creates headings. The number of # symbols determines the heading level</summary>
     
  <details>   
   <code>#</code> Heading 1 → largest, like a title 
     
   <code>#</code><code>#</code> Heading 2  → subheading

   <code>#</code><code>#</code><code>#</code> Heading 3 → sub subheading
   and so on, up to <code>#</code><code>#</code><code>#</code><code>#</code><code>#</code><code>#</code> Heading 6 (smallest heading)
</details>
    ......
</details>
<details>
    <summary>How do you mark italic or bold font?</summary>
   <summary> 
Italic : Use single asterisk oder underscores at the begin and the end the word  </summary>  
         
    *ananas*
<summary> Bold: Use double asterisks (**bold**) or double underscores (__bold__)   </summary> 

    **House**
</details>

<details>
   <summary>Which different ways are there to generate listings and tables?</summary>
     <summary> To generate listings you can use symbols like -, *, or + in front of item if it is a unordered list  
<details>
     
     -Apple
  
     -Banana
  
     - Cherry


</details>
     oder if it is a ordered list you use numbers followed by a period 
<details>
     
     1. First item
     2. Second item
     3. Third item

</details>
  <details>
   <summary>Which different ways are there to generate listings and tables?</summary>  
     <summary>If you want to generate table zou can use | (pipes) and - (dashes) oder also align text in columns by placing colons</summary>
<details>
     
     | Product | Price | In Stock |
     |---------|-------|----------|
     | Pen     | $1.00 | Yes      |
     | Notebook| $3.50 | No       |

</details>
oder also align text in columns by placing colons
<details>
     
     | Left Align | Center Align | Right Align |
     |:-----------|:------------:|------------:|
     | Apple      |    10        |        $1.00|
     | Banana     |    5         |        $0.50|

</details>
   
</details>

### Task 3: LaTeX
While markdown is great for light-weight rendering text within a limited context such as a browser or phone, when it comes to more complex and professional rendering, the `LaTeX` toolset is the standard for creating `.pdf` files.
`LaTeX` is usually not rendered _on the fly_, meaning while it is being displayed.
A special software which we call _compiler_ is used to generate a parametrized documents.
If you are running a local WSL, make sure to install `texlive-full` before continuing with the next steps.
This may take up to 30 minutes, since it's a large software package.
To check whether the installation was sucessful, run `pdflatex --version`.
The output should look something like this:
```sh
user@machine:~$ pdflatex --version
pdfTeX 3.141592653-2.6-1.40.25 (TeX Live 2023/Debian)
kpathsea version 6.3.5
Copyright 2023 Han The Thanh (pdfTeX) et al.
There is NO warranty.  Redistribution of this software is
covered by the terms of both the pdfTeX copyright and
the Lesser GNU General Public License.
For more information about these matters, see the file
named COPYING and the pdfTeX source.
Primary author of pdfTeX: Han The Thanh (pdfTeX) et al.
Compiled with libpng 1.6.43; using libpng 1.6.43
Compiled with zlib 1.3; using zlib 1.3
Compiled with xpdf version 4.04
```
If you are using the lecture-server, make sure to visit the [SCP tutorial](https://github.com/STEMgraph/301394c2-6efb-4677-aaff-47091fb8145d) first.
Otherwise, you might have a hard time opening the generated `.pdf`-document.

Create a new directory on the linux machine that texlive is installed at, navigate into it and open a file with the name `main.tex`.
Simply copy the following text into it:
```tex
\documentclass{article}             % Sets the document class to "article"
\usepackage[utf8]{inputenc}         % Allows you to use UTF-8 input encoding

\title{Minimal LaTeX Project}       % Sets your document title
\author{Your Name}                  % Sets your name as the author
\date{\today}                       % Sets the date to the day you compile

\begin{document}                    % Begins the document content

\maketitle                          % Generates the title using the above information

Hello, world!                       % This is where your content goes

\end{document}                      % Ends the document
```
Save and close the document.
Now run the following command to create a `.pdf`-file from it:
```sh
pdflatex -jobname=example.pdf main.tex
```
After it finishes, us `ls` to inspect the directory.

**Answer the following questions:**

<details>
    <summary> Which files were generated by the LaTeX compiler?</summary>
      <summary> example.pdf — the compiled PDF document (the output you want)</summary>

<summary>example.aux — auxiliary file used for references, citations, etc.</summary>

<summary>example.log — compilation log showing errors, warnings, and messages</summary>

<summary>main.tex — your original source file</summary>
    ......
</details>

<details>
       <summary>How do you change the name of the pdf-file?</summary>
       <summary>You can change the name of the output PDF by using the -jobname option, but without the .pdf extension.

     
       pdflatex -jobname=example main.tex
</details>

</summary>
    ......
</details>

### Task 4: Displaying your pdf
1) If you worked on the lecture-machine, use the `scp` command to copy your `.pdf`-file to your desktop. There you can display it with every regular `.pdf`-viewer
2) If you worked in the WSL: run `sudo apt install xpdf -y` to install the `xpdf`-viewer. Run `xpdf <your pdf path>` to open the document.

**Answer the following questions:**

<details>
     <summary>What changes in your pdf, if you change the documentclass to <code>book</code>  </summary>
    <summary>The title page is typically placed on a separate page.Chapters (<code>\chapter {}</code>) become available (they don't exist in article class). Section numbering changes .Blank pages may be added before new chapters. Page numbering might switch from Roman numerals in front matter to Arabic numbers.</summary>
    ......
</details>
<details>
     <summary>What changes in your pdf, if you add <code>\section{Intro}</code> after <code>\maketitle</code></summary>
    <summary>You will see a new section titled "Intro" appears directly after the title.It will be numbered if numbering is enabled. The text you write after <code>\section{Intro}</code> will apppear as the content of that section.</summary>
    ......
</details>


### Task 5:
If you are running on a Windows machine, make sure to install `vim` for Windows from the [official `vim` repository](https://github.com/vim/vim-win32-installer/releases).
Scroll down until you see the _Assets_ and use the `_64.exe` or `_x86.exe`, depending on your system.
If you run MacOS or Linux natively, make sure you have `vim` installed via your package-manager.

Open a terminal-session and create a new directory within your users home-directory called `html`.
Use `vim` to open a new file within it called: `index.html`.

Copy the following text into it:
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Minimal HTML Example</title>
  </head>
  <body>
    <p>Hello, world!</p>
  </body>
</html>
```
Depending on your system, run the following command to open the rendered file:
Windows:
```sh
start index.html
```
MacOS
```sh
open index.html
```
Linux
```sh
xdg-open index.html
```
If you are running in WSL, make sure to install the `w3m` browser before by executing `sudo apt install w3m -y`.


**Answer the following questions:**
<details>
 <summary>What happens if you exchange the <code>&lt;p&gt;&lt;/p&gt;</code> for <code>&lt;h1&gt;&lt;/h1&gt;</code>?</summary>
  <summary>The text "Hello, world!" will appear larger and bold</summary>
  ...... 
</details>

<details>
     <summary>How can you generate a listing of items?</summary>
     <summary>To create a list, you use either an unordered list <code>(&lt;ul&gt;)</code> or an ordered list <code>(&lt;ol&gt;)</code> with list items <code>(&lt;li&gt;)</code></summary> 
<details>    
    
     <ul>
     <li>First</li>
     <li>Second</li>
     <li>Third</li>
     </ul>
</details>     
<details>    
    
     <ol>
     <li>First</li>
     <li>Second</li>
     <li>Third</li>
     </ol>
</details>
 ......
</details>

<details>
      <summary>How can you create a table in this document?</summary>
    <summary>Use the <table> element along with<code> &lt;tr&gt;</code>(table row), <code>&lt;th&gt;</code> (table header), and <code>&lt;td&gt;</code> (table data) </summary>
<details>
  

    
    <table border="1">
    <tr>
    <th>Name</th>
    <th>Age</th>
    </tr>
    <tr>
    <td>Alice</td>
    <td>30</td>
    </tr>
    <tr>
    <td>Bob</td>
    <td>25</td>
    </tr>
    </table>
            
</details>
</details>


---

**Remember:** Stop working after 90 minutes and record where you stopped!
