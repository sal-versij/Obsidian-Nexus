# Mini Challenge Internet Security
# Funzioni Hash
Una funzione hash è una funzione di mappatura tra dati di arbitraria lunghezza e valori di lunghezza fissa, anche chiamati **hash values**, **hash codes**, **digests**, o semplicemente **hashes**.
Le funzioni hash mappano un insieme in input di cardinalità nettamente superiore rispetto all'output, questo comporta inevitabilmente delle collisioni, cosa dimostrata dal teorema dei cassetti. Una metrica da analizzare quando si parla di funzioni hash è proprio la probabilità di collisione.

L'uso delle funzioni hash si basa sulle proprietà statistiche della relazione tra chiave e funzione:

- nel caso peggiore si ha elevatissima probabiltà di collisioni, ma il caso peggiore stesso ha probabilità infinitamente piccola
- nel caso medio si ha collisione minima

Le funzioni di hash sono collegate (e spesso confuse con) a **checksum**, **check digits**, **fingerprints**, **compressione lossy**, **funzioni di randomizzazione**, **error-correcting codes** e **cifrari**. Anche se i concetti si sovrappongono in una certa misura, ognuno ha i propri usi e requisiti ed è progettato e ottimizzato in modo diverso. La funzione hash differisce da questi concetti principalmente in termini di integrità dei dati.
## Funzioni Hash in sicurezza informatica
Nella sicurezza informatica le funzioni hash utilizzate devono essere crittografiche, e quindi devono rispettare le seguenti proprietà:

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
### Birthday Attack
Un **birthday attack** è un tipo di attacco crittografico che sfrutta la matematica dietro il *birthday problem* nella teoria della probabilità. Questo attacco può essere usato durante la comunicazione tra due o più parti. L'attacco dipende dalla maggiore probabilità di collisioni riscontrata tra i tentativi di attacco casuale e un grado fisso di permutazioni (pigeonholes). Con un attacco di compleanno, è possibile trovare una collisione di una funzione hash in $\sqrt{2^n}=2^{\frac{n}{2}}$, con $2^n$ che è la classica sicurezza di resistenza della **pre-image**. C'è una concordanza generale (anche se contestato) che i computer quantistici possono eseguire attacchi di compleanno, rompendo così la resistenza alle collisioni, in $\sqrt[3]{2^n}=2^{\frac{n}{3}}$.

Come esempio, si consideri lo scenario in cui un insegnante con una classe di 30 studenti ($n = 30$) chiede il compleanno di tutti (per semplicità, ignorare gli anni bisestili) per determinare se due studenti hanno lo stesso compleanno (corrispondente a una collisione hash come descritto più avanti). Intuitivamente, questa possibilità può sembrare piccola. Controintuitivamente, la probabilità che almeno uno studente abbia lo stesso compleanno di *qualsiasi* altro studente in qualsiasi giorno è intorno al 70% (per $n = 30$), dalla formula $1-\frac{365!}{(365-n)!\cdot 365^n}$.
Se l'insegnante avesse scelto un giorno *specifico* (ad esempio, il 16 settembre), allora la probabilità che almeno uno studente sia nato in quel giorno specifico è $1-(\frac{364}{365})^{30}$, circa il 7,9%.

In un attacco di compleanno, l'attaccante prepara diverse varianti di contratti benigni e maligni, ognuno con una firma digitale. Si cerca una coppia di contratti benigni e maligni con la stessa firma. In questo esempio fittizio, supponiamo che la firma digitale di una stringa sia il primo byte del suo hash SHA-256. Dopo che la vittima accetta il contratto benigno, l'attaccante lo sostituisce con quello malevolo e sostiene che la vittima lo ha firmato, come dimostrato dalla firma digitale.
### Precomputed hash chains e Rainbow tables
Una **Rainbow table** è una tabella precompilata per memorizzare l'output delle funzioni hash crittografiche, di solito per craccare gli hash delle password. Le tabelle sono comunemente utilizzate per recuperare una funzione di derivazione della chiave fino ad una certa lunghezza che consiste in un insieme limitato di caratteri. È un esempio pratico di un compromesso spazio-tempo, utilizzando meno tempo di elaborazione del computer e più memoria di un attacco brute-force che calcola un hash ad ogni tentativo, ma più tempo di elaborazione e meno memoria di una semplice funzione di derivazione della chiave con una voce per hash. L'uso di una derivazione della chiave che impiega un sale rende questo attacco non fattibile.

