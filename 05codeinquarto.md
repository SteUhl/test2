---
title: "Creating and implementing code for visualisations"
teaching: 0
exercises: 2
---

::: questions 

- How do you implement code in Quarto? 
- How to use code to create visualisations and graphs?
- How do you annotate visualisations?
  
:::

::: objectives

- Implement Python, Mermaid and Graphviz code in your Quarto document.
- Create Visualisations of Python code using plotly.
- Create a barchart in Quarto using Mermaid.
- Create a flowchart in Quarto using Graphviz.
- Enrich your generated Visualisations by adding format and information in comments.

:::

Quarto can be used to both show and render code in a newly created document. One can basically program directly in quarto, using ones preferred coding language, and have the data rendered directly in the pdf or html document.
In order to do so you need to simply insert your code into the document.
In this lesson we will mostly implement python code, as well as several integrated coding languages.

::: callout
### Note:
By default, code inserted via Markdown will be shown as code blocks in the rendered document. If you want to use collapsable or hidden code blocks in your renders, simply add 'code-fold: true' to your YAML section.

One can not only insert code into one’s documents, but also directly visualize it in order to create illustrations based on the inserted code. 
This can be done in a variety of ways, such as using already integrated programming languages like mermaid, or by importing and using extensions like plotly in Python code cells.
:::


## Using Mermaid:

