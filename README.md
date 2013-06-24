**dataset-dictionary** is a Meteorite package that provides a the Webster Unabridged English Dictionary.

------------------------
### Installation

First, install the dataset-dictionary package from the command line, like so:

````
mrt add dataset-dictionary
````

Alternatively, if you'd like to bypass Atmosphere, and install directly from GitHub, you could update your application's smart.json file, like so:

````
{
  "meteor": {
    "branch": "master"
  },
  "packages": {
    "dataset-dictionary": {
      "git": "https://github.com/awatson1978/dataset-dictionary.git"
    }
  }
}

````

------------------------
### Data/Document Model

Second, you'll want to add some templates into your document model:

````html
<!--
<template name="usersListTemplate">
    <input id="customerSearchInput" type="text" placeholder="Filter..."></input>
    {{#each userList}}
    {{> userListItemTemplate }}
    {{/each}}
</template>

<template name="userListItemTemplate">
    <li class="list-group-item">{{FirstName}} {{LastName}}</div></li>
</template>
-->

````



------------------------
### Controller

Third, populate the template with data

````js

//Template.usersListTemplate.userList = function(){
//    return CustomerAccounts.find({
//        $or: [
//            {'FirstName': { $regex: Session.get('user_search_term'), $options: 'i' }},
//            {'LastName':  { $regex: Session.get('user_search_term'), $options: 'i' }}
//        ]
//    },{limit: 20});
//};
//Template.userListItemTemplate.events({
//    'click .list-group-item':function(event, template){
//        Session.set('selected_user', this._id);
//    },
//    'keyup #customerSearchInput': function(evt,tmpl){
//        try{
//            Session.set('user_search_term', $('#customerSearchInput').val());
//            Meteor.flush();
//        }catch(err){
//            console.log(err);
//        }
//    }
//});

````


------------------------
### Licensing

MIT License. Use as you wish, including for commercial purposes.
See license.mit.txt for full details.



English Language Dictionary
================================

This repository houses the contents of Webster's Unabridged English Dictionary.

The dictionary can be found in plain text form [here](http://www.gutenberg.org/ebooks/29765)

You'll also find some julia files that were used to parse the text and organize it into the nice
json you see here.

# Contents
- dictionary.json: This is the raw data scraped from the dictionary. Unsurprisingly, it's in the format
of a dictionary, i.e. ```{ "Word": "Definition" }```
- graph.json: This is a graph representation of the dictionary. Each word is paired with a list of the
words that define it
- dictionary.txt: This is the plain text file (I converted it from ISO-8859-1 to UTF-8)

# License
Creative Commons Attribution-NonCommerical 3.0 Unported

![](http://i.creativecommons.org/l/by-nc/3.0/88x31.png)

[Creative Commons Attribution-NonCommercial 3.0 Unported Licencse](http://creativecommons.org/licenses/by-nc/3.0/deed.en_US)
