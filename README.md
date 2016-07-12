# TED_Paper
The file items.json contain a dataset used in a scientific paper about relation discovery in knowledge graphs. The data was scrapped from the official website of TED http://www.ted.com/playlists.  The JSON file contains three types of items. You can differentiate them because they contain different fields. 

First we have groups of playlists. Each group of playlists has a title and a array of playlists URLs.
Secondly, we have the playlists. Each playlists has an URL, a title and an array of talk URLs.
Finally, we have the talks. Each talk is described by a textual description, a title, the amount of views, the related tags, the speaker and its related videos. We did not consider this relationship of related_videos as ground truth. It seems that some of them are randomly assigned. Instead, we consider that two talks are related if they appear together in at least one playlist. Acconding to TED, playlists are human curated, so it can be a high quality ground truth.

Additionally we computed Doc2Vec similarity values for each pair of TED talks based on the text form by the concatenation of the title, the description and the related tags. We used this values in order to discover relations between talks with KOI. The file is formatted as a matrix, where the content of the position [i,j] corresponds to the similarity between talks i and j. i and j corresponds to the i-th and j-th talks described in the items.json file.
