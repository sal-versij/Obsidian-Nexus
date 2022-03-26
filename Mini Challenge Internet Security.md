# Mini Challenge Internet Security
# Funzioni Hash
Una funzione hash è una funzione di mappatura tra dati di arbitraria lunghezza e **digest** di lunghezza fissa.
Le funzioni hash mappano un insieme in input di cardinalità nettamente superiore rispetto all'output, questo comporta collisioni, e in alcuni casi di utilizzo è necessario minimizzare queste collisioni
## Panoramica storica funzioni hash
## Attachi possibili
### Bruteforce
#### Strumenti di brute forcing
## Tabelle Rainbow
## Hash e Sistemi Operativi

---
# References
## Cyclic redundancy checks
| Nome           | Lunghezza |
| -------------- | --------- |
| cksum (Unix)   | 32 bits   |
| CRC-16         | 16 bits   |
| CRC-32         | 32 bits   |
| CRC-32 MPEG-2  | 32 bits   |
| CRC-64         | 64 bits   |

---
## Checksums
| Nome                 | Lunghezza       | tipo                       |
| -------------------- | --------------- | -------------------------- |
| BSD checksum (Unix)  | 16 bits         | sum with circular rotation |
| SYSV checksum (Unix) | 16 bits         | sum with circular rotation |
| sum8                 | 8 bits          | sum                        |
| sum16                | 16 bits         | sum                        |
| sum24                | 24 bits         | sum                        |
| sum32                | 32 bits         | sum                        |
| fletcher-4           | 4 bits          | sum                        |
| fletcher-8           | 8 bits          | sum                        |
| fletcher-16          | 16 bits         | sum                        |
| fletcher-32          | 32 bits         | sum                        |
| Adler-32             | 32 bits         | sum                        |
| xor8                 | 8 bits          | sum                        |
| Luhn algorithm       | 1 decimal digit | sum                        |
| Verhoeff algorithm   | 1 decimal digit | sum                        |
| Damm algorithm       | 1 decimal digit | Quasigroup operation       |

---
## Universal hash function families
| Nome                            | Lunghezza | tipo     |
| ------------------------------- | --------- | -------- |
| Rabin fingerprint               | variable  | multiply |
| tabulation hashing              | variable  | XOR      |
| universal one-way hash function |           |          |
| Zobrist hashing                 | variable  | XOR      |

---
## Non-cryptographic hash functions
| Nome                                                                                                  | Lunghezza                          | tipo                                               |
| ----------------------------------------------------------------------------------------------------- | ---------------------------------- | -------------------------------------------------- |
| Pearson hashing                                                                                       | 8 bits (or more)                   | XOR/table                                          |
| Paul Hsieh's SuperFastHash                                                                            | 32 bits                            |                                                    |
| Buzhash                                                                                               | variable                           | XOR/table                                          |
| Fowler–Noll–Vo hash function\\                                                                        |                                    |                                                    |
| (FNV Hash)                                                                                            | 32, 64, 128, 256,512, or 1024 bits | xor/product or product/XOR                         |
| Jenkins hash function                                                                                 | 32 or 64 bits                      | XOR/addition                                       |
| Bernstein's hash *djb2*                                                                               | 32 or 64 bits                      | shift/add or mult/add or shift/add/xor or mult/xor |
| PJW hash / Elf Hash                                                                                   | 32 or 64 bits                      | add,shift,xor                                      |
| MurmurHash                                                                                            | 32, 64, or 128 bits                | product/rotation                                   |
| Fast-Hash                                                                                             | 32, 64 bits                        | xorshift operations                                |
| SpookyHash                                                                                            | 32, 64, or 128 bits                | see Jenkins hash function                          |
| CityHash                                                                                              | 32, 64, 128, or 256 bits           |                                                    |
| FarmHash                                                                                              | 32, 64 or 128 bits                 |                                                    |
| MetroHash                                                                                             | 64 or 128 bits                     |                                                    |
| numeric hash (nhash)                                                                                  | variable                           | division/modulo                                    |
| xxHash                                                                                                | 32, 64, 128 bits                   | product/rotation                                   |
| t1ha (Fast Positive Hash)&action=edit&redlink=1 "T1ha (Fast Positive Hash) (page does not exist)")[9] | 64 and 128 bits                    | product/rotation/XOR/add                           |
| pHash                                                                                                 | fixed or variable                  | see Perceptual hashing                             |
| dhash                                                                                                 | 128 bits                           | see Perceptual hashing                             |
| SDBM                                                                                                  | 32 or 64 bits                      | mult/add or shift/add also used in GNU AWK         |

---
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


## Citations
- https://en.wikipedia.org/wiki/List_of_hash_functions
- https://www.sicurezzanazionale.gov.it/sisr.nsf/wp-content/uploads/2015/09/Crittografia-tra-arte-e-scienza-Tampanella.pdf
- https://www.growhub.it/varie/come-si-fa-un-attacco-brute-force/
- https://en.wikipedia.org/wiki/Brute-force_attack
- https://www.proofpoint.com/it/threat-reference/brute-force-attack
- https://resources.infosecinstitute.com/topic/popular-tools-for-brute-force-attacks/
