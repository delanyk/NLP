# English/German Spellchecker

In this project, tweets in both German and English were classified by their langauge and checked for spelling errors. Spelling corrections are offered within one Damerau-Levenstein disntance away. The most misspelled words in each respective language were listed along side their corrections.
<br/>
<br/>

##  Results
<br/>
<br/>

```python

output:
[('kinda', 2290, ['kind', 'linda']),
 ('bc', 712, ['be', 'by', 'b']),
 ('gonna', 492, ['donna', 'gonne', 'gona']),
 ('lol', 395, ['vol', 'lo', 'pol']),
 ('omg', 377, ['om', 'og']),
 ('wanna', 330, ['anna', 'canna', 'hanna']),
 ('rn', 297, ['in', 'an', 'on']),
 ('tbh', 284, ['th', 'tch']),
 ('idk', 261, ['id', 'ink', 'ilk']),
 ('ppl', 217, ['pol', 'pal'])]

```
<br/>

Here are the most misspelled words in English, along with their respective misspell count and the possible terms for replacement.

<br/>
<br/>


```python

output:
[('nen', 424, ['ren', 'nn']),
 ('nochmal', 294, ['nochmals']),
 ('nem', 233, ['dem', 'neu', 'nm']),
 ('erstmal', 216, ['erstmals']),
 ('lol', 214, ['hol', 'mol', 'aol']),
 ('daß', 180, ['saß', 'maß', 'dax']),
 ('gibts', 164, ['gibt', 'gifts']),
 ('nich', 151, ['nicht', 'noch', 'sich']),
 ('zb', 147, ['zu', 'ob', 'tb']),
 ('vllt', 146, [])]

```
<br/>

Here are the most misspelled words in English, along with their respective misspell count and the possible terms for replacement.

<br/>
<br/>


## Prerequisites
In addtion to string and regex, you will need the nltk library

```bash

pip install nltk

```

<br/>
<br/>

## Cleaning the data

Raw data from tweets in two different langauges had a lot to filter. Websites, hashtags, numbers, punctuation, and @ tags were removed from the text. These replacements were done consectively rather than a single regular experession to avoid group overlapping and for simplicity.

<br/>
<br/>

```python
    data_index[tweet] = re.sub('https?[^\s]+', ' ' , data_index[tweet])
    data_index[tweet] = re.sub('[@#][^\s]+', ' ' , data_index[tweet])
    data_index[tweet] = re.sub(r'[0-9][^\s]+', ' ' , data_index[tweet])
    data_index[tweet] = re.sub(r'\w+\.[^\s]+', ' ' , data_index[tweet])
    data_index[tweet] = re.sub(r'[^a-zäöüß\s]', ' ', data_index[tweet])
    data_index[tweet] = re.sub(r'[^\w\s]', ' ' , data_index[tweet])

```

<br/>
<br/>

## Running the Code

This can be run directly in the notebook.
However you may require jupyter-notebook as well.


```bash
sudo apt-get install jupyter-notebook
```


## The processing

The data was tokenized and normalized using NLTK libraries. Filtering and cleaning of the data was done through regular expressions, and string libraries.

```python

import re 
import string
from nltk.corpus import stopwords
from nltk.stem import WordNetLemmatizer as wnl

```
<br/>
<br/>

## Text classification

To classify between languages, the NLTK stop word list and character lists were used to intitally distinguish between them. For further refinement, dictionaries were generated of terms that occured most frequently in the previously classified texts. These were run again against to more accurately label each tweet. As a fall back if the tally for words occuring in either language could not determin which language the tweet was in, the stop word list and character screening was used.


<br/>
<br/>

## Misspells

<br/>
<br/>

## Spelling Corrections

<br/>
<br/>

## The Data

The data was given from twitter. It was collected and distributed via the University of Stuttgart. German and English dictionaries were also contributed from University of Stuttgart files.
<br/>
<br/>
<br/>
<br/>

## Authors


* **King De Lany** - *Initial work* - [DelanyK](https://github.com/DelanyK)



## Acknowledgments

*This project was from the Information Retrieval and Text mining course and the University of Stuttgart. Parterns that contributed ideas, [RenouB](https://github.com/RenouB) and [Amirasweilem](https://github.com/amirasweilem)
