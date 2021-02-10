XWN 2.0-1.1

SUMMARY
=======

1. LICENSE

2. What XWN 2.0-1 brings new
2.a What is different XWN 2.0-1.1 than XWN 2.0-1 release

3. XWN 2.0-1.1 files

4. How the information related to a synset is represented in XWN 2.0-1.1

5. Contact

====================================================================================

1. LICENSE
==========

XWN 2.0-1.1 software and database is being provided to you, the LICENSEE, 
by the University of Texas at Dallas under the following license. 
By obtaining, using and/or copying this software and database, 
you agree that you have read, understood, and will comply with 
these terms and conditions:

Permission to use, copy, modify and distribute this software and database 
and its documentation for any purpose and without fee or royalty 
is hereby granted, provided that you agree to comply with the following 
copyright notice and statements, including the disclaimer, and that 
the same appear on ALL copies of the software, database and documentation, 
including modifications that you make for internal use or for distribution.

eXtended WordNet 2.0-1.1 for WordNet 2.0 Copyright &copy; 2003 by the University of Texas 
at Dallas. All rights reserved.(WordNet is copyrighted by the Princeton University)

THIS SOFTWARE AND DATABASE IS PROVIDED "AS IS" AND THE UNIVERSITY OF TEXAS 
AT DALLAS MAKES NO REPRESENTATIONS OR WARRANTIES, EXPRESS OR IMPLIED. 
BY WAY OF EXAMPLE, BUT NOT LIMITATION, UNIVERSITY OF TEXAS AT DALLAS 
MAKES NO REPRESENTATIONS OR WARRANTIES OF MERCHANTABILITY OR FITNESS 
FOR ANY PARTICULAR PURPOSE OR THAT THE USE OF THE LICENSED SOFTWARE, 
DATABASE OR DOCUMENTATION WILL NOT INFRINGE ANY THIRD PARTY PATENTS, 
COPYRIGHTS, TRADEMARKS OR OTHER RIGHTS.

The name of University of Texas at Dallas may not be used in advertising 
or publicity pertaining to distribution of the software and/or database. 
Title to copyright in this software, database and any associated documentation 
shall at all times remain with University of Texas at Dallas and LICENSEE 
agrees to preserve same.

====================================================================================

2. What XWN 2.0-1 brings new
============================

The XWN 2.0-1 release is based on WordNet 2.0

Also, another difference with respect to XWN 1.7 is the alignment of the information at synset level.
In XWN 1.7 the information was not aligned. There were three different files for WSD, parse trees and LFTs.
In XWN 2.0-1 these three files are merged into a single file for each part of speech WordNet offers (noun, verb, adjective, adverb).

====================================================================================

2.a What is different in XWN 2.0-1.1 then XWN 2.0-1 release

Some bugs, regarding WSD tokens with lemma different than word form,
are corrected.

====================================================================================

3. XWN 2.0-1 files
==================

The XWN 2.0-1.1 release has 6 files:
    - this README.txt file;
    - xwn.xsd file, which contains the XSD schema for the remaining files;
    - adj.xml file, which contains the adjectives, in an XML format;
    - adv.xml file, which contains the adverbs, in an XML format;
    - noun.xml file, which contains the nouns, in an XML format;
    - verb.xml file, which contains the verbs, in an XML format.

====================================================================================

4. How the information related to a synset is represented in XWN 2.0-1.1
======================================================================

Here is an example extracted from adv.xml:

<---START EXAMPLE--->

<gloss pos="ADV" synsetID="00002223">
  <synonymSet>barely, hardly, just, scarcely, scarce</synonymSet>
 <text>
   by a small margin; "they could barely hear the speaker"; "we hardly knew them"; "just missed being hit"; "had scarcely rung the bell when the door flew open"; "would have scarce arrived before she would have found some excuse to leave"- W.B.Yeats  
 </text>
  <wsd>
      <wf pos="IN" >by</wf>
      <wf pos="DT" >a</wf>
      <wf pos="JJ" lemma="small" quality="gold" wnsn="1" >small</wf>
      <wf pos="NN" lemma="margin" quality="gold" wnsn="2" >margin</wf>
  </wsd>
<parse quality="SILVER">
(TOP (S (ADVP (RB barely) ) 
        (VP (VBZ is) 
            (PP (IN by) 
                (NP (DT a) (JJ small) (NN margin) ) ) ) 
        (. .) ) ) 
</parse>
 <lft quality="GOLD">
 barely:RB(e1) -> by:IN(e1, x1) small:JJ(x1) margin:NN(x1)
 </lft>
</gloss>

<---END EXAMPLE--->

Let's explain what's going on here:

For each synset in WordNet 2.0, we generated a <gloss>...</gloss> datagram.
The "gloss" tag has as attributes "pos" (the part of speech; we have an adverb here) and "synsetID" (the ID of the synset under discussion) which uniquely identify a certain synset.

Inside <gloss>...</gloss> we have another set of tags:
       - synonymSet - the set of synonyms of that synset;
       - text       - the gloss of that synset (definitions + examples (examples are quoted));
       - wsd        - the word sense disambiguation of gloss' definitions;
       - parse      - the parse trees of gloss' definitions;
       - lft        - the logic form transformations of gloss' definitions.

There is a "quality" attribute related to each parse tree, logic form transformation and open class word. Its values can be:
      - GOLD        - a human decided over that information;
      - SILVER	    - there was agreement in an automatic voting process, but no human intervention took place;
      - NORMAL      - output provided by the software without human checking or voting agreement.

====================================================================================

5. Contact
==========

Your feedback is important to us.

Please e-mail us at: xwn@hlt.utdallas.edu


Human Language Technology Research Institute
University of Texas at Dallas
December 19th, 2003
