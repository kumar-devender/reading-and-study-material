#### Index
* A collection of documents.
* An index can have multiple type of documents.
An index is a logical namespace that maps to one or more primary shards and can have zero or more replica shards.
#### Type(deprecated from elastic 7 version)
* A type used to represent the type of document, e.g. an email, a user, or a tweet
* you can still achieve type in two way
  * Create index for each type
  * If you do not want to create index for each type then add custom field `type` in your document. 
