# D_tr5: Transitive sentences, length 5

This is the first dataset for our causativity experiments. It consists of 50,000 sentences, split into `train` (40,000), `dev` (5,000) and `test` (5,000). Each set contains a balanced number of _causative sentences_ and _noncausative sentences_. All sentences are transitive, i.e. they contain exactly the top-level dependency relations `nsubj`, `root` and `dobj` (plus punctuation). All sentences have a length of exactly 5 tokens, where the last token is typically (but not necessarily) a punctuation character.

## Causative sentences and noncausative sentences
We define "causative sentences" as sentences whose root verb appears in our list of causative verbs. These are verbs whose transitive occurrences always carry a causative meaning, according to VerbNet.

Noncausative sentences have root verbs that appear in our list of noncausative verbs. These are verbs that have a transitive use, but the transitive use does not carry a causative meaning, according to VerbNet.

The verb lists were pruned by two trained linguists to remove ambiguous verbs and edge cases.

The causative and noncausative verbs can be found in file `verbs.json`, grouped by VerbNet class (version 3.3). This is the same verb list as the one used for the second dataset.

## Sentence selection
In order to reduce our corpus down to only 50,000 sentences, we perform a random selection. This involves the following steps:
1. Filter the ENCOW corpus down to only transitive sentences (9,775,119 sentences).
2. Filter the resulting subcorpus down to only sentences containing verbs appearing in `verbs.json` (1,133,751 causative sentences, 2,813,098 noncausative sentences).
3. Filter these subcorpora down to only sentences of length 5 including punctuation (47,455 unique causative sentences, 125,246 unique noncausative sentences).
4. For each set `train`, `test` and `dev`, select `n/2` causative and `n/2` noncausative sentences from the corpora, where `n` is the goal size of the set. The sentences are selected randomly from the corpora prepared in step 3, using `random.seed(20210114)`.

Each sentence surface form is only used exactly once throughout the three splits. This is a strategy to avoid multiple occurrences of one sentence inside one of the splits.

## Statistics
Statistics on each corpus split are available in `statistics.json`.