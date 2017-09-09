# CLI Opdracht Referentie

Open de opdrachtregel, navigeer naar de map waar het programma zich bevindt en voer de volgende code in om de opdrachtregelsportemonnee te starten (i.e. de NEO node).

`dotnet neo-cli.dll`

Deze handleiding zal alle commando's in de opdrachtsregel van de portemonnee invoeren. U kunt uw portemonnee manipuleren door middel van commando's voor het maken van een nieuwe portemonnee, het importeren en exporteren van een privé-sleutel, het maken van overdracht, en nog veel meer.

We zullen eerst de verschillende opdrachten in de opdrachtregel verkennen. In de opdrachtregel voert u `help` in, gevolgd door een retouropdracht, en u zult, zoals afgebeeld, een lijst met commando's zien.

![image](/assets/cli_2.png)

Het volgende is een beschrijving van alle commando's en de volgorde van de brackets:
Angular brackets ``<> `` Geef een parameter aan.
Square brackets`[]`is voor optionele parameters.
Het symbool `|` geeft de parameters weer, die van elk type kunnen zijn.
Het gelijk teken `=` geeft de standaardwaarde van de optionele parameter aan zonder een invoer.

## 1. Console Instructies

| Opdracht      | Functie Beschrijving      |
| ------- | --------- |
| versie | Toont de huidige software versie |
| legen    | Help menu      |
| clear   | Leeg screen      |
| exit    | Exit programma      |

## 2. Wallet instelling

Opdrcht | Functie Beschrijving | Opmerkingen |
| m--------------------------------------- | -------------------------------- | ------ |
| Maak wallet \<path> | Maak wallet bestand |
| open wallet \<path> | Open wallet bestand |
| stel wallet index opnieuw in | | Portomonnee moet hierbij geopend worden |
| noteer alle accounts in de portemonnee  | | Portomonnee moet hierbij geopend worden |
| noteer activa | Noteer all activa in the wallet | Portomonnee moet hierbij geopend worden |
| noteer key | Noteer alle publieke keys in uw wallet | Portomonnee moet hierbij geopend worden |
| creëer address [n = 1] | Creëer adres / creëer adres in grote aantallen | Portomonnee moet hierbij geopend worden |
| importeer key \<wif\|path> | Importeer private key / bulk import vn private keys | Portomonnee moet hierbij geopend worden |
| exporteer key \[address] [path] | Exporteer private key | Portomonnee moet hierbij geopend worden |
| stuur \<id\|alias> \<address> \<value> [fee=0]| Stuur naar een specifiek adres | Portomonnee moet hierbij geopend worden |

De volgende commando's worden uitvoerig toegelicht:

👉 `stel index opnieuw in`

Deze opdracht wordt gebruikt om de portemonnee index te herstellen.
Waarom is het nodig om de portemonnee index te herstellen?

Er is een veld in de portemonnee die de hoogte van het huidige synchronisatieblok van de portefeuille opneemt. Voor elke nieuwe blok, synchroniseert de portemonnee de blokken en worden de activa en transacties in de portemonnee vervolgens geupdate. Uitgaande van het feit dat de huidige geregistreerde blokhoogte 100 is, voert u de invoercode opdracht uit om de privé-sleutel te importeren. De portemonnee berekent nog steeds uw activa uit de blokhoogte van 100. Als het geïmporteerde adres enkele transacties heeft wanneer de blokhoogte minder is dan 100, zullen de transacties en de bijbehorende activa niet in de portemonnee worden weergegeven. De index van de portemonnee  moet hierdoor hersteld worden, waardoor de portemonnee wordt gedwongen om uw activa uit de blokhoogte van 0 te berekenen.

De nieuw gemaakte wallet hoeft niet de wallet index te herstellen, alleen de geïmporteerde privé-sleutel is nodig om de wallet index opnieuw te kunnen opbouwen.

👉 `create address [n = 1]`

 Deze opdracht gebruikt worden om een nieuw adres te maken. Men kan ook ‘create 100 addresses’ om 100 nieuwe adressen in te maken; Grote hoeveelheden van nieuwe adressen worden automatisch geëxporteerd naar het adres.txt bestand.

👉 `export sleutel [address] [path]`

U kunt opgeven welke adressen u de bijbehorende privé-sleutels naar wilt exporteren. U kunt ook de uitvoer opgeven naar het opgegeven bestand. (Zie hieronder voor voorbeelden). Deze commando vereist ook de verificatie van het wallet wachtwoord.

Export sleutel

Export sleutel AeSHyuirtXbfZbFik6SiBW2BEj7GK3N62b

Export sleutel key.txt

Export sleutel AeSHyuirtXbfZbFik6SiBW2BEj7GK3N62b key.txt

👉 `importeer sleutel <wif | path>`

Bij het importeren van de privé-sleutel kunt u opgeven om een privé-sleutel te importeren of een bestand te importeren met een aantal privé-sleutels. (De volgende opdrachten zijn geldig)

Importeer sleutel L4zRFphDJpLzXZzYrYKvUoz1LkhZprS5pTYywFqTJT2EcmWPPpPH

Importeer sleutel key.txt

Als er een specifiek bestand is, is het bestand in het privé-sleutelformaat. Raadpleeg hiervoor de exporteer sleutel key.txt uitvoer.

👉 `send <id | alias> <address> <value> [fee = 0]`

Voor transfers zijn er in totaal vier parameters. De eerste parameter is het activa-ID, de tweede parameter is het betalingsadres, de derde parameter is het overdrachtsbedrag en de vierde parameter is de vergoeding. (Deze parameter kan leeg worden gelaten, en de standaardwaarde is hierbij 0). De opdracht moet het wallet wachtwoord verifiëren. Om bijvoorbeeld 100 NEO naar het adres "AeSHyuirtXbfZbFik6SiBW2BEj7GK3N62b" over te brengen, zou men de volgende opdrcht moeten invoeren.

Stuur c56f33fc6ecfcd0c225c4ab356fee59390af8560be0e930faebe74a6daff7c9b AeSHyuirtXbfZbFik6SiBW2BEj7GK3N62b 100

Als u niet zeker bent de iD van uw activa, vul dan het commando-lijst in om alle activa in de portemonnee te bekijken.

## 3. Bekijk de node informatie

Command | Functie Beschrijving |
| ---------- | ----------------------- |
toon staat | Geeft de huidige status van de blokchainsynchronisatie weer
toon node | Geeft het adres en de poort van de aangesloten node weer |
toon pool | Toont de transacties in het geheugen pool (deze transacties hebben nul bevestiging)
## 4. Geadvanceerde instructies

Commando | Functie Beschrijving |
| --------------- | ---- |
Start consensus | Begin consensus
Begin de consensus met het uitgangspunt dat de portemonnee een consensusautoriteit heeft, waardoor de consensus macht via het stemmen op het hoofdnet kan worden verkregen. Als een private keten wordt ingezet, kan de publieke sleutel van de consensus worden opgezet in de `protocol.json`. Raadpleeg de [Private chain] (private-chain.md) voor meer informatie.
