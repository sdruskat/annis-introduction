# Introduction

Welcome to this video, which will introduce you to ANNIS, the analysis and visualization platform for linguistic corpora.

In this video, we will explain what ANNIS is, and how to use it.

We will not cover how to install it, or how to get your data into ANNIS, but we will provide links to the relevant documentation.

## ANNIS as part of corpus-tools.org

ANNIS has been, and is, developed at the department of German Studies and Linguistics at Humboldt-Universität zu Berlin.
It is an open source software that runs in web browsers, and can be installed either on a server, or locally on your computer.
In this tutorial we will use an instance of ANNIS that is run on a server at Georgetown University.

ANNIS is part of the corpus-tools.org software family.
corpus-tools.org also includes tools to convert between different corpus formats.
We are also working on a corpus annotation software that integrates seamlessly with ANNIS.
If you want to know more about corpus-tools.org, please visit the website at corpus-tools.org.

XXX BELOW XXX If you use ANNIS in your work, please cite it! We will provide the relevant reference later on in the video.

ANNIS is a search tool for linguistic corpora, which you can use to search in annotated corpora across all levels, or layers.

The search supports different annotation concepts, such as token annotation (for example POS tags), span annotations, pointers and trees.
ANNIS also includes a variety of visualizations for corpus data:

- A key-word in context view
- constituent syntax trees
- grids for token and span annotations
- token alignment between parallel texts
- discourse annotations with interactive coreference links
- dependency trees
- linked audio and video display
- PDF pages, or whole files
- rhetorical structure theory annotations
- and customizable HTML visualizations


To search in ANNIS, you use a query language called the Annis Query Language, or AQL.
AQL is similar to a lot of other corpus query languages.
AQL is based on key-value pairs, and regular expressions.
It is powerful, and can be used to construct complex queries for linguistic phenomena, but also supports simpler searches, such as free text search.

So how can you actually use ANNIS?

# Using ANNIS

## A tour of the ANNIS GUI

We will start with a tour of the user interface of ANNIS.
If you don't have access to a specific ANNIS installation that you want to use, you can browse to the ANNIS installation at Georgetown University.
To do so, open your web browser, and type the following URL in the address bar: https://tinyurl.com/georgetown-annis.

This will open the ANNIS user interface in your browser.

In the upper right corner, you see a login button.
Access to corpora can be restricted in the system, but for this video, we will use a freely available corpus.
If you want to learn about access restrictions or in ANNIS, or on how to set up and run your own ANNIS instance, please refer to the documentation at http://korpling.github.io/ANNIS/.

In the upper left corner, you have a button that will hide the left tool bar.
Clicking the About ANNIS button displays information on the version of ANNIS you are using.
And if you ever encounter a problem in ANNIS, you can use the Report Problem button to send us a message about it.

On the left hand side is the query window, which is used to enter AQL queries.
It also features the controls to export a search result, or run a frequency analysis.
You can also access your own search history from the history drop down menu.

Below the query window, there is a list of available corpora, as well as a tab where you can set search options, such as how results should be presented.
It is important to note, that a search query always runs on all selected corpora in the corpus list. 
This way, you can search for linguistic phenomena across more than one corpus.
You can select the corpora to search by clicking on the entries in the list, and using the Shift or Control button on your keyboard to select ranges.

The corpus list also contains some metadata about the corpora that are available, such as the number of texts contained in the corpus, and the number of tokens.

Clicking on the information button for a corpus opens a window with more detailed metadata, both for the entire corpus, and for each document in the corpus.
It also lists all available annotation layers, with an example query for each annotation layer, and a URL link for sharing the example.

By the way, you can not only share these example queries, but also actual queries you have used, and even single results.
But more about this later.

Next to the information button, you find a button which opens an overview of the documents in the corpus.
For each document, you can open a view of the full text of this document.
You can also view the document-specific metadata by using the information button in the document overview.

As you have already seen, the main area of the ANNIS window is used to display search results.
It also displays a list of example queries for each corpus, which you can try out.
And finally, the user documentation for ANNIS can be displayed in ANNIS itself, so if you want to re-visit any of the topics you have learned about in this video, or want to investigate further functionality, such as the advanced features of the ANNIS Query Language, the tutorial is a good place to start.
It includes further details about the ANNIS user interface, for example.
The tutorial also features details about how to search for specific linguistic phenomena.
And finally, the tutorial contains a very helpful list of AQL operators.

