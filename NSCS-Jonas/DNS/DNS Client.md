Zuerst wird die [[Hosts-Datei|Hosts-Datei]] angeschaut, bevor der [[DNS Allgemein|DNS]] angefragt wird. Als es kein [[DNS Allgemein|DNS]] gab, wurde nur die [[Hosts-Datei|Hosts-Datei]] für die Auflösung verwendet und automatisch vom Internet aktualisiert.

---
> [!cite]-
> ## Originale Quelle
 >Dieser sucht zuerst in der /etc/hosts (Windows: %windir%\system32\drivers\etc ) ob dort eine IP zu der Domain zu finden ist, wenn nicht, wird die Anfrage an die im System konfigurierten DNS Server gestellt. Die hosts Datei war der Vorläufer vom DNS System, diese Datei wurde manuell auf jedem Rechner im Netzwerk aktualisiert. Nach dem das Internet gewachsen ist, war dies nicht mehr möglich.