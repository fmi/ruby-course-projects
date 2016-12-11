# Lisp интерпретатор

Напишете gem, който интерпретира подмножество на езика [Scheme](https://en.wikipedia.org/wiki/Scheme_(programming_language)).

## Функционалности

- [Команда](http://guides.rubygems.org/make-your-own-gem/#adding-an-executable) за изпълняване на файл с lisp код.
- [Команда](http://guides.rubygems.org/make-your-own-gem/#adding-an-executable) за стартиране на [интерактивна конзола](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) (подобна на irb/pry).
- Ruby интерфейс за изпълняване на lisp код от низ.

## Минимално подмножество

- Придържайте се към духа на езика
  * Префиксен синтаксис, много кръгли скоби
  * Immutability is king
  * First class функции
- Булеви стойности
  * `#t` и `#f`
  * `not`, `equal?`
- Числа
  * реални, рационални и цели
  * `+`, `-`, `*`, `/`, `quotient`, `remainder`, `modulo`, `numerator`, `denominator`
  * [Още 5 по ваш изобор](https://docs.racket-lang.org/reference/generic-numbers.html)
- Низове
  * `string-length`, `substring`, `string-upcase`, `string-contains?`, `string->list`, `string-split` (без регулярни изрази)
  * [Още 5 по ваш избор](https://docs.racket-lang.org/reference/strings.html)
- Списъци/двойки
  * `null?`, `cons`, `null`, `list`, `car`/`cdr`/`caddr`/и т.н. безкрайна дълбочина
  * `map`, `foldl`, `filter`, `member`
  * [Още 5 по ваш избор](https://docs.racket-lang.org/reference/pairs.html)
- Функции/процедури
  * `lambda`, `apply`, `compose`
  * Рекурсия (главен способ за итериране)
  * Не забравяйте, че нещата, приличащи на оператори (`+`/`-`/...), са обикновени функции
- Общи
  * Литерален синтаксис за различните типове.
  * `define`

## Забележки
- Опитайте се да имплементирате истинско подмножество на езика, а не негов диалект. Би следвало да се държи възможно най-близо до реален Scheme. Неща като произволно позиционирани whitespace-и не трябва да объркват интерпретатора.
- Добавете адекватни съобщения при често срещани синтактични грешки (например небалансирани скоби) и при извикване на функция от стандартната библиотека с невалидни аргументи (например `(/ '42' 6)`).
- Не използвайте `eval` и други средства за изпълняване на Ruby код от низ.

## Помощни материали
[The Racket Reference](https://docs.racket-lang.org/reference/)
