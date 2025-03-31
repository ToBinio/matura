### Lightweight Directory Access Protocol 

Aktuelle Version ist 3. Unterschiede zu Version 2:
- Authentifizierung mittels SASL (Simple Authentication and Security Layer)
- Verschlüsselung von Daten mittels TLS
- UTF-8
- Einrichten von Aliase

LDAPv3 ist nicht mit LDAPv2 kompatibel.

Anwendungsbereiche von LDAP:
- Grundlage von [[Active Directory|Microsoft Active Directories]]
- Ressourcenverwaltung
- Single Sign On
- Verwaltung von Benutzern, Gruppen und Rechnern
- Verwaltung von IP-Adressen
- Verwaltung von DHCP Informationen

### Allgemeiner LDAP Aufbau
Besteht aus Objekten inkl. Klassen, Vererbung und Polymorphie. LDAP bildet diese Objekte ab und bringt sie miteinander in Beziehung.

Ein Verzeichniseintrag besitzt mehrere Attribute, welche das Objekt definieren. Der "Distinguished Name" ist die eindeutige Kennung eines Eintrags. 

### Objektarten
Grundsätzlich kann zwischen Containerobjekten und Blättern unterschieden werden. 
![[ldap_structure.png.png]]

#### Container
In Containern, kurz "ou", können weitere Objekte erzeugt werden. Weitere Beispiele: c (company), o (organisation) und dc (domain component).

#### Blätter (Leafs)
Blätter, kurz "cn" oder "uid", dienen zur Verwaltung von Ressourcen, z.B. Benutzer "uid=Stefan".
In LDAP können innerhalb von Blättern weitere Objekte erstellt werden.

### Attribute
Je nachdem, um welches konkrete Objekt es sich handelt, besitzt diesen unterschiedliche Attribute:
![[object_attributes.png]]

Attribute besitzen einen Namen und eine unterschiedliche Anzahl an Werten. Es gibt sowohl benötigte (MUST), als auch optionale Attribute (MAY):
![[optional_attributes.png]]

#### Attributtypen
Attribute werden als AttributTypen gespeichert, separat vom Objekt.
Aufbau eines Attributtypes:
- Name
- OID (Object Identifier)
- Beschreibung
- Optionale Regeln für die Suche (EQUALITY, SUBSTR, ORDERING)
- Syntaxbeschreibung in Form einer OID
- Qualifier (SINGLE-VALUE, COLLECTIVE, LENGTH zur Einschränkung der Länge)
![[attribute_type.png]]

### Verzeichniseinträge
Verzeichniseinträge stellen Instanzen von Objekten dar.

#### Vererbung
Ein Objekt kann Subklassen besitzen, welche die Attribute erben.

#### Polymorphie
Ein Objekt kann von mehreren Objekten erben, da objectClass ein multi-value Attribut ist. 
In LDAP muss ein Objekt entweder die Klasse "top" (reales Objekt) oder "alias" (Verweis) sein.

### DIT (Directory Information Tree)
Die Baumstruktur im [[NSCS/Verzeichnisdienste/X.500|X.500 Standard]] wird als DIT (Directory Information Tree) bezeichnet. Hier kann die Administration auf Unterbäume eingeschränkt werden.

Der DN (Distinguished Name) setzt sich aus mehreren RDN (Relative Distinguished Name) zusammen. Ein RDN kann aus mehreren Attributen bestehen. Der DN ist Vergleichbar mit einem Absoluten Pfad in einem Dateisystem. 

Der CN (Common Name) wird verwendet, um Objekten Namen zu geben (z.B. Vor- und Nachname bei Benutzern):
![[dn_rdn.png]]

Zusammengesetzter DN für beide Peters aus den RDNs:
![[concatinated_dn.png]]

### Schema
In einem Schema sind folgende Dinge textorientiert (Textdatei) definiert:
- verwendete Attributtypen
- verwendete Objektklassen
- Filter- und Matchingregeln bei Vergleichsoperationen
- Rechte zum Anlegen oder Modifizieren von Datensätzen

#### Schema-Dateien
Schemadateien enden mit der Dateiendung .schema:
- core.schema (Betrieb des LDAP-Servers)
- cosine.schema (Grundlegende Objektklassen und Attribute)
- inetorgperson.schema (Benutzerverwaltung)
- samba.schema (Für SambaServer, ka)

Aufgrund von Abhängigkeiten ist die Ladereihenfolge der Schema wichtig.

### LDIF-Dateien
LDIF-Dateien (LDAP Data Interchange Format) werden verwendet, um LDAP-Befehle textmäßig darzustellen. Sie besitzt eine Key-Value Struktur.

Zum erstellen muss der neue DN eingetragen werden, sowie die Objektklasse und die Attribute:
![[ldif_create.png]]
Hier wird implizit der changetype "add" verwendet:
![[ldif_change.png]]

Soll ein Eintrag geändert oder gelöscht werden, muss der changetype "modify" verwendet werden:
![[ldif_add.png]]
Löschen von Attributen:
![[ldif_delete.png]]