Il contenuto della tabella non dipende dal valore di hash da invertire. Viene creata una volta e poi utilizzata ripetutamente per le ricerche senza modifiche.
Aumentando la lunghezza della catena diminuisce la dimensione della tabella, aumentando anche il tempo richiesto per eseguire le ricerche, e questo è il compromesso tempo-memoria della **rainbow table**.
#### Precomputed hash chains
Supponiamo di avere una funzione di hash delle password $H$ e un insieme finito di password $P$. L'obiettivo è precompilare una struttura dati che, dato qualsiasi output $h$ della funzione di hash, possa localizzare un elemento $p$ in $P$ tale che $H(p) = h$, o determinare che non esiste un tale $p$ in $P$. Il modo più semplice per farlo è calcolare $H(p)$ per tutti gli $p$ in $P$, ma poi la memorizzazione della tabella richiede $\Theta(|P|n)$ bit di spazio, dove $|P|$ è la dimensione dell'insieme $P$ e $n$ è la dimensione di un output di $H$, che è proibitivo per grandi $|P|$. Le catene di hash sono una tecnica per diminuire questo requisito di spazio. L'idea è di definire una *reduction function* $R$ che rimappa i valori di hash in valori in $P$. Si noti, tuttavia, che la *reduction function* non è in realtà un'inversa della funzione hash, ma piuttosto una funzione diversa con un dominio e un codominio invertiti rispetto alla funzione hash. Alternando la funzione hash con la *reduction function*, si formano delle *catene* di password e valori hash alternati. Per esempio, se $P$ fosse l'insieme delle password alfabetiche minuscole di 6 caratteri, e i valori di hash fossero lunghi 32 bit, una catena potrebbe essere come questa:
${\displaystyle {\color {Red}{\mathtt {aaaaaa}}}\,{\xrightarrow[{\;H\;}]{}}\,{\mathtt {281DAF40}}\,{\xrightarrow[{\;R\;}]{}}\,{\mathtt {sgfnyd}}\,{\xrightarrow[{\;H\;}]{}}\,{\mathtt {920ECF10}}\,{\xrightarrow[{\;R\;}]{}}\,{\color {Violet}{\mathtt {kiebgt}}}}$
L'unico requisito per la funzione di riduzione è di essere in grado di restituire un valore "plain text" in una dimensione specifica.

Per generare la tabella, scegliamo un insieme casuale di *password iniziali* da $P$, calcoliamo catene di una lunghezza fissa $k$ per ciascuna di esse e memorizziamo *solo* la prima e l'ultima password in ogni catena. La prima password è chiamata *starting point* e l'ultima è chiamata il *endpoint*. Nell'esempio di catena di cui sopra, *"aaaaaa "* sarebbe il punto di partenza e *"kiebgt "* sarebbe il punto finale, e nessuna delle altre password (o valori di hash) verrebbe memorizzata.

Proseguendo, dato un valore hash $h$ di cui vogliamo trovarne la password corrispondente, calcoliamo una catena che inizia con $h$ applicando $R$, poi $H$, poi $R$, e così via. Se in qualsiasi punto osserviamo un valore corrispondente a uno dei punti finali della tabella, otteniamo il punto di partenza corrispondente e lo usiamo per ricreare la catena. C'è una buona probabilità che questa catena contenga il valore $h$, e se è così, il valore immediatamente precedente nella catena è la password $p$ che cerchiamo.

