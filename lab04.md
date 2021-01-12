# Słowniki (dictionaries)

## Zad. 1
Sprawdź w interaktywnym wierszu Pythona co zrobi każde wyrażenie ze słownikiem (`d`).

```python
d = {}               # Pusty słownik

d['A'] = 1           # 1
d['B'] = 2           # 2
d['A']               # 3
len(d)               # 4
list(d.keys())       # 5
list(d.values())     # 6
d['A'] = 3           # 7
d['B'] += 3          # 8
'A' in d             # 9
'A' not in d         # 10

```


## Zad. 2
Którą z wartości wygeneruje poniższy kod?

```python
d = {'A': 1, 'B': 2, 'C': 3}
print(d['A'])
```

1. `False`
2. `'B'`
3. `True`
4. `1`


## Zad. 3
Którą z wartości wygeneruje poniższy kod?

```python
d = {'A': 1, 'B': 2, 'C': 3}
print(list(d.values()))
```

1. `True`
2. `[1, 2, 3]`
3. `3`
4. `['A', 'B', 'C']`


## Zad. 4
Którą z wartości wygeneruje poniższy kod?

```python
d = {'A': 1, 'B': 2, 'C': 3}
print(list(d.keys()))
```

1. `['A', 'B', 'C']`
2. `[1, 2, 3]`
3. `True`
4. `False`


## Zad. 5
Którą z wartości wygeneruje poniższy kod?

```python
d = {'A': 1, 'B': 2, 'C': 3}
print(list(d.items()))
```

1. `[('A', 1), ('B', 2), ('C', 3)]`
2. `[(1, 'A'), (2, 'B'), (3, 'C')]`
3. `[('B', 1), ('A', True), (1, 'A')]`
4. `[('C', 3), ('A', 2), ('B', 1)]`


## Zad. 6
Którą z wartości wygeneruje poniższy kod?

```python
d = {'A': 1, 'B': 2, 'C': 3}
print(d['D'])
```

1. `None`
2. `D`
3. `an Error`
4. `False`


## Zad. 7
Którą z wartości wygeneruje poniższy kod?

```python
d = {'A': 1, 'B': 2, 'C': 3}
print(d.get('D', 0))
```

1. `None`
2. `D`
3. `an Error`
4. `0`


## Zad. 8
Którą z wartości wygeneruje poniższy kod?

```python
d = {'A': 1, 'B': 2, 'C': 3}
d['B'] = 4
print(d['B'])
```

1. `2`
2. `4`
3. `an Error`
4. `False`


## Zad. 9
Wyjaśnij, co robi poniższy kod:

```python
d = {2: 'B', 1: 'A', 4: 'D', 3: 'C'}

for key in d:
    print(key, d[key])
```


## Zad. 10
Wyjaśnij, co robi poniższy kod:

```python
for key in sorted(d.keys()):
    print(key, d[key])
```


## Zad. 11
Poniższy program zawiera **3 błędy**. Odszukaj je i popraw.

```python
d = {
    'alpha': [1, 2, 3],
    'beta': 'bioinfo'
    'gamma': 4,
    'delta': {'key': 'val'}
}

print(d['alpha'])

d['alpha'].append(4)

print(d['alpha'][4])

print(d['beta'][0])

print(d['delta']['val'])
```


## Zad. 12
Korzystając z pętli *for* utwórz z poniższej listy

```python
l = [
  'gene1   54      3234',
  'gene2   6031    100321',
  'gene3   12381   142132'
]
```

słownik:

```python
d = {
  'gene1': [54, 3234],
  'gene2': [6031, 100321],
  'gene3': [12381, 142132]
}
```


## Zad. 13
Poniżej znajduje się słownik, który zawiera masę molową (kDA) aminokwasów.

