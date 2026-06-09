---
title: "Creating a simple website with Quarto"
teaching: 0
exercises: 0
---

::: questions 

- How to create a website using Quarto?
- What seps and components are necessary to create a website with Quarto?
  
:::

::: objectives

- Learn how to create a .yml file to connect your Quarto documents.
- Learn the contents of a .yml file.



:::

A more advanced function of Quarto is, that users can not only create simple and standalone html pages and documets, but can also create more complex and connected webpages.
These webpages need a more complex structure of pages and files.

## Creating the necessary files

In order to create our website, we first need to plan how we want our website to be structured.
All files and must be situated in the same folder in order for our website to function!
In this case we want to have three main pages: A homepage, as well as two further sections about the history and the collections. The history section should have to subpages for the founding and the current history.

### Creating a new folder

Let us start with the most basic step: the creation of a new working folder.
Like in the previous lesson we first create a new folder called "moma_website" on our computer.
Then we open this folder in VSCode using the navigation bar on the left side.
This dolder will now contain all pages, images and ressources needed to create our website. We will slowly add more and more documents as our website grows.

### Creating our pages

#### Creating the mainpage

First we will create our mainpage, which will serve as our starting point and the first page a viewer of our website will most likely see.
in order to do so we create a new document in our folder by navigating to the left side of the VSCode window and selecting "New File" option under "File".
We then choose to create a Quarto document. By saving it (Ctrl+S), we can name it. 

::: caution
### Important!
Where we previously had comple freedom when it came to naming our document, this one need to have the name **"index.qmd"** in order to function as our mainpage!

:::

Once we named our webpage, we an start filling it.

We start with a very simple YAML header. In contrast to our previous headers, this one only need to Key-Value pairs: the title and the format.
While the format needs to be set as html, when deciding on the title you again have complete freedom.

::: tip

Always try to choose speaking and easy to understand titles and filenames, in order to avoid confusion or mishaps!

:::

