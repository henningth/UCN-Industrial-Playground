# UCN-Industrial-Playground
Projektbeskrivelse 

 

### Opgave: Tracking af produktionsproces. Sikring at et produkt kommer hele vejen rundt. 

Vi bruger RFID tags på hver station i produktionslinjen, og selve produktet som bliver fremstillet er modelleret med selve M5 Core2. 

Vi har tilkoblet RFID2 sensor på I2C, og denne kan læse og skrive Mifare RFID tags.  

Meningen er så, at når produktet går igennem produktionsprocessen, og standser ved en station (RFID tag), skal M2 Core2 læse data.  

Dette data er dog krypteret, og man kan kun læse det med den rigtige krypteringsnøgle. Denne kryptering og dekryptering bliver lavet med ATECC608B-TNGTLSU-G. 

Data (logs) skal sendes op i skyen. 

 

### Vigtige information og oplysninger 

ATECC608B-kort: I2C-adressen er 53(0x35). Blockly har en fejl, der indsætter I2C init-kode efter den er kaldte 
– mere nøjagtigt sagt er problemet at labels osv. kan være sat ind i micropython ovenpå I2C-koden – se billed. 

![I2C init-kode er sat ind lavere end label-kode, der referer til I2C-enheden](screenshot_2022-08-06_at_09_27_11_bFuuP9yWNx.avif) 

Løsningen er at flytte koden til det rette sted – det er endnu ikke klar om koden (og dermed fejlen) bliver gendannet, når man ændrer på Blockly-koden. 

 

### Kodning og dokumentation 

GitHub vs. Teams, ~~hvordan gør vi med versionsstyring? Bedst at bruge GitHub.~~ 
GitHubt bliver brugt for dokumentation.
Teams trafik (Lasse, Steffen, og René) henvises til GitHub.
VSCode med PlatformIO og Arduino Framework er valgt som udviklingsplatform.
