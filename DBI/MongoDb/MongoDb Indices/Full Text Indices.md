Wird verwendet, um einen ganzen Text in bestimmten Feldern suchen zu können. Die Sprache des [[MongoDb Indices Allgemein|Indixes]] muss angegeben werden. Der [[MongoDb Indices Allgemein|Index]] ist entweder auf Größe oder Performance optimiert.

**Erstellen eines Full Text Indexes**
Muss beim [[Indices Erstellung|Erstellen]] angegeben werden:
```>db.tweets.createIndex({"text":"text"},{default_language:"english"})```

**Verwenden eines Full Text Indexes**
```db.tweets.find({$text: {$search: "americans"}},{text:1})```

![[full-text-search.png]]

---

>[!cite]-
> ## Originale Quellen
> technique for searching a collection for full text in string fields or
arrays of strings
• language of text needs to be considered
• trade off between search performance and size/maintenance of index
>db.museum.createIndex({"properties.NAME":"text"},{default_language:"german"})
>db.tweets.createIndex({"text":"text"},{default_language:"english"})
>• $text query operator
• needs a text index
• search also based on stemming!
>db.tweets.find({$text: {$search: "americans"}},{text:1})
>db.tweets.find({$text: {$search: "waiting"}},{text:1})