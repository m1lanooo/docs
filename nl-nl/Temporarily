# API Referentie

Elke node in de Neo-CLI biedt een API-interface voor het verkrijgen van blockchain-gegevens van een node. waardoor het makkelijk is om blockchain-applicaties te ontwikkelen. De interface wordt geleverd via JSON-RPC, en het onderliggende protocol maakt gebruik van HTTP / HTTPS om te kunnen communiceren. Om een knooppunt te starten met RPC-service wordt de volgende opdracht uitgevoerd:

`dotnet neo-cli.dll /rpc`

Om toegang te krijgen tot de RPC-server via HTTPS moet u het configuratiebestand config.json wijzigen. Dit moet gebeuren voordat u de node kunt starten om de domeinnaam, het certificaat en wachtwoord in te kunnen instellen:

```json
{
  "ApplicationConfiguration": {
    "DataDirectoryPath": "Chain",
    "NodePort": 10333,
    "WsPort": 10334,
    "UriPrefix": [ "https://*:10331", "http://*:10332" ],
    "SslCert": "YourSslCertFile.xxx",
    "SslCertPassword": "YourPassword"
  }
}                                          
```

Nadat de JSON-RPC-server is gestart zal het de volgende poorten controleren die met de hoofd- en testnetten corresponderen:

Voor P2P en WebSocket informatie zie [Node/Introduction](introduction.md)。

|                | （Main Net） | （Test Net） |
| -------------- | ------------ | ------------- |
| JSON-RPC HTTPS | 10331        | 20331         |
| JSON-RPC HTTP  | 10332        | 20332         |

## Commando Lijst

| Commando                                       | Referentie                                      | Uitleg                         | Comments       |
| ---------------------------------------- | --------------------------------------- | -------------------------- | -------- |
| [getbalance](api/getbalance.md)          | \<asset_id>                             |Geeft het saldo van het overeenkomstige actief in de portemonnee op volgens het opgegeven activa nummer.   | De portemonnee moet hierbij geopend worden   |
| [getbestblockhash](api/getbestblockhash.md) |                                         | Krijgt de hash van het langste blok in de hoofdketen           |          |
| [getblock](api/getblock.md)              | \<hash> [verbose=0]                     | Returns the corresponding block information according to the specified hash value         |          |
| [getblock](api/getblock2.md)             | \<index> [verbose=0]                    | Geeft de bijbehorende blokinformatie terug volgens de opgegeven hashwaarde          |          |
| [getblockcount](api/getblockcount.md)    |                                         | Krijgt het aantal blokken in de hoofdketen                 |          |
| [getblockhash](api/getblockhash.md)      | \<index>                                | Retouneert de hashwaarde van het corresponderende blok op basis van de opgegeven index
         |          |
| [getconnectioncount](api/getconnectioncount.md) |                                         | Ontvang het huidige aantal verbindingen voor de node                 |          |
| [getrawmempool](api/getrawmempool.md)    |                                         | Krijg een lijst van niet-erkende transacties in het geheugen            |          |
| [getrawtransaction](api/getrawtransaction.md) | \<txid> [verbose=0]                     | Retourneert de bijbehorende transactiegegevens op basis van de opgegeven hashwaarde         |          |
| [gettxout](api/gettxout.md)              | \<txid> \<n>                            | Retourneert de bijbehorende transactieuitvoer (verandering) informatie op basis van de opgegeven hash en index |          |
| [sendrawtransaction](api/sendrawtransaction.md) | \<hex>                                  | Zendt een transactie over het netwerk uit. Zie de documentatie [netwerkprotocol] (network-protocol.md)                       |          |
| [sendtoaddress](api/sendtoaddress.md)    | \<asset_id> \<address> \<value> [fee=0] | Overboeken naar een specifiek adres                     | De portemonnee moet hierbij geopend worden   |
| submitblock                              | \<hex>                                  | Indienne nieuwe blokken                      | Moet een consensus node zijn |

## GET aanvraag voorbeeld

Een typisch JSON-RPC GET aanvraag formaat gaat als volgt:

Hieronder vindt men een voorbeeld hoe u het aantal blokken in de hoofdketen kunt krijgen.

Verzoek URL:

```
http://somewebsite.com:10332?jsonrpc=2.0&method=getblockcount&params=[]&id=1
```

Nadat u het verzoek heeft verzonden, krijgt u het volgende antwoord:

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": 909129
}
```

## POST aanvraag voorbeeld

Het formaat van een typische JSON-RPC Post aanvraag is als volgt:

Hieronder vindt men een voorbeeld hoe u het aantal blokken in de hoofdketen kunt krijgen.

Aanvraag URL:

```
http://somewebsite.com:10332
```

Request Body：

```json
{
  "jsonrpc": "2.0",
  "method": "getblockcount",
  "params":[],
  "id": 1
}
```

Nadat u het verzoek heeft verzonden, krijgt u het volgende antwoord：

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": 909122
}
```

## Test tools

U kunt de Chrome-extensie in Postman gebruiken om de test te vergemakkelijken (installatie van de Chrome-extensie vereist een wetenschappelijk internet), de volgende afbeelding is een test screenshot:

![image](http://docs.neo.org/images/2017-05-17_17-06-20.jpg)

![image](http://docs.neo.org/images/2017-05-17_16-55-58.jpg)

## Overige

[C# JSON-RPC Command List](https://github.com/chenzhitong/CSharp-JSON-RPC/blob/master/json_rpc/Program.cs)
