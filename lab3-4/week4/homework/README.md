# Четвърто домашно по функционално програмиране

Решенията на задачите се предават по e-mail на адрес:

>fp2014.fmi@gmail.com

Решението на всяка задача трябва да бъде под формата на файл с окончание `.scm*` който да съдържа дефиницията на функцията (със точната сигнатура дефинирана в условието на задачата) и евентуално други помощни дефиниции, необходими за реализацията.

Файловете се изпращат като *attachment-и* в *mail-a*.

Освен решения на задачите самият *mail* трябва да съдържа име, група и факултен номер. Успех!

## Задача 1 - N-ти елемент в списък

Във файла `nth.scm`, напишете функция, която има следната сигнатура:

```scheme
(define (nth index list) ... )
```

Функцията взима два аргумента - число `index` и списък `list` и връща елементът, който се намира на даденият `index` в нашия списък.

**Броим от 0!**

Също така, не се грижете, да следите дали индекса се намира в списъка. Програмата сама ще си гръмне ;)

### Примери

```scheme
> (nth 0 (list 1 2 3))
1
> (nth 1 (list "Scheme" "Haskell"))
"Haskell"
```

## Задача 2 - join

Във файла `join.scm`, напишете функция със следната сигнатура:

```scheme
(define (join glue parts) ... )
```
Функцията взима един низ `glue` и списък от низове - `parts` и връща нов низ, който представлява "слепеният" списък, като между всеки два елемента, поставяме низа `glue`.

Важното е, че не поставяме `glue` в началото и в края на новополучения string.

### Примери:

```scheme
> (join " " (list "Scheme" "is" "an" "akward" "language"))
"Scheme is an akward language"
> (join "1!" (list "One" "Two" "Three"))
"One1!Two1!Three"
```

## Задача 3 - split

Във файла `split.scm`, напишете обратната функция на `join` - `**split**`, която има следната сигнатура:

```scheme
(define (split delimiter str) ...)
```

Където `delimiter` и `str` са низове.

Функцията трябва да върне списък от разделените части на `str`.

### Примери:

```scheme
> (split " " "Scheme is an akward language")
("Scheme" "is" "an" "akward" "language")
> (split "1!" "One1!Two1!Three")
("One" "Two" "Three")
```

### Подсказка

За да ви е лесно, може би искате да обърнете низа в списък от символи по следния начин:

```scheme
> (string->list "Scheme")
(#\S #\c #\h #\e #\m #\e)
```

Тези странно изглеждащи `#\S` неща са начинът, по който Scheme записва символите.

**Може да направите и обратната операция:**

```scheme
> (list->string (string->list "Scheme"))
"Scheme"
```

Поекспериментирайте с `take` и `drop` :)

А тук пък има пълна документация на функции за работа с низове - http://docs.racket-lang.org/reference/strings.html