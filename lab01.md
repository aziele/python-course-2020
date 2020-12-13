# Liczby

## Zad. 1
Otwórz interaktywny wiersz poleceń Pythona 3. 

W jakiej wersji Pythona 3 pracujesz?


## Zad. 2
Które poniższe wyrażenia dają w wyniku liczbę 8?

1. `0 + 8`
2. `2 * 4`
3. `8 / 1`
4. `65 / 8`
5. `65 // 8`
6. `17 % 9`
7. `2 ** 4`
8. `64 ** 0.5`


## Zad. 3
Wbudowana funkcja `type` zwraca typ dowolnego *literału* (to co programista wpisuje w kod z klawiatury, np.: liczba, tekst). Na przykład wyrażenie `type(3)` informuje, że literał `3` jest liczbą całkowitą.

Zapisz typy poniższych literałów:

1. `17`
2. `1.618`
3. `'1.618'`
4. `"1.618"`
5. `1.6e-10`
6. `4E210`
7. `True`
8. `"bioinfo"`
9. `'3'`


## Zad. 4
Podaj wartość uzyskaną w wyniku poniższych wyrażeń:

1. `1 + 2 * 3`
2. `(1 + 2) * 3`
3. `2 * 3.1`
4. `2.2 / 2.2`
5. `(1 + 1) ** (5 - 2)`
6. `4 / 2 * 2`
7. `2 * 2 / 4`


## Zad. 5
Tworzenie zmiennej w Pythonie jest bardzo naturalne. Zmienna tworzona jest, kiedy kod pierwszy raz przypisuje jej wartość. Oznacza to, że nigdy nie deklarujemy zmiennych wcześniej.

Utwórz dwie zmienne:

```python
a = 1
b = 1 + 2         # Wyrażenia po prawej stronie przypisania są obliczane w pierwszej
                  # kolejności, zanim jakiekolwiek przypisanie ma miejsce.
```

Używając funkcji `print` wyświetl wartość zmiennej `b`.

Utwórz zmienną `c`, która będzie sumą kwadratów wartości zmiennych `a` i `b`. Ile wynosi wartość zmiennej `c`?


## Zad. 6
Zmienne można swobodnie *nadpisywać obiektami dowolnego typu*. Jest to możliwe, ponieważ typy powiązane są z obiektami, a nie ze zmiennymi. Zmienna jest tylko referencją do danego obiektu (tj. do miejsca w pamięci komputera).

Wypróbuj poniższy kod:

```python
a = 1             # Zmienna jest liczbą całkowitą.
a = 3.14          # Teraz zmienna jest liczbą zmiennoprzecinkową 
                  # (liczba 1 zostaje zwolniona z pamięci)
```

Jaki typ będzie miała zmienna `a` gdy przypiszemy do niej wartość `3 / 2`?


## Zad. 7 
Sprawdź, czy poniższe instrukcje zmieniają wartość `a`?

```python
a = 3             # Zmienna a jest przypisana do obiektu 3
b = a             # Zmienna b staje się referencją do tego samego obiektu
b = 4             
```


## Zad. 8
Jakie wartości mają zmienne `a` i `b` po wykonaniu poniższego kodu?

Spróbuj odpowiedzieć na to pytanie zanim przetestujesz kod.

```python
a = 3
b = a
a = a + 2
```


## Zad. 9
Które z poniższych nazw zmiennych są prawidłowe? Spróbuj przypisać do nich jakieś wartości liczbowe.

```
Gene
exon
5utr
utr5p
gene name
gene_name
gene.name
geneName
UTR
```


# Łańcuchy znaków (*strings*)

## Zad. 10
Jaką wartość będzie miała zmienna `name` w poniższym kodzie:

```python
first = 'James'                    # Nie ma różnicy, czy stringi definiujemy używając
last = "Watson"                    # pojedynczych czy podwójnych apostrofów (cudzysłowu).
name = first + ' ' + last
```

## Zad. 11
Funkcja `len` zwraca długość (liczbę znaków) danego łańcucha znaków.

Jaka jest długość tekstu znajdującego się pod zmienną `name`?


## Zad. 12
Sprawdź, które z poniższych wyrażeń są prawidłowe?

```python
'2' + 3               # 1
'2' + '3'             # 2
int('2') + 3          # 3
'2' + str(3)          # 4
float('2') + 3        # 5
'2' * 3               # 6
'2' * '3'             # 7
```


## Zad. 13
Wygeneruj poniższy łańcuch znaków w taki sposób, aby wpisać możliwie jak najmniej znaków: `A`, `C`, `G` i `T`. 

