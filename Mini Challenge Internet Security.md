# Mini Challenge Internet Security
# Funzioni Hash
Una funzione hash è una funzione di mappatura tra dati di arbitraria lunghezza e valori di lunghezza fissa, anche chiamati **hash values**, **hash codes**, **digests**, o semplicemente **hashes**.
Le funzioni hash mappano un insieme in input di cardinalità nettamente superiore rispetto all'output, questo comporta inevitabilmente collisioni, dimostrato dal teorema dei cassetti, quindi una metrica da analizzare quando si parla di funzioni hash è proprio la probabilità di collissione.

L'uso delle funzioni hash si basa sulle proprietà statistiche della relazione tra chiave e funzione:

- nel caso peggiore si ha elevatissima probabiltà di collisioni, ma il caso peggiore stesso ha probabilità inifitamente piccola
- nel caso medio si ha collisione minima

Le funzioni di hash sono collegate a (e spesso confuse con) **checksum**, **check digits**, **fingerprints**, **compressione lossy**, **funzioni di randomizzazione**, **error-correcting codes** e **cifrari**. Anche se i concetti si sovrappongono in una certa misura, ognuno ha i propri usi e requisiti ed è progettato e ottimizzato in modo diverso. La funzione hash differisce da questi concetti principalmente in termini di integrità dei dati.

Nel caso della sicurezza informatica le funzioni hash utilizzate sono crittografiche, quindi rispetta le seguenti proprietà:

- deve essere *deterministica*:
  dato lo stesso input darà **sempre** lo stesso output
- è *efficente* da computare per ogni dato input
- **non** è possibile *invertire* il processo:
  è impossibile generare un messaggio che produce un predeterminato **digest**
- **non** è possibile generare una *collisione*:
  trovare due input che forniscono lo stesso digest
- Gode della proprietà crittografica **avalanche effect**:
  una piccola modifica all'input genera un **digest** drasticamente diverso dall'originale, al punto che i due **digest** appaiono non correlati tra loro

Nella crittografia teorica, il livello di sicurezza di una funzione hash crittografica è definito utilizzando le seguenti proprietà:
- **Pre-image resistance**
  Dato un valore di hash $h$, dovrebbe essere difficile trovare qualsiasi messaggio $m$ tale che $h = \text{hash}(m)$. Le funzioni che non soddisfano questa proprietà sono vulnerabili agli attacchi preimage.
- **Second pre-image resistance**
  Dato un input $m_1$, deve essere difficile trovare un diverso input $m_2$ tale che $\text{hash}(m_1) = \text{hash}(m_2)$. Questa proprietà è talvolta indicata come **weak collision resistance**. Le funzioni che mancano di questa proprietà sono vulnerabili agli attacchi di seconda immagine.
- **Collision resistance**
  Dovrebbe essere difficile trovare due messaggi diversi $m_1$ e $m_2$ tali che $\text{hash}(m_1) = \text{hash}(m_2)$. Una tale coppia è chiamata **cryptographic hash collision**. Questa proprietà è talvolta indicata come **strong collision resistance**. Richiede un valore di hash almeno due volte più lungo di quello richiesto per la resistenza alla pre-immagine; altrimenti le collisioni possono essere trovate da un attacco di compleanno

