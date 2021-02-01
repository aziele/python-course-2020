## Zad. 6
Zapoznaj się z działaniem poniższego skryptu `07-06.py`.

```python
import argparse

parser = argparse.ArgumentParser(description='Retrieve FASTA sequences')

parser.add_argument('fasta', metavar='fasta_file', type=argparse.FileType('r'),
                    help='Genome sequence in FASTA')
parser.add_argument('gtf', metavar='gtf_file', type=argparse.FileType('r'),
                    help='Genome annotation in GTF')
parser.add_argument('-out', type=argparse.FileType('w'), default="genes.fasta",
                    help='Output file name (default: %(default)s)')
parser.add_argument('-f', '--f', '--feat', dest='feature',
                    choices=['gene', 'transcript', 'exon', 'CDS'], default="gene", 
                    help='gene / transcript / exon / CDS (default: %(default)s)')
args = parser.parse_args()


print(args.fasta)
for line in args.fasta:
    if line.startswith('>'):
        print(line.strip())
args.fasta.close()

print(args.gtf)  

print(args.feature)

args.out.write('My output')
args.out.close()
```

```bash
python3 07-06.py
python3 07-06.py -h
python3 07-06.py -f CDS Mycoplasma_hominis.fasta Mycoplasma_hominis.gtf
python 07-06.py -f CDS -out myoutput.fasta Mycoplasma_hominis.fasta Mycoplasma_hominis.gtf
```

Następnie zmodyfikuj skrypt `07-01.py` aby obsługiwany był przez moduł `argparse` - [dokumentacja argparse](https://docs.python.org/3/library/argparse.html). 


## Zad. 7
Metody *alignment-free* są nowoczesnymi metodami porównywania sekwencji. Większość z nich zakłada, że spokrewnione sekwencje (*homologiczne*) składają się z wielu podobnych krótszych podsekwencji (*k*-merów).

#### Przykład

Poniżej przedstawiono sposób porównania dwóch sekwencji: `x = ATGTGTG` i `y = CATGTG` przy użyciu *k*-mer = `3`.

1. Wyszukanie wszystkich *k*-merów w sekwencji `x` i `y`.
```
x = ATGTGTG           y = CATGTG
    ATG                   CAT          
     TGT                   ATG
      GTG                   TGT
       TGT                   GTG
        GTG
```

2. Zliczenia *k*-merów w sekwencji `x` i `y`.

```
       x      y
ATG    1      1
CAT    0      1
GTG    2      1           # GTG występuje 2 razy w x i 1 raz w y
TGT    2      1 
```

3. Częstości *k*-merów w sekwencjach `x` i `y`.

```
       x      y
ATG    0.2    0.25
CAT    0      0.25
GTG    0.4    0.25        # x: 2/5 = 0.4; y: 1/4 = 0.25
TGT    0.4    0.25 
```

4. Obliczenie [dystansu euklidesowego](https://en.wikipedia.org/wiki/Euclidean_distance) między wektorami częstości `x` i `y`.

```
d(x, y) = [(0.2 - 0.25)^2 + (0 - 0.25)^2 + (0.4 - 0.25)^2 + (0.4 - 0.25)^2]^0.5 
        = [0.0025 + 0.0625 + 0.0225 + 0.0225]^0.5
        = 0.11^0.5 = 0.332
```

Wartość `0.332` odpowiada dystansowi jaki dzieli dwie sekwencje `x` i `y`.


### Cel zadania
Celem zadania jest napisanie programu, który dla zadanego pliku sekwencji w formacie FASTA obliczy dystanse euklidesowe pomiędzy każdą parą sekwencji w zależności od podanej przez użytkownika długości słowa (*k*-mer) i sprecyzowania, czy wektorem mają być zliczenia czy częstości. Wynikiem powinnien być plik zawierający pary dystansów.

Na przykład dla 4 sekwencji białkowych:

```
>seq1
EVVIRSANFTDNAKIIIVQLNASVEINCTRPNNYTRKGIR
IGPGRAVYAAEEIIGDIRRAHCNISREKWNNTLKQVVTKL
REQFVNKTIIFTHPSGGDPEIVMHSVNCGGEFFY
>seq2
VIRSANFTDNAKIIIVQLNASVEINCTRPNNNTRKGIRIG
PGRAVYAAEEIIGDIRRAHCNISREKWNNTLKQVVTKLRE
QFVNKTIIFNHSSGGDPEIVMHSFNCGGEFFY
>seq3
EVVIRSANFTDNAKIIIVQLNASVEINCTRPNNNTRKGIH
IGPGRAVYATDRIIGDIRQAHCNISREKWNNTLKQVVTKL
REQFVNKTIIFTHPSGGDPEIVMHSVNCGGEFFY
>seq4
EVVIRSANFTDNAKIIIVQLNASVEINCTRPNNNTRRGIH
IGPGRAFYATDRIVGDIRQAYCNISREKWNNTLKQVVAKL
REQFVNKTIIFNHSSGGDPEIVMHSVNCGGEFFYCNT
```

Pary dystansów dla zliczeń 2-merów:

```
seq1 seq2 4.4721
seq1 seq3 4.2426
seq1 seq4 7.1414
seq2 seq3 5.4772
seq2 seq4 6.5574
seq3 seq4 5.7446
```

Pary dystanstów dla częstości 2-merów:

```
seq1 seq2 0.0400
seq1 seq3 0.0375
seq1 seq4 0.0623
seq2 seq3 0.0490
seq2 seq4 0.0577
seq3 seq4 0.0500
```