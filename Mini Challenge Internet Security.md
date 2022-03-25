# Mini Challenge Internet Security
Bruteforce password utente
Panoramica storica funzioni hash
Attachi possibili
Strumenti di brute forcing
Tabelle Rainbow/Rainbow List
Quali hash utilizzano gli ultimi sistemi operativi

---

Una funzione hash viene generalmente utilizzata per identificare un dato di variabile lunghezza con un indice di lunghezza fissa, utilizzato per esempio nelle tabelle di hash.

Le funzioni hash mappano un insieme in input di cardinalità nettamente superiore rispetto all'output, questo comporta collisioni, e in alcuni casi di utilizzo è necessario minimizzare queste collisioni
## Cyclic redundancy checks
| Nome          | Lunghezza |
| ------------- | --------- |
| cksum (Unix)  | 32 bits   |
| CRC-16        | 16 bits   |
| CRC-32        | 32 bits   |
| CRC-32 MPEG-2 | 32 bits   |
| CRC-64        | 64 bits   |

---
## Checksums
| Nome          | Lunghezza |tipo
| ------------- | --------- |-|

[BSD checksum (Unix)](https://en.wikipedia.org/wiki/BSD_checksum "BSD checksum")
|
16 bits
|
sum with circular rotation

[SYSV checksum (Unix)](https://en.wikipedia.org/wiki/SYSV_checksum "SYSV checksum")
|
16 bits
|
sum with circular rotation

sum8
|
8 bits
|
sum

[sum16](https://en.wikipedia.org/w/index.php?title=Sum16&action=edit&redlink=1 "Sum16 (page does not exist)")
|
16 bits
|
sum

sum24
|
24 bits
|
sum

sum32
|
32 bits
|
sum

[fletcher-4](https://en.wikipedia.org/wiki/Fletcher%27s_checksum "Fletcher's checksum")
|
4 bits
|
sum

[fletcher-8](https://en.wikipedia.org/wiki/Fletcher%27s_checksum "Fletcher's checksum")
|
8 bits
|
sum

[fletcher-16](https://en.wikipedia.org/wiki/Fletcher%27s_checksum "Fletcher's checksum")
|
16 bits
|
sum

[fletcher-32](https://en.wikipedia.org/wiki/Fletcher%27s_checksum "Fletcher's checksum")
|
32 bits
|
sum

[Adler-32](https://en.wikipedia.org/wiki/Adler-32 "Adler-32")
|
32 bits
|
sum

[xor8](https://en.wikipedia.org/wiki/Longitudinal_redundancy_check "Longitudinal redundancy check")
|
8 bits
|
sum

[Luhn algorithm](https://en.wikipedia.org/wiki/Luhn_algorithm "Luhn algorithm")
|
1 decimal digit
|
sum

[Verhoeff algorithm](https://en.wikipedia.org/wiki/Verhoeff_algorithm "Verhoeff algorithm")
|
1 decimal digit
|
sum

[Damm algorithm](https://en.wikipedia.org/wiki/Damm_algorithm "Damm algorithm")
|
1 decimal digit
|
[Quasigroup](https://en.wikipedia.org/wiki/Quasigroup "Quasigroup") [operation](https://en.wikipedia.org/wiki/Binary_operation "Binary operation")

-
## Universal hash function families[[edit](https://en.wikipedia.org/w/index.php?title=List_of_hash_functions&action=edit&section=3 "Edit section: Universal hash function families")]
Main article: [Universal hashing](https://en.wikipedia.org/wiki/Universal_hashing "Universal hashing")

Name

Length

hideType

[Rabin fingerprint](https://en.wikipedia.org/wiki/Rabin_fingerprint "Rabin fingerprint")

variable

multiply

[tabulation hashing](https://en.wikipedia.org/wiki/Tabulation_hashing "Tabulation hashing")

variable

XOR

[universal one-way hash function](https://en.wikipedia.org/wiki/Universal_one-way_hash_function "Universal one-way hash function")

[Zobrist hashing](https://en.wikipedia.org/wiki/Zobrist_hashing "Zobrist hashing")

variable

XOR
## Non-cryptographic hash functions[[edit](https://en.wikipedia.org/w/index.php?title=List_of_hash_functions&action=edit&section=4 "Edit section: Non-cryptographic hash functions")]
Name

Length

hideType

[Pearson hashing](https://en.wikipedia.org/wiki/Pearson_hashing "Pearson hashing")

8 bits (or more)

XOR/table

Paul Hsieh's SuperFastHash[[1]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-1>)

32 bits

[Buzhash](https://en.wikipedia.org/wiki/Rolling_hash#Cyclic_polynomial "Rolling hash")

variable

XOR/table

[Fowler–Noll–Vo hash function](https://en.wikipedia.org/wiki/Fowler%E2%80%93Noll%E2%80%93Vo_hash_function "Fowler–Noll–Vo hash function")\
(FNV Hash)

32, 64, 128, 256,\
512, or 1024 bits

xor/product or\
product/XOR

[Jenkins hash function](https://en.wikipedia.org/wiki/Jenkins_hash_function "Jenkins hash function")

32 or 64 bits

XOR/addition

[Bernstein](https://en.wikipedia.org/wiki/Daniel_J._Bernstein "Daniel J. Bernstein")'s hash *djb2*[[2]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-Hash_functions-2>)

32 or 64 bits

shift/add or mult/add\
or shift/add/xor or mult/xor

[PJW hash / Elf Hash](https://en.wikipedia.org/wiki/PJW_hash_function "PJW hash function")

32 or 64 bits

add,shift,xor

[MurmurHash](https://en.wikipedia.org/wiki/MurmurHash "MurmurHash")

32, 64, or 128 bits

product/rotation

Fast-Hash[[3]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-fasthash_github-3>)

32, 64 bits

[xorshift](https://en.wikipedia.org/wiki/Xorshift "Xorshift") operations

SpookyHash

32, 64, or 128 bits

see [Jenkins hash function](https://en.wikipedia.org/wiki/Jenkins_hash_function "Jenkins hash function")

CityHash[[4]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-4>)

32, 64, 128, or 256 bits

FarmHash[[5]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-5>)

32, 64 or 128 bits

MetroHash[[6]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-6>)

64 or 128 bits

numeric hash (nhash)[[7]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-7>)

variable

division/modulo

xxHash[[8]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-8>)

32, 64, 128 bits

product/rotation

[t1ha (Fast Positive Hash)](https://en.wikipedia.org/w/index.php?title=T1ha_(Fast_Positive_Hash)&action=edit&redlink=1 "T1ha (Fast Positive Hash) (page does not exist)")[[9]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-t1ha_github-9>)

64 and 128 bits

product/rotation/XOR/add

pHash[[10]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-pHash.org-10>)

fixed or variable

see [Perceptual hashing](https://en.wikipedia.org/wiki/Perceptual_hashing "Perceptual hashing")

dhash[[11]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-11>)

128 bits

see [Perceptual hashing](https://en.wikipedia.org/wiki/Perceptual_hashing "Perceptual hashing")

SDBM [[2]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-Hash_functions-2)[[12]](https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-12)>

32 or 64 bits

mult/add or shift/add\
also used in [GNU AWK](https://en.wikipedia.org/wiki/GAWK "GAWK")
## Keyed cryptographic hash functions[[edit](https://en.wikipedia.org/w/index.php?title=List_of_hash_functions&action=edit&section=5 "Edit section: Keyed cryptographic hash functions")]
Main article: [Message authentication code](https://en.wikipedia.org/wiki/Message_authentication_code "Message authentication code")

Name

Tag Length

hideType

[BLAKE2](https://en.wikipedia.org/wiki/BLAKE_(hash_function)#BLAKE2 "BLAKE (hash function)")

arbitrary

keyed hash function (prefix-MAC)

[BLAKE3](https://en.wikipedia.org/wiki/BLAKE3 "BLAKE3")

arbitrary

keyed hash function (supplied IV)

[HMAC](https://en.wikipedia.org/wiki/HMAC "HMAC")

[KMAC](https://en.wikipedia.org/wiki/SHA-3#Additional_instances "SHA-3")

arbitrary

based on Keccak

[MD6](https://en.wikipedia.org/wiki/MD6 "MD6")

512 bits

[Merkle tree](https://en.wikipedia.org/wiki/Merkle_tree "Merkle tree") [NLFSR](https://en.wikipedia.org/wiki/NLFSR "NLFSR")

[One-key MAC](https://en.wikipedia.org/wiki/One-key_MAC "One-key MAC") (OMAC; CMAC)

[PMAC (cryptography)](https://en.wikipedia.org/wiki/PMAC_(cryptography) "PMAC (cryptography)")

[Poly1305-AES](https://en.wikipedia.org/wiki/Poly1305-AES "Poly1305-AES")

128 bits

nonce-based

[SipHash](https://en.wikipedia.org/wiki/SipHash "SipHash")

32, 64 or 128 bits

non-collision-resistant PRF

HighwayHash[[13]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-13>)

64, 128 or 256 bits

non-collision-resistant PRF

[UMAC](https://en.wikipedia.org/wiki/UMAC "UMAC")

[VMAC](https://en.wikipedia.org/wiki/VMAC "VMAC")
## Unkeyed cryptographic hash functions[[edit](https://en.wikipedia.org/w/index.php?title=List_of_hash_functions&action=edit&section=6 "Edit section: Unkeyed cryptographic hash functions")]
Main article: [Cryptographic hash function](https://en.wikipedia.org/wiki/Cryptographic_hash_function "Cryptographic hash function")

See also: [Comparison of cryptographic hash functions](https://en.wikipedia.org/wiki/Comparison_of_cryptographic_hash_functions "Comparison of cryptographic hash functions")

Name

Length

hideType

[BLAKE-256](https://en.wikipedia.org/wiki/BLAKE_(hash_function) "BLAKE (hash function)")

256 bits

HAIFA structure[[14]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-haifa-14>)

[BLAKE-512](https://en.wikipedia.org/wiki/BLAKE_(hash_function) "BLAKE (hash function)")

512 bits

HAIFA structure[[14]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-haifa-14>)

[BLAKE2s](https://en.wikipedia.org/wiki/BLAKE_(hash_function)#BLAKE2 "BLAKE (hash function)")

up to 256 bits

HAIFA structure[[14]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-haifa-14>)

[BLAKE2b](https://en.wikipedia.org/wiki/BLAKE_(hash_function)#BLAKE2 "BLAKE (hash function)")

up to 512 bits

HAIFA structure[[14]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-haifa-14>)

[BLAKE2X](https://en.wikipedia.org/wiki/BLAKE_(hash_function)#BLAKE2 "BLAKE (hash function)")

arbitrary

HAIFA structure,[[14]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-haifa-14>) extensible-output functions (XOFs) design[[15]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-BLAKE2X-15>)

[BLAKE3](https://en.wikipedia.org/wiki/BLAKE3 "BLAKE3")

arbitrary

[Merkle tree](https://en.wikipedia.org/wiki/Merkle_tree "Merkle tree")

[ECOH](https://en.wikipedia.org/wiki/Elliptic_curve_only_hash "Elliptic curve only hash")

224 to 512 bits

hash

[FSB](https://en.wikipedia.org/wiki/Fast_Syndrome_Based_Hash "Fast Syndrome Based Hash")

160 to 512 bits

hash

[GOST](https://en.wikipedia.org/wiki/GOST_(hash_function) "GOST (hash function)")

256 bits

hash

[Grøstl](https://en.wikipedia.org/wiki/Gr%C3%B8stl "Grøstl")

up to 512 bits

hash

[HAS-160](https://en.wikipedia.org/wiki/HAS-160 "HAS-160")

160 bits

hash

[HAVAL](https://en.wikipedia.org/wiki/HAVAL "HAVAL")

128 to 256 bits

hash

[JH](https://en.wikipedia.org/wiki/JH_(hash_function) "JH (hash function)")

224 to 512 bits

hash

LSH[[16]](<https://en.wikipedia.org/wiki/List_of_hash_functions#cite_note-lsw-16>)

256 to 512 bits

wide-pipe [Merkle–Damgård construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")

[MD2](https://en.wikipedia.org/wiki/MD2_(cryptography) "MD2 (cryptography)")

128 bits

hash

[MD4](https://en.wikipedia.org/wiki/MD4 "MD4")

128 bits

hash

[MD5](https://en.wikipedia.org/wiki/MD5 "MD5")

128 bits

[Merkle–Damgård construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")

[MD6](https://en.wikipedia.org/wiki/MD6 "MD6")

up to 512 bits

[Merkle tree](https://en.wikipedia.org/wiki/Merkle_tree "Merkle tree") [NLFSR](https://en.wikipedia.org/wiki/NLFSR "NLFSR") (it is also a keyed hash function)

[RadioGatún](https://en.wikipedia.org/wiki/RadioGat%C3%BAn "RadioGatún")

arbitrary

ideal mangling function

[RIPEMD](https://en.wikipedia.org/wiki/RIPEMD "RIPEMD")

128 bits

hash

[RIPEMD-128](https://en.wikipedia.org/wiki/RIPEMD "RIPEMD")

128 bits

hash

[RIPEMD-160](https://en.wikipedia.org/wiki/RIPEMD "RIPEMD")

160 bits

hash

[RIPEMD-320](https://en.wikipedia.org/wiki/RIPEMD "RIPEMD")

320 bits

hash

[SHA-1](https://en.wikipedia.org/wiki/SHA-1 "SHA-1")

160 bits

[Merkle–Damgård construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")

[SHA-224](https://en.wikipedia.org/wiki/SHA-2 "SHA-2")

224 bits

[Merkle–Damgård construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")

[SHA-256](https://en.wikipedia.org/wiki/SHA-2 "SHA-2")

256 bits

[Merkle–Damgård construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")

[SHA-384](https://en.wikipedia.org/wiki/SHA-2 "SHA-2")

384 bits

[Merkle–Damgård construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")

[SHA-512](https://en.wikipedia.org/wiki/SHA-2 "SHA-2")

512 bits

[Merkle–Damgård construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")

[SHA-3](https://en.wikipedia.org/wiki/SHA-3 "SHA-3") (subset of Keccak)

arbitrary

[sponge function](https://en.wikipedia.org/wiki/Sponge_function "Sponge function")

[Skein](https://en.wikipedia.org/wiki/Skein_(hash_function) "Skein (hash function)")

arbitrary

[Unique Block Iteration](https://en.wikipedia.org/w/index.php?title=Unique_Block_Iteration&action=edit&redlink=1 "Unique Block Iteration (page does not exist)")

[Snefru](https://en.wikipedia.org/wiki/Snefru "Snefru")

128 or 256 bits

hash

[Spectral Hash](https://en.wikipedia.org/wiki/Spectral_Hash "Spectral Hash")

512 bits

wide-pipe Merkle–Damgård construction

[Streebog](https://en.wikipedia.org/wiki/Streebog "Streebog")

256 or 512 bits

[Merkle–Damgård construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")

[SWIFFT](https://en.wikipedia.org/wiki/SWIFFT "SWIFFT")

512 bits

hash

[Tiger](https://en.wikipedia.org/wiki/Tiger_(cryptography) "Tiger (cryptography)")

192 bits

[Merkle–Damgård construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction "Merkle–Damgård construction")

[Whirlpool](https://en.wikipedia.org/wiki/Whirlpool_(cryptography) "Whirlpool (cryptography)")

512 bits

hash