```
ATATATATATATAT ATGC ATGC ATGC ATGC ATGC ATGC ATGC CGCGCGCGCGCGCG
```

Na przykład: `4 * 'AT' + ' ' + 2 * 'AT'` wygeneruje `'ATATATAT ATAT'`.


## Zad. 14
Sprawdź i krótko odpowiedz, co robią poniższe operacje:

```python
s = '0123456789'
```

1. `s[0]`
2. `s[1]`
3. `s[9]`
4. `s[10]`
5. `s[-1]`
6. `s[-2]`


## Zad. 15
Sprawdź i krótko odpowiedz, co robią poniższe instrukcje wycinania (*ekstrakcji podłańcucha*):

1. `s[0:9]`
2. `s[0:10]`
3. `s[:len(s)]`
4. `s[:]`
5. `s[:11]`
6. `s[-3:-1]`
7. `s[-3:]`
8. `s[1:10:2]`
9. `s[::2]`
10. `s[::-1]`


## Zad. 16
Utwórz poniższą zmienną, wyświetl jej wartość funkcją `print` i odpowiedz czym są znaki: `\n`, `\t`

```python
s = 'Hello\tHolla\nGuten tag! Konnichi wa!'
```

W jaki sposób umieścić znak lewego ukośnika `\` w łańcuchu znaków?


## Zad. 17
Python udostępnia zbiór <a target="_blank" href="https://docs.python.org/3/library/stdtypes.html#string-methods">metod łańcuchów znaków</a>, które implementują często spotykane zadania związane z tym typem danych. Łańcuchów znaków w Pythonie **nie można modyfikować** w miejscu. Dlatego metody te zawsze generują nowe obiekty:

```python
>>> s = 'Bioinformatics'
>>> s.upper()
'BIOINFORMATICS'
>>> print(s)
Bioinformatics
```

Jak zmodyfikować powyższy kod, aby zmienna `s` miała na końcu wartość `BIOINFORMATICS`?


## Zad. 18
Rozszyfruj co robią poniższe wyrażenia:

```python
s = '  James Watson i Francis Crick odkryli strukturę DNA w 1953 roku.  '
```

1. `s.lstrip()`
2. `s.rstrip()`
3. `s.strip()`
4. `s.strip().rstrip('.')`
5. `s.strip().rstrip(',')`
6. `s.find('Watson')`
7. `s.find('Sherlock')`
8. `s.lower()`
9. `s.count('Watson')`
10. `s.replace('o', '0')`
11. `s.strip().replace('roku.', 'roku!').upper()`
12. `s.strip().startswith('James')`
13. `s.endswith('roku.  ')`


## Zad. 19
W jednej linii kodu (*one-liner*) sformatuj poniższą sekwencję aminokwasów poprzez jednoczesne: 
- pozbycie się znaku `>` 
- pozbycie się wszystkich spacji na końcu sekwencji 
- zamianę sekwencji na wielkie litery. 


```python
sequence = ">MAnlFKLgaENIFLGrKW    "
```


## Zad. 20
Utwórz *one-liner*, który zwróci liczbę cytozyn w pierwszych 30 nukleotydach poniższej sekwencji DNA.

```python
sequence = 'AGCCGAGCCCGGCGGCCACGGCTGGCGATGAGGAGCGGCGGGTTAGAGCGCGAGC'
```


## Zad. 21
Python oferuje *dwa mechanizmy formatowania łańcuchów znaków*: wyrażenie formatujące (`%`) i metodę `format`. Metoda `format` jest nowym i preferowym stylem formowatowania łańcuchów znaków w Pythonie i wkrótce zastąpi stary styl formatujący (`%`).

Poniższe instrukcje pozwolą Ci zapoznać się z użyciem obu mechanizmów.

Utwórz poniższe zmienne:

```python
name = 'Human'
nucl = 3234830000      # Liczba nukleotydów całego ludzkiego DNA
metr = 1.94            # Długość DNA w komórce wyrażona w metrach
```

Przetestuj poniższe instrukcje:
 
```python
'{} genome has {} meters and {} bp'.format(name, metr, nucl)
'%s genome has %f meters and %i bp' % (name, metr, nucl)           
```

```python
'{} genome has {:.1f} meters and {:,} bp'.format(name, metr, nucl)
'%s genome has %.1f meters and %i bp' % (name, metr, nucl)
```

```python
'{2} genome has {1} meters and {0} bp'.format(nucl, metr, name)
'%s genome has %f meters and %i bp' % (name, metr, nucl)
```

```python
'{0} genome sequence is in file: {0}_genome.txt'.format(name)
'%s genome sequence is in file: %s_genome.txt' % (name, name)
```

Metoda `format` ma olbrzymie możliwości w porównaniu do starego stylu `%`.  Więcej przykładów: https://pyformat.info 

Który mechanizm formatowania ciągów znaków (`%` / `format`) bardziej Ci odpowiada i dlaczego?



# Wykonywanie programów Pythona

## Zad. 22
W dowolnym edytorze tekstu (np.: *Sublime*, *gedit*) utwórz skrypt o nazwie `01-22.py` zawierający instrukcje:

```python
seq = 'CGAGCGCGGCGCCCTTGAGCTGCACCGCGGCGCAGGTTTGCGAGCCGACTTGTCAGCCGG'
seqlen = len(seq)
print(seqlen)
```

Wykonaj skrypt używając polecania powłoki *bash*: 

```bash
python3 01-22.py
```

Wyjaśnij, co robi powyższy program?


## Zad. 23
Zmodyfikuj skrypt `01-22.py`, aby wyświetlał na ekranie poniższy komunikat.

```
Sequence length: 60 nt.
```


## Zad. 24
Wysoka zawartość nukleotydów G i C w DNA wskazuje, że dana sekwencja może być genem. Rozszerz skrypt `01-22.py`, aby w wyniku jego działania dodatkowo otrzymać informacje o procentowej zawartości reszt `G` + `C`.

```
Sequence lenght: 60 nt
GC content: XX.X%
```


## Zad. 25
Poniższa sekwencja `chain_a` reprezentuje fragment białka supresora nowotworowego p53, który wiąże DNA.

```python
# Potrójny apostrof ''' definiuje wielolinijkowy string.
# Na końcu każdej linii jest "enter" (znak nowej linii).

