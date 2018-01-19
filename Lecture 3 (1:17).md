# Lecture 3 (1/17) 
#Lin177

* Spanish Program diagrammed out on page 36 of the textbook
-> You can rewrite this as rules and postulates
	* eva is Postulate 1 (P1)
	* Transitive very is Postulate 6 (P6)
* This is shown on page 38 of the textbook
* You end up with the derivational history of the program in simple expression: `R4(P1,R3(P6,R2(P2)))`

- - - -
* First Homework has a problem very similar to this
* Homework will go up tomorrow
* Due Monday
* Mostly material from chapter 1, with one question about Phentics that’s easy
- - - -

# Chapter 2: Phonetics (the sounds themselves)
Every language has unique set of sounds
-> “Phones”
* IPA (international Phonetic alphabet) tries to give a symbol to all human sounds
* Hundreds of symbols

### How do you split up these sounds?
* Look at anatomical differences in producing sounds

#### Constances 
* Voicing 
* Place 
* Manner

 Complete or partial closure
* “puh” closes completely
* “shhh” obsctructs air to make noise

#### Vowels
* height
* frontness
* tense/lax
	* Sheet (tense)
	* Shit (lax)

``` properties.swipl
# Defines set of properties (explained on page 58 in text)
```

The properties we have in mind are the following:
## Consonant Properties
```
```
```
```
```
• NASAL: This property holds only of sounds which resonate in the nasal (rather than the oral) cavity. Consequently, in English, it applies only to m, n, and ŋ.
```
```
• VOICED: This property characterizes sounds that involve vibrating vocal folds (the lip-like organs in the larynx, which is commonly known as Adam's apple). Thus, in English, it applies only to b, d, g, v, ð, z, ʒ, ǰ— as well as to all sonorants.
```
```
	* We can extend past some length
	* Anything you can control the length of
```
```
```
```
```
```
```
-> Hard to recognize, probably should memorize sounds as palatal
```
```

```
```
```
```

```
```

## Vowel Properties
```
```
```
```
```
```


```
```
```
```


```
```
```
```


## Properties.swipl
* first call in phone.swipl 
	* gives it all the possible symbols 
	* need to use unicode values throughout
* cns/1 rules are consonantic
* voi/1 rules are voices
* cnt/1
Etc. etc.

-> Let’s run it:
```Prolog 
?- ['properties.swipl'].
true
?- phone(A).
A = p ;
A = b ;
etc. etc.

?- cnt(A).
A = f ;
A = v ;
etc. etc.

?- vel(A), snt(A). # a sound that has both of these properties
A = w ;
etc.

?- mid(A), bck(A).
A = o ; 
false.
```

-> That’s pretty much all we need for the phonetics
	* the symbols and the properties of the sounds

## Syllables
Some things to mention before we continue
	* one of the most important things in Phonology is the syllable 
	* Syllable structure is arbitrary to a language

### Parts of a Syllable
* Onset
* Nucleus (rime)
	* the most sonorant part of the syllable
	* any sound with sonorant property
* Coda (rime)

EX: “ton”
	* onset: ’t’
	* nucleus: ^ (uh)
	* Coda: ’n’

EX: “tahn”
	* pronounceable, but not an actual word
	* add complex onset, ‘tr’
		* tron, that’s a word
	* add complex coda: ’ns’
		* trons





