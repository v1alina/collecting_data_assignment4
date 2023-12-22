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

I took no extra steps of cleaning or preprocessing the texts. The texts downloaded from Genius already contain some extra information and are not completely 'raw' as sections are labeled according to the song structure (e.g. "chorus","verse 1", "outro", etc.)

## Annotations added and tools used



The annotations were added using a spacy Jupyter Notebook tutorial. Some notes were added to evaluate and comment on the quality of the annotations.

## Format of corpus files

The final csv-file contains the following rows:

| Filename | length |release_year | ablum_title | Text | Doc | Tokens | Lemmas | POS | Proper_Nouns | Named_Entities | NE_Words
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

## Quality checks

There were no final quality checks added, but I would not recommend using the annotated corpus as many annotations seem to be incorrect. For instance, vocalizations such as 'la-la-la' are recognized as persons or organisation by the spacy annotations. It seems that spacy is struggling with annotating a lyrcial corpus.
