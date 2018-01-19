# Lecture 4 (1/19)
#Lin177

Make sure you can do the following in prolog:
1. Run swipl
2. open a file
3. consult within a file
- - - -
## Homework 1 Intro
All questions adapted from text.
1. Tons of examples to choose from
2. Sound alike and mean different
Mean alike but sound differently
-> actually more difficult
3. See excursive given in the book
	* You’ll see it’s very similar to spanish, but slightly different
	* Modify spanish program, not writing something from scratch
	* similar enough that edits are fine
4. Don’t overthink this. 
	* The solution to 4 is incredibly short
	* presumably translate from spanish to english, then english to japanese
		* Could this be one line?
- - - -

# More stuff about Properties of Phones
* We don’t normally want just one sound in isolation: `phone(X), cns(X)`
	* Gives one at a time
* We want the full set of solutions:
	* “Natural Class”
	* The overlap between different features 
```
findall(
	Variable,
	Conditions we want to be true, // can be more than one in parenthetical block
	Output Variable
)

EX:
?- findall(X, (phone(X), cns(X), ant(X)), Y).
Y = [p, b, m, t, n, f...].
```
You may find that Prolog truncates this output.
To fix this, there is a program called Full Display
`[‘fulldisplay.swipl’]` if it doesn’t work, get new version

```
findall(X), (phone(X), not(cns(X))), Y).
# note the use of not(cns(X)) to select vowels
```

# More About Syllables
* Remember “Strengths” having a complex coda 
* In Japanese, the only possible coda is a nasal, no complex coda allowed
	* Reason for odd syllable arrangement when pronouncing foreign words
	* Spice (english) -> su | spi | su (follows japanese syllabic rules)
	* If you break rules, you have things that are “unpronouceable”

* How many possible syllables are there in English?
	* A Lot! But there are rules that restrict range
	* `tranz` is a syllable
	* Can we have `tlanz`? No!

### Page 64 & 65: Rules of English Syllables

```
R1. The sequence of an onset and a rhyme is a syllable.
```
```
R2. Any consonantic nonnasal phone is an onset (so p, b, t, d, k, g, f, v, θ, ð, s, z, ʃ, ʒ, č, ǰ, j, l, ɹ, j, w, h are all onsets).
```
```
R3. Any nonvelar nasal phone is an onset (so m and n are both onsets).
```
```
R4. Any nonsonorant, noncontinuant, nonpalatal phone followed by an al-
veolar palatal phone is an onset (so pɹ, bɹ, tɹ, dɹ, kɹ, and gɹ are all on-
sets).
```
```
R5. Any nonsonorant, noncontinuant, noncoronal phone followed by a son-
orant, nonnasal, alveolar, nonpalatal phone is an onset (so pl, bl, kl,
and gl are all onsets).
```
```
R6. Any nonsonorant, noncontinuant, nonlabial, nonpalatal phone followed
by a velar continuant phone is an onset (so tw, dw, kw, and gw are all
onsets).
```
```
R7. Any nonvoiced, continuant, labial phone followed by a sonorant con-
tinuant alveolar phone is an onset (so fl and fɹ are both onsets).
```
```
R8. Any nonvoiced, continuant, nonalveolar, coronal phone followed by an
alveolar palatal phone is an onset (so θɹ and ðɹ are both onsets).
```
```
R9. Any nonvoiced, continuant, alveolar phone followed by a consonantic, sonorant, nonnasal, nonpalatal phone is an onset (so sl and sw are both
onsets).
```
```
R10. Any nonvoiced, continuant, alveolar phone followed by a nasal non-
velar phone is an onset (so sm and sn are both onsets).
```
```
R11. Any nonvoiced, continuant, alveolar phone followed by an onset headed by a nonvoiced, noncontinuant, nonpalatal is an onset (so sx is an onset if x is itself an onset–albeit one that begins with p, t, or k).
```
```
R12. The sequence of a nucleus and a coda is a rhyme.
```
```
R13. Any nonconsonantic phone is a nucleus (so i, ɪ, u, ʊ, e, o, ə, ʌ, a and
æ are all nuclei).
```
```
R14. Any mid noncentral phone followed by a consonantic, sonorant,
nonnasal, nonalveolar phone is a nucleus (so ej, ew, oj, and ow are all
nuclei).
```
```
R15. Any low back phone followed by a consonantic, sonorant, non-nasal,
nonalveolar phone is a nucleus (so aj and aw are both nuclei).
```
```
R16. Any nonsonorant phone is a coda (so p, b, t, d, k, g, f, v, θ, ð, s, z, ʃ, ʒ, č, ǰ, j, l, ɹ, and h are all codas).
```
```
R17. Any nasal phone is a coda (so m, n, and ŋ are all codas). R18. Any liquid phone is a coda (so l and ɹ are both codas).
```

-> All of these rules are loaded into `syllable.swipl`
-> He’s going over this now. 








