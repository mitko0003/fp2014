# Трето домашно по функционално програмиране

Решенията на задачите се предават по e-mail на адрес:

>fp2014.fmi@gmail.com

Решението на всяка задача трябва да бъде под формата на файл с окончание `.scm*` който да съдържа дефиницията на функцията (със точната сигнатура дефинирана в условието на задачата) и евентуално други помощни дефиниции, необходими за реализацията.

Файловете се изпращат като *attachment-и* в *mail-a*.

Освен решения на задачите самият *mail* трябва да съдържа име, група и факултен номер. Успех!

## Задача 1 - take-while

Във файл с име `take-while.scm`, напишете функция със следната сигнатура:

```scheme
(define (take-while pred? l) ...)
```

Функцията връща нов списък с елементи от `l`, докато `pred?` не срещне първият елемент, който ще върне `#f` за него.

### Примери

```scheme
> (take-while even? (list 2 4 6 1 2 4 6))
; Спираме при първия случай, в който намерим нечетно число
(2 4 6)
> (take-while (lambda (x) #t) (list 1 2 3 4 5 6))
(1 2 3 4 5 6)
> (take-while (lambda (row) (> (sum row) 20)) (list (list 1 10 15) (list 10 10 10) (list 2 3 2)))
((1 10 15) (10 10 10))
```

## Задача 2 - drop-while

Във файл с име `drop-while.scm`, напишете функция със следната сигнатура:

```scheme
(define (drop-while pred? l) ...)
```

Функцията връща нов списък, като маха поредни елементи от `l`, докато `pred?` не срещне първият елемент, който ще върне `#f` за него.

### Примери

```scheme
> (drop-while even? (list 2 4 6 1 2 4 6))
; Спираме при първия случай, в който намерим нечетно число
(1 2 4 6)
> (drop-while (lambda (x) #t) (list 1 2 3 4 5 6))
()
> (drop-while (lambda (row) (> (sum row) 20)) (list (list 1 10 15) (list 10 10 10) (list 2 3 2)))
((2 3 2))
```

## Задача 3

Във файл `suffix.scm` напишете функция със следната сигнатура:

```scheme
(define (suffix? l1 l2) ... )
```
s
Функцията проверява дали списъкът `l1` е суфикс на `l2`.

### Примери

```scheme
>(suffix? (list 1 2 3) (list 4 5 6))
#f
>(suffix? (list 1 2 3) (list 4 5 6 1 2))
#f
>(suffix? (list 1 2 3) (list 4 5 6 1 2 3))
#t
>(suffix? (list) (list 4 5 6))
#t
>(suffix? (list 6) (list 4 5 6))
#t
>(suffix? (range 1 10) (range 1 10))
#t
>(suffix? (range 1 10) (range 1 11))
#f
```

## Задача 4

Във файла `occrr.scm` напишете функция със следната сигнатура:

```scheme
(define (occurrences l1 l2) ... )
```

`l1` и `l2` са списъци от числа, а функцията връща списък, който се състои от броя срещания на всеки елемент от `l1` в `l2`

### Примери

```scheme
>(occurrences (list 1 2 3) (list 1 2 4 1))
(2 1 0)
>(occurrences (list 2 2 2) (list 0 5 6))
(0 0 0)
>(occurrences (list 2 2 2) (list 2 2 2 2 2 2 2 2 2 2 2 2))
(12 12 12)
>(occurrences (list) (list 2 2 2 2 2 2 2 2 2 2 2 2))
()
>(occurrences (list 2 3 4) (list))
(0 0 0)
```

### Задача 5

Напишете функция `digit-factorials`, която да приема като аргумент число `n` и връща списък от всички числа, които са по-малки или равни на `n`, за които е изпълнено, че са равни на сумата от факториелите на цифрите си (едно такова число е 145 = 1! + 4! + 5!)

**Сигнатура:**

```scheme
(define (digit-factorials n) ...)
```

**Примери:**

```scheme
> (digit-factorials 100)
(1 2)
> (digit-factorials 1000)
(1 2 145)
> (digit-factorials 50000)
(1 2 145 40585)
```