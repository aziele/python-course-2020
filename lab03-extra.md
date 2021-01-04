## Zad. 21
Plik [words_english.txt](./data/words_english.txt) zawiera ponad *370 000* słów języka angielskiego. Pobierz plik na dysk i podejrzyj jego zawartość.

Napisz skrypt `03-21.py` zwracający liczbę słów, które są [palindromami](https://pl.wikipedia.org/wiki/Palindrom) składającymi się z co najmniej trzech liter.


## Zad. 22
Zmodyfikuj skrypt `03-21.py`, aby zapisał wszystkie palindromy do pliku `palindromes.txt`. 


## Zad. 23
Zmodyfikuj skrypt `03-21.py`, aby palindromy były zapisane w pliku w kolejności od najdłuższego do najkrótszego.


## Zad. 24
W katalogu [data/](./data/) znajduje się 10 plików, z których każdy zawiera jeden rekord sekwencji w formacie GenBank. Pobierz sekwencje na dysk. Napisz skrypt `03-22.py`, który w pętli *for* otworzy te 10 plików i odczyta identyfikator każdej sekwencji.

Output:

```
XM_003063680
NM_001031912
NM_001047041
NM_001013207
NM_171360
XM_013499304
XM_012793813
XM_011130266
XM_638989
XM_626579
```


## Zad. 25
Zmodyfikuj skrypt, aby wyliczał procentowy udział nukleotydów `G` + `C` w każdej z 10 sekwencji.

Output:

```
XM_003063680 70.29
NM_001031912 52.15
NM_001047041 61.97
NM_001013207 41.90
NM_171360 44.49
XM_013499304 55.96
XM_012793813 43.17
XM_011130266 57.93
XM_638989 23.98
XM_626579 29.98
```