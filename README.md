# dissertation-template
This repo holds a template to build a dissertation with LaTeX

Use your favorite LaTeX IDE, e.g., Visual Studio Code with LaTeX Workshop extension, to work on your dissertation document. Make sure to install a TeX distribution on your system like, e.g., TeXLive or MiKTeX.

The template makes use of the more advanced `biblatex` package instead of `bibtex` to enable new important features, e.g., supporting multiple bibliographies in one file (handy for cumulative dissertations) and default styles. Further, `makeglossaries` is used to support acronyms and glossaries.

For a successful compilation run the following commands:

`2*pdflatex -> biber -> makeglossaries -> pdflatex`

or simply

`latexmk`

Note: The package `latexmk` automates the process and runs the commands `biber` and `makeglossaries` only if the bibliography or glossary was changed. This way compilation time is sped up. `latexmk` is made aware of `makeglossaries` through the file `.latexmkrc`.

Note: In order to execute the `makeglossaries` command, further a Perl interpreter installation is required. Perl is installed on Ubuntu by default but needs to be added on Windows, e.g., through Strawberry Perl or ActivePerl.

Note: The source code is so far only compatible with glossaries package <=v4.49 and requires an update for use with newer versions. An update suggestion for a code snippet similar to the glossary style definitions in the template can be found [here](https://golatex.de/viewtopic.php?t=24728).

Note on PDF/A compliance: The dissertation needs to be compliant with PDF/A-1b standard according to the university library staff. Since modern figures usually include transparency, we adapted the template to use PDF/A-2b by default and to not further care about it. Take a look at the [Section “PDF/A compliance" in the ANTwiki](https://github.com/ant-uni-bremen/antwiki/wiki/Publications#pdfa-compliance) for more information.

Note: Check your PDF for compliance with PDF/A-2b in the end, e.g., with veraPDF.

## Publication

You will eventually worry about publication. Usually after your PhD defense. Here are some pointers.

You probably prefer to publish under some Creative Commons license, e.g. CC-BY-SA 4.0, to make sure you can alter your own work and publish it however you like.

### Requirements

You must publish your dissertation after your defense to complete your PhD, and thus receive your doctoral certificate.

Depending on how you publish, this will require a few copies. Here is a list of possible recipients.

- yourself
- Armin, your "Doktorvater"
- Zweitgutachter very likely
- Carsten
- Dirk

Thus, these are 5 copies.

Some argue that all your coworkers should get one. This would be a lot of copies. Also, I got like one. You might want to add a personal note to everyone as well.

Legal requirements:
- 1 copy for the uni library, if and only if you publish online with them
- 7-10 copies for the uni library, if you publish with a publisher (probably Shaker Verlag). The numbers vary depending on whom you ask.
- 1 copy for the FB1 archive. Though, this is unconfirmed yet.

Thus, a minimum of 3 copies, more likely 9 copies and it might go up to 12 copies.

### My configuration

- A5 14.8x21 mm
- white paper 80g/m²
- 243 pages
- 92 colored pages
    - be careful how you count. RGB based or CMYK based. You probably want the RGB version.
    - the `colorcount.sh` script will help you.
- soft cover, colored, 250g/m²
- non-glare finish
- 20 copies


### Haus der Dokumente
[Haus der Dokumente](https://www.haus-der-dokumente.de) behind-ish Mensa. They offer an [Onlinetool](https://www.haus-der-dokumente.de/webcu/product-configurator/84438b115e754a7790289bea1a58df7c). They require sheets instead of pages, i.e. divide by 2 and round up.


My configuration 
- Wie werden Farbseiten gezaehlt?
	- Unbekannt. Was auch immer der Drucker nachher sagt.
- Wie kann ich das vorher herausfinden?
	- Gar nicht. Weil es unbekannt ist wie das technisch passieren soll

### Configuration

- 243 pages => 122 sheets
	- paper size A5
- 92 color pages
    - they don't know how to count in advance. The printer will tell them afterwards.
- double sided print
	- always use 100g/m² paper
- Content PDF does not require a cut off border, only the cover page

The cover can be designed to your very own liking. Imagine front, back, and book spine as one page.

- One PDF with back on left, book spine in the middle, and front left
	- 3mm for cut off
- book spine thickness calculation
	- 80g/m²: sheets * 0,1mm = 122 * 0,1mm = 12.2mm
	- 100g/m²: sheets * 0,12mm = 122 * 0,12mm = 14.64mm

**COST**: approx ~400€ for 20 copies.

### Shaker Verlag

> **_NOTE:_** Armin really wants you to publish in his series of books [Dissertationen aus dem Arbeitsbereich Nachrichtentechnik der Universität Bremen, Herausgeber Prof. Dr.-Ing. Armin Dekorsy, Bremen](https://www.shaker.de/de/content/catalogue/index.asp?lang=de&ID=6&category=630)

However, this is also the absurdly expensive version. You need more copies and they are way more expensive.
With the given configuration 20 copies end up at 1155€. Keep in mind, you need more copies in this case anyways. You need to give more copies to the library such that you may (this is your risk) receive some money from VG Wort.

**COST**: 1155€ for 20 copies.

#### Issues

By an anonymous source in academia that I met:
> Shaker is the publisher equivalent of a "predatory journal"

Their whole process feels like they are stuck in the 80s. Tell them to send you email with all the stuff you need before they arrive by snailmail. They might have issues that could be fixed faster this way. It seems like they did better 25 years ago.

#### Fixes

They start of with a ["Mustervertrag"](https://www.shaker.de/de/content/download/Mustervertrag_Dissertation.pdf). Be careful, it is outdated and differs from the actual contract they'd send you.
Further, this publication contract is subject to change and negotiation.

I decided to

- only publish print versions with Shaker
- changed their publication and usage rights from "ausschließlich" (only they are allowed) to "einfach" (they are allowed but you may give permissions to others at your discretion)
- I'll be able to publish online under CC-BY-SA 4.0 as I wanted without any issue.

#### VG Wort

VG Wort is an organization that is supposed to help creators recover some of their losses due to printing etc. Often, they also follow their own agenda that is not always in your best interest.

How to recover some money

- register with them the same year you publish
- **HOPE** that at least 5 scientific libraries list your dissertation.
    - at least one former coworker had bad luck and couldn't recover any money.
    - at least one former coworker published with the library first and couldn't recover any money.
- In 2022 you would've received approximately 700€.

In order to up your changes of recovering any money, you will receive advice to wait with your online publication until after you recovered your money. Out of the 12 former publications, I could only find 1 online publication by Fabian Monsees. No one else ever published online later.

The standard online publication with Shaker is called "Green Open Access" which is a euphemism, or more precisely bullshit. You want **Gold Open Access**, i.e. Creative Commons, to make sure you can use your own material however you like.

#### Cost calculations for Shaker

100€ for a picture on the cover, assuming it is approved.
In order to figure out how much this will cost, you need to register. I did some exemplary calculations.

- 10 copies
	- 0 colored: 480,63€
	- 50 colored: 732,44€
	- 92 colored: 943,95€
	- cost: y = 5.04€ * x + 480.63€
- 20 copies
	- 0 colored: 593,45€
	- 50 colored: 899,04€
	- 92 colored: 1155,74€
	- cost: y = 6.11€ * x + 593.45€
- 30 copies
	- 0 colored: 703,35€
	- 50 colored: 1.053,18€
	- 92 colored: 1.347,04€
	- cost: y = 7.00€ * x + 703.35€
- Scaling with number of copies
	- 0 colored: y = 11.14€ * x + 369.76€
	- 50 colored: y = 16.04€ * x + 574.15€
	- 92 colored: y = 20.15€ * x + 745.82€

I used these lines in Python to compute a linear regression.
```python
import numpy as np
x = [ ..... ]
y = [ ..... ]

m, b = np.polyfit(x, y, 1)
```



