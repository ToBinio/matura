Indices sind eine Datenstruktur, um Daten effizient zu finden.

Teilweise müssen Abfragen eine ganze Collection abzufragen. Mit Indices wird versucht, die zu untersuchenden Dokumente zu verringern. Hierfür werden B-Bäume verwendet.

**Einstufung von Indices**
- [[Primäre Indices|Primäre Indices]]
- [[Sekundäre Indices|Sekundäre Indices]]
- Single Field Index
	- Ein Feld
- Compound Index
	- Mehrere Felder
- Multi Key Index (limitiert auf einen)
	- Index auf einem Array-Element
	- ```db.people.createIndex({"hobbies":1})```
	

**Typen von Indices**
- Standart
	- Auf den Wert des Felds, sortiert
- [[Hash Indices|Hash Indices]]
- [[Full Text Indices|Full-Text Search]]
- [[Time To Live Indices|Time To Live Indices]]

Für das [[Indices Erstellung|Erstellen von Indices]] stellt MongoDb Funktionen zur verfügung.

Die Storage Engine sucht sich selber aus, welchen Index sie verwendet. Mittels Hint kann angegeben werden, welcher verwendet werden soll.

---

>[!cite]-
> ## Originale Quellen
> https://moodle.htlstp.ac.at/pluginfile.php/45361/mod_resource/content/0/DBI5%2005%20MongoDB%20Indexes.pdf
>
> "Indexes are special data structures that store a small portion of the
total amount of data in an easy-to-search form."
>
> Indexes in MongoDB
What is a collection
scan?
• problem statement
• MongoDB must perform a collection scan to find the documents that match a
query
• goal
• reduce the number of documents to inspect when a query is executed
• MongoDB uses B-tree structures for indexes
• specific fields or sets of fields of the documents ordered by value
• allows efficient range-based sorting and traversal 
Index Types: Single Field Index
• index based on one field
MaxKey MinKey
singlefield_idx
>db.tweets.find({"user.friends_count":{$gt:500}}).explain()
>db.tweets.find({"user.friends_count":300}).explain()
db.tweets.find().sort({"user.friends_count":-1}).explain()
db.tweets.find().sort({"user.friends_count":1}).explain()
>
> • based on set of fields
> • order of fields matter
> • support for queries depends on nature of
> query
> ZZZ 1
> ZZZ 2
> ZZZ 3
> ...
> MMM 8
> MMM 10
>db.tweets.createIndex(
{"source":-1,
"user.statuses_count":1
},
{"name":"compound_idx"}
1st sort criteria
2nd sort criteria
MMM 40
...
AAA 5
)
AAA 7
AAA 12
>db.tweets.createIndex({"source":-1, "user.statuses_count":1})
ZZZ ZZZ >db.tweets.find({"source":{$not:{$in:[null]}}})
ZZZ ...
MMM >db.tweets.find({"user.statuses_count":{$gt:4000},"source":{$not:{$in:[null]}}})
MMM MMM >db.tweets.find({"user.statuses_count":{$gt:4000}})
...
>db.tweets.find().sort({"source":-1,"user.statuses_count":-1})
AAA AAA >db.tweets.find({"user.statuses_count":{$gt:4000}}).sort({"source":1})
AAA NULL >db.tweets.find({"user.friends_count":{$gt:4000}}).sort({"source":1})
NULL count
(1)
1100
3331
4050
3001
4008
4010
3000
4100
4200
NULL
NULL
>db.tweets.createIndex({"user.friends_count":-1},{"name":"singlefield_idx"})
>db.tweets.createIndex({"source":-1, "user.statuses_count":1})
>db.tweets.find({"user.friends_count":{$gt:4000}}).sort({"source":1})
can be used to create an index using the values of an array field
• index values for each element of the array, pointing at the same
document
• not possible to use more than one array field in compound indexes
hobbies_1
>db.people.createIndex({"hobbies":1})
...
skating
{"name":"Anna",
"hobbies":
["skiing",
"skating",
"swimming"],
"score": [3,100],
...
}
>db.people.find({"score":{$gt:90},"hobbies":"hiking"})
skiing
skiing
>db.people.createIndex({"hobbies":1,"score":1})
>Ensure that indexes fit in
RAM!
>db.tweets.totalIndexSize()
Know your queries!
Use indexes to speed up
sorting!
Build selective queries and
indexes!
Summary
After this lesson you ...
... can design and create indexes to support efficient queries in
MongoDB.
... can explain the different types of indexes in MongoDB.
... can explain how a full-text search basically works.
... know the concept of hashing.
References
ID Name [MOD21] mongoDB | Documentation [TREL14] MongoDB - Der praktische Einstieg [MUN21] M001: MongoDB Basics
Learn the fundamentals of MongoDB
Online Course
[WIKI01] Wikipedia: Stemming [WIKI02] Wikipedia: Full-text search [WIKI03] Wikipedia: Hash function [WEB01] The list of stop words Quellverweis (Link, ISBN ...)
>  https://docs.mongodb.com/manual/
Tobias Trelle, dpunkt.verlag GmbH, 1. Auflage 2014
> ISBN 978-3-86490-153-9
> https://university.mongodb.com/courses/M001/about
> https://en.wikipedia.org/wiki/Stemming
> https://en.wikipedia.org/wiki/Full-text_search
> https://en.wikipedia.org/wiki/Hash_function
> https://countwordsfree.com/stopwords
