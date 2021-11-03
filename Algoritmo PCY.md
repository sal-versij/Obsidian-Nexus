# Algoritmo PCY
#study #not-understood

> Algoritmo di Park, Chen, Yu

```ad-def
In una prima passata sui dati contiamo il supporto deli item e leggiamo le coppie di item in ogni basket.

Le coppie lette vengono raggruppate in bucket usando una funzione hash.

Se il supporto di un bucket è sotto la soglia, allora nessuna coppia di item che va a finire nel bucket sarà frequente.

Una bitmap può essere costruita per denotare se un bucket è frequente o no.

L'insieme delle coppie candidate $C_2$ sarà formato dalle coppie $(i,j)$ tali che:
- $i$ e $j$ sono item frequenti
- La coppia $(i,j)$ cade in un bucket
```