But now, let's get started with some actual queries in ANNIS.
For this presentation, we will XXX primarily XXX use the Georgetown University Multilayer Corpus.
You can find more information about the corpus on its website at http://corpling.uis.georgetown.edu/gum/.

## Usage

### AQL

To get started, we will first look at some of the features of the ANNIS Query Language, or AQL.

AQL works with key value pairs, and relations between key value pairs.
A very simple example for an AQL query using a key value pair is a search for a specific part-of-speech tag.
Using the GUM corpus, we search for POS="NN".
Running this query yields 14165 matches in 126 documents.
The results are displayed in the main part of the window.
If you hover over an annotation value, the name of that annotation is displayed in a tool-tip.
From here, you can view the different available visualizations of each result, as configured.
You can also share the query from this view, or a single result in a specific visualization.

This isn't a very interesting search, but it gives you an idea about how different visualizations may work.
XXX video XXX

To show you an example of a customized visualization, let's run a similar query on a Coptic corpus.
pos="V" shenoute.fox - syntax dependencies + analytic view (custom HTML)

We have searched for a fixed string as the value in a key value pair.
But actually, values can be regular expressions.
To give you a simple example, you can search for all POS tags that start with a double V, that are followed by zero or more characters.
In AQL, regular expressions are written between single slashes.
GUM pos=/VV.*/

We have mentioned earlier that AQL can also search for relations between key value pairs.
Let's have a look at this now.
If, for example, you want to search for a noun with a specific POS tag that is directly followed by a verb with a POS tag starting with a double "V",
you can search for this relation by using a specific operator.
Remember, you can always look up the complete list of operators in the help window.
In this case, we are looking for the first operator in the list, the direct precedence operator.

To construct our search query, we will therefore search for both key value pairs we are looking for, and connect them with the direct precedence operator.
In AQL, key value pairs are linked up in a query with the ampersand.
pos="NN" & pos=/VV.*/
Just using this query, however, results in an error message, which tells us, that we need to use an operator.
In order to do this, we can refer to our two key value pairs within the query - once they are defined - through their position in the query.
This is done with a hash and a number.
At the same time, we use the operator we have chosen, the direct precedence operator.
pos="NN" & pos=/VV.*/ & #1 . #2
The error message disappears, and we have now constructed a valid AQL query.

Before we run this query, let's have a look at it again.
In natural language, the query reads like this:
"Search for a key value pair number 1 which is a pos tag that is exactly NN, and a key value pair number 2 which is a pos tag that starts with two Vs which are followed by zero or more characters, and search for all occurrences of number 1 and number 2 in the corpus where number 1 is directly followed by number 2."

At the moment, this relatively simple query is already a little too hard to read, so here are two tips to make it more readable.
Firstly, ANNIS doesn't care if you type out a query over more than one line, so we can make the query look a lot nicer by just adding a line break after each ampersand.
And the query still runs.

Additionally, for shorter queries such as this, we can use a short form of AQL by simply replacing the ampersand that connects the two key value pairs with the operator itself.
This way, we don't have to type out the third line in the query which connects the two.

Once we have run our query, we can get a frequency analysis of our query.
In our simple example, this can help us find out the distribution of the different verbal parts-of-speech that are directly preceded by a Common Noun.
To do this, we simply click on the Frequency Analysis button that is available from the drop-down menu reading "More".
The parameters of the frequency analysis are already pre-filled with the key value pairs used in our query.
Running the analysis gives us a tabular and diagrammatic overview of the information we were looking for.
For the diagram, we can switch between linear and logarithmic views.

Additionally, we can include metadata in the frequency analysis, which can help us find out more about how language use, for example, differs between speakers or sources.
For our arbitrary example we create a new analysis and add the meta annotation "author" to the analysis, and then run it.

Using the AQL operators, we can construct more complex queries, for example for searching across different layers in a corpus.

