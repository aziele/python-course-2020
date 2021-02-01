# Projektowanie i tworzenie skryptów

Na tych zajęciach potrzebne będą dwa pliki, które dotyczą sekwencji DNA bakterii *M. hominis*:

1. [Mycoplasma_hominis.fasta](./data/Mycoplasma_hominis.fasta) zawiera 15 sekwencji genomowych tej bakterii.
```
>contig011 dna:supercontig supercontig:ASM75938v1:contig011:1:234279:1 REF
ACAGCCAGCGTTCATCCTGAGCCAGGATCAAACTCTTATAAAAAAATTTGAATTGGTTGA
TTATAAATAAAAAAATAAATTGACGTTAATGGTATTCGTATCCAGTTTTCAAAGAACTAT
CTCGTTGTTTCAAAACAACCTTTAAATATTATATACACTTTTTTTTATTTTTTCAAAAAA
...
>contig008 dna:supercontig supercontig:ASM75938v1:contig008:1:234153:1 REF
CAAGAAGTCAAATTGAAGCATTCATTAATGCAAATAAAACTAATCAAAATTATGCAGATT
TGATTGCAAAATTAACTAATGCTAAAAAAGCAAAGGAATCAGTTTCTGAATCTTCAAATA
AATCAGACATTATTGCAGCAAATCAAGCCTTACAACAAGCATTAAATACTGCGAAGGCTA
...
```
2. [Mycoplasma_hominis.gtf](./data/Mycoplasma_hominis.gtf) zawiera w osobnych wierszach adnotacje wszystkich znanych fragmentów genomowych tej bakterii (np.: *gene*, *transcript*, *CDS*, itd.) w odniesieniu do sekwencji genomowej powyżej.
```
#!genome-build ASM75938v1
#!genome-version ASM75938v1
#!genome-date 2014-10
#!genome-build-accession GCA_000759385.1
#!genebuild-last-updated 2014-10
contig011   ena gene    1   105 .   -   .   gene_id "JX73_01575"; gene_name "JX73_01575"; gene_source "ena"; gene_biotype "rRNA";
contig011   ena transcript  1   105 .   -   .   gene_id "JX73_01575"; transcript_id "JX73_01575-1"; gene_name "JX73_01575"; gene_source "ena"; gene_biotype "rRNA"; transcript_name "JX73_01575"; transcript_source "ena"; transcript_biotype "rRNA";
contig011   ena exon    1   105 .   -   .   gene_id "JX73_01575"; transcript_id "JX73_01575-1"; exon_number "1"; gene_name "JX73_01575"; gene_source "ena"; gene_biotype "rRNA"; transcript_name "JX73_01575"; transcript_source "ena"; transcript_biotype "rRNA"; exon_id "JX73_01575-1";
contig011   ena gene    5831    5905    .   +   .   gene_id "JX73_01605"; gene_name "JX73_01605"; gene_source "ena"; gene_biotype "tRNA";
...
```

Na przykład gen `JX73_01575` znajduje się w sekwencji `contig011` na nici `-` w lokalizacji `1` - `105` i koduje `rRNA`. Z kolei gen `JX73_01605` znajdujący się w sekwencji `contig011` umiejsowiony jest na nici `+` w pozycji `5831` - `5905`.

---

## Zad. 1
Zaprojektuj i utwórz skrypt `07-01.py`, który na podstawie informacji zawartych w pliku z adnotacjami wydobędzie sekwencje genów i zapisze je do pliku `genes.fasta` w poniższym formacie:

```
>contig011|gene|JX73_01575|1:105|-
ACAGCCAGCGTTCATCCTGAGCCAGGATCAAACTCTTATAAAAAAATTTGAATTGGTTGATTATAAATAAAAAAATAAATTGACGTTAATGGTATTCGTATCCAG
>contig011|gene|JX73_01605|5831:5905|+
GGTCGCATAGCTCAGTGGAAGAGCACGAGCCTCCTAAGCCCGGGGTCGCAGGTTCAACTCCTGTTGCGATCGCCA
>...
```


## Zad. 2
Zmodyfikuj skrypt, aby sekwencje genów nici `-` zostały zapisane do pliku w kierunku 5'-3' (tj. odwrotnie komplementarnym). W tym celu wykorzystaj funckję `reverse_complement` z [lab05](./lab05.md) (zad. 16). 


