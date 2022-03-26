# Mini Challenge Internet Security
# Funzioni Hash
Una funzione hash è una funzione di mappatura tra dati di arbitraria lunghezza e valori di lunghezza fissa, anche chiamati **hash values**, **hash codes**, **digests**, o semplicemente **hashes**.
Le funzioni hash mappano un insieme in input di cardinalità nettamente superiore rispetto all'output, questo comporta inevitabilmente collisioni, dimostrato dal teorema dei cassetti, quindi una metrica da analizzare quando si parla di funzioni hash è proprio la probabilità di collissione.

L'uso delle funzioni hash si basa sulle proprietà statistiche della relazione tra chiave e funzione:

- nel caso peggiore si ha elevatissima probabiltà di collisioni, ma il caso peggiore stesso ha probabilità inifitamente piccola
- nel caso medio si ha collisione minima

Le funzioni di hash sono collegate a (e spesso confuse con) **checksum**, **check digits**, **fingerprints**, **compressione lossy**, **funzioni di randomizzazione**, **error-correcting codes** e **cifrari**. Anche se i concetti si sovrappongono in una certa misura, ognuno ha i propri usi e requisiti ed è progettato e ottimizzato in modo diverso. La funzione hash differisce da questi concetti principalmente in termini di integrità dei dati.
## Funzioni Hash in sicurezza informatica
Nella sicurezza informatica le funzioni hash utilizzate devono essere crittografiche, quindi rispettare le seguenti proprietà:

- deve essere *deterministica*:
  dato lo stesso input darà **sempre** lo stesso output
- è *efficente* da computare per ogni dato input
- deve essere *difficile* invertire il processo (**Pre-image resistance**):
  deve essere *difficile* generare un messaggio che produce un predeterminato **digest**
- deve essere *difficile* generare una *collisione*:
  - **Second pre-image resistance**
    dato un input, deve essere difficile trovare un diverso input che risulti nello stesso **digest**; questa proprietà è talvolta indicata come **weak collision resistance**.
  - **Collision resistance**
    deve essere difficile trovare due messaggi diversi che risultino nello stesso **digest**; questa proprietà è talvolta indicata come **strong collision resistance**.
    Una coppia di messaggi che genera lo stesso **digest** è chiamata **cryptographic hash collision**.
- gode della proprietà crittografica **avalanche effect**:
  una piccola modifica all'input genera un **digest** drasticamente diverso dall'originale, al punto che i due **digest** appaiono non correlati tra loro

La **collision resistance** implica la **Second pre-image resistance**, ma non implica la **Pre-image resistance**. L'assunzione più debole è sempre preferita nella crittografia teorica, ma in pratica, una funzione hash che è solo **Second pre-image resistant** è considerata insicura e quindi non è raccomandata per applicazioni reali.
### Grado di difficoltà
Nella crittografia pratica, *"difficile"* significa generalmente *"quasi certamente al di fuori della portata di qualsiasi avversario a cui deve essere impedito di violare il sistema per tutto il tempo in cui la sicurezza del sistema è considerata importante"*. Il significato del termine è quindi in qualche modo dipendente dall'applicazione, poiché lo sforzo che un agente maligno può mettere nel compito è di solito proporzionale al suo guadagno atteso.
Tuttavia, poiché lo sforzo necessario di solito si moltiplica con la lunghezza del digest, anche un vantaggio di mille volte nella potenza di elaborazione può essere neutralizzato aggiungendo qualche decina di bit a quest'ultimo.

