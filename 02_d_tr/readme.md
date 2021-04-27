# D_tr: Transitive sentences, length 5 to 20

This is the second dataset for our causativity experiments. It consists of 50,000 sentences, split into `train` (40,000), `dev` (5,000) and `test` (5,000). Each set contains a balanced number of _causative sentences_ and _noncausative sentences_. All sentences are transitive, i.e. they contain exactly the top-level dependency relations `nsubj`, `root` and `dobj`.

In this dataset, sentences have lengths between 5 and 20 tokens, where the last token is typically (but not necessarily) a punctuation character.

## Causative sentences and noncausative sentences
We define "causative sentences" as sentences whose root verb appears in our manually compiled list of causative verbs. These are verbs whose transitive occurrences always carry a causative meaning, according to VerbNet.

Noncausative sentences have root verbs that appear in our manually compiled list of noncausative verbs. These are verbs that have a transitive use, but the transitive use does not carry a causative meaning, according to VerbNet.

The verb lists were pruned by two trained linguists to remove ambiguous verbs and edge cases.

The causative and noncausative verbs can be found in file `verbs.json`, grouped by VerbNet class (version 3.3). This is the same verb list as the one used for the first dataset.

## Sentence selection
The sentence selection was implemented in the same way as in the first dataset, but here using 5 and 20 as minimum and maximum lengths. The random seed for the selection of sentences for each split was `random.seed(20200205)`.

## Statistics
Statistics on the train, dev and test sets are available in `statistics.json`.