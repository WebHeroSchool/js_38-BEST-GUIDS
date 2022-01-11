# 1) Избегайте глобальных переменных
### Сведите к минимуму использование глобальных переменных. 
###Вместо этого используйте локальные переменные и узнайте, как использовать замыкания.
### GOOD:
```
function input() {
  const num = 4;
  function output() {
    console.log(num);
}
}
```
### BAD:
```
const num = 4;
function output() {
  console.log(num);
}
```

# 2)Всегда объявлять локальные переменные
### Переменные объявленные без ключевого слова let, var или const считаются объявленными глобально.

### GOOD:
```
function one() {
  let num = 4; 
}
```
### BAD:
```
function one() {
  num = 4; 
}
```

# 3)Объявлять объекты с помощью const.
### Объявление объектов с помощью const предотвратит любое случайное изменение типа.

### GOOD:
```
const girl = {
  name = 'Anna',
  age = '13'
};
girl = 'Piter'  //Значение не изменится
```
### BAD:
```
let girl = {
  name = 'Anna',
  age = '13'
};
girl = 'Piter';  //Значение изменится
```

# 4) Объявления сверху
### Хорошей практикой кодирования является размещение всех объявлений в верхней части каждого скрипта или функции.

### EXAMPLE:
```
let firstName, lastName;

firstName = 'Vika';
lastName = 'Khamova';
```

# 5) Остерегайтесь автоматического преобразования типов
### Числа могут быть случайно преобразованы в строки или NaN.
### Переменная может содержать разные типы данных, при этом в ходе кода может изменять свой тип данных
### При выполнении математических операций JavaScript может преобразовывать числа в строки.
### Вычитание строки из строки не генерирует ошибку, но возвращает NaN.
### EXAMPLE:
```
let x = 'Hello';     // x это строка
x = 5;               // изменение x на номер
```

# 6) Используйте === Сравнение
### Оператор сравнения == всегда преобразует (в соответствующие типы) перед сравнением. 
### Оператор === заставляет сравнивать значения и тип

### GOOD:
```
1 === '1';  // результат будет false
``` 
### BAD:
```
1 == '1';  // результат будет true
```
# 7) Завершите свои переключатели настройками по умолчанию
### Всегда заканчивайте свои инструкции switch значением по умолчанию. Даже если вы думаете, что в этом нет необходимости.
### GOOD:
```
switch (d) { 
  case 1: alert(да); 
    break; 
  default: alert(нет);
}
```
### BAD:
```
switch (d) { 
  case 1: alert(да); 
    break; 
  case 4: alert(иногда); 
    break;}
```

# 8) Никогда не объявляйте числовые, строковые или логические объекты
### Всегда рассматривайте числа, строки или логические значения как примитивные значения. Не как объекты.
### GOOD:
```
cost name = ' ';
```
### BAD:
```
const name = new String(' ');
```
# 9) Избегайте использовать eval()
### Функция eval() используется для запуска текста в виде кода. Почти во всех случаях в его использовании не должно быть необходимости.
### GOOD:
```
console.log(2 + 2);
```
### BAD:
```
console.log(eval('2 + 2'));
```
# 10) Используйте параметры по умолчанию
### Если функция вызывается с отсутствующим аргументом, значение отсутствующего аргумента устанавливается равным undefined.

### GOOD:
```
function primer(x = 1) {
  console.log(2 * x); 
}
```
### BAD:
```
function primer() {
  console.log(2 * x);  //undefined.
}
```