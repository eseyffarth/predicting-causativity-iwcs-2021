# D_all: Transitive and intransitive sentences, length 5 to 20

This is the third dataset for our causativity experiments. It consists of 50,000 sentences, split into `train` (40,000, half of which are transitive/intransitive), `dev` (5,000, half of which are transitive/intransitive) and `test` (5,000, half of which are transitive/intransitive). Each set contains a balanced number of _causative sentences_ and _noncausative sentences_. All sentences are either transitive, i.e. they contain exactly the top-level dependency relations `nsubj`, `root` and `dobj`, or intransitive, i.e. they contain only the top-level dependency relations `nsubj` and `root`.

In this dataset, sentences have lengths between 5 and 20 tokens, where the last token is typically (but not necessarily) a punctuation character.

## Causative sentences and noncausative sentences
For this corpus, we use three types of verbs, documented in the file `verbs_and_types.json`. Type I contains verbs that participate in the causative-inchoative alternation: Their transitive uses are causative, but their intransitive uses are noncausative. Type II contains causative verbs that do not participate in that alternation. Type III contains noncausative verbs that do not participate in the alternation.

Type I contains 450 distinct verb lemmas. Type II contains 557 distinct verb lemmas. Type III contains 617 distinct verb lemmas.

The original source for +caus and -caus verb labels was the verb list that we used as the seed for our first two datasets.

In the corpus files in this subfolder, transitive sentences are labeled as causative if their root verb is either of type I or type II. Transitive sentences with a root verb of type III are labeled as noncausative.

Intransitive sentences are labeled as causative if their root verb is of type II. Intransitive sentences with a root verb of type I or type III are labeled as noncausative.

Each sentence surface form is only used exactly once throughout the three splits. This is a strategy to avoid multiple occurrences of one sentence inside one of the splits.

The random seed for the sentence selection was `random.seed(20210209)`.

## Statistics
Statistics on each corpus split are available in `statistics.json`.