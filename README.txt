This is the readme_first file for the Galician Dependency Treebank v0.5 (UTF-8).

San Diego, March 17th 2008:

Developer: Paulo Malvar Fernández
email: paulomal@gmail.com


1- Introduction:

This Galician Dependency Treebank has been developed by transliterating and adapting lexically the Portuguese part (Bosque 7.3 by the Floresta sintá(c)tica project) of the CONLL-X 2006, New York City June 8-9 2006.

The original Portuguese Dependency Treebank ws downloaded from:

http://nextens.uvt.nl/~conll/free_data.html

More information about that original Portuguese data can be found at:

http://acdc.linguateca.pt/treebank/info_floresta_English.html

The readme (README.txt) file that comes with the original Portuguese data is also included in this package. Therefore, further information regarding the Portuguese part of the CONLL-X 2006 can be found in it.

2- License

Consistently with the availability of the original Portuguese data, Galician Treebank is released, under the GPLv2 license, as a freely available contribution to the research community.


3- Development preprocessing steps:

The processing steps for development of the Galician version of the Portuguese Dependency Treebank were two:

- Transliteration: The original Portuguese data were transliterated into Galician using port2gal (written in Perl). port2gal original implementation was made by Berto Garcia. However for the development of this Galician Treebank, Pablo Gamallo's version was used. port2gal is freely available at:

http://gramatica.usc.es/~gamallo/

- Lexical adaptation and orthographical correction: Because the transliteration process ouput is not quite Galician, an additional process of lexical adaptation and orthographical correction was necessary.


4- Technical specs:

Version 0.5 of the Galician Dependency Treebank keeps the same syntactic structure of the sentences as the original. Although this syntax is not in some case exactly the same of Galician it is really close and by most speakers could be considered a correct (although somehow weird) variation of their syntactic rules.
	Of course a completely revised version of a Galician Dependency Treenbank would need to go through the syntactic adaptation of those cases in which the syntactic structure of Portuguese and Galician are not exactly the same. For this reason, any contribution, as well as any comment or suggestion, to the development of a more advanced version of this Galician Dependency Treebank will be welcome.
	Differently from the original Portuguese data, the Galician Dependency Treenbank is not in CONLL-X format, but rather it is in MaltTAB data format. This means is that each entry instead of having 8 different information fields, it has only 4.
	The 4 info fiels found in each entry are the following (as described in README.txt):

Field 1: FORM

Word form or punctuation mark.

Field 2: POSTAG         

Fine-grained part-of-speech tag. This is the part-of-speech as annotated in the Bosque Treebank. See http://visl.sdu.dk/visl/pt/symbolset-floresta.html
2.3. Word classes (terminals)

Fields 3: HEAD         

Head of current token, which is either a value of ID or zero ('0'). A value of zero means the token attaches to the virtual root node.
The dependency structure resulting from the HEAD information can be non-projective. This is certainly true for the converted Bosque treebank, as the original treebank contains discontinuous constituents and the head rules (unlike Collins-style head rules) also introduce non-projectivity.

Field 8: DEPREL         

Dependency relation to the HEAD. 
See http://visl.sdu.dk/visl/pt/symbolset-floresta.html
1. Function labels (F:...)

The following DEPREL values occur in the CoNLL-X data
(comments only for those that are not explained (as of 08/01/2006) on the English web page):

	  >A          
          >N
          >P          premodifier of preposition (?)
          >S
          ?           unclear function (?)
          A<
          A<PRED      ??? (rare)
          ACC
          ACC-PASS    ??? (rare)
          ACC>-PASS   ??? (rare)
          ADVL
          ADVO
          ADVS
          APP
          AS<
          AUX
          AUX<        constituent containing coordinated main verb
          CJT
          CJT&ADVL
          CJT&PRED
          CMD         contrary to what the English web page
                      currently says, "CMD" is used for "command" and "COM" 		      for something else 
          CO
          COM         contrary to what the English web page currently says, 		      this is not "command" but probably a comparison 			      conjunction or adverb (e.g. "como" and "que")
          DAT
          EXC
          FOC
          H
          KOMP<
          MV
          N<
          N<PRED
          NUM<
          OC
          P
          P<
          PASS
          PCJT        "PCJT are a cross of conjuncts and
                       predication, used for pp-chaining, where the second
                       depends on the first, rather than be merely 			       conjuncted"
          PIV
          PMV         main verb within coordination
          PRD         used for "como" in certain (?) constructions ...
          PRED
          PRT-AUX     variant (?) of PRT-AUX<
          PRT-AUX<    particle belonging to auxiliary, e.g. "a", "de", 		              "por", "que"
          PRT-AUX>    typo (?) for PRT-AUX<
          PUNC
          QUE
          S<
          SC
          STA
          SUB
          SUBJ
          TOP
          UTT
          VOC          the 7.3 treebank version is inconsistent in
          VOK          the spelling of VOC/VOK 


For information in the textual material used in the original Portuguese Dependency Treebank see section "2.2 Text" in CONLL-X_README_v1.1.txt.
