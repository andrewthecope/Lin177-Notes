# Lecture 5 (1/24)
#Lin177

## Homework 1 Answers
1. Any recursive word
2. Bear (n.), bear (v.)
Lawyer, attorney / car, automobile
3. Best way to approach that is to edit the spanish program into the japanese program
4. consult japanese.swipl and spanish.swipl
```
spanishjapanese(A,B) :-
	spanish(A,_,English,_),
	japanese(B,_,English,_).
```

- - - -
## Homework 2
* in back of book: page 331, there’s a list of prolog tutorials
* Highly recommended that you do one of these

1. structural  description: 
derivational history:
signature: 
draw it out
2. create `trilingual/1` rule
need some kind of predicate to verify a given person
3. 
4. eleven english words. express the parts of speech
Not terribly easy, for things like too
we would want to use this information to make valid sentences
5. must be principled

- - - -
## Syllable.swipl
* defines onset, rhyme. What makes a valid english syllable
```
?- findall(X, syllable(X), Y).
-> giant list of syllables
-> number of syllables > number of words

?- findall(X,syllable(X), Y), length(Y, Length).
Length = 20608
```

# Syllables in Japanese
onset: cns
nucleus: not(cns(X)). (any vowel)
coda: nas(X) (only a nasal)
```
:- ['properties.swipl'].

onset([A]) :-
	phone(A), cns(A). %any sound that is a consonant
onset([]).

nucleus([A]) :-
	phone(A), not(cns(A)).

nucleus([A, B]) :-
	nucleus(A),
	nucleus(B). % two nuclei in sequence is an allowable nucleus
% NOTE: This causes infinite recursion. This will be adressed on Friday

coda([A]) :-
	phone(A), nas(A).

coda([]).

rime(A) :-
	nucleus(B),
	coda(C),
	append(B, C, A).

syllable(A) :-
	onset(B),
	rime(C),
	append(B,C,A).
```











