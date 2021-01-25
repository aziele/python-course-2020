# Składanie list (list comprehension)

## Zad. 1
Napisz tradycyjną pętlę for, która zamieni nazwy ludzkich genów z

```python
names = ['tnrc6a', 'PrP', 'bak1']
```

w

```python 
new_names = ['HsTNRC6A', 'HsPRP', 'HsBAK1']     # Hs = Homo sapiens
```


## Zad. 2
Poniższy kod przedstawia sposób tworzenia list, który nazywa się ***składaniem list*** (*list comprehensions*). Co znajduje się pod zmienną `new_names`?

```python
names = ['tnrc6a', 'PrP', 'bak1']
new_names = ['Hs' + name.upper() for name in names]

# Listy składane działają przynajmniej 2 razy szybciej od ręcznie zapisanych
# instrukcji pętli for, ponieważ ich iteracje wykonywane są wewnątrz interpretera
# z szybkością języka C, a nie z szybkością kodu Pythona.
```


## Zad. 3
Jakie wartości będzie miała poniższa lista?

```python
lst = [i for i in range(10) if i % 2 == 0]
```


## Zad. 4
Użyj składania list, aby zamienić string: 

```python
string = "ATGNA"
```

w poniższą listę

```python
lst = ['AA', 'TT', 'GG', 'AA']   # Pomiń jeżeli N
```



# Krotki (tuples)

## Zad. 5
Utwórz dwu-elementową krotkę. 

```python
t = ('gene1', 'chr1')       # To jest krotka. Tworzy się ją przez nawiasy okrągłe ().
                            # Dla jasności: krotki nie muszą być dwu-elementowe.
                            # Mogą mieć różne liczebności (od 0 w górę).
```

Które z poniższych instrukcji są prawidłowe?

1. `len(t)`
2. `t.pop()`
3. `t.append('+')`
4. `t.sort()`
5. `t[1]`
6. `t[1] = 3`
7. `list(t)`


## Zad. 6
Skoro krotki są obiektami, których nie można modyfikować w miejscu, ich istnienie wydaje się zbyteczne. 

Zapoznaj się poniższym przykładem i odpowiedz na pytanie, do czego krotki mogą się przydać?

```python
>>> d = {}
>>> d[('gene1', 'chr1')] = [1000, 1400, '+']
>>> d[('gene1', 'chr8')] = [22783274, 22784862, '+']
```

```python
>>> d = {}
>>> d[['gene1', 'chr1']] = [1000, 1400, '+']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
```



# Zbiory (sets)

## Zad. 7
Sprawdź co zrobi każde wyrażenie ze zbiorem w środku (`s`).

![set1.png](./images/set.png)


## Zad. 8
Ile elementów będzie miał poniższy zbiór:

```python
nucl = {'A', 'A', 'T', 'T', 'G', 'G', 'C', 'C'}
print(nucl)
```

## Zad. 9
Które z poniższych sposobów tworzenia zbioru są prawidłowe?

1. `set()`
2. `set('AATTGGCC')`
3. `set(['A', 'T', 'G'])`
4. `{'A', 'T', 'G', 'C'}`


## Zad. 10
Które z poniższych wyrażeń są nieprawidłowe?

```python
s = {'A', 'T', 'G', 'C'}
```

1. `len(s)`
2. `s.add('G')`
3. `'G' in s`
4. `'G' not in s`
5. `s[0]`
6. `s['A']`
7. `s.remove('C')`


## Zad. 11
Co otrzymasz w wyniku poniższych działań matematycznych:

```python
dna = set('ATGC')
rna = set('AUGC')
```

1. `dna - rna` oraz `dna.difference(rna)`
2. `dna | rna` oraz `dna.union(rna)`
3. `dna & rna` oraz `dna.intersection(rna)`
4. `dna ^ rna` oraz `dna.symmetric_difference(rna)`


## Zad. 12
Jaką wartość boolean (`True`/`False`) otrzymasz w wyniku działania poniższych metod:

```python
nuc = set('ATGCU')
dna = set('ATGC')
```

1. `dna.issubset(nuc)` oraz `dna <= nuc`
2. `nuc < dna`
3. `nuc <= nuc`
4. `nuc.issuperset(dna)` oraz `nuc >= dna`
5. `nuc == dna`


## Zad. 13
Które z poniższych konwersji typów obiektów są prawidłowe?

1. `list({1, 2, 3})`
2. `set([1, 2, 3])`
3. `tuple([1, 2, 3])`
4. `list((1, 2, 3))`
5. `set((1, 2, 3))`


## Zad. 14
Utwórz *one-liner*, który zwróci listę wspólnych elementów dwóch list:

```python
lst1 = [1, 3, 6, 78, 35, 55]
lst2 = [12, 24, 35, 24, 88, 120, 155]
```


## Zad. 15
Która z poniższych instrukcji jest prawidłowa?

```python
dna_dic = {'A':'T', 'T':'A', 'C':'G', 'G':'C'}        # Słownik
rna_set = {'A', 'U', 'G', 'C'}                        # Zbiór
```

1. `dna_dic & rna_set`
2. `rna_set & dna_dic`
3. `dna_dic.intersection(rna_set)`
4. `rna_set.intersection(dna_dic)`
5. `rna_set.union(dna_dic)`


## Zad. 16
Użyj odpowiedniej funkcji sprawdzającej typ i odpowiedz na pytanie: czy `{}` to pusty zbiór czy pusty słownik?


## Zad. 17
Sprawdź, czy działania na zbiorach można wykonywać dla więcej niż dwóch zbiorów?

```python
s1 = {'Gene1', 'Gene2', 'Gene3'}
s2 = {'Gene2', 'Gene3', 'Gene4', 'Gene5'}
s3 = {'Gene6', 'Gene2', 'Gene7', 'Gene3'}
```

Np.:

```python
s1 & s2 & s3
s1.intersection(s2, s3)
```


## Zad. 18
W trzech plikach [cancer1.txt](./data/cancer1.txt), [cancer2.txt](./data/cancer2.txt) i [control.txt](./data/control.txt) znajdują się nazwy genów, które wykazują podwyższony poziom ekspresji, odpowiednio, dla pacjentów z nowotworem skóry, białaczki i ludzi zdrowych.

Utwórz skrypt `06-18.py`, który wyszuka geny charakterystyczne jedynie dla pacjentów chorych na oba typy raka (i których nie ma w control) i zapisze je do pliku tekstowego `cancer_common.txt`

Input:

```
cancer1.txt     cancer2.txt       control.txt
-----             -----             -----
gene1             gene3             gene1
gene2             gene4             gene3
gene3             gene2             gene5
```

Output:

```
cancer_common.txt
-----
gene2
```


## Zad. 19
Zmodyfikuj skrypt `06-18.py` aby geny w pliku wynikowym `cancer_common.txt` były uszeregowane alfabetycznie.