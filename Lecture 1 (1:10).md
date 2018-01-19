# Lecture 1 (1/10)
#Lin177

* Week 1, focus is getting Prolog installed (not coding till next week)
* We are going to start with an overview of Linguistics

- - - -
## What is a Language?
-> can give examples easily
-> but harder to give a general definition
-> We are going to split a language into multiple pieces, model them independently

### For every language we have:
	* Sounds
	* Signs
	* Combinations 
	-> Combinations of signs -> words -> sentences -> whatever

	1. Phonetics 
		* The “gestures” of languages
			* put mouth in a certain position, coordinate air, make a sound
		* The articulation of sound, or the acoustics of a sound
	2. Phonology
		* The perception of sounds…
			* “Pot”
				* Starts with voiceless articulation of “Puh” 
				* Needs a certain amount of air puff, otherwise people will perceive it as “Bot” 
					* Perception of sounds depends on this kind of Phonology, spelling isn’t enough
	3. Morphology
		* the Study of words
		* more than just grouping sounds:
			* “Add an ’s’ to a group to make it plural”
				* Pot + s -> add s sound
				* Pan + s -> add z sound
				* Church + s -> add es sound
			-> So it’s more complicated. Can’t simply put an s on something.
	4. Syntax
		* Word order
			* There’s all kinds of patterns: Subject-Verb-Object is an example
			* Is there a principled way of writing a sentence in correct order?
	3. Semantic
		* Word meaning
			* All kinds of complications:
				* Difference between “chair” and “stool”?
				* There’s some precise difference between chair and stool that people agree on, but hard to define.
		* Hardest one to deal with in Computational Linguistics, but there is a way to do it. We’ll get there later. 

-> So “What is a language?” is too hard, but we can discuss “What are the morphological properties of a language?”
	* Note: Every language is going to have some set of sounds, but every language is different
		* So every property in a given language is arbitrarily different. 
	* However, there are some shared elements:
		* Almost all languages have vowels, but that depends on how you look at it 
		 I don’t really know what he’s talking about right now, but I don’t think it matters.

## Why are we using Prolog?
	* Closer to what we think the mind is doing. Not procedural.
	* Obviously, you wouldn’t write Siri in Prolog, but we’re able to focus more on the Linguistics this way.
	* We are going to try to come up with a “grammar” to model a language…

## Goals of our Grammar
	1. Explicit
		* set of specific rules
		* Enough details that our Prolog declarations create a functioning program
	2. Accuracy 
		* Needs to be recognizable as a real language
		* There will come a time where we have our rules all set up and the program spits out garbage. Caused by either too many or not enough rules. 
	3. Principled-ness
		* We want to do what we think the mind is doing.
		* We don’t want to take shortcuts 
			* Antithetical to regular programming where we optimize to get the same result faster
		* Don’t just make a series of hacky rules to generate the outcome we want
	4. Simplicity
		* We want the solution to be as simple as possible
		* But needs to be principled! 

## Introduction to Prolog
	* We are not giving Prolog commands to execute
	* We are giving Prolog a set of facts, some proceudure finds solutions based on facts we give it
``` testword.swipl
word(blah). %blah is a word
word(X-blah) :- word(X). %something is a word if followed by blah
```

``` swipl
?- ['testword.swipl'].
true. 
?- word(Y). % give me all solutions that are a word
blah ; 
blah-blah ;
blah-blah-blah ;
...
```

- - - -
-> He’s explaining `spanish.swipl` (which is posted online)