We will demonstrate this by using different operators to search for annotations on different layers that cover the same or parts of the same text.

In the GUM corpus, we can search for declarative sentences, which include an abstract entity that is referred to with a personal pronoun.
To do this, we need three key value pairs on different levels, that is, the sentence type s_type="decl", the entity annotation "abstract", and the Penn POS tag PRP.
We will construct the query as follows:
First, we declare the key value pairs, each on its own line
s_type=‎"decl‎" & entity=‎"abstract‎" &
penn_pos=‎"PRP‎" &

Then, we define the relations between the key value pairs, such that
the sentence shall include the entity, for which we use the inclusion operator.
And we use the identical coverage operator to define that the entity and the pronoun must cover exactly the same tokens.

#1 _i_ #2 &
#2 _=_ #3

To make things more fun, we add another constraint, namely that the declarative sentence should also include the phrase "language codes", with language either capitalized or not.
To do this, we introduce two more key value pairs.
This time, because we will search for actual word form occurrences, we don't have to specify a key, but can simply state the words we're looking for in double quotes.
Additionally, we need to state that the sentence should include them, so we will use the inclusion operator again, for both words.
Also, we need to specify that "codes" should directly follow "language", so we need to use the direct precedence operator.

s_type=‎"decl‎" & entity=‎"abstract‎" &
penn_pos=‎"PRP‎" &
#1 _i_ #2 &
#2 _=_ #3 &
‎/language‎/ & 
‎"codes‎" &
#1 _i_ #4 &
#1 _i_ #5 &
#4 . #5

If we leave out the direct precedence operator, we expect to yield the same result, and indeed we do, but another result, catching the second occurrence of "language" in the sentence, is also found.

This example is arbitrary, but shows how search across different layers may work in ANNIS.

With AQL, you can also search for other linguistic entities than just text tokens and spans.
For example, we can search for syntax trees.

If we wanted to find a tree in which a nominal phrase is directly dominated by a prepositional phrase, for example, you do this by searching for the two categories, and defining the relation to be found with the direct dominance operator.
cat="PP" > cat="NP"

This also works across layers, for example, to find prepositional phrases directly dominating an adverb, we can combine the cat annotation with a POS tag:
cat="PP" > pos="RB".

We can also search for more complex trees, for example, by searching for another prepositional phrase, which shall be dominated indirectly by the first one.
To do this, we use the indirect dominance operator:

cat=‎"PP‎" & 
pos=‎"RB‎" &
#1 > #2 &
#1 >* cat=‎"PP‎"

And to make sure we're always shown the complete tree, we include the root element as indirectly dominating the first prepositional phrase as well.

cat=‎"PP‎" & 
pos=‎"RB‎" &
#1 > #2 &
#1 >* cat=‎"PP‎" &
cat=‎"ROOT‎" >* #1

Note the mixture of the long and the short form of AQL to yield a readable query.

ANNIS can also search for other types of relations than the dominance relations used in syntax trees, for example, pointing relations in coreference annotations.

To search for an occurrence where a person is said to be coreferent with an antecedent non-person, we can search for a coreference relation between the two entities.
The following query also introduces inequality assignment of values to keys.
First, we define the two entities:

entity=‎"person‎" &
entity!=‎"person‎" &

And then we link them with a relation of the coref type, denoting coreference relations.

entity=‎"person‎" &
entity!=‎"person‎" &
#1 ->coref #2

This yields some interesting examples of bridging, where for example an organization implies the existence of its parts.

This concludes our introduction to the basic concepts in AQL.

Feel free to go through the tutorial and the list of operators, and try them out on any of the available corpora.

## Contribute to ANNIS

### ANNIS on GitHub

ANNIS is open source under the permissive Apache License Version 2.
Feel free to have a look at the source code, and please contribute if you can.
The source code is available on GitHub at https://github.com/korpling/annis.

### File bug reports and feaure requests

A very helpful contribution would be to report any bugs you may find on GitHub. To do so, simply go to the source code page, and to the issue tracker there, and file a new issue, or suggest a new feature.

If you use ANNIS in your work, please cite it XXX

### Thank you

Thank you for your attention.

We would like to acknowledge funding for ANNIS from XXX

# Credits