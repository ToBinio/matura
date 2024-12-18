**Erstellen eines Hash Indexes**
Muss beim [[Indices Erstellung|Erstellen]] angegeben werden:
```>db.tweets.createIndex({"user.screen_name":"hashed"})```

**Hash Werte**
Eine Hash-Funktion convert jeden beliebigen Wert in einen Hash-Wert mit fixer Länge. Der ursprüngliche Wert ist nicht aus dem Hash extrahierbar. Ein kleiner Unterschied generiert einen sehr unterschiedlichen Hash.

**Load Factor**
Gibt an, wieviel % der Hashes schon verwendet worden sind:
```Anzahl verwendeter Hashes / Anzahl aller Hashes```

**Verwendung Hash Indices**
Bieten höhe Leistung, wenn man eine Abfrage auf genaue Wertübereinstimmungen hat. Z.B. Name

---

>[!cite]-
> ## Originale Quellen
> to map data of arbitrary size to
fixed-size values
• input set >> target set
⇒hash functions are not injective
• hash values are often scalars (ϵℕ)
• similar key values should result in
very different hash values
ℎ: 𝐾 → 𝑆
𝐾 → |𝑆|
set of values that can be hashed: K
possible hash values: S
used keys:
𝐾′ ⊆ 𝐾
used hash values:
𝑆′ ≔ {ℎ(𝑘)|𝑘 ∈ 𝐾′}
...
Max Muster
7
8
Ali Auer
9
h(k)
10
Barbara Bubenik
...
Georg Ganz
14
|𝑆′|
...
load factor: 𝛽 =
|𝑆|
performance increase only for exact match queries
>db.tweets.createIndex({"user.screen_name":"hashed"})
>db.tweets.find({"user.screen_name":"Engineerious"})
