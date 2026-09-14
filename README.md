# Summary

UD_Polish-MPDT is a treebank of Middle Polish (17th–18th centuries). It is a rule-based conversion of the [Middle Polish Dependency Treebank](https://korba.edu.pl/treebank?lang=en) (Wieczorek, 2025) from its original annotation to the Universal Dependencies format. The MPDT sentences are sourced from the [KorBa corpus](https://korba.edu.pl/overview?lang=en) (Gruszczyński et al., 2022). 

# Introduction

The UD_Polish-MPDT treebank contains sentences from the Middle Polish period (17th–18th centuries). The material is drawn from the [KorBa corpus](https://korba.edu.pl/overview?lang=en) – The Electronic Corpus of 17th- and 18th-century Polish Texts – a large and diverse collection of Polish literature, scientific texts, official documents, press releases, and more from 1601–1772.

The syntactic annotations originate from the [Middle Polish Dependency Treebank](https://korba.edu.pl/treebank?lang=en), a project led by Aleksandra Wieczorek, which adds a dependency layer to a selected part of KorBa. The original MPDT annotation follows the conventions of the [Polish Dependency Bank (PDB)](https://zil.ipipan.waw.pl/PDB).

This UD release contains 2,515 sentences and approximately 59K syntactic words (58,560 surface tokens).

# Data

## Data Split

In line with the guidelines for treebanks of 20K–110K words, approximately 10K words are allocated to the test set, ~10% of the remaining data to the development set, and the rest to the training set.

The initial 2,018 sentences (v2.17) were randomly shuffled (using seed 42) and assigned to the three subsets based on word-count quotas. In subsequent releases, published sentence assignments remain strictly frozen. New material (MPDT_3) is assigned whole documents at a time to preserve document cohesion, topping up dev to 10% of the non-test material while keeping corpus-wide genre proportions:

| Set   | Sentences | Syntactic Words | Surface Tokens |
|-------|-----------|-----------------|----------------|
| Train | 1 876     | 44 346          | 43 816         |
| Dev   | 216       | 4 949           | 4 888          |
| Test  | 423       | 10 005          | 9 856          |
| Total | 2 515     | 59 300          | 58 560         |

## Genres / Document Structure

Sentence IDs are contiguous integers (1–2515). While the initial 2,018 sentences were sampled at the sentence level, new sentences are assigned by source document (tracked in the `orig_file_sentence` metadata comment, which records the KorBa document siglum). The treebank covers nonfiction, biblical texts, legal/administrative documents, fiction/belles-lettres, press/news, and poetry.

# Acknowledgments

We thank the original Middle Polish Dependency Treebank team, led by Dr. Aleksandra Wieczorek. The data was annotated by Aleksandra Wieczorek, Bożena Itoya, Emanuel Modrzejewski, and Martyna Sabała-Bolek. Programming support for data preparation was provided by Dorota Komosińska.

The conversion to the UD format was developed by Kamil Tomaszek as part of his M.A. thesis at the University of Warsaw, under the supervision of Dr. Alina Wróblewska (Institute of Computer Science, Polish Academy of Sciences).

# References

* Gruszczyński, Włodzimierz; Adamiec, Dorota; Bronikowska, Renata; Kieraś, Witold; Modrzejewski, Emanuel; Wieczorek, Aleksandra; Woliński, Marcin. 2022. “The Electronic Corpus of 17th- and 18th-century Polish Texts.” *Language Resources and Evaluation*, 56(1): 309-332. https://doi.org/10.1007/s10579-021-09549-1  
* Wieczorek, Aleksandra. 2025. “Towards the Middle Polish Dependency Treebank.” In *Native Language in the 21st Century: System, Communication Practices and Education*. V & R Unipress.

# Changelog

* 2026-11-15 v2.19
  * Added 497 sentences (12,027 words) from MPDT_3, bringing the treebank to 2,515 sentences (59,300 words).
  * Re-analyzed numeral expressions to align with UD Polish standards (`nummod:gov`, `det:numgov`, `det:nummod`, identifying numbers to `nmod`).
  * Standardized comparative relation subtypes (`obl:cmp`, `advcl:cmp`, `acl:cmp`, `nmod:cmp`).
  * Fixed whitespace and metadata text alignment across published sentences.
* 2026-05-15 v2.18
  * The :cmpr deprel subtype was renamed to :cmp.
* 2025-11-15 v2.17
  * Initial release in Universal Dependencies.

<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.17
License: CC BY-SA 4.0
Includes text: yes
Parallel: no
Genre: nonfiction bible legal fiction news poetry
Lemmas: manual native
UPOS: converted from manual
XPOS: automatic with corrections
Features: converted from manual
Relations: converted from manual
Contributors: Tomaszek, Kamil; Wróblewska, Alina; Wieczorek, Aleksandra
Contributing: here
Contact: kamiltomaszek@icloud.com
===============================================================================
</pre>
