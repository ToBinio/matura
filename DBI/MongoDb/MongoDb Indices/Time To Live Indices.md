Muss beim [[Indices Erstellung|Erstellen]] angegeben werden. Wird auf Datumsfelder angewandt, um Dokumente nach einer bestimmten Zeit zu löschen:
```>db.people.createIndex({"lastModified":1},{expireAfterSeconds:120})```

---

>[!cite]-
> ## Originale Quellen
> Index Types: TTL Index
• Time To Live
• allows to define a time span after that documents are deleted from a
collection
• index can be created on date fields
• every 60s MongoDB checks whether the field value exceeds the
treshhold
>db.people.createIndex({"lastModified":1},{expireAfterSeconds:120})