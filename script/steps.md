Intro slide

TOC slide

cto slide

vis slide

# Georgetown ANNIS

Login

Hide the toolbar

About ANNIS

Report Problem button

Query window

Export result

Frequency Analysis button

History

List of corpora

Select corpora

information button
	Corpus metadata
	Document metadata

	Annotation layers
	Example -> RUN
	Share button

Corpus list: Full Text

Full Text

Info button

Main area

Search results

List of example queries

Tutorial
	Menu

http://corpling.uis.georgetown.edu/gum/

---

AQL slide

SIMPLE Q 1 slide

GUM corpus:

	POS="NN"

	No. of results

	Hover over annotation value

	View different visualizations

	Share the query

	Share a result

Shenoute.Fox:

	POS="V"

	Syntax dependencies

	Analytic view

REGEX slide

GUM corpus:

	pos=/VV.*/ (followed by zero or more characters)

SIMPLE Q 2 slide

Tutorial:

	List of all operators

	direct precedence operator

GUM corpus:

	pos="NN" & pos=/VV.*/

	error message

	pos="NN" & pos=/VV.*/ & #1 . #2

	no error message

	pos="NN" & 
	pos=/VV.*/ & 
	#1 . #2

	pos="NN" . pos=/VV.*/

	RUN QUERY

	Frequency analysis

	Switch between linear and logarithmic

COMPLEX Q slide

	s_type=‎"decl‎" & 
	entity=‎"abstract‎" &
	penn_pos=‎"PRP‎" &

	#1 _i_ #2 &
	#2 _=_ #3

	‎/language‎/ & 
	‎"codes‎" &
	#1 _i_ #4 &
	#1 _i_ #5 &
	#4 . #5

	/language‎/ & 
	‎"codes‎" &
	#1 _i_ #4 &
	#1 _i_ #5

	cat="PP" > cat="NP"

	cat="PP" > pos="RB"

	cat=‎"PP‎" & 
	pos=‎"RB‎" &
	#1 > #2 &
	#1 >* cat=‎"PP‎"

	cat=‎"PP‎" & 
	pos=‎"RB‎" &
	#1 > #2 &
	#1 >* cat=‎"PP‎" &
	cat=‎"ROOT‎" >* #1

	entity=‎"person‎" &
	entity!=‎"person‎" &

	#1 ->coref #2

	: Malaysia's + reference(grid)

https://hu.berlin/annis

	Filter: "dia"

	dialogie.demo

	utterance0 _o_ utterance1

	play video

BEST PRACTICE slide

deutschdiachrondigital.de

	Annotationsebenen

	pos
	lemma
	edition

ANNIS

	Select all subcorpora

	pos=‎"APPR‎" &

	pos=‎/D.+‎/ &

	#1 . #2

	edition &
	lemma & 
	lemma &

	#3 _o_ #1 &
	#3 _o_ #2 &

	#4 _=_ #1 &
	#5 _=_ #2

	frequency analysis

	zen

https://github.com/korpling/ANNIS

	Issues

	Create new

THANKS slide


