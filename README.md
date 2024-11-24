# Assignment2 | Collecting Data 
## MA Digital Humanities | University of Groningen

### Ungaretti war poems corpus
The corpus comprises seven of the most well-known war poems by Giuseppe Ungaretti, a prominent Italian poet of the 20th century and one of the greatest representatives of the Hermetic movement. The poems are extracted from various collections published over a period of 15 years, all of which were integrated into “L’Allegria” (1931). 
The poet, who voluntarily participated in World War I, draws from personal experience and pours it into his poems, which mainly reflect his torment and heartbreak, but also hope and resilience. 
This corpus is intended for Italian literature scholars and enthusiasts who wish to analyze a representative sample of Ungaretti’s war poems to yield valuable insights into his poetic expression and stylistic choices. An examination of the tokens and lemmas can, for instance, be combined with sentiment analysis to detect emotionally charged words and assess the emotional tone of each poem, enhanced by the use of minimalism. Parts-of-speech tags could, furthermore, reveal patterns in Ungaretti’s language choices, such as the predominance of personal pronouns or possessive adjectives, which suggest an intimate perspective due to his active participation in the war. Such investigations might also enable a comparative analysis with other war poets who may have employed different approaches due to their role as observers. 

### Data collection process
The texts were manually extracted from two distinct websites, https://www.italialibri.net/opere/poesiediguerra.html (“Veglia”, “Sono una creatura”, “San Martino del Carso”, “Soldati”) and https://lasottilelineadombra.com/2018/03/05/poesie-di-guerra-ungaretti/ (“Fratelli”, “In dormiveglia”, “Pellegrinaggio”). Subsequently, the content was transferred to TextEdit and converted into plain text (.txt) file format. 

### Cleaning and preprocessing steps
The only text cleaning operations performed were string replacement (str.replace()) and whitespace stripping (str.strip()), in order to remove line break characters and excess whitespace. 
As far as preprocessing steps, tokenization, lemmatization and parts-of-speech tagging were performed using spaCy. 

### Annotations
Additional columns (“Title”, “Author”, “Collection”, “Year”) were annexed to the initial dataset by merging it with a secondary table using spaCy. The same tool was later employed to perform named entity recognition, adding a column with named entity tags and one with the words and phrases identified as named entities (“Named_Entities”, “NE_Words”). 
At the end of the code execution, the dataset was saved in a CSV format. 

### CSV file description 
The CSV file contains the following columns: 

| Variable name | Description |
| -------------- | ------------------------------------------------------------------------------------------ |
| Filename       | The original .txt file name                                                                |
| Title          | The poem’s title                                                                           |
| Author         | The author of the poem                                                                     |
| Collection     | The collection where the poem was first published and the one that includes all of them |
| Year           | Years of the collections’ publication                                                      |
| Document       | The original, unprocessed, text                                                            |
| Text           | The full cleaned text                                                                      |
| Tokens         | Individual words of each poem                                                              |
| Lemmas         | Base form of each token                                                                    |
| POS            | Parts-of-speech tags categorizing each word                                                |
| Named_Entities | Named entities categories                                                                  |
| NE_Words       | The words associated with named entities                                                   |
