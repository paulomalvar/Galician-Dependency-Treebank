This is the readme file for the Portuguese part of the CONLL-X Shared Task.

Version: $Id: README,v 1.1 2006/01/09 17:45:09 erwin Exp $


1. Preamble

    1.1 Source

        Bosque 7.3 by the Floresta sintá(c)tica project, see

        - in English: http://acdc.linguateca.pt/treebank/info_floresta_English.html
          and links from there:
          - http://visl.sdu.dk/visl/pt/symbolset-floresta.html
          - http://visl.sdu.dk/visl/pt/guidelines.html
          - http://visl.sdu.dk/visl/pt/MainDocumentationTreebank.html
          - http://www.linguateca.pt/Diana/download/AfonsoetalLREC2002.ps:
            Afonso, Susana, Eckhard Bick, Renato Haber & Diana
            Santos. ""Floresta sintá(c)tica": a treebank for Portuguese",
            in Manuel González Rodríguez & Carmen Paz Suárez Araujo
            (eds.), Proceedings of LREC 2002, the Third International
            Conference on Language Resources and Evaluation (Las Palmas de
            Gran Canaria, Spain, 29-31 May 2002), ELRA, 2002,
            pp.1698-1703. 
        - in Portuguese: http://acdc.linguateca.pt/treebank/PaginaFloresta.html
          - the "Floresta bible": http://www.linguateca.pt/Floresta/ArvoresDeitadas.doc

    1.2 License

        From the project web site:
        "Floresta Sintá(c)tica (syntactic forest) is a publicly available treebank"

