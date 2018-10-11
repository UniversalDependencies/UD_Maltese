# Summary
MUDT (Maltese Universal Dependencies Treebank) is a manually annotated treebank of Maltese, a Semitic language of Malta descended from North African Arabic with a significant amount of Italo-Romance influence.
MUDT was designed as a balanced corpus with four major genres (see Splitting below) represented roughly equally.

# Introduction
## Origin
This treebank is the product of the PhD thesis *Constituent order in Maltese: A quantitative analysis* by Slavomír Čéplö. The text (see References) contains a detailed description of the annotation decisions and composition of the treebank.
The treebank was originally produced in accordance with UDv1, this version is brought up to the UDv2.3 standard.

## Splitting
MUDT contains 2074 sentences and 44,162 tokens (both defined orthographically) in the following text types:

| Text type    | Subtype                                 | Sentence count |
|--------------|-----------------------------------------|---------------:|
| newspaper    | news                                    | 239            |
|              | op-eds                                  | 240            |
|              | *Subtotal*                              | *479*          |
| quasi-spoken | newspaper interviews                    | 280            |
|              | parliament: debates and Q&A             | 294            |
|              | *Subtotal*                              | *574*          |
| fiction      | short stories                           | 246            |
|              | novel chapters                          | 251            |
|              | *Subtotal*                              | *497*          |
| non-fiction  | humanities                              | 249            |
|              | science, encyclopedic and instructional | 275            |
|              | *Subtotal*                              | *524*          |
|              |                                         |                |
|              | **Total**                               | **2074**       |

The annotated sentences have been manually split into train, test and dev sets as follows:

| File                           | Sentence count | Token count |
|--------------------------------|---------------:|------------:|
| mt_mudt-ud-train.conllu        | 1671           | 34446       |
| mt_mudt-ud-test.conllu         | 202            | 4930        |
| mt_mudt-ud-dev.conllu          | 201            | 4876        |

# Conversion
The original treebank was annotated according to UDv1, this version was automatically converted to UDv2 as follows:
- UPOS were added by automatic conversion from XPOS using a conversion table
- UDv1-specific relations where only the label was changed were automatically converted to UDv2 relations (e.g. dobj > obj or nmod:advmod > obl)
- for all \*_DEF and DEF tokens, as well as for *b'*, *f'*, *m'*, *s'* and *t'*, SpaceAfter=No was added automatically
- Udapi was used to convert those relations which involved changes in dependency relations (e.g. conj or flat) to UDv2, as well as to add SpaceAfter=No to punctuation
- all ToDo items were checked manually and fixed wherever necessary
- all validation errors were fixed manually

̥̥# To do (status as of 2018-10-11)
- doublecheck the attachment of ADPs to compounds
- doublecheck nmods attached to a non-verbal predicate
- doublecheck SpaceAfter=No in general, for \' and \" and in particular


# Changelog
* 2018-10-04 v1
	* Removed the old version of the Maltese UD treebank, prepared the repository and updated README
* 2018-10-07 
	* Added the files, updated README
* 2018-10-11
	* Added the files converted to UDv2 (see above), updated README

## References
**(Čéplö 2018)** Slavomír Čéplö. (2018) [Constituent order in Maltese: A quantitative analysis](http://www.bulbul.sk/phd/Text/Slavomir_Ceplo-text.pdf). Prague: Charles University.


<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.3
License: CC BY-SA 4.0
Includes text: yes
Genre: news legal nonfiction fiction wiki
Lemmas: not available
UPOS: converted from manual
XPOS: manual native
Features: not available
Relations: manual native
Contributors: Čéplö, Slavomír; Zeman, Daniel
Contributing: here
Contact: bulbul@bulbul.sk
===============================================================================
</pre>
