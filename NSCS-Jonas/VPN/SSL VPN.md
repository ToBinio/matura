Verwendet die [[Public Key Infrastructure|Public Key Infrastructure]]. Gründe für/gegen [[SSL|SSL]]:

| Feature                  | IPSec     | [[SSL\|SSL]] |
|--------------------------|-----------|--------------|
| Program-Unterstützung    | Groß      | Limitiert    |
| Authentifizierungsstärke | Stark     | Mittel       |
| Verschlüsselungsstärke   | Start     | Mittel-Stark |
| Verbindungskomplexität   | Mittel    | Niedrig      |
| Verbindungsoptionen      | Limitiert | Groß         |

---

> [!cite]-
> ## Originale Quelle
> SSL uses the public key infrastructure and digital certificates to authenticate peers. The type of VPN method implemented is based on the access requirements of the users and the organization’s IT processes. The table compares IPsec and SSL remote access deployments.
>
> |Feature|IPsec|SSL|
> |Applications supported|Extensive – All IP-based applications|Limited – Only web-based applications and file sharing|
> |Authentication strength|Strong – Two-way authentication with shared keys or digital certificates|Moderate – one-way or two-way authentication|
> |Encryption strength|Strong – Key lengths 56 – 256 bits|Moderate to strong - Key lengths 40 – 256 bits|
> |Connection complexity|Medium – Requires VPN client installed on a host|Low – Requires web browser on a host|
> |Connection option|Limited – Only specific devices with specific configurations can connect|Extensive – Any device with a web browser can connect|