**dataset-dictionary** is a Meteorite package that provides a the Webster Unabridged English Dictionary.

------------------------
### Installation

First, install the dataset-dictionary package from the command line, like so:

````
meteor add awatson1978:dataset-dictionary
````

------------------------
### Data/Document Model for Reading Data from Collection

Once done, you'll want to display data from the collection by adding the following templates into your document model.  The class names come from Bootstrap v3.

````html
<template name="dictionaryIndexTemplate">
  <div class="padded">
    <div class="panel panel-info">
      <div class="panel-heading">
          <input id="dictionarySearchInput" type="text" placeholder="Filter..." value="life"></input>
      </div>
      <ul class="list-group">
        {{#each dictionaryList}}
          {{> dictionaryItemTemplate }}
        {{/each}}
      </ul>
    </div>
  </div>
</template>
<template name="dictionaryItemTemplate">
  <li class="list-group-item"><span class="bold">{{ Word }}</span>  {{Definition}}</li>
</template>


````

------------------------
### Controller for Reading Data from Collection

To dislay data, you'll also need to add the controllers, like so:

````js

Template.dictionaryIndexTemplate.helpers({
  dictionaryList = function(){
    return Dictionary.find({
      'Word': { $regex: Session.get('dictionary_search'), $options: 'i' }
    },{limit: 20});
  }
});

````


================================
### Licensing

All code is MIT License. Use as you wish, including for commercial purposes.



================================
###  English Language Dictionary


This repository houses the contents of Webster's Unabridged English Dictionary.

The dictionary can be found in plain text form [here](http://www.gutenberg.org/ebooks/29765)

You'll also find some julia files that were used to parse the text and organize it into the nice
json you see here.


#### Contents
- dictionary.json: This is the raw data scraped from the dictionary. Unsurprisingly, it's in the format
of a dictionary, i.e. ```{ "Word": "Definition" }```
- graph.json: This is a graph representation of the dictionary. Each word is paired with a list of the words that define it dictionary.txt: This is the plain text file (I converted it from ISO-8859-1 to UTF-8)

#### License
Creative Commons Attribution-NonCommerical 3.0 Unported

![](http://i.creativecommons.org/l/by-nc/3.0/88x31.png)

[Creative Commons Attribution-NonCommercial 3.0 Unported Licencse](http://creativecommons.org/licenses/by-nc/3.0/deed.en_US)
