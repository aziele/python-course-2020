# Moduł [itertools](https://docs.python.org/3/library/itertools.html)

```python
import itertools
```

## Zad. 1
Wyjaśnij, co robią poniższe dwie pętle `for`:

```python
for pair in itertools.combinations(['A', 'B', 'C', 'D'], 2):
    g1 = pair[0]
    g2 = pair[1]
    print(g1, g2)
```

```python
for g1, g2, g3 in itertools.combinations(['A', 'B', 'C', 'D'], 3):
    print(g1, g2, g3)
```


## Zad. 2
Z [dokumentacji modułu itertools](https://docs.python.org/3/library/itertools.html) wybierz odpowiednią *funkcję kombinatoryczną*, która uprości poniższe trzy zagnieżdżone pętle `for` do jednej pętli.

```python
lst1 = [1, 2, 3]
lst2 = [3, 1, 4]
lst3 = [6, 2, 5]

for v1 in lst1:
    for v2 in lst2:
        for v3 in lst3:
            print(v1, v2, v3)
```



# Moduł [os](https://docs.python.org/3/library/os.html)

```python
import os
```

## Zad. 3
Zapisz kod poprzedniego zadania do pliku `08-03.py`. Następnie sprawdź i wyjaśnij, co robi poniższy kod.

```python
print(os.getcwd())
os.mkdir('directory')
os.system('python3 08-03.py')
os.rmdir('directory')
os.remove('08-03.py')
```


## Zad. 4
Sprawdź i wyjaśnij, co robią poniższe instrukcje.

```python
print(os.listdir())

print(os.path.join('data', 'bioinfo', 'human', 'genome', 'chr1.fa'))
```


## Zad. 5
Wyjaśnij (bez uruchamiania), co robi poniższy kod.

```python
seqlen = 0
for f in os.listdir('./human/genome/'):
    if f.endswith('.fasta'):
        fh = open(os.path.join('./human/genome', f))
        for line in fh:
            if not line.startswith('>'):
                seqlen += len(line.strip())
        fh.close()
print(seqlen)
```

Powyższy kod można napisać za pomocą modułu [pathlib](https://docs.python.org/3/library/pathlib.html).

```python
from pathlib import Path
seqlen = 0
for f in Path('./human/genome/').iterdir():
    if f.suffix('.fasta'):
        fh = open(f)
        for line in fh:
            if not line.startswith('>'):
                seqlen += len(line.strip())
        fh.close()
print(seqlen)
```

# Moduł [re](https://docs.python.org/3/library/re.html)

```python
import re
```

## Zad. 6
Zapisz wynik każdej poniższej funkcji `findall()` i upewnij się, że jest on dla Ciebie zrozumiały. Jeżeli nie jesteś pewny/a co do wyniku, skorzystaj z dokumentacji modułu.


```python
text = '''The DMD gene, encoding the dystrophin protein, is one of the longest
human genes known, covering 2300 kbp (0.08% of the Human Genome). Dystrophin has
79 exons and introns of variable size ranging from 107 bp (intron 14) to >200 kbp
(intron 44). The primary transcript in muscle measures 2100 kbp and takes 16 hours
to transcribe; the mature mRNA measures 14 kbp.'''
```

1. `re.findall('dystrophin', text)`
2. `re.findall('[Dd]ystrophin', text)`
3. `re.findall('\d', text)`
4. `re.findall('\d\d', text)`
5. `re.findall('\d+', text)`
6. `re.findall('\d+ kbp', text)`
7. `re.findall('\d+ k*bp', text)`
8. `re.findall('(\d+) k*bp', text)`
9. `re.findall('[A-Z]+ gene', text)`
9. `re.findall('The primary [^;]+', text)`


## Zad. 7
Użyj funkcji `findall()` aby wyodrębnić numery intronów w tekście z poprzedniego zadania.


## Zad. 8
Użyj funkcji `findall()` aby wyodrębnić procentowy udział genu DMD w genomie człowieka. 


## Zad. 9
Zapoznaj się z poniższym przykładem i wyjaśnij, jak działa funkcja `re.search()`.

```python
tata_box = 'TATAA[AT]'
sequence = 'GTCGATGCTAGTATAATGATGCTGATATAAAGCGATGCG'

m = re.search(tata_box, sequence)
print(m)
print(m.group())
print(m.span())
print(m.start())
print(m.end())

m = re.search('NNNNN', sequence)
print(m)
```


## Zad. 10
Zapoznaj się z poniższym przykładem i wyjaśnij, jak działa funkcja `re.finditer()`.

```python
for m in re.finditer(tata_box, sequence):
    print(m.group(), end=': ')
    print('{}-{}'.format(m.start(), m.end()))
```


## Zad. 11
W celu zwiększenia szybkości działania funckji *wyrażeń regularnych*, szukany wzorzec może najpierw zostać ***skompilowany*** przy użyciu funkcji `re.compile()`, przed rozpoczęciem dopasowywania wzorca funkcjami `search()`, `findall()`, czy `finditer()`.

```python
>>> pattern = re.compile('TATAA[AT]')
>>> pattern.findall(sequence)
['TATAAT', 'TATAAA']
```

Ostatnia badania wskazują, że *aktywność cyklazy guanylowej (GC)* mają sekwencje zbudowane z 14 aminokwasów:

| Pozycja motywu | Aminokwas   |
| ------------- |:-------------:|
| 1      | R / K / S |
| 2     | Y / F / W     |
| 3 | C / T / G / H      |
| 4 | V / I / L      |
| 5 | F / V      |
| 6 | G      |
| 7 | A / D / N      |
| 8 | jakikolwiek      |
| 9 | V / I / L     |
| 10 | jakikolwiek     |
| 11 | jakikolwiek     |
| 12 | jakikolwiek     |
| 13 | jakikolwiek    |
| 14 | K / R     |

Jak będzie wyglądał wzorzec powyższego motywu sekwencyjnego?


# Moduł [urllib](https://docs.python.org/3.5/library/urllib.request.html#module-urllib.request)

```python
import urllib.request
```

## Zad. 12
Sprawdź i wyjaśnij, co robi poniższy kod.

```python
f = urllib.request.urlopen('http://www.uniprot.org/uniprot/Q93062.fasta')
respond = f.read()
print(respond)                    # Obiekt bajtowy
print(respond.decode('utf-8'))    # Ciąg znaków
```


## Zad. 13
Sprawdź i wyjaśnij, co robi poniższy kod.

```python
f = urllib.request.urlopen('http://www.uniprot.org/uniprot/Q93062.fasta')
for line in f:
    line = line.decode('utf-8')
    if not line.startswith('>'):
        print(line)
```

## Zad. 14
Utwórz skrypt `08-14.py`, który pobierze z bazy UniProt sekwencje białkowe (w formacie FASTA) podanych poniżej identyfikatorów i zapisze je do pliku `uniprot.txt`.

```python
uniprot_ids = ['P68431', 'Q6ZQ08', 'O94687']
```



# Moduł [argparse](https://docs.python.org/3/library/argparse.html)


## Zad. 15
Zapisz poniższy skrypt do pliku `08-15.py`.

```python
import argparse

parser = argparse.ArgumentParser(description='Retrieve proteins from UniProt database')
parser.add_argument('-i', '--id', dest='uniprot', required=True,
                    nargs='+', help='Uniprot ID (e.g. P68431)')
parser.add_argument('-o', '--o', '--out', dest='output', default='uniprot.txt',
                    help='Output filename (default: %(default)s)')
args = parser.parse_args()


print(args.uniprot)
print(args.output)
```

Uruchom skrypt poniższymi poleceniami i na podstawie ich wyników wyjaśnij, do czego służy moduł `argparse`.

```bash
python3 08-15.py
python3 08-15.py --help
python3 08-15.py --id P68431
python3 08-15.py -i P68431 Q6ZQ08
python3 08-15.py --id P68431 Q6ZQ08 -o output.fasta
```


## Zad. 16
Do skryptu `08-15.py` dodaj kod, który pobierze rekordy sekwencji z bazy UniProt i zapisze je do odpowiedniego pliku tekstowego.


## Zad. 17
UniProt pozwala wyświetlać rekord białkowy *w dwóch formatach*:

1. *fasta*: <a href="http://www.uniprot.org/uniprot/Q93062.fasta">http://www.uniprot.org/uniprot/Q93062.fasta</a>
2. *txt*:   <a href="http://www.uniprot.org/uniprot/Q93062.txt">http://www.uniprot.org/uniprot/Q93062.txt</a>

Dodaj do skryptu argument `--format`, który będzie umożliwiał użytkownikowi wybranie jednego z dwóch formatów (domyślnie `fasta`).