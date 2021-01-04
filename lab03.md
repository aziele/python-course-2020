# Wczytywanie plików tekstowych

## Zad. 1
Utwórz plik tekstowy `sequences.fasta` zawierający poniższe sekwencje w formacie FASTA:

```
>hsa-miR-576-3p MIMAT0004796
AAGAUGUGGAAAAAUUGGAAUC
>hsa-miR-140-5p MIMAT0000431
CAGUGGUUUUACCCUAUGGUAG
>hsa-miR-522-5p MIMAT0005451
CUCUAGAGGGAAGCGCUUUCUG
>hsa-miR-1298-5p MIMAT0005800
UUCAUUCGGCUGUCCAGAUGUA
>hsa-miR-133a-3p MIMAT0000427
UUUGGUCCCCUUCAACCAGCUG
>hsa-miR-4743-3p MIMAT0022978
UUUCUGUCUUUUCUGGUCCAG
>hsa-miR-557 MIMAT0003221
GUUUGCACGGGUGGGCCUUGUCU
>hsa-miR-548ao-3p MIMAT0021030
AAAGACCGUGACUACUUUUGCA
>hsa-miR-5088-5p MIMAT0021080
CAGGGCUCAGGGAUUGGAUGGAGG
>hsa-miR-4649-5p MIMAT0019711
UGGGCGAGGGGUGGGCUCUCAGAG
```

W tym samym katalogu, w którym znajduje się powyższy plik tekstowy utwórz skrypt `03-01.py` i umieść w nim poniższy kod. W brakujące miejsca wstaw: `close`, `line`, `'sequences.fasta'`, `print`, aby skrypt działał prawidłowo.

```python
'''
Poniższy kod wczytuje plik wiersz po wierszu.
Kod zwraca po jednym wierszu z każdą iteracją
pętli. Innymi słowy, w pamięci przechowywany
jest tylko pojedynczy wiersz (a nie cały plik).
'''

fh = open(___)
for ____ in fh:
    ____(line)        # Zmienna `line` jest typu string.
fh.____()
```


## Zad. 2
Zmodyfikuj skrypt `03-01.py`, aby wyświetlał na ekran tylko linie z nagłówkiem sekwencji.

Output:

```
>hsa-miR-576-3p MIMAT0004796
>hsa-miR-140-5p MIMAT0000431
>hsa-miR-522-5p MIMAT0005451
...
```


## Zad. 3
Zmodyfikuj skrypt `03-01.py`, aby wyświetlał na ekran jedynie identyfikator sekwencji.

Output:

```
hsa-miR-576-3p
hsa-miR-140-5p
hsa-miR-522-5p
...
```

## Zad. 4
Zmodyfikuj skrypt `03-01.py`, aby wyświetlał na ekran identyfikator i numeru dostępu każdej sekwencji.

Output:

```
ID: hsa-miR-576-3p ACCESSION: MIMAT0004796
ID: hsa-miR-140-5p ACCESSION: MIMAT0000431
ID: hsa-miR-522-5p ACCESSION: MIMAT0005451
...
```


## Zad. 5
Zmodyfikuj skrypt `03-01.py`, aby identyfikatory sekwencji zostały zapisane do listy `ids`.

Output:

```python
['hsa-miR-576-3p', 'hsa-miR-140-5p', 'hsa-miR-522-5p']    # itd.
```


## Zad. 6
Utwórz plik tekstowy `human.txt` zawierający poniższe dane (*lokalizacje pierwszych 20 genów człowieka na chrom. 1*):

```
#name start end strand
OR4F5 65419 71585 +
OR4F29 450703 451697 -
OR4F16 685679 686673 -
SAMD11 923928 944581 +
NOC2L 944204 959309 -
KLHL17 960587 965715 +
PLEKHN1 966497 975865 +
PERM1 975204 982093 -
HES4 998962 1000172 -
ISG15 1001138 1014540 +
AGRN 1020123 1056118 +
RNF223 1070966 1074307 -
C1orf159 1081818 1116361 -
TTLL10 1173884 1197935 +
TNFRSF18 1203508 1206691 -
TNFRSF4 1211326 1214138 -
SDF4 1216908 1232031 -
B3GALT6 1232226 1235041 +
C1QTNF12 1242446 1246722 -
UBE2J2 1253909 1273885 -
```

Poniższy kod jest nieprawidłowy. Miał on na celu podać liczbę genów zlokalizowanych na *nici plus*. **Uszereguj** poniższe linie kodu i **sformatuj wcięcia**, tak aby kod działał prawidłowo. 

```python
fh.close()

plus = 0

if not line.startswith('#'):

fh = open('human.txt')

print(plus)

if " +" in line: 

for line in fh:

plus += 1
``` 


## Zad. 7
Skrypt z poprzedniego zadania z każdym wczytaniem linii sprawdza czy zaczyna się ona od znaku `#`. Zamiast tego można *ominąć pierwszą linię* i zacząć iterację w pętli *for* od drugiej linii.

Zapoznaj się z tą możliwością poniżej i odpowiednio zmodyfikuj skrypt z poprzedniego zadania.

