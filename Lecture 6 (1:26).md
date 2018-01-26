# Lecture 6 (1/26)
#Lin177

Recall issue with infinite nucleus from Lecture 5. 
	* Use Length?
		* No, that’s not principled. Language not actually based on magic value like length. Want to model what we think is happening linguistically
```
nucleus([A,B]) :-
	phone(A), not(cns(A)),
	phone(B), not(cns(B)),
	not(A = B).
```

Recall the issue of excluding the ‘err’ sound:
```
onset([A]) :-
	phone(A), cns(A), alv(A), not(pal(A)).

oneset([A]) :-
	phone(A), cns(A), not(alv(A)).
```
	* Not great. It would be better to have one natural class that gives all solutions. But prof is not sure if this is possible given our syllable properties.
	* The problem on the homework is a little easier, presumably…

-> Chapter on phenetics ends on english syllables, and goes into semantics.
- - - -
# Semantics
## The Procedural Definition of Semantics
“The planet closest to the sun” -> Mercury
“The planet Mercury” -> Mercury
-> This meaning is called the **Reference**

Both of these phrases refer to Mercury, but do they mean the same thing? Not necessarily.
	* The method we use to get to the meaning is different
	* The procedure to get to meaning is affected by the current state of the world.
	* So we have to make some sort of distinction or else “The President of the US” would always mean Donald Trump (the horror!)
-> This procedure is called the **Sense**.

* specific entities are given with underlines:
Sid -> _Sid_
Nancy -> _Nancy_
	* In this particular universe, there is only one sid and one nancy
	
* Next, we can add relation between S & N
loves -> (Nancy -> Sid)
	   -> (Sid -> Nancy)

* Given any english sentence, and leaf of the sentence structure, we can evaluate it to a true or false.
“Sid loves Nancy”
 Sid          Sid 
        true 

For each phrase type, there’s a particular thing you are looking for:
	* Nouns: looking for entities
	* Verbs: looking for relations
	* Sentences: looking for T/F
-> See example above
		* You can see how Prolog will be very good at this
		* The way Prolog handles procedure/variable bindings is identical to the way we are relating things in this procedural definition of semantics

## Expressing References in Prolog
```
Reference :: (Reference is 3+2).
Reference :: (Reference is 1+4).
```
	* Note how it distinguishes the difference between reference and expression.

```
num(0).
num(N) :-
	num(M),
	N is M + 1.
```
	* The set of all positive integers.
	* If you do a `findall`, it’ll find all numbers until it runs out of memory. 
	* In linguistic, we need to do a better job referencing infinite sets. Because lots of things are an infinite set in linguistics
```
Reference :: (findall(A, num(A), Reference)).	
```
	* Can’t evaluate it (because will run out of memory).
	* But we can still express it in a principled way. 
	%: Not exactly sure what the point of this is, but presumably it will come up later… 

