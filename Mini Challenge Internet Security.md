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
I primi design di funzioni hash crittografiche risalgono alla fine degli anni '70; altri design sono emersi negli anni '80. Durante gli anni '90, il numero di design di funzioni hash è cresciuto molto rapidamente, ma per molte di queste proposte sono stati identificati difetti di sicurezza. Nonostante l'importanza delle funzioni hash, solo uno sforzo limitato è stato speso per studiare le loro definizioni formali e i loro fondamenti. Nel 2004 *Wang et al.* ha perfezionato la crittoanalisi differenziale al punto che trovare collisioni per **MD5** è diventato molto facile; per **SHA-1** è stata ottenuta una sostanziale riduzione del margine di sicurezza. Questa scoperta ha portato ad una raffica di ricerche, che hanno portato a nuovi edsign e ad un crescente corpo di ricerca fondazionale. Il NIST ha annunciato nel novembre 2007 che avrebbe organizzato la competizione SHA-3, con l'obiettivo di selezionare una nuova famiglia di funzioni hash entro il 2012. Dai 64 candidati presentati entro ottobre 2008, 14 sono arrivati al secondo turno.

- *Diffie* e *Hellman* hanno identificato la necessità di una funzione hash **unidirezionale** come elemento costitutivo di uno schema di firma digitale nel loro documento seminale del 1976 sulla crittografia a chiave pubblica
- Le prime definizioni, analisi e costruzioni per le funzioni hash crittografiche possono essere trovate nel lavoro di *Rabin*, *Yuval* e *Merkle* della fine degli anni '70
  - *Rabin* ha proposto un progetto con un risultato a 64 bit basato sul cifrario a blocchi **DES**
  - *Yuval* ha mostrato come trovare collisioni per una funzione hash a $n$ bit in tempo $\frac{2n}{2}$ con il **birthday paradox**
  - Il lavoro di *Merkle* ha introdotto i requisiti di **collision resistance**, **second pre-image resistance** and **pre-image resistance**
- Nel 1987, *Damgård* formalizzò la definizione di **collision resistance**
- Nel 1989 *Naor* e *Yung* definirono una variante delle funzioni **second pre-images resistant** chiamata ***Universal One Way Hash Functions (UOWHFs)***

- Weaknesses in **MD4** were demonstrated by *Den Boer* and *Bosselaers* in a paper published in 1991

- Nel 2004 *Rogaway* e *Shrimpton* hanno studiato formalmente le relazioni tra la collision resistance e diversi tipi di resistenza a pre-image e second pre-image
- Le funzioni di hash dovrebbero anche distruggere la struttura algebrica dello schema di firma; esempi tipici sono l'euristica di *Fiat-Shamir* e l'attacco di *Coppersmith* alla funzione di hash nell'*X.509 Annex D*
- La costruzione di algoritmi MAC basati su funzioni hash (come HMAC) ha portato al requisito che la funzione hash possa essere usata per costruire funzioni pseudo-casuali, che è stato tra l'altro studiato da *Bellare et al.*


