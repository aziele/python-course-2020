# Funkcje

## Zad. 1
Co otrzymasz w wyniku działania tego kodu:

```python
def print_line(text):
    print(text, 'is coming.')

print_line('Winter')
```

1. `Winter`
2. `Winter is coming.`
3. `text is coming.`
4. `is coming.`


## Zad. 2
Poniżej znajduje się kod, który oblicza skład nukleotydów `GC` w sekwencji DNA znajdującej się pod zmienną `dna`. W oparciu o ten kod utwórz funkcję `gc_content`, która jako argument będzie przyjmowała dowolny łańcuch znaków.

```python
dna = "ACTGATCGATTACGTATAGTATTTGCTATCATACATATATATCGATGCGTTCAT" 

c_count = dna.count('C') 
g_count = dna.count('G') 
gc_content = (c_count + g_count) / len(dna) 

print(f"CG content is {gc_content}")
```


## Zad. 3
Na czym polega różnica między poniższymi dwoma funkcjami?

```python
def power(n):
    print(n ** 2)

x = power(4)
print(x)
```

```python
def power(n):
    return n ** 2

x = power(4)
print(x)
```


## Zad. 4
Zmodyfikuj funkcję `gc_content`, aby zwracała liczbę:

```python
gc = gc_content(dna='ATGC')
print(gc)                          # 0.5
print(gc_content('ATGC'))          # 0.5
```


## Zad. 5
Czy funkcja `gc_content()` zadziała, jeżeli jako argument przyjmie `['A', 'C', 'G', 'T']`?

Jak w *programowaniu* nazywa się taka właściwość?

1. `mutowalność`
2. `polimorfizm`
3. `obiektowość`
4. `delegacja`


## Zad. 6
Utwórz funkcję `hamming_distance`, która przyjmuje jako argumenty dwie sekwencje równej długości i oblicza między nimi [dystans Hamminga](https://pl.wikipedia.org/wiki/Odległość_Hamminga) - liczba miejsc (pozycji), na których dwie sekwencje się różnią.

Input:
```
GAGCCTACTAACGGGAT
CATCGTAATGACGGCCT
```

Output:
```
7
```

## Zad. 7
Czy funkcja `hamming_distance` zwróci poprawny wynik jeżeli użytkownik wprowadzi `ACTG` i `actg`. 

W jaki sposób można poprawić ten błąd logiczny?


## Zad. 8
Które zdanie jest nieprawdziwe?

```python
def multiply(a, b=2, c=3):
    return a * b * c 
```

1. `multiply(1)` da `6`
2. `multiply(a=1)` da `6`
3. `multiply(1, 4)` da `12`
4. `multiply(1, 4, 5)` da `20`
5. `multiply(1, c=4)` da `8`
6. `multiply(1, c=4, b=2)` da `8`
7. `multiply(b=2, c=3)` da `6`


## Zad. 9
Ile wynosi `x` w miejscu pierwszego i drugiego wyrażenia `print(x)`?

```python
x = 99             # Zmienna widoczna w całym pliku

def func():
    x = 88         # Zmienna widoczna jedynie wewnątrz funkcji func().
    print(x)

func()
print(x)
```


## Zad. 10
Czy `lst` jest takie samo w miejscu pierwszego i drugiego wyrażenia `print(lst)`?

```python
lst = [1, 2, 3]

def func():
    lst = [3, 2, 1]
    print(lst)

func()
print(lst)
```


## Zad. 11
Czy `lst` jest takie samo w miejscu pierwszego i drugiego wyrażenia `print(lst)`?

```python
lst = [1, 2, 3]

def func():
    lst[1] = 3
    print(lst)

func()
print(lst)
```


## Zad. 12
Wymień przynajmniej 5 wbudowanych funkcji Pythona, które już wykorzystywałe/aś na poprzednich zajęciach 1-4.


## Zad. 13
Wyjaśnij co robią poniższe dwa wyrażenia:

```python
help(print)
print(print.__doc__)
```

## Zad. 14
Utwórz dokumentację funkcji `hamming_distance()` i wywołaj ją poleceniem `help()`.

> Kod Pythona udostępniany przez wiele projektów (np. [Google Example Code](http://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html), NumPy, SciPy) stosuje poniższy styl dokumentowania funkcji.

```python
def function_with_types_in_docstring(param1, param2):
    """Example function with types documented in the docstring.

    Args:
        param1 (int): The first parameter.
        param2 (str): The second parameter.

    Returns:
        bool: The return value. True for success, False otherwise.

    """
    # Python instructions go here.
```


## Zad. 15
W pliku `05-15.py` utwórz funkcję `complement()`, która przyjmuje sekwencję DNA i zamienia ją na sekwencję komplementarną.

Input: 

```
ACTG
```   

Output:

```
TGAC
```


## Zad. 16
W tym samym pliku `05-15.py` utwórz funkcję `reverse_complement()`, która przyjmuje sekwencję DNA i wykorzystuje funkcję `complement()` aby zwrócić sekwencję odwrotnie komplementarną.

Input: 

```
ACTG
``` 

Output: 

```
CAGT
```


## Zad. 17
Wykorzystując funkcję `reverse_complement()` wygeneruj sekwencje odwrotnie komplementarne do sekwencji z poniższej listy.

Input:

```python
lst = ['CTGACT', 'GCATAGT', 'TAGATTAT', 'CGATGTTTA']
```

Output:

```python
AGTCAG
ACTATGC
ATAATCTA
TAAACATCG
```

## Zad. 18
Wyjaśnij, co robi poniższy kod.

```python
import random

for i in range(10):
    print(random.randint(0, 3))
```


## Zad. 19
Wyjaśnij, co robi poniższy kod.

```python
import random

for i in range(10):
    print(random.choice(['DNA', 'RNA', 'protein']))
```


## Zad. 20
Utwórz funkcję `mutate()`, która w sekwencji DNA wprowadzi jedną losową *substytucję* nukleotydu na losowej pozycji.

Na przykład:

```python
>>> mutate('ATGCG')
ACGCG
>>> mutate('ATGCG')
ATGCT
```