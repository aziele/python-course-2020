## Zad. 32
Zmodyfikuj kod zadania 31, aby wyświetlił w osobnej linii każdą literę kodonu.


## Zad. 33
Utwórz skrypt `02-33.py`, który przyjmie od użytkownika ciąg liczb dowolnej długości. Po ich wczytaniu skrypt powinien wyświetlić na ekranie wartość średnią wprowadzonych liczb.

Output:

```
Enter your numbers: 5 6 2 6 1
Mean: 4.0
```

```
Enter your numbers: 1 3 2
Mean: 2.0
```


## Zad. 34
Zapis *dot-bracket* używany jest do tekstowego przedstawienia struktury drugorzędowej cząsteczek RNA.

Przykładowy zapis *dot-bracket*:
```
.((..(((...)))..((..)))).
```

Korzystając ze zdobytych do tej pory wiadomości na temat Pythona (lab01-lab02), napisz skrypt `02-34.py` sprawdzający, czy dany zapis *dot-bracket* jest prawidłowy, tj:
* składa się jedynie z nawiasów i kropek,
* liczba nawiasów otwierających i zamykających musi być identyczna,
* każdy nawias otwierający musi mieć swój nawias zamykający.

Przykłady **prawidłowego** zapisu:

```
.((.))..()
```

```
.(((...).(...)))
```

```
()
```

```
.(.).
```

Przykłady **nieprawidłowego** zapisu:

```
.(..)..(.
```

```
.(..)..a()..
```

```
..()..)(..
```

```
(.)))(((.)
```