One of the coding languages already integrated in Quarto is Mermaid. 
Mermaid is a simple, text-based diagramming and visualization language that lets you create flowcharts, sequence diagrams, Gantt charts, class diagrams, and more using plain text.
It uses a very simple text-based programming language.
To make the work with Mermaid easy, you can use one of several web-based Mermaid editors. These allow you to create your graphs visually and copy the underlying code. You can then paste this code into your Quarto document.
One of these Website is [Mermaid.live](https://mermaid.live/).

In order to use Mermaid in your Quarto document, simply create a mermaid code block and insert your code.
An empty mermaid code block should look like this:
    
    ```{mermaid}
    
    ```


### Using Mermaid to create a piechart :
A commonly used graph, which can be used and implemented to visualize a wide variety of data, is the piechart. It offers an easy and comprehensive form of displaying percentages and relative strength of different aspects of data. 
A bar chart can be easyly implemented into a Quarto document using the implemented Mermaid language. 

For our scientific paper, we can create a pie chart, showing the relative distribution of the eight most used Media in the MOMA, that were created between 1930 and 1934. It is split into eight categories, representing each medium . Each categorie is represented by an indented Key-Value pair, with the titles of each categorie funntioning as the key. The value of each key contains the total number of the relevant media added. 

When rendered the pie chart will not show the numbers used in the code. Instead it will show the percentage of the categorie relevant to the total amount of media, made up pf all eight categories combined.
    
    ```{mermaid}
    pie title Medium Distribution, Top 8 1930-34
        "Lithigraphy" : 320
        "Etching" : 49
        "Pencil on tracing paper" : 589
        "Letterpress" : 225
        "Pencil on paper" : 97
        "Gelatin silver print" : 777
        "Alburnen silver print" : 0
        "Chromogenic print" : 0
    ```
    
The resulting pie chart would look like this in your rendered paper: 
![](https://pad.zdv.net/uploads/38f52583-9659-4eb4-a409-57f8d2fcf3f3.png)



::: challenge
### Exercise 1: Mermaid

Try to create your own pie chart. Try out different numbers of categories and change the associated values to experiment on how the resulting graph will change.
:::

## Using Graphviz

Similar to Mermaid, Graphviz is an integrated coding language, which uses simple text-based descriptions of charts in order to create visualisations.
Where Mermaid is mostly used for common or simple charts and graphs, Graphviz can be used to create more complex forms of visualisations and workflows.
Like with Mermaid, the simplest way to use Graphviz with Quarto is to use a [web based Graphwiz editor](https://edotor.net/) and copy the resulting code into your Quarto document.
To do this we will use another code block, this time using "Dot", which is the internal name for the Graphviz coding language.
A code block for Graphvioz wouzld look like this:

    ```{dot}
    
    ```
    


::: callout
### Creating a flow chart in Graphviz:
One of the possibilities Graphviz offers is the abilitie to quickly create flow charts in your Quarto document. 
As an example we will create a simple and small flow chart showing the process of coding in Quarto:
The code is split into 4 sections:
The first section is made out of the name of the graph. It creates the "borders" of the remaining code, which is later placed inside the {} brackets.
The second section established the different categories and steps in the flowchart. In our example each of these are made out of an internal name (here for example "code", "works", "try" and "retry"), a label, which establishes what will be written inside the shape, and the form of the shape itself (rectangle, oval, diamond etc.)
The third step establishes the connections between the shapes created in step 2. Here Graphviz uses an easy to understand concept: Connections between different shapes/categories are depicted in the code as arrows. The arrow can be labled with text or flipped by adding the relevant code ( "label =" for text, "dir=back" for a flipped arrow) behind the newly created directional pair.
The forth step {rank = same} is optional and dictates that the three categories "try", "works" and "retry" will be displayed next to each other as they are now on the same rank.

    ```{dot}
    digraph G {
    
      code [
        label = "Try to code in Quarto";
        shape = rect;
      ];
      works [
        label = "You win!";
        shape = oval;
      ];
      try [
        label = "Did the code work?";
        shape = diamond;
      ];
      retry [
        label = "Change things\nuntil it works.";
        shape = rect;
      ];
    
      code -> try;
      works -> try [ label = "Yes"; dir=back ];
      retry:s -> try:s;
      try -> retry [ label = "No" ];
      {
        rank=same;
        try; works; retry; 
      }
    }
    ```
:::

::: solution
### Here is an example of this Graphviz in your document: 
![](https://pad.zdv.net/uploads/ba70f6c0-391d-4ab5-b503-512cc2894344.png)

:::


::: challenge
### Exercise 2: Graphviz

Try to create your own flow chart. Try out different numbers of categories and change the connections and directions to experiment on how the resulting flow chart will change.
:::

## Adding information

When implementing visualisations, it is always important to add relevant information in form of titles, descriptions etc to the chart.
This can be done by inserting the relevant information into the relevant code chunk in form of comments.

::: callout
Here one can use the same commands that are also used for the sizing and descriptions of pictures and illustrations. An overview of the possibilities can be found [here](https://quarto.org/docs/authoring/figures.html)
:::

For our Example we, will now try to add some additional informations to our Mermaid pie chart:
First we will give it an actual internal name. This can be done by adding the Key-Value pair "label: 'selected name'" as a comment to your code. In order to keep it simple we just choose "Illustration 1"
Then we add a caption for our illustration.  Here we also use a Key-Value pair, this time with the Key "fig-cap". This will create a caption for our illiustration. 
lastly we want to limit how wide our newly created graph will be when displayed. This can be done by adding a third Key-Value pair, this time with the "fig-width" key.

    ```{mermaid}
    
    pie title Medium Distribution, Top 8 1930-34
        "Lithigraphy" : 320
        "Etching" : 49
        "Pencil on tracing paper" : 589
        "Letterpress" : 225
        "Pencil on paper" : 97
        "Gelatin silver print" : 777
        "Alburnen silver print" : 0
        "Chromogenic print" : 0
    %%| label: Illustration 1
    %%| fig-cap: "Medium Distribution, Top 8 1930-34"
    %%| fig-width: 6.5
    ```

## A quick forey into Python:
Various python extensions can be used to plot and illustrate data in Quarto. Doing so will poste no difference to doing this in a pure Python environment.
The steps needed to be performed to create and implement a wide variety of illustrations and graphs in Python are explained in the Carpenty Lesson [Python101](https://hermes-dkz.github.io/python_101_humanities/). 
Step 4 of the episode "Analyzing Tabular Data" concerns itself with the visualisation of tabular data. 

::: caution
The intricacies of creating useful charts and visualisations using various Python libraries would be too much to discuss in this lesson. We would encourage you to visit our lesson Python101 in order to learn more about this.
:::

You simply need to insert the following part into your Quarto document in order to insert your code:

    ```{python}
    
    ```

If we want to insert a Python based carchart into our paper we can actually use some of the code used in the Python101 course for our paper. In the couse, a comprehensive database of artworks exibited in the MOMA is used and visualised in various form. 
We can use one of the code chunks used, and modify it for our puposes.
As Quarto is able to read, render and calculate Python code, you can be creative and use all forms of coding used when writing Python code as a stand alone program.
The result could look something like this:

    ```{Python}
    import plotly.express as px
    import pandas as pd
    
    data_path= 'https://raw.githubusercontent.com/HERMES-DKZ/Python_101_humanities/main/episodes/data/moma_artworks.csv'
    moma_df= pd.read_csv(data_path)
    
    df = moma_df.copy()
    df['Date'] = pd.to_numeric(df['Date'], errors='coerce')
    
    top_media = df['Medium'].value_counts().nlargest(8).index
    medium_df = df[df['Medium'].isin(top_media)]
    
    fig = px.histogram(medium_df, x='Date', color='Medium',
                       nbins=50,
                       title='Trends in Medium Usage Over Time: the Top 8 Media')
    
    fig.update_xaxes(title_text='Year')
    fig.update_yaxes(title_text='Number of Artworks')
    
    fig.show()
    ```

Using the Plotly library, the python code is now loaded into our quarto document and will be shown in our rendred document as a barchart.

Using this Code chuck in VSCode could look like the following example:
![](https://pad.zdv.net/uploads/1aaad49a-e618-486d-b63c-b368b59a3ce8.png)


::: caution
### Caution!
Not all forms of visualisation work in every format. In this example Plotly only works in html formats, not in pdf or similar formats.
:::


::: caution
### Caution:

Every Coding language has a different way of creating comments. The ones used in this Lesson are the following:

Python: ##|
Mermaid: %%|
Graphviz: //|
:::
