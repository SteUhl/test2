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

Footnotes offer an easy way to add useful information or literature to your text. 
They can be implemented into your Quarto document by using the Insert -> Footnotes option in the Visual Mode of Quarto.
![](https://pad.zdv.net/uploads/824de089-c707-4076-bd50-3c2c8fe24fe6.png)

Let us now add a quick footnote to our paper on the MoMA.
In order to do so we just have to add the text for our footnote into the new textbox on tghe lower part of the VSCode window:
![](https://pad.zdv.net/uploads/c3174576-c563-4404-89b4-0fda49e03143.png)

## Citations

In a similar vein to footnotes, you can also directly add citations to your document. This can be done through the Insert window of the Visual Mode:
![](https://pad.zdv.net/uploads/563f1c2c-4aab-4a60-84b5-222be982b5f3.png)

Doing so will accomplish two things: It will open a new window called "Insert citation", and it will create a new file called "references.bib" in your working folder.
![](https://pad.zdv.net/uploads/f0b75353-7f33-47b4-8fa5-d8e9c426e3d3.png)

This new file will contain your newly created bibliography, which can now be filled in a variety of ways.
The easiest to do are the four already integrated options of either searching for a publication through their DOI (a unique number given to all published articles and books) or by searching through the databases of Crossref, Datacite or Pubmed.
Simply add relevant information such as the DOI, Title or name of the author into the search bar and see what you can find there. In the best case your needed citation is already part of one of these databases.

In our paper we want to reference Alan Wallachs scentific reviiew of the book "Museums and American Intellectual Life, 1876–1926 " by Steven Conn.
In order to do so we can simply search for Alan Wallachs name using the Crossref database.
![](https://pad.zdv.net/uploads/fb2f8f12-68db-478f-8db6-b2a4cd7af9ee.png)

By pressing the + button on the right, we can quickly add it to our bibliography.

We also want to add a refernce to the the article "Selling the American Dream: MoMA, Industrial Design and Post-War France" by Gay McDonald.
As we are not able to find the article using the integrated databanks, we have to add it manually. 
In order to do this, you need to open your newly created references.bib file with a text editor of your choice. This can also be done in Visual studio code.
![](https://pad.zdv.net/uploads/b2d8db2d-926f-4ba5-aeba-6f0601544743.png)

In this file you will find all your already added references in form of code chunks.
The citation function uses a format called Bibtex, which is used by a variety of databases. 
It is in part made up of a reference name, signified by a @, which is used internally as a unique signifier of this specific reference. Following this are the reference name, which will be shown in your Quarto document when using the citation function, and a variety of information inside {} brackets. These contain the relevant metadata of the publication.

You can now simply add further objects to your list of references by either manually typing in additional sources, or by copy and pasting the relevant BibTex chunks from other websites. Many Websites used to publish academic texts, such as Jstor, or libraries offer the download oft txt files containing the relevant BibTex Chunks as part of their own citation functions.
Here is an example using Jstor:
![](https://pad.zdv.net/uploads/0d7a5347-3b4c-461c-9ac8-215894a0dda0.png)

And here is how it looks when added to your reference.bib file:
![](https://pad.zdv.net/uploads/75f52405-4829-4bb1-aeb8-b7330593d701.png)


Once you have added the new code chunk to you refernces.bb file, you can save (Ctrl+S) and return to your "Insert Citation" window.
Here you will now find your newly added reference as part of you bibliography:
![](https://pad.zdv.net/uploads/b26f826c-4fb1-4609-a002-4beb505fe335.png)

Now you can simply click on the different references in order to insert them into your work. 
In our case we want to add McDonalds article as areference into our text.
This will create a reference in the following format: [[@63aecae8-5ed6-394e-883b-12026c168381]] in source mode.
The rendered Document will have the Authors name and the publication date in brackets in its place.
Using the reference feature will also create a reference index at the bottom of your rendered document. This index will contain a full bibliographical list of all used refences, using the information contained in the reference.bib file.
The result could look something like this:
![](https://pad.zdv.net/uploads/90afe058-a7d8-450c-8a22-206d77e13402.png)

::: challenge
### Exercise
Use the **References** and **Footnote** features to enrich your document with citations.  
Create and fill out a bibliography, then render your document one last time.
:::