The first full-round **MD4** collision attack was found by *Hans Dobbertin* in 1995
In August 2004, *Wang et al.* found a very efficient collision attack, alongside attacks on later hash function designs in the **MD4**/**MD5**/**SHA-1**/**RIPEMD family**
In 2008, the **pre-image resistance** of **MD4** was also broken by *Gaëtan Leurent*, with a $2^{102}$ attack
In 2010 Guo et al published a $2^{99.7}$ attack
In 2011, ***RFC 6150*** stated that **RFC 1320 (MD4)** is **historic** (obsolete)
Rivest designed **MD5** in 1991 as a secure replacement for his predecessor **MD4**
In 1993, *Den Boer* and *Bosselaers* gave an early, although limited, result of finding a *"pseudo-collision"* of the **MD5** compression function that is, two different initialization vectors that produce an identical **digest**.
In 1996, *Dobbertin* announced a collision of the compression function of **MD5**
The size of the hash value (128 bits) is small enough to contemplate a **birthday attack**. **MD5CRK** was a distributed project started in March 2004 to demonstrate that MD5 is practically insecure by finding a collision using a **birthday attack**.
**MD5CRK** ended shortly after 17 August 2004, when collisions for the full **MD5** were announced by *Xiaoyun Wang*, *Dengguo Feng*, *Xuejia Lai*, and *Hongbo Yu*.
On 1 March 2005, *Arjen Lenstra*, *Xiaoyun Wang*, and *Benne de Weger* demonstrated construction of two **X.509** certificates with different public keys and the same **MD5** hash value, a demonstrably practical collision
A few days later, *Vlastimil Klima* described an improved algorithm, able to construct **MD5** collisions in a few hours on a single notebook computer
On 18 March 2006, *Klima* published an algorithm that could find a collision within one minute on a single notebook computer, using a method he calls tunneling
On 24 December 2010, *Tao Xie* and *Dengguo Feng* announced the first published single-block (512-bit) MD5 collision (Previous collision discoveries had relied on multi-block attacks)
In 2011 an informational **RFC 6151** was approved to update the security considerations in **MD5** and **HMAC-MD5**.
In 1997, *Rogier* and *Chauvaud* described collisions of **MD2**'s compression function, although they were unable to extend the attack to the full **MD2**.
In 2004, MD2 was shown to be vulnerable to a [preimage attack](https://en.wikipedia.org/wiki/Preimage_attack "Preimage attack") with [time complexity](https://en.wikipedia.org/wiki/Time_complexity "Time complexity") equivalent to 2104 applications of the compression function.[[6]](https://en.wikipedia.org/wiki/MD2_(hash_function)#cite_note-Muller_2004-6) The author concludes, "MD2 can no longer be considered a secure one-way hash function".

In 2008, MD2 has further improvements on a [preimage attack](https://en.wikipedia.org/wiki/Preimage_attack "Preimage attack") with [time complexity](https://en.wikipedia.org/wiki/Time_complexity "Time complexity") of 273 compression function evaluations and memory requirements of 273 message blocks.[[7]](https://en.wikipedia.org/wiki/MD2_(hash_function)#cite_note-Thomsen_2008-7)

In 2009, MD2 was shown to be vulnerable to a [collision attack](https://en.wikipedia.org/wiki/Collision_attack "Collision attack") with [time complexity](https://en.wikipedia.org/wiki/Time_complexity "Time complexity") of 263.3 compression function evaluations and memory requirements of 252 hash values. This is slightly better than the [birthday attack](https://en.wikipedia.org/wiki/Birthday_attack "Birthday attack") which is expected to take 265.5 compression function evaluations.[[8]](https://en.wikipedia.org/wiki/MD2_(hash_function)#cite_note-Knudsen_et_al_2009-8)

In 2009, security updates were issued disabling MD2 in [OpenSSL](https://en.wikipedia.org/wiki/OpenSSL "OpenSSL"), [GnuTLS](https://en.wikipedia.org/wiki/GnuTLS "GnuTLS"), and [Network Security Services](https://en.wikipedia.org/wiki/Network_Security_Services "Network Security Services").[[9]](https://en.wikipedia.org/wiki/MD2_(hash_function)#cite_note-9)

The original RIPEMD function was designed in the framework of the [EU](https://en.wikipedia.org/wiki/European_Union "European Union") project RIPE ([RACE](https://en.wikipedia.org/wiki/RACE_(Europe) "RACE (Europe)") Integrity Primitives Evaluation) in 1992.[[1]](https://en.wikipedia.org/wiki/RIPEMD#cite_note-1)[[2]](https://en.wikipedia.org/wiki/RIPEMD#cite_note-2) Its design was based on the [MD4](https://en.wikipedia.org/wiki/MD4 "MD4") hash function. In 1996, in response to security weaknesses found in the original RIPEMD,[[3]](https://en.wikipedia.org/wiki/RIPEMD#cite_note-3) [Hans Dobbertin](https://en.wikipedia.org/wiki/Hans_Dobbertin "Hans Dobbertin"), [Antoon Bosselaers](https://en.wikipedia.org/w/index.php?title=Antoon_Bosselaers&action=edit&redlink=1 "Antoon Bosselaers (page does not exist)") and [Bart Preneel](https://en.wikipedia.org/wiki/Bart_Preneel "Bart Preneel") at the [COSIC](https://en.wikipedia.org/wiki/COSIC "COSIC") research group at the [Katholieke Universiteit Leuven](https://en.wikipedia.org/wiki/Katholieke_Universiteit_Leuven "Katholieke Universiteit Leuven") in [Leuven, Belgium](https://en.wikipedia.org/wiki/Leuven "Leuven") published four strengthened variants: RIPEMD-128, RIPEMD-160, RIPEMD-256, and RIPEMD-320.[[4]](https://en.wikipedia.org/wiki/RIPEMD#cite_note-4)

In August 2004, a collision was reported for the original RIPEMD.[[5]](https://en.wikipedia.org/wiki/RIPEMD#cite_note-5) This does not apply to RIPEMD-160.[[6]](https://en.wikipedia.org/wiki/RIPEMD#cite_note-6)

Research has uncovered weaknesses which make further use of HAVAL (at least the variant with 128 bits and 3 passes with 26 operations) questionable. On 17 August 2004, [collisions](https://en.wikipedia.org/wiki/Hash_collision "Hash collision") for HAVAL (128 bits, 3 passes) were announced by [Xiaoyun Wang](https://en.wikipedia.org/wiki/Xiaoyun_Wang "Xiaoyun Wang"), Dengguo Feng, [Xuejia Lai](https://en.wikipedia.org/wiki/Xuejia_Lai "Xuejia Lai"), and Hongbo Yu.[[2]](https://en.wikipedia.org/wiki/HAVAL#cite_note-2)

### SHA-0[[edit](https://en.wikipedia.org/w/index.php?title=SHA-1&action=edit&section=6 "Edit section: SHA-0")]

At [CRYPTO](https://en.wikipedia.org/wiki/CRYPTO_(conference) "CRYPTO (conference)") 98, two French researchers, [Florent Chabaud](https://en.wikipedia.org/w/index.php?title=Florent_Chabaud&action=edit&redlink=1 "Florent Chabaud (page does not exist)") and [Antoine Joux](https://en.wikipedia.org/wiki/Antoine_Joux "Antoine Joux"), presented an attack on SHA-0: [collisions](https://en.wikipedia.org/wiki/Hash_collision "Hash collision") can be found with complexity 261, fewer than the 280 for an ideal hash function of the same size.[[29]](https://en.wikipedia.org/wiki/SHA-1#cite_note-sha0-chabaud-29)

In 2004, [Biham](https://en.wikipedia.org/wiki/Eli_Biham "Eli Biham") and Chen found near-collisions for SHA-0 – two messages that hash to nearly the same value; in this case, 142 out of the 160 bits are equal. They also found full collisions of SHA-0 reduced to 62 out of its 80 rounds.[[30]](https://en.wikipedia.org/wiki/SHA-1#cite_note-30)

Subsequently, on 12 August 2004, a collision for the full SHA-0 algorithm was announced by Joux, Carribault, Lemuet, and Jalby. This was done by using a generalization of the Chabaud and Joux attack. Finding the collision had complexity 251 and took about 80,000 processor-hours on a [supercomputer](https://en.wikipedia.org/wiki/Supercomputer "Supercomputer") with 256 [Itanium 2](https://en.wikipedia.org/wiki/Itanium_2 "Itanium 2") processors (equivalent to 13 days of full-time use of the computer).

On 17 August 2004, at the Rump Session of CRYPTO 2004, preliminary results were announced by [Wang](https://en.wikipedia.org/wiki/Xiaoyun_Wang "Xiaoyun Wang"), Feng, Lai, and Yu, about an attack on [MD5](https://en.wikipedia.org/wiki/MD5 "MD5"), SHA-0 and other hash functions. The complexity of their attack on SHA-0 is 240, significantly better than the attack by Joux _et al._[[31]](https://en.wikipedia.org/wiki/SHA-1#cite_note-31)[[32]](https://en.wikipedia.org/wiki/SHA-1#cite_note-32)

In February 2005, an attack by [Xiaoyun Wang](https://en.wikipedia.org/wiki/Xiaoyun_Wang "Xiaoyun Wang"), [Yiqun Lisa Yin](https://en.wikipedia.org/wiki/Yiqun_Lisa_Yin "Yiqun Lisa Yin"), and Hongbo Yu was announced which could find collisions in SHA-0 in 239 operations.[[4]](https://en.wikipedia.org/wiki/SHA-1#cite_note-autogenerated1-4)[[33]](https://en.wikipedia.org/wiki/SHA-1#cite_note-33)

Another attack in 2008 applying the [boomerang attack](https://en.wikipedia.org/wiki/Boomerang_attack "Boomerang attack") brought the complexity of finding collisions down to 233.6, which was estimated to take 1 hour on an average PC from the year 2008.[[34]](https://en.wikipedia.org/wiki/SHA-1#cite_note-34)

In light of the results for SHA-0, some experts[_[who?](https://en.wikipedia.org/wiki/Wikipedia:Manual_of_Style/Words_to_watch#Unsupported_attributions "Wikipedia:Manual of Style/Words to watch")_] suggested that plans for the use of SHA-1 in new [cryptosystems](https://en.wikipedia.org/wiki/Cryptosystem "Cryptosystem") should be reconsidered. After the CRYPTO 2004 results were published, NIST announced that they planned to phase out the use of SHA-1 by 2010 in favor of the SHA-2 variants.[[35]](https://en.wikipedia.org/wiki/SHA-1#cite_note-35)

### Attacks[[edit](https://en.wikipedia.org/w/index.php?title=SHA-1&action=edit&section=7 "Edit section: Attacks")]

In early 2005, [Vincent Rijmen](https://en.wikipedia.org/wiki/Vincent_Rijmen "Vincent Rijmen") and [Elisabeth Oswald](https://en.wikipedia.org/wiki/Elisabeth_Oswald "Elisabeth Oswald") published an attack on a reduced version of SHA-1 – 53 out of 80 rounds – which finds collisions with a computational effort of fewer than 280 operations.[[36]](https://en.wikipedia.org/wiki/SHA-1#cite_note-36)

In February 2005, an attack by [Xiaoyun Wang](https://en.wikipedia.org/wiki/Xiaoyun_Wang "Xiaoyun Wang"), Yiqun Lisa Yin, and Hongbo Yu was announced.[[4]](https://en.wikipedia.org/wiki/SHA-1#cite_note-autogenerated1-4) The attacks can find collisions in the full version of SHA-1, requiring fewer than 269 operations. (A [brute-force search](https://en.wikipedia.org/wiki/Brute-force_search "Brute-force search") would require 280 operations.)

The authors write: "In particular, our analysis is built upon the original differential attack on SHA-0, the near collision attack on SHA-0, the multiblock collision techniques, as well as the message modification techniques used in the collision search attack on MD5. Breaking SHA-1 would not be possible without these powerful analytical techniques."[[37]](https://en.wikipedia.org/wiki/SHA-1#cite_note-37) The authors have presented a collision for 58-round SHA-1, found with 233 hash operations. The paper with the full attack description was published in August 2005 at the CRYPTO conference.

In an interview, Yin states that, "Roughly, we exploit the following two weaknesses: One is that the file preprocessing step is not complicated enough; another is that certain math operations in the first 20 rounds have unexpected security problems."[[38]](https://en.wikipedia.org/wiki/SHA-1#cite_note-38)

On 17 August 2005, an improvement on the SHA-1 attack was announced on behalf of [Xiaoyun Wang](https://en.wikipedia.org/wiki/Xiaoyun_Wang "Xiaoyun Wang"), [Andrew Yao](https://en.wikipedia.org/wiki/Andrew_Yao "Andrew Yao") and [Frances Yao](https://en.wikipedia.org/wiki/Frances_Yao "Frances Yao") at the CRYPTO 2005 Rump Session, lowering the complexity required for finding a collision in SHA-1 to 263.[[6]](https://en.wikipedia.org/wiki/SHA-1#cite_note-:3-6) On 18 December 2007 the details of this result were explained and verified by Martin Cochran.[[39]](https://en.wikipedia.org/wiki/SHA-1#cite_note-39)

Christophe De Cannière and Christian Rechberger further improved the attack on SHA-1 in "Finding SHA-1 Characteristics: General Results and Applications,"[[40]](https://en.wikipedia.org/wiki/SHA-1#cite_note-40) receiving the Best Paper Award at [ASIACRYPT](https://en.wikipedia.org/wiki/ASIACRYPT "ASIACRYPT") 2006. A two-block collision for 64-round SHA-1 was presented, found using unoptimized methods with 235 compression function evaluations. Since this attack requires the equivalent of about 235 evaluations, it is considered to be a significant theoretical break.[[41]](https://en.wikipedia.org/wiki/SHA-1#cite_note-41) Their attack was extended further to 73 rounds (of 80) in 2010 by Grechnikov.[[42]](https://en.wikipedia.org/wiki/SHA-1#cite_note-42) In order to find an actual collision in the full 80 rounds of the hash function, however, tremendous amounts of computer time are required. To that end, a collision search for SHA-1 using the distributed computing platform [BOINC](https://en.wikipedia.org/wiki/BOINC "BOINC") began August 8, 2007, organized by the [Graz University of Technology](https://en.wikipedia.org/wiki/Graz_University_of_Technology "Graz University of Technology"). The effort was abandoned May 12, 2009 due to lack of progress.[[43]](https://en.wikipedia.org/wiki/SHA-1#cite_note-43)

At the Rump Session of CRYPTO 2006, Christian Rechberger and Christophe De Cannière claimed to have discovered a collision attack on SHA-1 that would allow an attacker to select at least parts of the message.[[44]](https://en.wikipedia.org/wiki/SHA-1#cite_note-44)[[45]](https://en.wikipedia.org/wiki/SHA-1#cite_note-45)

In 2008, an attack methodology by Stéphane Manuel reported hash collisions with an estimated theoretical complexity of 251 to 257 operations.[[46]](https://en.wikipedia.org/wiki/SHA-1#cite_note-46) However he later retracted that claim after finding that local collision paths were not actually independent, and finally quoting for the most efficient a collision vector that was already known before this work.[[47]](https://en.wikipedia.org/wiki/SHA-1#cite_note-47)

Cameron McDonald, Philip Hawkes and Josef Pieprzyk presented a hash collision attack with claimed complexity 252 at the Rump Session of Eurocrypt 2009.[[48]](https://en.wikipedia.org/wiki/SHA-1#cite_note-48) However, the accompanying paper, "Differential Path for SHA-1 with complexity [_O_](https://en.wikipedia.org/wiki/Big_O_notation "Big O notation")(252)" has been withdrawn due to the authors' discovery that their estimate was incorrect.[[49]](https://en.wikipedia.org/wiki/SHA-1#cite_note-49)

One attack against SHA-1 was Marc Stevens[[50]](https://en.wikipedia.org/wiki/SHA-1#cite_note-Cryptanalysis_of_MD5_&_SHA-1-50) with an estimated cost of $2.77M(2012) to break a single hash value by renting CPU power from cloud servers.[[51]](https://en.wikipedia.org/wiki/SHA-1#cite_note-51) Stevens developed this attack in a project called HashClash,[[52]](https://en.wikipedia.org/wiki/SHA-1#cite_note-52) implementing a differential path attack. On 8 November 2010, he claimed he had a fully working near-collision attack against full SHA-1 working with an estimated complexity equivalent to 257.5 SHA-1 compressions. He estimated this attack could be extended to a full collision with a complexity around 261.

#### The SHAppening[[edit](https://en.wikipedia.org/w/index.php?title=SHA-1&action=edit&section=8 "Edit section: The SHAppening")]

On 8 October 2015, Marc Stevens, Pierre Karpman, and Thomas Peyrin published a freestart collision attack on SHA-1's compression function that requires only 257 SHA-1 evaluations. This does not directly translate into a collision on the full SHA-1 hash function (where an attacker is _not_ able to freely choose the initial internal state), but undermines the security claims for SHA-1. In particular, it was the first time that an attack on full SHA-1 had been _demonstrated_; all earlier attacks were too expensive for their authors to carry them out. The authors named this significant breakthrough in the cryptanalysis of SHA-1 _The SHAppening_.[[9]](https://en.wikipedia.org/wiki/SHA-1#cite_note-shappening-9)

The method was based on their earlier work, as well as the auxiliary paths (or boomerangs) speed-up technique from Joux and Peyrin, and using high performance/cost efficient GPU cards from [NVIDIA](https://en.wikipedia.org/wiki/NVIDIA "NVIDIA"). The collision was found on a 16-node cluster with a total of 64 graphics cards. The authors estimated that a similar collision could be found by buying US$2,000 of GPU time on [EC2](https://en.wikipedia.org/wiki/Amazon_Elastic_Compute_Cloud "Amazon Elastic Compute Cloud").[[9]](https://en.wikipedia.org/wiki/SHA-1#cite_note-shappening-9)

The authors estimated that the cost of renting enough of EC2 CPU/GPU time to generate a full collision for SHA-1 at the time of publication was between US$75K and 120K, and noted that was well within the budget of criminal organizations, not to mention national [intelligence agencies](https://en.wikipedia.org/wiki/Intelligence_agency "Intelligence agency"). As such, the authors recommended that SHA-1 be deprecated as quickly as possible.[[9]](https://en.wikipedia.org/wiki/SHA-1#cite_note-shappening-9)

#### SHAttered – first public collision[[edit](https://en.wikipedia.org/w/index.php?title=SHA-1&action=edit&section=9 "Edit section: SHAttered – first public collision")]

On 23 February 2017, the [CWI (Centrum Wiskunde & Informatica)](https://en.wikipedia.org/wiki/Centrum_Wiskunde_%26_Informatica "Centrum Wiskunde & Informatica") and Google announced the _SHAttered_ attack, in which they generated two different PDF files with the same SHA-1 hash in roughly 263.1 SHA-1 evaluations. This attack is about 100,000 times faster than brute forcing a SHA-1 collision with a [birthday attack](https://en.wikipedia.org/wiki/Birthday_attack "Birthday attack"), which was estimated to take 280 SHA-1 evaluations. The attack required "the equivalent processing power of 6,500 years of single-CPU computations and 110 years of single-GPU computations".[[2]](https://en.wikipedia.org/wiki/SHA-1#cite_note-sha1-shattered-2)

#### Birthday-Near-Collision Attack – first practical chosen-prefix attack[[edit](https://en.wikipedia.org/w/index.php?title=SHA-1&action=edit&section=10 "Edit section: Birthday-Near-Collision Attack – first practical chosen-prefix attack")]

On 24 April 2019 a paper by Gaëtan Leurent and Thomas Peyrin presented at Eurocrypt 2019 described an enhancement to the previously best [chosen-prefix attack](https://en.wikipedia.org/wiki/Collision_attack#Chosen-prefix_collision_attack "Collision attack") in [Merkle–Damgård](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")–like digest functions based on [Davies–Meyer](https://en.wikipedia.org/wiki/One-way_compression_function#Davies%E2%80%93Meyer "One-way compression function") block ciphers. With these improvements, this method is capable of finding chosen-prefix collisions in approximately 268 SHA-1 evaluations. This is approximately 1 billion times faster (and now usable for many targeted attacks, thanks to the possibility of choosing a prefix, for example malicious code or faked identities in signed certificates) than the previous attack's 277.1 evaluations (but without chosen prefix, which was impractical for most targeted attacks because the found collisions were almost random)[[53]](https://en.wikipedia.org/wiki/SHA-1#cite_note-stevens-sha1-53) and is fast enough to be practical for resourceful attackers, requiring approximately $100,000 of cloud processing. This method is also capable of finding chosen-prefix collisions in the [MD5](https://en.wikipedia.org/wiki/MD5 "MD5") function, but at a complexity of 246.3 does not surpass the prior best available method at a theoretical level (239), though potentially at a practical level (≤249).[[54]](https://en.wikipedia.org/wiki/SHA-1#cite_note-54)[[55]](https://en.wikipedia.org/wiki/SHA-1#cite_note-leurent-peyrin-sha1-55) This attack has a memory requirement of 500+ GB.

On 5 January 2020 the authors published an improved attack.[[7]](https://en.wikipedia.org/wiki/SHA-1#cite_note-leurent-peyrin-sha1-shambles-7) In this paper they demonstrate a chosen-prefix collision attack with a complexity of 263.4, that at the time of publication would cost 45k USD per generated collision.



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