Per esempio, se ci viene dato l'hash *920ECF10*, calcoleremo la sua catena applicando prima $R$:
${\displaystyle {\mathtt {920ECF10}}\,{\xrightarrow[{\;R\;}]{}}\,{\color {Violet}{\mathtt {kiebgt}}}}$
Poiché *"kiebgt "* è uno dei punti finali della nostra tabella, prendiamo la corrispondente password iniziale *"aaaaaa "* e seguiamo la sua catena fino a raggiungere *920ECF10*:
${\displaystyle {\color {Red}{\mathtt {aaaaaa}}}\,{\xrightarrow[{\;H\;}]{}}\,{\mathtt {281DAF40}}\,{\xrightarrow[{\;R\;}]{}}\,{\mathtt {sgfnyd}}\,{\xrightarrow[{\;H\;}]{}}\,{\mathtt {920ECF10}}}$
Così, la password è *"sgfnyd "* (o una password diversa con lo stesso valore di hash).

Si noti tuttavia che questa catena non contiene *sempre* il valore hash $h$; può accadere che la catena che inizia da $h$ si fonda con una catena che ha un punto di partenza diverso. Per esempio, possiamo avere un valore di hash *FB107E70*, e quando seguiamo la sua catena, otteniamo *kiebgt*:
${\displaystyle {\mathtt {FB107E70}}\,{\xrightarrow[{\;R\;}]{}}\,{\mathtt {bvtdll}}\,{\xrightarrow[{\;H\;}]{}}\,{\mathtt {0EE80890}}\,{\xrightarrow[{\;R\;}]{}}\,{\color {Violet}{\mathtt {kiebgt}}}}$
Ma *FB107E70* non è nella catena che inizia con *"aaaaaa "*. Questo è chiamato un *falso allarme*. In questo caso, ignoriamo la corrispondenza e continuiamo ad estendere la catena di $h$ cercando un'altra corrispondenza. Se la catena di $h$ si estende fino alla lunghezza di $k$ senza nessuna buona corrispondenza, allora la password non è mai stata prodotta in nessuna delle catene.
#### Rainbow tables
Le **rainbow tables** risolvono efficacemente il problema delle collisioni con le catene hash ordinarie sostituendo la singola funzione di riduzione $R$ con una sequenza di funzioni di riduzione correlate $R_1$ attraverso $R_k$. In questo modo, perché due catene collidano e si fondano devono colpire lo stesso valore *nella stessa iterazione*: di conseguenza, i valori finali in queste catene saranno identici. Un passaggio finale di post-elaborazione può ordinare le catene nella tabella e rimuovere qualsiasi catena "duplicata" che ha gli stessi valori finali di altre catene. Vengono quindi generate nuove catene per riempire la tabella.

L'uso di sequenze di funzioni di riduzione cambia il modo in cui viene fatto il lookup: poiché il valore di hash di interesse può essere trovato in qualsiasi punto della catena, è necessario generare $k$ catene diverse. La prima catena assume che il valore di hash sia nell'ultima posizione di hash e applica solo $R_k$; la catena successiva assume che il valore di hash sia nella penultima posizione di hash e applica $R_{k-1}$, poi $H$, poi $R_k$; e così via fino all'ultima catena, che applica tutte le funzioni di riduzione, alternandole con $H$. Questo crea un nuovo modo di produrre un falso allarme: se "indoviniamo" male la posizione del valore di hash, potremmo valutare inutilmente una catena.

Sebbene le tabelle arcobaleno debbano seguire più catene, compensano ciò avendo meno tabelle: le semplici tabelle di catene di hash non possono crescere oltre una certa dimensione senza diventare rapidamente inefficienti a causa della fusione delle catene; per far fronte a ciò, esse mantengono più tabelle, e ogni ricerca deve cercare attraverso ogni tabella. Le **tabelle arcobaleno** possono raggiungere prestazioni simili con tabelle che sono $k$ volte più grandi, permettendo loro di eseguire un fattore di $k$ in meno di ricerche.
#### Defense against rainbow tables
Una **rainbow table** è inefficace contro i one-way hash che includono grandi salt
### Brute-force attack
Gli attacchi brute-force consistono nel calcolare ogni possibile combinazione che potrebbe comporre una password e nel testarla per vedere se è la password corretta. All'aumentare della lunghezza della password, la quantità di tempo, in media, per trovare la password corretta aumenta esponenzialmente.

Tipi di attacchi di forza bruta:

- **Semplice attacco di brute force**
  utilizza un approccio sistematico che non si basa su una logica esterna
