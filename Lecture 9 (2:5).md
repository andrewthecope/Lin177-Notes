# Lecture 9 (2/5)
#Lin177

Coding Challenge in class. Turn in on HW4 for extra points (or something).
I, being the kiss-ass I am, showed off my program in class, and he said it was basically correct:
```Prolog
word(make, [verb]).
word(made, [verb]).
word(cat, [noun]).
word(tend, [noun]).
word(done, [verb]).
prefix(Word, Prefixed) :- 
  word(Word, [verb]),
  atom_concat(pre, Word, Prefixed).
```