```
>contig011|gene|JX73_01575|1:105|-
CTGGATACGAATACCATTAACGTCAATTTATTTTTTTATTTATAATCAACCAATTCAAATTTTTTTATAAGAGTTTGATCCTGGCTCAGGATGAACGCTGGCTGT
>contig011|gene|JX73_01605|5831:5905|+
GGTCGCATAGCTCAGTGGAAGAGCACGAGCCTCCTAAGCCCGGGGTCGCAGGTTCAACTCCTGTTGCGATCGCCA
>...
```


## Zad. 3
Zmodyfikuj skrypt, aby sekwencja w pliku wynikowym była zawinięta do 60 znaków.

> Wskazówka: Utwórz funkcję `wrap`, która przyjmuje jako argument string i liczbę znaków do zawinięcia tekstu.

```
>contig011|gene|JX73_01575|1:105|-
CTGGATACGAATACCATTAACGTCAATTTATTTTTTTATTTATAATCAACCAATTCAAAT
TTTTTTATAAGAGTTTGATCCTGGCTCAGGATGAACGCTGGCTGT
>contig011|gene|JX73_01605|5831:5905|+
GGTCGCATAGCTCAGTGGAAGAGCACGAGCCTCCTAAGCCCGGGGTCGCAGGTTCAACTC
CTGTTGCGATCGCCA
>...
```

## Zad. 4
Zapoznaj się z poniższym kodem i zmodyfikuj skrypt `07-01.py`, aby przyjmował on nazwy plików z systemowego wiersza poleceń.

script.py
```python
import sys

print(sys.argv)
```

bash
```bash
python3 script.py Mycoplasma_hominis.fasta Mycoplasma_hominis.gtf
['script.py', 'Mycoplasma_hominis.fasta', 'Mycoplasma_hominis.gtf']
```


## Zad. 5
Zmodyfikuj skrypt, aby użytkownik mógł również wpisać w poleceniu typ sekwencji: `gene`, `CDS`, `transcript`, `exon`.

```bash
python3 07-01.py Mycoplasma_hominis.fasta Mycoplasma_hominis.gtf CDS
```

```
>contig011|CDS|JX73_01580|323:907|-
ATGGAATTAACAAATAATGATTTTAAATGATATATGATTTCAACAGTTTCAGGCAAAGAA
GAAAATGTTATAGAATCATTAAAAAATAAAATTGCTGCTCAAAGAATGGATGAATACTTT
AAAGATATAAGGATGTTTAAAGAACCCCATCTATCAAATAAAGAATTAGAAAAGAAGCAA
AGAAACGAAGAATTTACTGTTAAATTTGTAAATATGTACAAAGGTTATATTTTTTTAAAT
ATGGCAATGACTGATGATACATGATATCTTGTTAGAAATACTCAATATGTAACCGGACTA
ATTGGTTCAAGTGGTAACAAAACAAAACCAACCCCAATAAGTGATAAAAAATTCCAATTA
ATGATTGATAAAGAAGCAATGTTGCTAGCTAAATTTAAAGCAGGGGACATTGAAACTGCT
TTTAAAGAAGGGGCTTTAGTAAAAATTTCTAGTGGAATATTCAAAGATGAAGTTGGCGAA
ATAATTAAAAATAATGATATTACCCAAAAAGCCTTTGTTAATATTGAACAATTTGGTAGA
AAAGTTCCAACTGAATTTGATTATGCAGATCTAGAAATAGTAGGT
>contig011|CDS|JX73_01585|923:1159|-
ATGACTAGAGAACAAAAAAAACAAGCTAAATTGCAAGCAAAAGCAGAAAAAGGCCAAGTT
AAGCTATATACATTTCGAAATTGAATAAAGGAAATAAAGAGAGTTATCTGGCCAAAATCT
GCAAAATCTTGAAAATGATTTGGTATTACAATTTTATTTCTAGTTTTAATGGCTGCATTT
TGTTTTGCAATAACCCTTGGATTTAGTAGTTTATGAAATTCAGTAGGAATAAAGGCT
...
```