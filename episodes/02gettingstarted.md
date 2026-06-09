---
title: "Getting started"
teaching: 0
exercises: 1
---

::: questions

+ How do i open a new Quarto document? 
+ What editing modes exist?
+ How do i switch between modes?

:::

::: objectives

+ Open a new Quarto document.
+ Create a working folder
+ Switch between editing modes 

:::

## Choosing your working folder

In order to work in a clean and organized environment, we will first create a new working folder and choose to use it in Visual Studio Code. 
In order to do so, we will first open the options in the upper left corner of the window (depicted as three parallel horizontal lines). There we will follow the path of File -> Open Folder.

<img style="display: block; margin: auto;" src="images/gettingstarted_01.png" width="350">

Here we can then create a new folder, which we call ***"Art_distribution_paper"***.
Once selected, it will open the folder in VSCode and select it as our new working environment. All new documents, outputs and relevant data will be stored in this folder.


## Opening a Quarto Document

Now we continue by creating our Quarto file. This is done by again selecting the options in upper left corner and following the path File -> New File.
After installing the extension, two new options appear when creating a new file in VS Code: Quarto Document and Quarto Project.
A Quarto Document creates a single file, that can be used to create singular Documents such as a PDF.
A Quarto Project offers you the option to choose between several premade setups used to create more complex structures such as a blog, book or website.

As we are currently working on the very basics, we will choose the "Quarto Document" option when creating a new file.


After opening the new file, you should see the following:

<img style="display: block; margin: auto;" src="images/gettingstarted_02.png">

The "empty" Documents only contain a small YAML header with generic information about title and format of the document.

By using the keybord shortcut *Ctrl + S*, we can now save our new Quarto document in our previously created "Art_distribution_paper" folder. We will call it *"Moma_paper"*

## Visual and Source Mode

When working in a Quarto environment the user can decide if they wish to work in a visual or source code-based layout.
The visual layout offers an easy to navigate environment similar to the layout of programs like MSWord. The Markdown specific code chunks are hidden as to not confuse the user.
The source layout lacks the visual interface but includes the underlying markdown code of the document.

Neither of the two environments are inherently better then the other. 
We will be working with both the source and the visual layout of Quarto. You will be shown the correct ways of selecting the needed options in the visual interface and how to write the needed code in the source code of the document.

::: callout

You can easily switch between the two editing modes by right clicking on your screen and selecting "Edit in Visual/Source Mode". This will instantly switch you over. 
In this lesson we will continue to work with Source Mode.

<img style="display: block; margin: auto;" src="images/gettingstarted_03.png" width="350">

:::

## Rendering Your document

To render your document and see its final look, you need to click the "Preview" Button on the top right side of the screen:
<img style="display: block; margin: auto;" src="images/gettingstarted_04.png">

Alternatively you can use Ctrl+Shift+K.

This will have two effects:
1. It will create a new file in your "Art_distribution_paper" folder, corresponding to your chosen format.
   
    <img style="display: block; margin: auto;" src="images/gettingstarted_06.png" width="150">
   
3. It will split your screen and show you your preview on the right side of VSCode.
   
   <img style="display: block; margin: auto;" src="images/gettingstarted_05.png" width="550">

::: challenge
### Exercise:
Create a new folder called "Quarto_lesson" and open it in VSCode. Open a new Quarto document in VSCode and save it in your newly created folder.

:::