```python
protein_weights = { 
   'A': 89.0932, 
   'C': 121.1582, 
   'D': 133.1027, 
   'E': 147.1293, 
   'F': 165.1891, 
   'G': 75.0666, 
   'H': 155.1546, 
   'I': 131.1729, 
   'K': 146.1876, 
   'L': 131.1729, 
   'M': 149.2113, 
   'N': 132.1179, 
   'O': 255.3134, 
   'P': 115.1305, 
   'Q': 146.1445, 
   'R': 174.201, 
   'S': 105.0926, 
   'T': 119.1192, 
   'U': 168.0532, 
   'V': 117.1463, 
   'W': 204.2252, 
   'Y': 181.1885 
}
```

Utwórz skrypt `04-13.py`, który obliczy masę molową poniższej sekwencji białkowej (sumę mas aminokwasów znajdujących się w sekwencji). Zwróć uwagę, że w poniższej sekwencji znajduje się znak, który nie jest aminokwasem (`X`) - jeżeli aminokwasu nie ma w słowniku to `protein_weights` to potraktuj, że jego masa molowa to `0`. 

```python
pep = "MRPSGTAGAALLALLAALCPASRALEEKKVCQGTSNKLTQLGTFEDHFLSLQRMFNNXCEVVLGNLEITYVQRNYDLSFLKTXIQEVAGYVL"
```

OUTPUT:

```
13064.474299999989
```


## Zad. 14
Bez korzystania z wyrażeń warunków `if` napisz skrypt `04-14.py`, który zamieni poniższą sekwencję DNA, na sekwencję komplementarną (cDNA).

```python
dna = 'AGCCCGATGCTTA'
#cdna  TCGGGCTACGAAT 
```


## Zad. 15
Krótko wyjaśnij, co robi poniższy kod.

```python
seq = 'MNNGGKAEKENTPSEANLQEEEVRTLFVSGLPLDIKPRELYLLFRPFKGYEGSLIKLTSKQPVGFVSFDSRSEAEAAKNALNGIRFDPEI'

d = {}
for char in seq:
    if char not in d:
        d[char] = 0
    d[char] += 1
print(d)
```


## Zad. 16
Zmodyfikuj kod z poprzedniego zadania, aby zapisywał do pliku procentowy udział występowania każdego aminokwasu.

Output:

```
#aa percent
A   6.7
D   3.3
E   12.2
..
```


## Zad. 17
Utwórz skrypt `04-17.py`, który zliczy dwunukleotydowe podsekwencje występujące w poniższej sekwencji DNA.

```python
dna = 'AGCCCGATGCTTAAACGTAGATTTTCC'
```

Output:

```
AA  2
AC  1
AG  2
AT  2
CC  3
CG  2
CT  1
GA  2
GC  2
GT  1
TA  2
TC  1
TG  1
TT  4
```


## Zad. 18
W pliku [ecoli.pep.fasta](./data/ecoli.pep.fasta) znajdują się sekwencje wszystkich 4 309 białek bakterii *Escherichia coli*. Utwórz skrypt `04-18.py`, który wczyta sekwencje z pliku [ecoli.pep.fasta](./data/ecoli.pep.fasta) do słownika w taki sposób, aby kluczem był identyfikator sekwencji, a wartością pełnej długości sekwencja:

```python
d = {
   'sp|P52697|6PGL_ECOLI': 'MKQTVYIA...',
   'sp|P0CK95|ACFD_ECOLI': 'MNKKFKYK..',
   # ...
}
```


## Zad. 19
Do skryptu `04-18.py` dodaj instrukcje, które obliczą masę molową każdego białka i wynik zapiszą do pliku `ecoli.mass.txt`.

Output:

```
sp|P52697|6PGL_ECOLI  42252.3
sp|P0CK95|ACFD_ECOLI  194609.3
sp|P75747|ABRB_ECOLI  43134.6
sp|P24182|ACCC_ECOLI  57391.0
sp|P21515|ACPH_ECOLI  26419.8
sp|P24177|ACRD_ECOLI  131709.9
sp|P0A9Q5|ACCD_ECOLI  38780.2
```