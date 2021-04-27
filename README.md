# Predicting Causativity at IWCS 2021
This repository contains the data for our IWCS 2021 paper: **Esther Seyffarth, Younes Samih, Laura Kallmeyer, Hassan Sajjad (2021): _Implicit representations of event properties within contextual language models: Searching for "causativity neurons"_**.

This paper addresses the question to which extent neural contextual language models such as BERT implicitly represent complex semantic properties. More concretely, the paper shows that the neuron activations obtained from processing an English sentence provide discriminative features for predicting the (non-)causativity of the event denoted by the verb in a simple linear classifier. A layer-wise analysis reveals that the relevant properties are mostly learned in the higher layers. Moreover, further experiments show that appr.~10% of the neuron activations are enough to already predict causativity with a relatively high accuracy.

# Data

Each subfolder contains the materials for one of the three datasets **D_tr5**, **D_tr** and **D_all**. Please refer to the `readme` files in each subfolder for more information.

All sentences are taken from the MALT-parsed [ENCOW16AX](https://corporafromtheweb.org/encow16/) corpus. Sentences are identified by an ID consisting of the string `#ENCOW`, followed by a dash and the corpus file number (between 1 and 15), followed by a dash and the sentence's ID. For instance, the following refers to a sentence from the 12th ENCOW file, having the sentence ID 12407321: `#ENCOW-12-12407321`

A script to extend our data with each sentence's content from ENCOW can be made available upon request. Contact Esther Seyffarth for more information.