2. Documentation

    2.1 Data format

        Data adheres to the following rules:

        * Data files contain one or more sentences separated by a
          blank line.

        * A sentence consists of one or tokens, each one starting on a
          new line.

        * A token consists of ten fields described in the list
          below. Fields are separated by one tab.

        * All data files will contains these ten fields, although only
          the ID, FORM, CPOSTAG, POSTAG, HEAD and DEPREL columns are
          guaranteed to contain non-underscore values for all
          languages.

        * Data files are UTF-8 encoded (Unicode).

        Field 1: ID         

          Token counter, starting at 1 for each new sentence.

        Field 2: FORM

          Word form or punctuation mark.

        Field 3: LEMMA         

          The lemma of the FORM.

        Field 4: CPOSTAG 

          Coarse-grained part-of-speech tag. The Bosque Treebank does
          not have a notion of coarse and fine-grained part-of-speech
          tags. However, some tags have internal structure, i.e. a
          first and a second part joined by a hyphen (e.g. pron-pers,
          pron-det). In that case, we took only the first part as the
          coarse-grained POS tag (otherwise the whole tag).
          See http://visl.sdu.dk/visl/pt/symbolset-floresta.html
          2.3. Word classes (terminals)

        Field 5: POSTAG         

          Fine-grained part-of-speech tag. This is the part-of-speech
          as annotated in the Bosque Treebank.
          See http://visl.sdu.dk/visl/pt/symbolset-floresta.html
          2.3. Word classes (terminals)

        Field 6: FEATS         

          List of set-valued syntactic and/or morphological
          features. These are the morphological information and
          secondary tags as found in the Bosque Treebank.
          See http://visl.sdu.dk/visl/pt/symbolset-floresta.html
          3. Morphological information (connected to terminals)
  	  4. Secondary tags (<>)

	  Note that the Bosque secondary tags "<poss 1S>" etc. got
	  split into two FEATS: "<poss|1S>"
	  We think that this is actually useful as it allows more
	  generalisation. 

        Fields 7: HEAD         

          Head of current token, which is either a value of ID or zero ('0').
          A value of zero means the token attaches to the virtual root node.
          The dependency structure resulting from the HEAD information can be
          non-projective. This is certainly true for the converted
          Bosque treebank, as the original treebank contains
          discontinuous constituents and the head rules (unlike
          Collins-style head rules) also introduce non-projectivity. 
        
        Field 8: DEPREL         

          Dependency relation to the HEAD. 
          See http://visl.sdu.dk/visl/pt/symbolset-floresta.html
	  1. Function labels (F:...)

	  The following DEPREL values occur in the CoNLL-X data
          (comments only for those that are not explained (as of
          08/01/2006) on the English web page):

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
                      currently says, "CMD" is used for "command" and "COM" for
                      something else 
          CO
          COM         contrary to what the English web page currently says, this is
                      not "command" but probably a comparison conjunction or
                      adverb (e.g. "como" and "que")
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
                       depends on the first, rather than be merely conjuncted"
          PIV
          PMV         main verb within coordination
          PRD         used for "como" in certain (?) constructions ...
          PRED
          PRT-AUX     variant (?) of PRT-AUX<
          PRT-AUX<    particle belonging to auxiliary, e.g. "a", "de", "por", "que"
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
         
        Field 9: PHEAD         

          Projective head of current token, which is always an
          underscore because it is not easily available from the
          Bosque treebank. Probably a completely different,
          Collins-style conversion would be needed, but even then,
          discontinuous constituents would complicated things.

        Field 10: PDEPREL 

          Dependency relation to projective head, which is always an
          underscore, because it is not easily available from the
          Bosque treebank.

    2.2 Text

        The textual material of Floresta comes from the CETEMPúblico and
        CETENfolha corpora (actually their first one-million words).

        CETEMPúblico (Corpus de Extractos de Textos Electrónicos MCT/Público)
        is a corpus containing some 180 million words in European Portuguese,
        created by the Computational processing of Portuguese project after an
        agreement between the Portuguese Ministry for Science and Technology
        (MCT) and the Portuguese daily newspaper PÚBLICO was signed in April
        2000.

	[Could not find English translation]
        O CETENFolha (Corpus de Extractos de Textos Electrónicos NILC/Folha de
        S. Paulo) é um corpus de cerca de 24 milhões de palavras em português
        brasileiro, criado pelo projecto Processamento computacional do
        português (projecto que deu origem à Linguateca) com base nos textos
        do jornal Folha de S. Paulo que fazem parte do corpus NILC/São Carlos,
        compilado pelo Núcleo Interinstitucional de Lingüística Computacional
        (NILC).

    2.3 Conversion

        The conversion process started from the AD format. In the end,
        we decided to implement a direct conversion script from AD to
        the CoNLL-X format instead of relying on the pipeline of
        Eckhard Bick's scripts. However, as far as possible, his head
        rules are implemented. One detail that is probably different
        from his rules is the linkage in case of more than one
        auxiliary in combination with a coordinated main verb,
        especially if the main verbs are accompanied by auxiliary
        particles. There just wasn't enough time to do this, sorry...

	In some cases, the Bosque trees contain ambiguities that the
	annotators could not resolve. For the training data, ambiguity
	was resolved by simply taking the first annotated
	possibility. For the test data, sentences that contain
	ambiguity were discarded.

        For reference: Original description of the head rules:

        >As to dependency conventions, here are a couple of design principles.
        >1. Main verbs are attached to auxiliaries 
        >2. subjects and subordinators attach to the finite verb, the rest of the
        >   clause level functions attach to the main verb
        >3. coordinators and second and following conjuncts attach to the first
        >   conjunct 
        >4. in averbal clauses, the first constituent is regarded the head
        >
        >
        >and some comments in the tiger2dep.pl script:
        >### every word has a head
        >
        >### there is only one top node (to change this, use flatco.pl after
        >tigerdep2malt.pl)
        >
        >### in hypotactic groups and pp's, H stays head
        >
        >### in an fcl or icl, the first verb is head, subordinators become
        >dependents, even if they don't have a real clause function
        >
        >### in a "regular" par, 1. CJT gets to be the head (to flatten this, use
        >flatco.pl after tigerdep2malt.pl)
        >
        >### by extension, in acl, 1. constituent gets to be the head (typically the
        >SUB) [fx da74] 
        >
        >### 'hverken' gets 'eller' as head [fx da79]
        >
        >### in a "non-regular" par, without CJTs, X becomes head, if there is one
        >[fx da55]. If X is itself a "regular" par, this automatically means, its 1. 
        >CJT will become head [fx da26]
        >
        >### otherwise, "non-regular" par is treated like an acl, i.e. the first
        >constituent becomes head (1. X og two, 1. fA of two, fA in fA STA [da39], )

        > and some comments about an example involving multiple
        > auxiliaries (without coordination):
        > CP751-4
        > =P:vp
        > ==AUX:v-fin('ir' PR 3S IND) vai
        > ==AUX:v-inf('ter') ter
        > ==PRT-AUX<:prp('de') de
        > ==MV:v-inf('responder') responder
        >
        > My humble opinion is that the AUX, if more than one, should be chained, 
        > i.e. each is dependent of the preceding one (i.e. ter dependent of vai). 
        > MV (responder) is dependent of the last AUX (ter), and PRT-AUX< (de) is 
        > dependent of the preceding AUX (ter). The original CG tagging the 
        > Floresta is based on, and which is one of its formats, is a shallow 
        > dependency notation, and used ICL-AUX< and PRT-AUX< for chaining, where 
        > '<' is the dependency direction marker, with head information (AUX) at 
        > its point, where both a second auxiliary and the main verb would get 
        > ICL-AUX<. In my view, auxiliaries have valency and selection 
        > restrictions showing who is head and who is dependent.
        
    3. Acknowledgements
        
        Diana Santos, Eckhard Bick and other Floresta sintá(c)ticathe
        project members for creating the treebank and making it
        publicly available.

	Diana Santos and Eckhard Bick for answering many questions
	about the treebank. Diana Santos also for correcting problems
	and making new releases. Eckhard Bick also for sharing his
	scripts and explaining the head rules implemented in them.

	Jason Baldridge for useful discussion. Ben Wing for
	independently reporting problems that Diana then fixed.

