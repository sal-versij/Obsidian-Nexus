# Maximal and Closed Frequent Items
A variant of [[Association rule learning]] consiste nella ricerca di **Maximal [[Frequent Itemsets]]** or **Closed [[Frequent Itemsets]]**.

```ad-def
title:Insieme frequente chiuso
se non esiste un suo super-insieme che ha lo stesso supporto.
```

```ad-def
title:Insieme frequente massimale
se non esiste un suo super-insieme frequente.
```

```ad-note
collapse:true
title:Relazioni tra insiemi chiusi e massimali
- Gli insiemi frequenti massimali sono anche insiemi frequenti chiusi
- Qualsiasi algoritmo in grado di trovare insiemi frequenti è anche in grado di trovare insiemi frequenti massimali e chiusi
- Per questo motivo, ci concentreremo sul problema della ricerca di itemset frequenti

```
## Examples
![[Frequent Itemset's Supports.png]]
![[Clsoed & Maximal Frequent Itemset.png]]