In alcune analisi teoriche "difficile" ha un significato matematico specifico: *"non risolvibile in tempo polinomiale asintotico "*). Tali interpretazioni di *difficoltà* sono importanti nello studio di funzioni hash crittografiche provatamente sicure, ma di solito non hanno una forte connessione con la sicurezza pratica. Per esempio, un algoritmo a tempo esponenziale può a volte essere ancora abbastanza veloce per fare un attacco fattibile. Al contrario, un algoritmo a tempo polinomiale (ad esempio, uno che richiede $20n$ passi per chiavi di $n$ cifre) può essere troppo lento per qualsiasi uso pratico.
### Utilizzo
- Verifica dell'integrità dei messaggi e dei file[.](https://en.wikipedia.org/wiki/File_verification "File verification")
  Un'importante applicazione degli hash sicuri è la verifica dell'integrità dei messaggi. Confrontando i digest dei messaggi (digest dell'hash sul messaggio) calcolati prima e dopo la trasmissione, si può determinare se sono state fatte delle modifiche al messaggio o al file.
- Generazione e verifica di signatures[.](https://en.wikipedia.org/wiki/Digital_signature "Digital signature")
  Quasi tutti gli schemi di firma digitale richiedono il calcolo di un hash crittografico sul messaggio. La proprietà di integrità del messaggio dell'hash crittografico è usata per creare schemi di firma digitale sicuri ed efficienti.
- Verifica della password[.](https://en.wikipedia.org/wiki/Password_hashing "Password hashing")
  La verifica delle password si basa comunemente sugli hash crittografici. Per autenticare un utente, la password presentata dall'utente viene sottoposta a hash e confrontata con l'hash memorizzato. Un metodo di reimpostazione della password è necessario quando si esegue l'hash delle password; le password originali non possono essere ricalcolate dal valore dell'hash memorizzato.
- Proof-of-work[.](https://en.wikipedia.org/wiki/Proof-of-work_system "Proof-of-work system")
  Un sistema (o protocollo, o funzione) di *proof-of-work* è una misura economica per scoraggiare gli attacchi *denial-of-service* e altri abusi di servizio come lo *spam* su una rete, richiedendo del lavoro all'usufruitore del servizio. Una caratteristica chiave di questi schemi è la loro asimmetria: il lavoro deve essere moderatamente difficile (ma fattibile) dal lato del richiedente ma facile da verificare per il fornitore del servizio.
- Identificatore di file o dati
  Un **digest** può anche servire come mezzo per identificare in modo affidabile un file.
## Panoramica storica delle funzioni hash
I primi design di funzioni hash crittografiche risalgono alla fine degli anni '70; altri design sono emersi negli anni '80. Durante gli anni '90, il numero di design di funzioni hash è cresciuto molto rapidamente, ma per molte di queste proposte sono stati identificati difetti di sicurezza. Nonostante l'importanza delle funzioni hash, solo uno sforzo limitato è stato speso per studiare le loro definizioni formali e i loro fondamenti. Nel 2004 *Wang et al.*  trovarono collisioni per le maggiori funzioni dei tempi(**MD4**, **MD5**, **HAVAL-128** e **RIPEMD**). Queste scoperte hanno portato ad una raffica di ricerche, che hanno portato a nuovi design e ad un crescente corpo di ricerca fondazionale. Il **NIST** ha annunciato nel 2006 che avrebbe organizzato la competizione SHA-3, con l'obiettivo di selezionare una nuova famiglia di funzioni hash entro il 2012. Dai 64 candidati presentati entro ottobre 2008, 14 sono arrivati al secondo turno e **Keccak** arrivò all'ultimo turno diventando lo stanadrd **SHA-3**. Il 23 febbraio 2017, il **CWI** (*Centrum Wiskunde & Informatica*) e **Google** hanno annunciato l'attacco ***SHAttered***, in cui hanno generato due diversi file PDF con lo stesso hash **SHA-1**. Questo attacco è circa 100.000 volte più veloce di un collision brute-force per **SHA-1** con un *birthday attack*

### Timeline estensiva
- *Diffie* e *Hellman* hanno identificato la necessità di una funzione hash **unidirezionale** come elemento costitutivo di uno schema di firma digitale nel loro documento seminale del 1976 sulla crittografia a chiave pubblica
- Le prime definizioni, analisi e costruzioni per le funzioni hash crittografiche possono essere trovate nel lavoro di *Rabin*, *Yuval* e *Merkle* della fine degli anni '70
  - *Rabin* ha proposto un progetto con un risultato a 64 bit basato sul cifrario a blocchi **DES**
  - *Yuval* ha mostrato come trovare collisioni per una funzione hash a $n$ bit in tempo $\frac{2n}{2}$ con il **birthday paradox**
  - Il lavoro di *Merkle* ha introdotto i requisiti di **collision resistance**, **second pre-image resistance** and **pre-image resistance**
- Nel 1987, *Damgård* formalizzò la definizione di **collision resistance**
- Nel 1989 *Naor* e *Yung* definirono una variante delle funzioni **second pre-images resistant** chiamata ***Universal One Way Hash Functions (UOWHFs)***
- Nel 1991 le debolezze in **MD4** sono state dimostrate da *Den Boer* e *Bosselaers* in un documento pubblicato
- Nel 1991 Rivest progettò **MD5** come sostituto sicuro del suo predecessore **MD4**
- Nel 1992 la funzione originale **RIPEMD** fu progettata nell'ambito del **progetto europeo RIPE** (*RACE Integrity Primitives Evaluation*)
- Nel 1995 il primo attacco di collisione full-round **MD4** è stato trovato da *Hans Dobbertin*
- Nel 1996, in risposta alle debolezze di sicurezza trovate nel RIPEMD originale, *Hans Dobbertin*, *Antoon Bosselaers* e *Bart Preneel* del gruppo di ricerca **COSIC** della *Katholieke Universiteit Leuven a Leuven, Belgio* hanno pubblicato quattro varianti rafforzate: **RIPEMD-128**, **RIPEMD-160**, **RIPEMD-256**, e **RIPEMD-320**
- Nel 1996, *Dobbertin* ha annunciato una collisione della funzione di compressione di **MD5**
- Nel 1997 *Rogier* e *Chauvaud* hanno descritto collisioni della funzione di compressione di **MD2**, anche se non sono stati in grado di estendere l'attacco all'intero **MD2**
- Al **CRYPTO 98**, due ricercatori francesi, Florent Chabaud e Antoine Joux, hanno presentato un attacco a SHA-0
- Nel 2001 con la pubblicazione di **FIPS PUB 180-2**, **NIST** ha aggiunto tre funzioni hash aggiuntive nella famiglia **SHA**. Gli algoritmi sono conosciuti collettivamente come **SHA-2**, dal nome delle loro lunghezze di digest (in bit): **SHA-256**, **SHA-384** e **SHA-512**.
- Nel 2004 **MD2** ha dimostrato di essere vulnerabile ad un attacco preimage
- Nel 2004, *Biham* e *Chen* hanno trovato delle quasi-collisioni per **SHA-0** - due messaggi che hanno un hash quasi uguale; in questo caso, 142 dei 160 bit sono uguali. Hanno anche trovato collisioni complete di *SHA-0* ridotte a 62 dei suoi 80 round
- Nel 2004 *Rogaway* e *Shrimpton* hanno studiato formalmente le relazioni tra la collision resistance e diversi tipi di resistenza a pre-image e second pre-image
- Nell'agosto 2004, *Wang et al.* hanno trovato un attacco di collisione molto efficiente, insieme ad attacchi su progetti successivi di funzioni hash nella famiglia **MD4**/**MD5**/**SHA-1**/**RIPEMD**
- Il 12 agosto 2004, una collisione per l'intero algoritmo **SHA-0** è stata annunciata da *Joux*, *Carribault*, *Lemuet*, e *Jalby*. Questo è stato fatto usando una generalizzazione dell'attacco di *Chabaud* e *Joux*.
- Il 17 agosto 2004, alla *Rump Session* di **CRYPTO 2004**, sono stati annunciati risultati preliminari da *Wang*, *Feng*, *Lai*, e *Yu*, riguardo un attacco a **MD5**, **SHA-0** e altre funzioni hash
- Il 17 agosto 2004, le collisioni per HAVAL (128 bit, 3 passaggi) sono state annunciate da *Xiaoyun Wang*, *Dengguo Feng*, *Xuejia Lai*, e *Hongbo Yu*
- Dopo la pubblicazione dei risultati di **CRYPTO 2004**, **NIST** ha annunciato di aver pianificato di eliminare gradualmente l'uso di **SHA-1** entro il 2010 in favore delle varianti **SHA-2**.
- Nel febbraio 2005, fu annunciato un attacco da parte di *Xiaoyun Wang*, *Yiqun Lisa Yin*, e *Hongbo Yu* che poteva trovare collisioni in **SHA-0**
- All'inizio del 2005, *Vincent Rijmen* e *Elisabeth Oswald* hanno pubblicato un attacco su una versione ridotta di *SHA-1* - 53 su 80 round - che trova collisioni
- Nel febbraio 2005, un attacco di *Xiaoyun Wang*, *Yiqun Lisa Yin*, e *Hongbo Yu* è stato annunciato. L'attacco può trovare collisioni nella versione completa di **SHA-1**
- Il 1° marzo 2005, *Vlastimil Klima* ha descritto un algoritmo migliorato, in grado di costruire le collisioni **MD5** in poche ore su un singolo computer portatile
- Il 17 agosto 2005, un miglioramento dell'attacco SHA-1 è stato annunciato a nome di *Xiaoyun Wang*, *Andrew Yao* e *Frances Yao* alla **CRYPTO 2005** Rump Session, abbassando la complessità richiesta per trovare una collisione in **SHA-1**
- Il 18 marzo 2006, *Klima* ha pubblicato un algoritmo che potrebbe trovare una collisione in un minuto su un singolo computer notebook, usando un metodo che lui chiama tunneling
- Alla Rump Session di CRYPTO 2006, *Christian Rechberger* e *Christophe De Cannière* affermarono di aver scoperto un attacco di collisione su **SHA-1** che avrebbe permesso ad un attaccante di selezionare almeno parti del messaggio
- Nel 2006, **NIST** ha iniziato ad organizzare il concorso **NIST** per funzioni di hash per creare un nuovo standard di hash, **SHA-3**. **SHA-3** non è destinato a sostituire **SHA-2**, poiché nessun attacco significativo a **SHA-2** è stato dimostrato. A causa del successo degli attacchi a **MD5**, **SHA-0** e **SHA-1**, **NIST** ha percepito la necessità di un hash crittografico alternativo e diverso, che è diventato **SHA-3**
- Nel 2008, anche la **resistenza pre-immagine** di **MD4** è stata violata da *Gaëtan Leurent*.
- Nel 2008 un attacco a **SHA-0** applicando l'attacco boomerang ha portato la complessità della ricerca di collisioni, stimata in 1 ora su un PC medio dell'anno 2008
- Nel 2009, **MD2** ha dimostrato di essere vulnerabile ad un attacco di collisione
- Nel 2009, sono stati rilasciati aggiornamenti di sicurezza che disabilitano **MD2** in OpenSSL, GnuTLS, e Network Security Services
- Nel luglio 2009, 14 algoritmi sono stati selezionati per il secondo round per **SHA-3**
- Nel dicembre 2010 **Keccak** ha avanzato all'ultimo turno del concorso **NIST** per **SHA-3**
- Nel 2011, ***RFC 6150*** ha dichiarato che **RFC 1320 (MD4)** è **storico** (obsoleto)
- Nel 2011 è stata approvata una **RFC 6151** informativa per aggiornare le considerazioni sulla sicurezza in **MD5** e **HMAC-MD5**
- Nel gennaio 2011, **NIST** ha pubblicato **SP800-131A**, che ha specificato un passaggio dal minimo allora corrente di 80-bit di sicurezza (fornito da **SHA-1**) consentito per l'uso del governo federale fino alla fine del 2013, a 112-bit di sicurezza (fornito da **SHA-2**) sia il requisito minimo (a partire dal 2014) e il livello di sicurezza consigliato (a partire dalla data di pubblicazione nel 2011)
- Nel marzo 2012, lo standard è stato aggiornato in **FIPS PUB 180-4**, aggiungendo le funzioni hash **SHA-512/224** e **SHA-512/256**, e descrivendo un metodo per generare valori iniziali per versioni troncate di **SHA-512**
- Nel luglio 2012, **NIST** ha rivisto **SP800-57**, che fornisce una guida per la gestione delle chiavi crittografiche. La pubblicazione ha vietato la creazione di firme digitali con una sicurezza hash inferiore a 112 bit dopo il 2013.
- Nel 2012 il concorso **NIST** per le funzioni di hash ha selezionato una nuova funzione di hash, **SHA-3**. L'algoritmo **SHA-3** non è derivato da **SHA-2**
- Nel 2014 **NIST** ha pubblicato un progetto **FIPS 202** "**SHA-3** Standard: *Funzioni Hash e Extendable-Output* basate sulla permutazione".
- Il 5 agosto 2015 **FIPS 202** è stato approvato
- Il 5 agosto 2015 **NIST** ha annunciato che **SHA-3** era diventato uno standard di hashing
- L'8 ottobre 2015, *Marc Stevens*, *Pierre Karpman*, e *Thomas Peyrin* hanno pubblicato un *attacco alla collisione di freestart* sulla funzione di compressione di **SHA-1**
  era la prima volta che un attacco su **SHA-1** completo era stato *dimostrato*; tutti gli attacchi precedenti erano troppo costosi per i loro autori per portarli a termine. Gli autori hanno chiamato questo significativo passo avanti nella crittoanalisi di **SHA-1** ***The SHAppening***.
- Il 23 febbraio 2017, il **CWI** (*Centrum Wiskunde & Informatica*) e **Google** hanno annunciato l'attacco ***SHAttered***, in cui hanno generato due diversi file PDF con lo stesso hash **SHA-1**. Questo attacco è circa 100.000 volte più veloce della forza bruta di una collisione **SHA-1** con un *attacco di compleanno*
- Il 24 aprile 2019 un documento di *Gaëtan Leurent* e *Thomas Peyrin* presentato a **Eurocrypt 2019** ha descritto un miglioramento dell'attacco *chosen-prefix* precedentemente migliore nelle funzioni digest **Merkle-Damgård**-like basate su **Davies-Meyer** block ciphers.
- Il 5 gennaio 2020 *Gaëtan Leurent* e *Thomas Peyrin* hanno pubblicato un attacco migliorato
## Attachi possibili
### Bruteforce
#### Strumenti di brute forcing
## Hash e Sistemi Operativi
## Citations
- [Wikipedia: Cryptographic hash function](https://en.wikipedia.org/wiki/Cryptographic_hash_function)
  - Al-Kuwari, Saif; Davenport, James H.; Bradford, Russell J. (2011). ["Cryptographic Hash Functions: Recent Design Trends and Security Notions"](https://eprint.iacr.org/2011/565). *Cryptology ePrint Archive*. Report 2011/565.
  - Rogaway, P.; Shrimpton, T. (2004). "Cryptographic Hash-Function Basics: Definitions, Implications, and Separations for Preimage Resistance, Second-Preimage Resistance, and Collision Resistance".  [10.1.1.3.6200](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.3.6200).
  - [Mendel et al.](https://en.wikipedia.org/wiki/Cryptographic_hash_function#CITEREFMendelRechbergerSchl%C3%A4ffer2009), p. 145:Concatenating ... is often used by implementors to "hedge bets" on hash functions. A combiner of the form MD5
  - [Harnik et al. 2005](https://en.wikipedia.org/wiki/Cryptographic_hash_function#CITEREFHarnikKilianNaorReingold2005), p. 99: the concatenation of hash functions as suggested in the TLS... is guaranteed to be as secure as the candidate that remains secure.
  - [Joux 2004](https://en.wikipedia.org/wiki/Cryptographic_hash_function#CITEREFJoux2004).
  - [Finney, Hal](https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist) "Hal Finney (computer scientist)") (August 20, 2004). ["More Problems with Hash Functions"](https://web.archive.org/web/20160409095104/http://article.gmane.org/gmane.comp.encryption.general/5154). *The Cryptography Mailing List*. Archived from [the original](http://article.gmane.org/gmane.comp.encryption.general/5154) on April 9, 2016. Retrieved May 25, 2016.
  - [Hoch & Shamir 2008](https://en.wikipedia.org/wiki/Cryptographic_hash_function#CITEREFHochShamir2008), pp. 616–630.
  - Andrew Regenscheid, Ray Perlner, Shu-Jen Chang, John Kelsey, Mridul Nandi, Souradyuti Paul, [Status Report on the First Round of the SHA-3 Cryptographic Hash Algorithm Competition](https://nvlpubs.nist.gov/nistpubs/Legacy/IR/nistir7620.pdf)
  - XiaoyunWang, Dengguo Feng, Xuejia Lai, Hongbo Yu, [Collisions for Hash Functions MD4, MD5, HAVAL-128, and RIPEMD](https://eprint.iacr.org/2004/199.pdf)
  - Alshaikhli, Imad Fakhri; AlAhmad, Mohammad Abdulateef (2015), "Cryptographic Hash Function", *Handbook of Research on Threat Detection and Countermeasures in Network Security*, IGI Global, pp. 80–94, [doi](https://en.wikipedia.org/wiki/Doi_(identifier) "Doi (identifier)"):[10.4018/978-1-4666-6583-5.ch006](https://doi.org/10.4018%2F978-1-4666-6583-5.ch006), [ISBN](https://en.wikipedia.org/wiki/ISBN_(identifier) "ISBN (identifier)") [978-1-4666-6583-5](https://en.wikipedia.org/wiki/Special:BookSources/978-1-4666-6583-5 "Special:BookSources/978-1-4666-6583-5")
  - Xiaoyun Wang, [Yiqun Lisa Yin](https://en.wikipedia.org/wiki/Yiqun_Lisa_Yin "Yiqun Lisa Yin"), and Hongbo Yu, [Finding Collisions in the Full SHA-1](http://people.csail.mit.edu/yiqun/SHA1AttackProceedingVersion.pdf)
  - Bruce Schneier, [Cryptanalysis of SHA-1](http://www.schneier.com/blog/archives/2005/02/cryptanalysis_o.html) (summarizes Wang et al. results and their implications)
  - Fox-Brewster, Thomas. ["Google Just 'Shattered' An Old Crypto Algorithm – Here's Why That's Big For Web Security"](https://www.forbes.com/sites/thomasbrewster/2017/02/23/google-sha-1-hack-why-it-matters/#3f73df04c8cd). *Forbes*. Retrieved 2017-02-24.
  - Alexander Sotirov, Marc Stevens, Jacob Appelbaum, Arjen Lenstra, David Molnar, Dag Arne Osvik, Benne de Weger, [MD5 considered harmful today: Creating a rogue CA certificate](http://www.win.tue.nl/hashclash/rogue-ca/), accessed March 29, 2009.
  - Swinhoe, Dan (April 17, 2020). ["The 15 biggest data breaches of the 21st century"](https://www.csoonline.com/article/2130877/the-biggest-data-breaches-of-the-21st-century.html). CSO Magazine.
  - Goodin, Dan (2012-12-10). ["25-GPU cluster cracks every standard Windows password in <6 hours"](https://arstechnica.com/information-technology/2012/12/25-gpu-cluster-cracks-every-standard-windows-password-in-6-hours/). [Ars Technica](https://en.wikipedia.org/wiki/Ars_Technica "Ars Technica"). Retrieved 2020-11-23.
  - Claburn, Thomas (February 14, 2019). ["Use an 8-char Windows NTLM password? Don't. Every single one can be cracked in under 2.5hrs"](https://www.theregister.co.uk/2019/02/14/password_length/). *[www.theregister.co.uk](http://www.theregister.co.uk)*. Retrieved 2020-11-26.
  - ["Mind-blowing GPU performance"](https://improsec.com/tech-blog/mind-blowing-gpu-performance). Improsec. January 3, 2020.
  - Grassi Paul A. (June 2017). *SP 800-63B-3 – Digital Identity Guidelines, Authentication and Lifecycle Management*. NIST. [doi](https://en.wikipedia.org/wiki/Doi_(identifier) "Doi (identifier)"):[10.6028/NIST.SP.800-63b](https://doi.org/10.6028%2FNIST.SP.800-63b).
- [The First 30 Years of Cryptographic Hash Functions and the NIST SHA-3 Competition by Bart Preneel](https://www.esat.kuleuven.be/cosic/publications/article-1532.pdf)
- [Lifetimes of popular cryptographic hashes](https://valerieaurora.org/hash.html)
- [Collisions for Hash Functions MD4, MD5, HAVAL-128 and RIPEMD](https://eprint.iacr.org/2004/199.pdf)

---
# References
- <https://en.wikipedia.org/wiki/Hash_function>
- <https://en.wikipedia.org/wiki/List_of_hash_functions>
- <https://en.wikipedia.org/wiki/Cryptographic_hash_function>
- <https://en.wikipedia.org/wiki/Deterministic_algorithm>
- <https://en.wikipedia.org/wiki/Avalanche_effect>
- <https://en.wikipedia.org/wiki/Comparison_of_cryptographic_hash_functions>
- <https://valerieaurora.org/hash.html>
- <https://en.wikipedia.org/wiki/Rainbow_table>
- <https://www.thesslstore.com/blog/rainbow-tables-a-path-to-password-gold-for-cybercriminals/>
- <https://www.geeksforgeeks.org/understanding-rainbow-table-attack/>
- <https://cyberhoot.com/cybrary/rainbow-tables/>
- <https://www.beyondidentity.com/glossary/rainbow-table-attack>
- <https://www.sciencedirect.com/topics/computer-science/rainbow-table>
- <https://www.mrw.it/sicurezza/password-cracking-tramite-rainbow-tables_7694.html>
- <https://en.wikipedia.org/wiki/Password_cracking>
- <https://en.wikipedia.org/wiki/Birthday_attack>
- <https://en.wikipedia.org/wiki/Brute-force_attack>
- <https://www.growhub.it/varie/come-si-fa-un-attacco-brute-force/>
- <https://www.proofpoint.com/it/threat-reference/brute-force-attack>
- <https://resources.infosecinstitute.com/topic/popular-tools-for-brute-force-attacks/>
## Keyed cryptographic hash functions
| Nome                                       | Lunghezza Tag       | tipo                              |
| ------------------------------------------ | ------------------- | --------------------------------- |
| BLAKE2#BLAKE2 "BLAKE (hash function)")     | arbitrary           | keyed hash function (prefix-MAC)  |
| BLAKE3                                     | arbitrary           | keyed hash function (supplied IV) |
| HMAC                                       |                     |                                   |
| KMAC                                       | arbitrary           | based on Keccak                   |
| MD6                                        | 512 bits            | Merkle tree NLFSR                 |
| One-key MAC (OMAC; CMAC)                   |                     |                                   |
| PMAC (cryptography) "PMAC (cryptography)") |                     |                                   |
| Poly1305-AES                               | 128 bits            | nonce-based                       |
| SipHash                                    | 32, 64 or 128 bits  | non-collision-resistant PRF       |
| HighwayHash[13]                            | 64, 128 or 256 bits | non-collision-resistant PRF       |
| UMAC                                       |                     |                                   |
| VMAC                                       |                     |                                   |

---
## Unkeyed cryptographic hash functions
| Nome                                    | Lunghezza Tag   | tipo                                                       |
| --------------------------------------- | --------------- | ---------------------------------------------------------- |
| BLAKE-256 "BLAKE (hash function)")      | 256 bits        | HAIFA structure                                            |
| BLAKE-512 "BLAKE (hash function)")      | 512 bits        | HAIFA structure                                            |
| BLAKE2s#BLAKE2 "BLAKE (hash function)") | up to 256 bits  | HAIFA structure                                            |
| BLAKE2b#BLAKE2 "BLAKE (hash function)") | up to 512 bits  | HAIFA structure                                            |
| BLAKE2X#BLAKE2 "BLAKE (hash function)") | arbitrary       | HAIFA structure, extensible-output functions (XOFs) design |
| BLAKE3                                  | arbitrary       | Merkle tree                                                |
| ECOH                                    | 224 to 512 bits | hash                                                       |
| FSB                                     | 160 to 512 bits | hash                                                       |
| GOST "GOST (hash function)")            | 256 bits        | hash                                                       |
| Grøstl                                  | up to 512 bits  | hash                                                       |
| HAS-160                                 | 160 bits        | hash                                                       |
| HAVAL                                   | 128 to 256 bits | hash                                                       |
| JH "JH (hash function)")                | 224 to 512 bits | hash                                                       |
| LSH                                     | 256 to 512 bits | wide-pipe Merkle–Damgård construction                      |
| MD2 "MD2 (cryptography)")               | 128 bits        | hash                                                       |
| MD4                                     | 128 bits        | hash                                                       |
| MD5                                     | 128 bits        | Merkle–Damgård construction                                |
| MD6                                     | up to 512 bits  | Merkle tree NLFSR (it is also a keyed hash function)       |
| RadioGatún                              | arbitrary       | ideal mangling function                                    |
| RIPEMD                                  | 128 bits        | hash                                                       |
| RIPEMD-128                              | 128 bits        | hash                                                       |
| RIPEMD-160                              | 160 bits        | hash                                                       |
| RIPEMD-320                              | 320 bits        | hash                                                       |
| SHA-1                                   | 160 bits        | Merkle–Damgård construction                                |
| SHA-224                                 | 224 bits        | Merkle–Damgård construction                                |
| SHA-256                                 | 256 bits        | Merkle–Damgård construction                                |
| SHA-384                                 | 384 bits        | Merkle–Damgård construction                                |
| SHA-512                                 | 512 bits        | Merkle–Damgård construction                                |
| SHA-3 (subset of Keccak)                | arbitrary       | sponge function                                            |
| Skein "Skein (hash function)")          | arbitrary       | Unique Block Iteration")                                   |
| Snefru                                  | 128 or 256 bits | hash                                                       |
| Spectral Hash                           | 512 bits        | wide-pipe Merkle–Damgård construction                      |
| Streebog                                | 256 or 512 bits | Merkle–Damgård construction                                |
| SWIFFT                                  | 512 bits        | hash                                                       |
| Tiger "Tiger (cryptography)")           | 192 bits        | Merkle–Damgård construction                                |
| Whirlpool "Whirlpool (cryptography)")   | 512 bits        | hash                                                       |
| ## Citations                            |                 |                                                            |
