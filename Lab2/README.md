# Unsupervised Learning in Carnegie Mellon Movie Summary Corpus

## Application 1: Movie's Reccomendation System (content base)
Based on what the user likes, this algorithm will simply pick items with similar content to recommend.

![1](https://user-images.githubusercontent.com/50829499/111079177-78053200-8501-11eb-90ac-2dbb8ec48a15.png)
### Dataset Preview:

This dataset consists of 42,306 movie plot summaries extracted from Wikipedia. 

### App Description:

First of all we convert dataset to **tf- idf** representation. It is a numerical statistic that is intended to reflect how important a word is to 
a document in a collection or corpus and it is based on tf (term frequency) and idf (inverse document frequency). For better data preprocessing we romove pronouns, articles, intentions, peoples names etc. 
After that we apply Stemming/Lemmatization. These techiques, in the field of Natural Language Processing, are for Text Normalization. More specifically:
* **Stemming** is the process of reducing inflection in words 
to their root forms such as mapping a group of words to the same stem even if the stem itself is not a valid word in the Language, and  
 * **lemmatization** reduces the inflected words properly ensuring that the root word belongs to the language

### Example Result:

For input movie `"The Ward"` which belongs to categories: `['"Thriller",  "Psychological thriller",  "Horror",  "Haunted House Film",  "Supernatural"']` we take `4` recommendations:

Movie 1: `"Day of the Dead 2: Contagium"` in categories `['"Zombie Film",  "Horror"']` <br/>
Movie 2: `"Forget Me Not"` in categories ` ['"Thriller",  "Horror",  "Teen"']` <br/>
Movie 3: `"Shake, Rattle & Roll 13"` in categories `['"Thriller",  "Drama",  "Horror"']` <br/>
Movie 4: `"Room 6:` in categories `['"Horror"']` <br/>


## Application 2: Topological and Semantic Representation using Self-Organizing Maps (SOM)

![2](https://user-images.githubusercontent.com/50829499/111079324-3923ac00-8502-11eb-95c4-4abf6575fb10.jpg)

### App Description:

Working on the same dataset, we construct a 2D grid. In this grid, the movies are placed depending on the different species. As an example, movies with 
similar content (plot) are neighboring. This clustering became possible using and training Self Organizing Maps.

### Example Result:

![23](https://user-images.githubusercontent.com/50829499/111312056-984f0100-8667-11eb-8465-2eee348fd664.png)

The output of code was a 30 x 30 grid with 30 clusters. Each colored dot is a neuron, and each movie is assigned to a neuron. Finally the color behind these neurons ( in the map ) declares how close are movie's patterns. With this map we succeeded to seperate up to 11 movie's genres: <br/> 
`[Drama, Action - Adventure, Thriller - Crime, Horror, Comedy, Romance, Animation - Short - Family, Word Cinema, Silent - Black and White, Documentary, Indie ]`.