- **Attacchi dizionario**
  indovina nomi utente o password usando un dizionario di possibili stringhe o frasi
- **Attacchi ibridi di brute force**
  parte da una logica esterna per determinare quale variazione di password può avere più probabilità di successo, e poi continua con il semplice approccio di provare molte possibili variazioni
- **Attacco reverse brute force**
  utilizza una password comune o una collezione di password contro molti possibili nomi utente. Prende di mira una rete di utenti per i quali gli aggressori hanno precedentemente ottenuto dati
- **Credential stuffing**
  utilizza coppie *password-username* conosciute in precedenza, provandole con più siti web. Sfrutta il fatto che molti utenti hanno lo stesso nome utente e password su diversi sistemi
#### Strumenti di brute forcing
- **THC-Hydra**
  Esegue rapidamente un gran numero di combinazioni di password, sia simple brute force che dictionary-based. Può attaccare più di 50 protocolli e più sistemi operativi
- **Aircrack-ng**
  può essere utilizzato su Windows, Linux, iOS e Android. Utilizza un dizionario di password molto usate per violare le reti wireless
- **John the Ripper**
  funziona su 15 piattaforme diverse, tra cui Unix, Windows e OpenVMS. Prova tutte le combinazioni possibili usando un dizionario di possibili password
- **L0phtCrack**
  uno strumento per craccare le password di Windows. Utilizza **rainbow tables**, dizionari e algoritmi *multiprocessore*
- **Ophcrack**
  Ophcrack è un altro strumento per eseguire brute-force usato appositamente per craccare le password di Windows. Cracca le password di Windows utilizzando gli hash LM attraverso le **rainbow tables**
- **Hashcat**
  funziona su Windows, Linux e Mac OS. Può eseguire semplici attacchi brute force, rule-based e hybrid.
- **DaveGrohl**
  uno strumento open-source per craccare Mac OS. Può essere distribuito su più computer
- **Ncrack**
  uno strumento per craccare l'autenticazione di rete. Può essere usato su Windows, Linux e BSD
- **Rainbow Crack**
  genera **rainbow tables** da utilizzare durante degli attacchi, differisce da altri strumenti convenzionali di brute-forcing perchè le **rainbow tables** sono precomputed
## Hash e Sistemi Operativi
### Linux
Principalmente su linux le password sono hash-ate con un lungo *salt*, gli algoritmi utilizzabili sono:
- MD5, Blowfish, SHA-256, SHA-512.

### Windows
Per l'uso nelle reti **Windows**, inclusi i domini *Active Directory*, la password è memorizzata in due modi diversi per impostazione predefinita: come *LAN Manager one-way function* (**LM OWF**) e come **NT OWF.** 

Ci sono molti tipi diversi di funzioni unidirezionali. Tutte le funzioni hash sono, per definizione, funzioni unidirezionali. Tuttavia, anche le funzioni crittografiche ordinarie che sono tipicamente reversibili possono essere usate per creare una funzione unidirezionale. Questo può essere fatto scambiando i dati e la chiave in una funzione crittografica e criptando il valore fisso (la chiave) usando i dati come chiave. Questo è il caso per l'**hash LM** che viene calcolato come segue:

1.  La password è riempita con byte NULL fino a 14 caratteri esatti. Se la password è più lunga di 14 caratteri, viene sostituita con 14 byte NULL per le restanti operazioni.
2.  La password viene convertita in tutte le lettere maiuscole.
3.  La password viene divisa in due chiavi da 7 byte (56 bit).
4.  Ogni chiave è usata per criptare una stringa fissa.
5.  I due risultati del passo 4 sono concatenati e memorizzati come hash LM.

L'algoritmo **LM OWF** è incluso in **Windows** per la retro-compatibilità con software e hardware che non possono usare algoritmi più recenti.

L'**hash NT** è semplicemente un hash. La password è sottoposta a hash utilizzando l'algoritmo **MD4** e memorizzata. L'**NT OWF** è usato per l'autenticazione dei membri del dominio sia nei domini **Windows NT 4.0** e precedenti che nei domini *Active Directory*.

Né l'**hash NT** né l'**hash LM** sono concatenati con un qualche tipo di *salt*.

