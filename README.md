# collecting_data_assignment4

## Intended use
The intended use of the collected corpus is the lyrical analysis of singer-songerwiter and producer Grimes. 
Anyone with interest in her musical projects can download and use the corpus.

## Corpus collection and selection
The corpus of 16 songs was manually selected and downloaded via the [Genius artist page of Grimes](https://genius.com/artists/Grimes).
There were several criteria for the song selections:
(1) Grimes was the only singer in the song.
(2) The song is popular amongst Grimes' song searches on Genius as suggested by the view counter.
(3) I tried balancing the corpus by including songs from different EPs and Albums. However, there might be some overrepresentation of songs from the Vision and especially Art Angels albums.

## Metadacta collection
I decided to gather some metadata on the selected corpus of 16 songs. The following values were manually collected for each song via the [Discogs artist page of Grimes](https://www.discogs.com/artist/1993487-Grimes-4):

| title | length |release_year | ablum_title |
| --- | --- | --- | --- |
| song title | length in minutes | release year in int | album/EP/release title |

## Cleaning and preprocessing

The texts downloaded from Genius already contain some extra information and are not completely 'raw' as sections are labeled according to the song structure (e.g. "chorus","verse 1", "outro", etc.). Therefore, I decided to use this annotation for creating the different song parts and adding them to our CSV file. This way, we can for instance compare all the choruses in the corpus. Additionally, after the creation of the song parts, I removed the brackets indicating the song parts to get the 'raw' lyric text. I reassign this to the `Text` column and only tokenized and lemmatized this part. 

## Annotations added and tools used


The annotations were added using a spaCy Jupyter Notebook tutorial. Some notes were added to evaluate and comment on the quality of the annotations.

## Format of corpus files

The final csv-file contains the following rows:

| Column | Description |
| --- | --- |
| Filename | 
| length | length in minutes 
| release_year | year of release |
| ablum_title | Title of the release (can also be an EP or Single) |
| Text | Cleaned lyric |
| Song Part | As the Genius lyrics were annotated, I assigned the lyrics to the part they belong to, i.e. "verse_1" or "chorus" |
| Doc | The doc element created using spaCy |
| Tokens | Tokenization of the entire text |
| Lemmas | Lemmatization of the entire text |

## Quality checks

The doc element created with the used spaCy pipeline contained some errors with the more complex corpus annotation tasks. For instance, for Named Entity Recognition (NER) vocalizations such as 'la-la-la' are recognized as persons or organisation by spaCy. It seems that spaCy is struggling with annotating a lyrcial corpus, which might be due to a lack of lyrical training material of the pipeline. I therefore decided to remove these annotations in the updated version so that the enriched CSV file only contains well processed annotations. Concretely, this means that the updated CSV file now does not contain the following columns anymore:  `Proper_nouns`, `POS`, `NER`. More explanation is given in the Juypter Notebook. 
