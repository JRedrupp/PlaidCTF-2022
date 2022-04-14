# PlaidCTF-2022 - flagsong

misc
Sing, O Muse, of the flage of Achilles... Required reading: https://en.wikipedia.org/wiki/X-SAMPA Note: the flag is NOT in `PCTF{...}` format.

Handout - https://plaidctf.com/files/flagsong.7854c4382578b0eb4ce9acb7384cc4ec26819b09c488538676c7bd671b563999.tgz


## Wikipedia
Reading the wiki its all about Extended Speech Assessment Methods Phonetic Alphabet (X-SAMPA). 

SAMPA was devised as a hack to work around the inability of text encodings to represent IPA symbols.

This section may come in use:
https://en.wikipedia.org/wiki/X-SAMPA#Charts

## The ZIP
Looking at the handout it is a Tar in a Zip - lets decompress it all.

Unzipping it all i get:
- README
- generate.py
- audio clip
- .rar File

The [README](flagsong_archive/README) states:

	install Violet Aura Split VCCV.rar in OpenUtau
	run generate.py to generate song.ustx
	open song.ustx in OpenUtau and export song-01.wav
	
	(Violet Aura Split VCCV.rar from https://utau.fandom.com/wiki/Violet_Aura)

## The Python
Here I see the set the flag:
`assert(set(vowels+consonants) == set(FLAG))`
So I know the flag contains the following:
```python
# X-SAMPA
vowels = '3AIOao{}'
consonants = '45DGLNSTfglprw'
dummy_vowel = '@'
dummy_consonant = 'h'

assert(set(vowels+consonants) == set(FLAG))
assert(len(FLAG) == 29)
```

## Conclusion
I wasn't able to reverse engineer the script - Will Keep an eye out for the writeups