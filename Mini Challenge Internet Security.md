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
## Panoramica storica funzioni hash

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

---
# References
- <https://en.wikipedia.org/wiki/Hash_function>
- <https://en.wikipedia.org/wiki/List_of_hash_functions>
- <https://en.wikipedia.org/wiki/Cryptographic_hash_function>
- <https://en.wikipedia.org/wiki/Deterministic_algorithm>
- <https://en.wikipedia.org/wiki/Avalanche_effect>
- <https://valerieaurora.org/hash.html>
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
