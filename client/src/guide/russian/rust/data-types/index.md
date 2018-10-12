---
title: Rust Data Types
localeTitle: Типы данных ржавчины
---
Понимание системы типов языка программирования важно для начала написания программ. Система типа - это просто система, в которой язык программирования обеспечивает сохранение информации в данных. Если вы являетесь разработчиком из C / C ++, некоторые из этих типов данных могут быть вам уже знакомы.

Давайте посмотрим на примитивные типы Руста

* * *

Когда мы смотрим на Rust, мы видим язык, в котором гораздо больше внимания уделяется **безопасности типов** . Это означает, что взаимодействие и обработка, как программист хранит данные, компилятор является гораздо более строгим и неумолимым. Один пример (который мы увидим в ближайшее время) вводится через **предупреждения** .

Rust также является статически типизированным языком программирования. Это означает, что когда компиляция программы (также называемая _временем компиляции_ ), тип переменных должен быть известен. Rust имеет возможность предоставления _неявных_ или _явных_ типов.

### Целые

Давайте посмотрим, как работают _неявные_ или _явные_ типы, объявив простое целое число.
```
let number = 13; 
```

Мы объявили нашу переменную, `number` равняется значению 13. Когда мы скомпилируем это, Rust знает, что тип номера `i32` , также известный как 32-разрядное целое число. Если мы хотим сделать это _явно_ , мы можем объявить переменную так:
```
let number: i32 = 13; 
```

Конечно, `i32` - это не единственный тип, который мы можем указать. Вот таблица других `integer` типов, которые вы можете реализовать. Имейте в виду, что они имеют _фиксированный размер_ , а количество бит, соответствующее типу, - это количество бит, которое может быть сохранено в этой переменной.

| Размер | Подписано | Без подписи | | ----- | ---- | --- | | 8-битный | i8 | u8 | | 16-бит | i16 | u16 | | 32-битный | i32 | u32 | | 64-бит | i64 | u64 |

Подписанные ( `i` preend) и unsigned ( `u` preend) представляют собой, являются ли переменные, которые мы объявляем, положительными или отрицательными, соответственно.

Rust также имеет `isize` и `usize` , который будет зависеть от архитектуры вашего компьютера. Если вы используете 64-битную архитектуру, у вас будет 64-битная переменная. Если вы используете 32-битную архитектуру, у вас будет 32-битная переменная.

### Плавает

Rust также поддерживает значения float или десятичные значения.
```
let floaty = 3.0; // type is f64 
```

Значение переменной `floaty` было объявлено неявным типом `f64` или 64-битным поплавком. Если вы хотите `f32` , вы можете принудить переменную, либо явную, либо добавив тип к концу значения переменной:
```
let float1: f32 = 4.5; // type is f32 
 let float2 = 5f32;   // type is f32 
```

Вы можете видеть, что `float2` теперь является `f32` , хотя он имеет не десятичное значение. Добавляя `f32` , мы принуждены `float2` представлять `f32` тип.

## Булевы

На каждом языке программирования значения boolean ( `true` и `false` ) всегда присутствуют в той или иной форме. Rust поддерживает это через тип `bool` .
```
let t = true; 
 let f: bool = false; 
```

## Численные операции

С учетом сказанного мы теперь можем использовать Rust для выполнения простых числовых операций. Обратите внимание, что типы ограничены вычислениями только с их собственными типами.
```
let a = 4 + 5;        // => 9 
 let b = 5.0 - 4.0;    // => 1.0 
 let c = 3 * 4.0;      // => ERROR! 
 let d = 6.0 / 2.0;    // => 3.0 
 let e = 10 % 4;       // => 2 
```

## Предупреждение!

Давайте рассмотрим некоторые из потенциальных проблем, которые могут уже присутствовать в Rust. Поскольку использование данных эффективно и обеспечение того, что используемые нами переменные фактически используются, Rust будет вызывать предупреждения для неиспользуемых переменных:
```
fn main(){ 
  let a = 4; 
  // and now we close our program. 
 } 
```

Теперь, если мы запустим эту программу:
```
warning: unused variable: `a` 
```

Важно помнить, что всегда используйте наши переменные, а если нет, прокомментируйте их или удалите их!

## Прочитайте больше:

https://doc.rust-lang.org/book/second-edition/ch03-02-data-types.html