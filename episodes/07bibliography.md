---
title: "Using the Bibliography"
teaching: 0
exercises: 1
---

::: questions 

- What is the bibliography feature in Quarto?
- How do you use and expand the bibliography and citations?
- How do you implement footnotes?
  
:::

::: objectives

- Learn the basics of citations and footnotes in Quarto.
- Learn to insert footnotes.
- Learn to create citations in a document. 
- Learn to find publications in the integrated databases and insert them manually into your references file
- Learn how to expand your bibliography.

:::

One of the most important aspects of scientific publishing is the inclusion and organisation of sources,. citations and footnotes. These are all included in Quarto, which offers an integrated menu to organize and implement Citation from a variety of different sources.

::: callout

For this part of the lesson, we will switch from Source Mode to Visual Mode, in order to offer you an easier to understand guide on how to use these.

:::

## Footnotes:
![](images/bibliography_footnotes01.png)

Footnotes offer an easy way to add useful information or literature to your text. 
They can be implemented into your Quarto document by using the Insert -> Footnotes option in the Visual Mode of Quarto.



Let us now add a quick footnote to our paper on the MoMA.
In order to do so we just have to add the text for our footnote into the new textbox on tghe lower part of the VSCode window:

![](images/bibliography_footnotes02.png)

## Citations

In a similar vein to footnotes, you can also directly add citations to your document. This can be done through the Insert window of the Visual Mode:
![](images/bibliography_citations01.png)

Doing so will accomplish two things: It will open a new window called "Insert citation", and it will create a new file called "references.bib" in your working folder.

![](images/bibliography_citations02.png)


This new file will contain your newly created bibliography, which can now be filled in a variety of ways.
The easiest to do are the four already integrated options of either searching for a publication through their DOI (a unique number given to all published articles and books) or by searching through the databases of Crossref, Datacite or Pubmed.
Simply add relevant information such as the DOI, title or name of the author into the search bar and see what you can find there. In the best case your needed citation is already part of one of these databases.

In our paper we want to reference Alan Wallachs scentific review of the book "Museums and American Intellectual Life, 1876–1926 " by Steven Conn.
In order to do so we can simply search for Alan Wallachs name using the Crossref database.

![](images/bibliography_citations03.png)

By pressing the + button on the right, we can quickly add it to our bibliography.

We also want to add a reference to the the article "Selling the American Dream: MoMA, Industrial Design and Post-War France" by Gay McDonald. Sadly the article is found in none of the integrated databases.
As we are not able to find the article using the integrated databanks, we have to add it manually. 
In order to do this, you need to open your newly created references.bib file with a text editor of your choice. This can also be done in Visual Studio Code.

![](images/bibliography_citations04.png)

In this file you will find all your already added references in form of code chunks.
The citation function uses a format called Bibtex, which is used by a variety of databases. 

It is, in part, made up of a reference name, signified by a @, which is used internally as a unique signifier of this specific reference.

Following this are the reference name, which will be shown in your Quarto document when using the citation function, and a variety of information inside {} brackets. These contain the relevant metadata of the publication.
As you can see, the information is stored in form of Key-Value pairs, similar to the YAML headers we have already encountered. they contain information such author, publication date, DOI or relevant URLs. 
You can freely add or subtract information should you find yourself missing some information. But as academic best practice, the authots name, publication date and publisher should always be names as part of a citation or literary reference.

You can now simply add further objects to your list of references by either manually typing in additional sources, or by copy and pasting the relevant BibTex chunks from other websites. Many Websites used to publish academic texts, such as Jstor, or libraries, offer the download of txt files containing the relevant BibTex Chunks as part of their own citation functions.
Here is an example using Jstor:

![](images/bibliography_citations05.png)

And here is how it looks when added to your reference.bib file:

![](images/bibliography_citations06.png)


Once you have added the new code chunk to you refernces.bb file, you can save (Ctrl+S) and return to your "Insert Citation" window.
Here you will now find your newly added reference as part of you bibliography:

![](images/bibliography_citations07.png)


Now you can simply click on the different references in order to insert them into your work. 
In our case we want to add McDonalds article as a reference into our text.
This will create a reference in the following format: [[@63aecae8-5ed6-394e-883b-12026c168381]] in source mode.
The rendered Document will have the Authors name and the publication date in brackets in its place.
Using the reference feature will also create a reference index at the bottom of your rendered document. This index will contain a full bibliographical list of all used refences, using the information contained in the reference.bib file.
The result could look something like this:

![](images/bibliography_citations08.png)

::: challenge

### Exercise
Use the **References** and **Footnote** features to enrich your document with citations. 
Try to find publications that you already know from previous projects, yourself or collegues. If they are not part of the integrated databases, try to add them manually to your reference.bib file!
Create and fill out your bibliography, then render your document one last time.

:::

::::::::::::::::::::::::::::::::::::: keypoints

+ Quarto has an integrated Bibliography feature
+ The bibliography can be accessed via the visual mode
+ You can add literature via four integrated databases, or by manually typing them into the reference.bib file
+ Literature added via the bibliography feature can be added into the text via footnotes and citations

::::::::::::::::::::::::::::::::::::::::::::::