chain_a = '''SSSVPSQKTYQGSYGFRLGFLHSGTAKSVTCTYSPALNKM
FCQLAKTCPVQLWVDSTPPPGTRVRAMAIYKQSQHMTEVV
RRCPHHERCSDSDGLAPPQHLIRVEGNLRVEYLDDRNTFR
HSVVVPYEPPEVGSDCTTIHYNYMCNSSCMGGMNRRPILT
IITLEDSSGNLLGRNSFEVRVCACPGRDRRTEEENLRKKG
EPHHELPPGSTKRALPNNT'''
```

Utwórz skrypt `01-25.py`, umieść w nim sekwencję `chain_a` i napisz instrukcje, które odpowiedzą na poniższe pytania:

1. Wyświetl na ekranie sekwencję `chain_a`. Ile linii zawiera powyższa sekwencja (użyj odpowiedniej metody)?
2. Zapisz do nowej zmiennej sekwencję bez znaków nowej linii. Z ilu aminokwasów składa się sekwencja?
3. Podaj fragment sekwencji, który znajduje się w pozycji od 144 do 156 aminokwasu. 
4. Czy sekwencja zawiera podłańcuch `NLRVEYLDDRN`? W jakiej pozycji?
5. W jaki sposób można użyć metody `find` i tworzenia wycinku `[i:j]` aby wydobyć pierszą linię zmiennej `chain_a`?


## Zad. 26
Poniższa sekwencja stanowi fragment ludzkiego genu BRCA2, który związany jest z rakiem piersi.

```python
# Potrójny cudzysłów """ również definiuje wielolinijkowy string.

dna = """GGGCTTGTGGCGCGAGCTTCTGAAACTAGGCGGCAGAGGCGGAGCCGCT
GTGGCACTGCTGCGCCTCTGCTGCGCCTCGGGTGTCTTTT
GCGGCGGTGGGTCGCCGCCGGGAGAAGCGTGAGGGGACAG
ATTTGTGACCGGCGCGGTTTTTGTCAGCTTACTCCGGCCA
AAAAAGAACTGCACCTCTGGAGCGG"""
```

Utwórz skrypt `01-26.py`, umieść w nim sekwencję `dna` i napisz instrukcje, które zrealizują następujące zadania:

1. Zamień sekwencję DNA na RNA i zapisz ją do zmiennej `rna` (np. `ATGCA` na `AUGCA`).
2. W pozycji 51-156 nukleotydów sekwencji znajduje się intron - zapisz jego sekwencję do zmiennej `intron`.
3. Sekwencję bez intronu (połączone 2 sekwencje) zapisz do zmiennej `mrna`.