```python
fh = open('human.txt')
fh.readline()                   # Wczytanie linii nr 1 i natychmiastowe uwolnienie jej z pamięci.
line = fh.readline()            # Wczytanie linii nr 2 i przypisanie jej do zmiennej line.
print(line)
for line in fh:                 # Iteracja rozpoczyna się od linii nr 3
    print(f'FOR LOOP: {line}')
```


## Zad. 8
Rozbuduj skrypt aby wyświetlał procentowy udział *genów nici plus* i *genów nici minus*. Procentowy udział genów na nici plus to liczba genów na nici plus podzielona przez liczbę wszystkich genów razy `100`.

Output:

```
Genes (+): 40.0%
Genes (-): 60.0%
```

## Zad. 9
Poniższy skrypt tworzy listę genów, które znajdują się na chromosomie 1 w lokalizacji powyżej 1 miliona pz. Niestety kod zawiera **pięć błędów**. Odszukaj je i popraw, aby program działał prawidłowo.

```python
genes = []

fh = open('human.txt')
fh.readline()      
for line in fh
    columns = line.split()
    name = columns[1]
    start = columns[2]
    if start > 1000000
        genes.append(name)
fh.close()

print(genes)
```


## Zad. 10
Zmodyfikuj skrypt z poprzedniego zadania, aby w pętli *for* obliczał i wyświetlał długość sekwencji każdego z 20 genów.


## Zad. 11
Zmodyfikuj skrypt z poprzedniego zadania, aby wyświetlił nazwę i długość genu o najdłuższej sekwencji.


## Zad. 12
Zapoznaj się z dwoma poniższymi wycinkami kodu.

```python
>>> l = [["Gene2", 4000], ["Gene1", 5000], ["Gene3", 2000]]
>>> l.sort()
>>> l
[['Gene1', 5000], ['Gene2', 4000], ['Gene3', 2000]]
>>> l.sort(reverse=True)
[['Gene3', 2000], ['Gene2', 4000], ['Gene1', 5000]]
```


```python
>>> l = [[4000, "Gene2"], [5000, "Gene1"], [2000, "Gene3"]]
>>> l.sort()
>>> l
[[2000, 'Gene3'], [4000, 'Gene2'], [5000, 'Gene1']]
>>> l.sort(reverse=True)
[[5000, 'Gene1'], [4000, 'Gene2'], [2000, 'Gene3']]
```

Zmodyfikuj skrypt z poprzedniego zadania tak, aby wyświetlił nazwę i długość sekwencji trzech najdłuższych genów.


## Zad. 13
W oparciu o poniższy kod wyjaśnij co robi metoda `read()`.

```python
fh = open('human.txt')
content = fh.read()
fh.close()
print(content)
print(type(content))
```

## Zad. 14
<img align="right" src="./images/mobydick.jpg" alt="Moby Dick cover" height="270px"> Książka *"Moby Dick"* przedstawia walkę ponurego kapitana ze swoim odwiecznym wrogiem, białym wielorybem.

Pobierz ksiązkę [mobydick.txt](./data/mobydick.txt) na dysk. Przy użyciu Pythona odpowiedz na pytanie, które słowo pojawia się częściej w książce: `captain` czy `whale`. 


# Zapisywanie do pliku

## Zad. 15
Wykonaj poniższy program i wyjaśnij jego działanie.

```python
names = ['SAMD11', 'NOC2L', 'KLHL17']

oh = open('mygenes.txt', 'w')           # Utworzenie pliku do zapisu ('w' - write)
for name in names:
    oh.write(f'{name}\n')
oh.close()
```


## Zad. 16
Usuń z powyższego kodu znak nowej linii (`\n`) i uruchom program ponownie. Jak teraz wygląda wynik programu?


## Zad. 17
Co należy dodać do powyższego kodu, aby geny w pliku wynikowym były ułożone w kolejności alfabetycznej?


## Zad. 18
Utwórz skrypt `03-18.py`, który zapisze poniższe dane do pliku tekstowego w dwóch kolumnach.

```python
names = ['OR4F5', 'OR4F29', 'OR4F16', 'SAMD11', 'NOC2L']
values = [918, 939, 939, 20654, 15106]
```

***Wskazówka:*** Jeżeli nie chcesz korzystać z indeksowania dwóch list, możesz skorzystać z funkcji `zip()`:

```python
>>> lst1 = ['a', 'b', 'c']
>>> lst2 = [1, 2, 3]
>>> for el1, el2 in zip(lst1, lst2):
...     print(el1, el2)
... 
a 1
b 2
c 3
```


## Zad. 19
Zmodyfikuj skrypt z poprzedniego zadania, aby geny w pliku wynikowym ułożone były według malejących wartości *values*.


```python
>>> lst1 = ['a', 'b', 'c']
>>> lst2 = [1, 2, 3]
>>> list(zip(lst1, lst2))
[('a', 1), ('b', 2), ('c', 3)]
```


## Zad. 20
Zmodyfikuj skrypt z **zad. 10**, aby zapisywał w dwóch kolumnach nazwę genu i długość sekwencji do pliku tekstowego `human_length.txt`.