Collision resistance implies second pre-image resistance but does not imply pre-image resistance.[[5]](https://en.wikipedia.org/wiki/Cryptographic_hash_function#cite_note-FOOTNOTERogawayShrimpton2004in_Sec._5._Implications-5) The weaker assumption is always preferred in theoretical cryptography, but in practice, a hash-function which is only second pre-image resistant is considered insecure and is therefore not recommended for real applications.

Informally, these properties mean that a [malicious adversary](https://en.wikipedia.org/wiki/Adversary_(cryptography) "Adversary (cryptography)") cannot replace or modify the input data without changing its digest. Thus, if two strings have the same digest, one can be very confident that they are identical. Second pre-image resistance prevents an attacker from crafting a document with the same hash as a document the attacker cannot control. Collision resistance prevents an attacker from creating two distinct documents with the same hash.

A function meeting these criteria may still have undesirable properties. Currently, popular cryptographic hash functions are vulnerable to [_length-extension_ attacks](https://en.wikipedia.org/wiki/Length_extension_attack "Length extension attack"): given hash(_m_) and len(_m_) but not _m_, by choosing a suitable _m_′ an attacker can calculate hash(_m_ ∥ _m_′), where ∥ denotes [concatenation](https://en.wikipedia.org/wiki/Concatenation "Concatenation").[[6]](https://en.wikipedia.org/wiki/Cryptographic_hash_function#cite_note-Y0rF6-6) This property can be used to break naive authentication schemes based on hash functions. The [HMAC](https://en.wikipedia.org/wiki/HMAC "HMAC") construction works around these problems.

In practice, collision resistance is insufficient for many practical uses. In addition to collision resistance, it should be impossible for an adversary to find two messages with substantially similar digests; or to infer any useful information about the data, given only its digest. In particular, a hash function should behave as much as possible like a [random function](https://en.wikipedia.org/wiki/Random_function "Random function") (often called a [random oracle](https://en.wikipedia.org/wiki/Random_oracle "Random oracle") in proofs of security) while still being deterministic and efficiently computable. This rules out functions like the [SWIFFT](https://en.wikipedia.org/wiki/SWIFFT "SWIFFT") function, which can be rigorously proven to be collision-resistant assuming that certain problems on ideal lattices are computationally difficult, but, as a linear function, does not satisfy these additional properties.[[7]](https://en.wikipedia.org/wiki/Cryptographic_hash_function#cite_note-FOOTNOTELyubashevskyMicciancioPeikertRosen200854%E2%80%9372-7)

Checksum algorithms, such as [CRC32](https://en.wikipedia.org/wiki/CRC32 "CRC32") and other [cyclic redundancy checks](https://en.wikipedia.org/wiki/Cyclic_redundancy_check "Cyclic redundancy check"), are designed to meet much weaker requirements and are generally unsuitable as cryptographic hash functions. For example, a CRC was used for message integrity in the [WEP](https://en.wikipedia.org/wiki/Wired_Equivalent_Privacy "Wired Equivalent Privacy") encryption standard, but an attack was readily discovered, which exploited the linearity of the checksum.

### Degree of difficulty[[edit](https://en.wikipedia.org/w/index.php?title=Cryptographic_hash_function&action=edit&section=2 "Edit section: Degree of difficulty")]

In cryptographic practice, "difficult" generally means "almost certainly beyond the reach of any adversary who must be prevented from breaking the system for as long as the security of the system is deemed important". The meaning of the term is therefore somewhat dependent on the application since the effort that a malicious agent may put into the task is usually proportional to their expected gain. However, since the needed effort usually multiplies with the digest length, even a thousand-fold advantage in processing power can be neutralized by adding a few dozen bits to the latter.

For messages selected from a limited set of messages, for example [passwords](https://en.wikipedia.org/wiki/Password "Password") or other short messages, it can be feasible to invert a hash by trying all possible messages in the set. Because cryptographic hash functions are typically designed to be computed quickly, special [key derivation functions](https://en.wikipedia.org/wiki/Key_derivation_function "Key derivation function") that require greater computing resources have been developed that make such [brute-force attacks](https://en.wikipedia.org/wiki/Brute-force_attack "Brute-force attack") more difficult.

In some [theoretical analyses](https://en.wikipedia.org/wiki/Computational_complexity_theory "Computational complexity theory") "difficult" has a specific mathematical meaning, such as "not solvable in [asymptotic](https://en.wikipedia.org/wiki/Asymptotic_computational_complexity "Asymptotic computational complexity") [polynomial time](https://en.wikipedia.org/wiki/Polynomial_time "Polynomial time")". Such interpretations of _difficulty_ are important in the study of [provably secure cryptographic hash functions](https://en.wikipedia.org/wiki/Provably_secure_cryptographic_hash_function "Provably secure cryptographic hash function") but do not usually have a strong connection to practical security. For example, an [exponential-time](https://en.wikipedia.org/wiki/Exponential_time "Exponential time") algorithm can sometimes still be fast enough to make a feasible attack. Conversely, a polynomial-time algorithm (e.g., one that requires _n_20 steps for _n_-digit keys) may be too slow for any practical use.
## Panoramica storica funzioni hash
## Attachi possibili
### Bruteforce
#### Strumenti di brute forcing
## Tabelle Rainbow
## Hash e Sistemi Operativi
---
# References
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

- <https://en.wikipedia.org/wiki/Hash_function>
- <https://en.wikipedia.org/wiki/List_of_hash_functions>
- <https://en.wikipedia.org/wiki/Cryptographic_hash_function>
- <https://en.wikipedia.org/wiki/Brute-force_attack>
- <https://en.wikipedia.org/wiki/Deterministic_algorithm>
- <https://en.wikipedia.org/wiki/Avalanche_effect>
- https://en.wikipedia.org/wiki/Birthday_attack
- <https://www.sicurezzanazionale.gov.it/sisr.nsf/wp-content/uploads/2015/09/Crittografia-tra-arte-e-scienza-Tampanella.pdf>
- <https://www.growhub.it/varie/come-si-fa-un-attacco-brute-force/>
- <https://www.proofpoint.com/it/threat-reference/brute-force-attack>
- <https://resources.infosecinstitute.com/topic/popular-tools-for-brute-force-attacks/>
