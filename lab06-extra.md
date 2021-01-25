## Zad. 20
Celem zadania jest obliczenie podobieństwa sekwencji między każdą parą wirusów z pliku [phages.fasta](./data/phages.fasta).

Dla każdej sekwencji wirusa wyodrębnij zbiór wszystkich jego podsekwencji długości 10 nukleotydów. Następnie oblicz [współczynnik podobieństwa Jaccarda](https://pl.wikipedia.org/wiki/Indeks_Jaccarda) pomiędzy każdą parą wirusów.

OUTPUT:

```
NC_000866.4    NC_000871.1    0.052327459800680966
NC_000866.4    NC_000872.1    0.058190024217813545
NC_000866.4    NC_000896.1    0.06743851785083499
NC_000866.4    NC_000902.1    0.049351275268499195
...
```

Która para wirusów ma największe podobieństwo sekwencji?