# ОБЪЕКТЫ(ПРАКТИКА).
***

## Пример один:
Наш знакомый уважает футбол, но смотреть игры ему лень. Но это не страшно, ведь  достаточно знать имена лучших бомбардиров и их результативность, чтобы поддержать беседу в нужный момент (поставить на игрока).


Заказчику нужна программа, которая подсчитает полезность и результативность игроков на основе их статистики. Оформите код в виде функции getStatistics с одним параметром — массивом игроков.
 Каждый футболист в этом массиве описывается объектом с тремя полями: имя (свойство name), забитые голы (свойство goals) и голевые пасы (свойство passes).

Функция должна возвращать этот же массив, в котором каждому игроку добавлены ещё два поля: коэффициент полезности (свойство coefficient) и результативность (свойство percent).

- Коэффициент полезности считается так: умножаем голы игрока на 2 (потому что я считаю, что голы важнее всего) и прибавляем к этому значению все голевые пасы футболиста.
- Результативность (процент забитых мячей футболиста от результата всей команды) считаем так: находим сумму голов всех игроков и выясняем, сколько процентов от этого числа забил каждый футболист. Округляйте значение с помощью Math.round().
**Подсказка**
Рассчитываем, какой процент составляет число:
```javascript
// Общее значение, то есть 100%
1200
// Сколько процентов составляет 225 от 1200
(225 * 100) / 1200 = 18.75
// После округления с помощью Math.round()
19
```
Пример работы:
```javascript
var firstPlayer = {
name: 'Pavel',
goals: 30,
passes: 20
};

var secondPlayer = {
name: 'Vladimir',
goals: 25,
passes: 15
};


var totalGoals = 0;

var players = [firstPlayer, secondPlayer];

var getStatistics = function (players) {
for(var j = 0; j < players.length; j++){
totalGoals += players[j].goals;
}

for(var i = 0; i < players.length; i++){
players[i].coefficient = players[i].goals*2+players[i].passes;
players[i].percent = Math.round(players[i].goals*100/totalGoals);
}
return players;

};
```
***
## Пример два:
Пока вы работали над интернет-магазином, наш любимый заказчик решил построить дом. Он начал писать конфигуратор для расчёта площади и стоимости строительства, но утомился. И правда, зачем писать код самому, если есть разработчики?

Допишите конфигуратор. Был создан объект house и задано ему несколько свойств: rooms (количество комнат), floors (этажи), material (материал для стен), coefficient (средняя площадь каждой комнаты).

Ещё заведена мапа materialPrice, в которой записана стоимость каждого возможного материала для строительства.

- Добавьте в объект два метода: calculateSquare, который будет возвращать площадь дома, и calculatePrice, который будет возвращать стоимость строительства.

- Площадь считайте так: умножь количество комнат на коэффициент и число этажей в доме.

- Цена строительства — произведение площади и стоимости материала дома.


**Один из примеров работы:**
```javascript
var materialPrice = {
'wood': 1000,
'stone': 1500,
'brick': 2000
};

var house = {

rooms: 10,
floors: 5,
material: 'wood',
coefficient: 10.5,
calculateSquare: function(){

return  this.rooms*this.coefficient*this.floors;
},

calculatePrice: function () {
return this.calculateSquare() * materialPrice[this.material];
}

};
```
