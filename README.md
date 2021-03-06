# Mushroom

*Mushroom* helps data scientists synthesize utterances for training text classifiers. In the intended use case, the data scientist wishes to synthesize utterances from some target class and has at their disposal an existing corpus of utterances which do not belong to the target class. The data scientist provides the corpus as well as a small number of seed utterances from the target label class, and *Mushroom* does the rest, leveraging the corpus to output a synthesized set of utterances.

# Installation

You will need the following packages:

    pip install nltk tqdm numpy

In addition, you will need to install the `stopwords` package in `nltk` which you can do by executing the following in the Python shell:

    import nltk
    nltk.download('stopwords')

# Scripts

## mushroom.py

Computes a ranked list of synthesized utterances using a corpus, a context phrase, and a keyword phrase

### Arguments

#### filename

Corpus of utterances, one utterance per line.

#### context_phrase

A context phrase

#### keyword_phrase

A keyword phrase

### Optional arguments

#### depth

The depth of search in the electric network (default: 2)

#### output

Filename for outputting synthesized utterances

### Example invocations

python mushroom.py atis.txt "what is the __" "luggage limit" --output results.txt

## bleu.py

Computes a variant of the BLEU score between a set of reference utterances and a set of generated utterances.

### Arguments

#### reference_utterances_filename

A file of reference utterances, one utterance per line

#### synthesized_utterances_filename

A file of syntehsized utterances, one utterance per line

## baseline.py

Construct a baseline of synthesized utterances by sampling 

### Arguments

#### filename

The corpus to sample from

#### keyword_phrase

The keyword phrase to interpolate into the synthesized utterances

#### n

The number of samples to generate
