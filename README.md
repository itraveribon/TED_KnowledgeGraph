# TED_KnowledgeGraph
The TED talks knowledge graph (items.json) consists of 846 talks and 125 playlists. Playlists are described with a title and the set of included TED talks. Each TED talk is described with the following set of datatype properties:
* dc:title (Dublin Core vocabulary) or title of the talk.,
* dc:creator or speaker,
* dc:description or abstract,
* ted:relatedTags or set of related keywords.

Apart from the datatype properties, talks are connected to playlists that include them through the object property ted:playlist. A vol:hasLink (Vocabulary Of Links http://purl.org/vol/ns/) object property connect each pair of talks that are together in at least one playlist.
We crawled the playlists available in the TED website http://www.ted.com/playlists. Playlists contain sets of TED talks that usually address similar topics. TED playlists are created and maintained by curators, who decide if a certain video may or may not be included in a certain playlist.

Additionally, we enriched the knowledge graph by adding similarity values between each pair of entities. We computed four similarity measures (TFIDF, ESA} and Doc2Vec) using as input the concatenation of datatype properties title, description and related tags. ESA similarity values were obtained using the public ESA endpoint http://vmdeb20.deri.ie:8890/esaservice, and Doc2Vec (D2V) values were obtained training the gensim implementation~ with the pre-trained Google News dataset https://goo.gl/flpokK.

Similarity values are stored in three different matrix where the content of the position [i,j] corresponds to the similarity between talks i and j. i and j corresponds to the i-th and j-th talks described in the items.json file.