## Bibliografia
- [Cryptographic hash function](https://en.wikipedia.org/wiki/Cryptographic_hash_function)
  - Al-Kuwari, Saif; Davenport, James H.; Bradford, Russell J. (2011). ["Cryptographic Hash Functions: Recent Design Trends and Security Notions"](https://eprint.iacr.org/2011/565). *Cryptology ePrint Archive*. Report 2011/565
  - Rogaway, P.; Shrimpton, T. (2004). "Cryptographic Hash-Function Basics: Definitions, Implications, and Separations for Preimage Resistance, Second-Preimage Resistance, and Collision Resistance"
  - [Mendel et al.](https://en.wikipedia.org/wiki/Cryptographic_hash_function#CITEREFMendelRechbergerSchl%C3%A4ffer2009), p. 145:Concatenating ... is often used by implementors to "hedge bets" on hash functions. A combiner of the form MD5
  - [Harnik et al. 2005](https://en.wikipedia.org/wiki/Cryptographic_hash_function#CITEREFHarnikKilianNaorReingold2005), p. 99: the concatenation of hash functions as suggested in the TLS... is guaranteed to be as secure as the candidate that remains secure
  - [Joux 2004](https://en.wikipedia.org/wiki/Cryptographic_hash_function#CITEREFJoux2004)
  - [Finney, Hal](https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist) "Hal Finney (computer scientist)") (August 20, 2004). ["More Problems with Hash Functions"](https://web.archive.org/web/20160409095104/http://article.gmane.org/gmane.comp.encryption.general/5154). *The Cryptography Mailing List*. Archived from [the original](http://article.gmane.org/gmane.comp.encryption.general/5154) on April 9, 2016. Retrieved May 25, 2016
  - [Hoch & Shamir 2008](https://en.wikipedia.org/wiki/Cryptographic_hash_function#CITEREFHochShamir2008), pp. 616–630
  - Andrew Regenscheid, Ray Perlner, Shu-Jen Chang, John Kelsey, Mridul Nandi, Souradyuti Paul, [Status Report on the First Round of the SHA-3 Cryptographic Hash Algorithm Competition](https://nvlpubs.nist.gov/nistpubs/Legacy/IR/nistir7620.pdf)
  - XiaoyunWang, Dengguo Feng, Xuejia Lai, Hongbo Yu, [Collisions for Hash Functions MD4, MD5, HAVAL-128, and RIPEMD](https://eprint.iacr.org/2004/199.pdf)
  - Alshaikhli, Imad Fakhri; AlAhmad, Mohammad Abdulateef (2015), "Cryptographic Hash Function", *Handbook of Research on Threat Detection and Countermeasures in Network Security*, IGI Global, pp. 80–94
  - Xiaoyun Wang, [Yiqun Lisa Yin](https://en.wikipedia.org/wiki/Yiqun_Lisa_Yin "Yiqun Lisa Yin"), and Hongbo Yu, [Finding Collisions in the Full SHA-1](http://people.csail.mit.edu/yiqun/SHA1AttackProceedingVersion.pdf)
  - Bruce Schneier, [Cryptanalysis of SHA-1](http://www.schneier.com/blog/archives/2005/02/cryptanalysis_o.html) (summarizes Wang et al. results and their implications)
  - Fox-Brewster, Thomas. ["Google Just 'Shattered' An Old Crypto Algorithm – Here's Why That's Big For Web Security"](https://www.forbes.com/sites/thomasbrewster/2017/02/23/google-sha-1-hack-why-it-matters/#3f73df04c8cd). *Forbes*. Retrieved 2017-02-24
  - Alexander Sotirov, Marc Stevens, Jacob Appelbaum, Arjen Lenstra, David Molnar, Dag Arne Osvik, Benne de Weger, [MD5 considered harmful today: Creating a rogue CA certificate](http://www.win.tue.nl/hashclash/rogue-ca/), accessed March 29, 2009
  - Swinhoe, Dan (April 17, 2020). ["The 15 biggest data breaches of the 21st century"](https://www.csoonline.com/article/2130877/the-biggest-data-breaches-of-the-21st-century.html). CSO Magazine
  - Goodin, Dan (2012-12-10). ["25-GPU cluster cracks every standard Windows password in <6 hours"](https://arstechnica.com/information-technology/2012/12/25-gpu-cluster-cracks-every-standard-windows-password-in-6-hours/). [Ars Technica](https://en.wikipedia.org/wiki/Ars_Technica "Ars Technica"). Retrieved 2020-11-23
  - Claburn, Thomas (February 14, 2019). ["Use an 8-char Windows NTLM password? Don't. Every single one can be cracked in under 2.5hrs"](https://www.theregister.co.uk/2019/02/14/password_length/). *[www.theregister.co.uk](http://www.theregister.co.uk)*. Retrieved 2020-11-26
  - ["Mind-blowing GPU performance"](https://improsec.com/tech-blog/mind-blowing-gpu-performance). Improsec. January 3, 2020
  - Grassi Paul A. (June 2017). *SP 800-63B-3 – Digital Identity Guidelines, Authentication and Lifecycle Management*. NIST.
- [The First 30 Years of Cryptographic Hash Functions and the NIST SHA-3 Competition by Bart Preneel](https://www.esat.kuleuven.be/cosic/publications/article-1532.pdf)
- [Lifetimes of popular cryptographic hashes](https://valerieaurora.org/hash.html)
- [Collisions for Hash Functions MD4, MD5, HAVAL-128 and RIPEMD](https://eprint.iacr.org/2004/199.pdf)
- [popular tools for brute force attacks](https://resources.infosecinstitute.com/topic/popular-tools-for-brute-force-attacks/)
- [Rainbow table](https://en.wikipedia.org/wiki/Rainbow_table)
  - Oechslin, P. (2003). ["Making a Faster Cryptanalytic Time-Memory Trade-Off"](https://lasec.epfl.ch/pub/lasec/doc/Oech03.pdf) (PDF). *Advances in Cryptology - CRYPTO 2003*. Vol. 2729. pp. 617–630
  - Hellman, M. (1980). ["A cryptanalytic time-memory trade-off"](http://www-ee.stanford.edu/~hellman/publications/36.pdf) (PDF). *IEEE Transactions on Information Theory*. **26** (4): 401–406
  - ["LASEC - Security and Cryptography Laboratory: Dr Philippe Oechslin - Research"](https://lasec.epfl.ch/people/oechslin/). *Faculté I&C - School of Computer and Communication Sciences*. March 20
- [crackstation](https://crackstation.net/hashing-security.htm)
  - [Kerckhoffs's principle](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle)
- [Birthday attack](https://en.wikipedia.org/wiki/Birthday_attack)
  - Daniel J. Bernstein. ["Cost analysis of hash collisions : Will quantum computers make SHARCS obsolete?"](http://cr.yp.to/hash/collisioncost-20090823.pdf) (PDF). *Cr.yp.to*. Retrieved 29 October 2017.
  - Brassard, Gilles; HØyer, Peter; Tapp, Alain (20 April 1998). *LATIN'98: Theoretical Informatics*. Lecture Notes in Computer Science. Vol. 1380. Springer, Berlin, Heidelberg. pp. 163–169
- [understanding etc/shadow file](https://www.cyberciti.biz/faq/understanding-etcshadow-file/)
- [Microsoft Docs](https://docs.microsoft.com/)
- [Store passwords using Reversible Encryption](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/store-passwords-using-reversible-encryption)
- [Passwords technical overview](https://docs.microsoft.com/en-us/windows-server/security/kerberos/passwords-technical-overview)
- [MS NLMP](https://docs.microsoft.com/en-us/openspecs/windows_protocols/ms-nlmp/f05874ce-efe5-45f8-b9b7-7586a45763b3)
- [# Windows 10 Microsoft Passport (aka Microsoft Next Generation Credential) In Detail](https://adsecurity.org/?p=1535)
- [LSASS](https://en.wikipedia.org/wiki/Local_Security_Authority_Subsystem_Service)
- [Why doesnt microsoft implement salt on users passwords](https://security.stackexchange.com/questions/30654/why-doesnt-microsoft-implement-salt-on-users-passwords-in-windows/30657#30657)