In our case we will give this page the title "mainpage" and start to fill it with text and other media.
The filling of our document follows the same rules and steps that you have learned previously. You can simply add a header by using # and hen add some text.
When we do this with our main page it could look like this:
![](https://pad.zdv.net/uploads/b57dd590-3fb2-4290-8abf-6ac42c3377c6.png){fig-align="center"}

#### Adding pictures

We now want to add a picture of the MoMA to our main page.
In order to do so we can use the same syntax we used to add pictures to our previous documents.
To make sure our pictures can always be accessed we will add them to our folder as a ressource.
This can be simple done by copying the chosen file into our folder. But while this is the easiest solution, it also can get disorganized and chaotic fast, if you choose to add a lot of different images to your website.
Because we want to try to keep our folder structure neat and easy to navigate we will put our images into a new folder calles "images" which we will put into our "moma_website" fodler.
Now we add our picture into this newly created folder:
![](https://pad.zdv.net/uploads/a9e217af-ff3e-42e4-91c1-5503b574ac69.png){fig-align="center"}

When we now want to insert this image into our main page we simple have to enter the following code into our Quarto document:

```
![](images/moma_image.png)
```
As you can see we have inserted the relevant folder, in this case "images", and the name of the chosen picture, in this case "moma_image.png", into the brackets.

#### Creating the other pages

Now we can save our mainpage and continue creating our three remaining pages.
These follow the same steps as creating our main page, with one exception: We are again free to choose the name of our files.
We now create three more pages: One page for the museums collections, and two pages for its history.
We again create a file for each page, fill a simple YAML header with title and html format, and then fill our page with headers, text and images.
When done we have thre more pages with the filenames collections.qmd, founding.qmd and modernhistory.qmd.

### The YAML File

#### Creating the .yml file
Up until now he have just created a couple of Quarto files in the html format. These will not interact with each other or act as anything other than singular documents.
We have also used just the barest minimum of YAML headers in these files.
In order to connect our different document and give our files the needed formatting and metadata we will now have to create the heart of a Quarto website: The **YAML-File**!

To create this file we again navigate down the "File" -> "New File" path, as we did with our other documents. But instead of choosing to create a Quarto document, we will now enter something different into our text window.

::: caution
### Important!
Like with our mainpage, this file also needs a very specific name: "_quarto.yml."
You see the file ending is now .yml insted of .qmd.

:::

It will look like this in VSCode:
![](https://pad.zdv.net/uploads/232a7b43-0610-4869-bf86-0b0690f8500f.png){fig-align="center"}

#### Filling the .yml file

Now that we created our YAML file, we need to fill it with the specific Key-Value pairs needed to create a website.

In order to do so the file needs three sections: The "project" section, the "website" section and the "format" section.

##### The project section

The project section is located at the beginning of the document and consists of the following elements:
```
type:        This sets the type of structure and entities this YAML file will create. In our case this will be set to "website"
output-dir:  This will dictate where the rendered html files for our webpage will be stored. it will also create a folder with the name put as a value. In our case this will be "public/"
ressources:  This will dictate which folders will contai ressources used for this website. You can create and enter multiple ressource folders for images, videos, audiofildes etc. in our cas e will will enter our previously created "images/" folder.
```

When we have entered everything our project section ourld look like this:
``` {YAML}
  project:
    type: website
    output-dir: "public/"
    resources:
      - "images/"
```

##### The website section

The "website" section of the YAML file will contain the most information and create the connections between our different Quarto documents.
It contains the following elements:
```
title:   The name of our Website
image:   Here you can put an image file that will act as a logo for the website. it will be the picture displayes next to the title and in the tab of the browser
navbar:  this will create the navigation bar at the top of the website. This will be used to connect our different Quarto html pages. The navbar consists out of multiple Key-             Value pairs that are indented:
    left/right/center:  The different areas of the navigation bar can be filled up seperatly with different elements. To do so simple add the corresponding positiona and add the                         relevant elements indented after it.
    href + text:        "href" contains the file names of your Quarto documents, while "text" contains the official names of these pages, which will be shown in the navigation                           bar. They are added below each other, with only href having a "-" in front of it
    text + menu:        If you want to have one navigation bar item to consists of multiple subpages, you can add them using these Key-Value pairs. "Text" will determine the                             name of the overarching navigation bar item. The different subpages can then be added by inserting the filenames of the relevant Quarto files as part of                          the "menu" element. The names shown for these subpages in the navigation bar will be determined by the title given in the YAML header of the document.
    icon + href:        This combination of Key-Value Pairs can be used to create clickable icons that will act as links to erelevant websites such as gitlab, github or                                  different social media sites. "Icon" will determine the oüptical aspect and can be filled with any image file. Quarto also has already a large variety of                         integrated icons for most social media platforms and datashating websites (such as github, etc.), they can be used by simply writing the name of the                              platform as the value. "href" will contain the relevant webadress for the link.
page-footer:  This elemet is used to create a footer for your website. Like the navigation bar, it can also be divided into left, right and center. It can also contain a variety               of icons, text or images. Icon can be added by using the previously mentioned "icon + href" element, while text can be added via the "text" element.
```

We now want to create the 2website section of our MoMA website. 
As the title of the website we choose "A Short Guide to the MoMA"
For our image we found a good looking logo of the museum. We put the logo under the name "moma_icon.png" inro our previously created "images" folder.
We want the navigation bar to be sepetarted into two sections. On the left we want to have our different pages.  Our starting page will be calles "Home" in the navigation bar. Our page about the Collections can be found under "Collections". And our two subpages about the Founding and the modern history of the MoMA will be found under the name "History of the MoMA".
On the right side we want to add an icon that leed to the GitHub page of the project. 
As a footer we simply add a textblock in the center. It will contain the names of our authors as well as their universities.

When we add all this information into our YAML file, it could look somewhat like this:

``` {YAML}
website:
  title: "A Short Guide to the MoMA"
  image: "images/moma_icon.png"
  navbar:
    left:
      - href: index.qmd
        text: Home
      - href: collections.qmd
        text: Collections
      - text: History of the MoMA
        menu: 
          - founding.qmd
          - modernhistory.qmd
    right:
      - icon: github
        href: https://github.com/ExampleUser/MoMA_website/main

  page-footer: 
    center: "© John Doe, Jane Public <br> Example University / XYZ Collage"
```

##### The format section

lastly we need to add the Key-value pairs that determine the appearence of our website. In this section we can use the same commands and Key-Value pairs previously discussed in Section 6 of the course.
We choose to use twi themes in order to create the option for a light and dark mode. For the light theme we choose the theme "united", while for the dark theme we choose "darkly".
We also want our website to contain tables of content in the different pages.

Wenn added to the YAMl file our "format" section looks like this:

``` {YAML}
format: 
  html: 
    theme:
      light: united
      dark: darkly
    toc: true
```

When all of these elements are added, we can save our .yml file and render our finished website.

### The finished website:

Now that we have added everything our "moma_website" o#folder should look something like this:
![](https://pad.zdv.net/uploads/e844f2e7-da4e-43fe-8cfd-e9d4483eaf7f.png){fig-align="center"}

And our rendered result like this:
![](https://pad.zdv.net/uploads/b8e50c67-0d46-4ee3-b6c7-4741e70e502c.png){fig-align="center"}
