**Erstellen von Indices**
Um [[Sekundäre Indices|sekundäre Indices]] zu erstellen gibt es folgenden Befehl:
```db.collection.createIndex(key_data, options)```

key_data sind die Felder, auf denen der [[MongoDb Indices Allgemein|Index]] angewandt wird, mit jeweils 1 für auf- und -1 für absteigend. In den Optionen kann dann z.B. der Name gesetzt werden, oder ob die Felder unique sein sollen.

**Löschen von Indices**
Hierfür gibt es die Befehle:
```db.collection.dropIndex(index)```
und
```db.collection.dropIndexes(indexes)```

Indexes kann entweder der Name, oder die zuvor übergebene key_data sein. Fürs updaten muss immer gelöscht und erstellt werden.

---

>[!cite]-
> ## Originale Quellen
> db.collection.createIndex(
> \<key and index type\>
> \<options\>)
> db.tweets.createIndex({"user.friends_count":-1},
> {name:"friendsDescIdx"})
> [
> db.collection.getIndexes()
> { v: 2, key: { _id: 1 }, name: '_id_' },
> {
>db.tweets.getIndexes()
> name generated if not
> provided
> v: 2,
> key: { 'user.friends_count': -1 },
> name: 'friendsDescIdx'
>
> 
> }
> ]
> 
> parameter type description
unique boolean if true, the collection won't accept documents where the field index
key value matches an existing value in the index, default is false
name string index name decided by user, otherwise default naming
partialFilterExpression document include only documents in the index that match the filter criteria in
the expression
sparse boolean include only documents where the key fields exist, default is false
expireAfterSeconds integer for TTL indexes only, allows to define that documents have to be
removed from the collection after a certain time span
db.collection.dropIndex(
> \<index\>)
> db.collection.dropIndexes(
> \<indexes\>)
> db.tweets.dropIndex({"user.friends_count":-1})
> db.tweets.dropIndex("friendsDescIdx")
> db.tweets.dropIndexes()
> • no update function
> • you need to drop and recreate the
> index