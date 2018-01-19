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
```• CONSONANTIC: This property is true of sounds articulated with some degree of obstruction in the oral cavity; it therefore applies to all of the consonants (but none of the vowels) of Section 2 above.
```
```• SONORANT: This property applies to sounds which are naturally (or normally, or most effortlessly) voiced (see below). In English, the class of sonorants includes nothing but the vowels, the nasals (m, n, ŋ), the lateral (l), the approximant (ɹ), and the glides (j, w).
```
```
• NASAL: This property holds only of sounds which resonate in the nasal (rather than the oral) cavity. Consequently, in English, it applies only to m, n, and ŋ.
```
```
• VOICED: This property characterizes sounds that involve vibrating vocal folds (the lip-like organs in the larynx, which is commonly known as Adam's apple). Thus, in English, it applies only to b, d, g, v, ð, z, ʒ, ǰ— as well as to all sonorants.
```
```• CONTINUANT: This property is true of phones throughout the articula- tion of which the air flows uninterrupted. In English it is true of all phones other than the stops (p, b, t, d, k, g, m, n, ŋ) and the affricates (č, ǰ).
	* We can extend past some length
	* Anything you can control the length of
```
```• LABIAL: This property applies only to the phones that involve the lips. It therefore describes, in English, the bilabials (p, b, m), the labiodentals (f, v), the lip-rounded glide (w), and nothing else.
```
```• ALVEOLAR: This property holds of phones which are articulated at the alveolar ridge. Thus, in English, it holds only of t, d, n, s, z, l, and ɹ.6 I am indebted to my colleague Orhan Orgun for help with deciding on this set of properties.
```
```• PALATAL: This property characterizes the phones articulated at the pal- ate (or roof of the mouth). In English it holds of the palatals proper (ʃ, ʒ, č, ǰ, j) and the alveopalatal (ɹ), which is both alveolar and palatal.
```
-> Hard to recognize, probably should memorize sounds as palatal
```• ANTERIOR: This property is true of phones articulated with an obstruc- tion at the alveolar ridge or before. In English it therefore applies to all labial (p, b, m, f, v) and alveolar (t, d, n, s, z, l, ɹ) consonantic phones.
```

```• VELAR: This property applies to sounds articulated at the velum (or soft palate)—the veil like continuation of the palate. In English, these would be k, g, ŋ, and w.
```
```• CORONAL: This property holds of phones involving the tip (or crown) of the tongue. Thus, in English, it is true of the interdentals (θ, ð), the al- veolars (t, d, n, s, z, l, ɹ), and the palatals (ʃ, ʒ, č, ǰ, j, ɹ).
```

```• SIBILANT: This property characterizes ‘whistling’ (or s-like) phones. In English, these phones are only s, z, ʃ, ʒ, č, ǰ.
```

## Vowel Properties
```• HIGH: This property is true of vowels articulated with the tongue in a relatively high position. Consequently, it applies in English only to i, ɪ, u, and ʊ.
```
```• MID: This property applies to vowels articulated with the tongue at middle height. In English, this describes only e, o, ə, and ʌ.
```
```• LOW: This property holds of vowels articulated with the tongue in a relatively low position. In English, this property is extremely discrimi- nating, as it is true only of two phones: a and æ.
```


```• BACK: This property characterizes vowels articulated with the tongue in a relatively back position. In English, this describes only u, ʊ, o, and a.
```
```• CENTRAL: This property is true of vowels articulated with the tongue at mid-back (or mid-front) position. In English, this property, too, is ex- tremely discriminating, as it is true only of two phones: ə and ʌ.
```


```• TENSED: This property applies to vowels articulated with relatively high muscular tension. Again, only two phones satisfy this property in Eng- lish. They are i and u.
```
```• STRESSED: This property holds of vowels that may serve as syllabic nuclei. In English they are all except ə.
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






