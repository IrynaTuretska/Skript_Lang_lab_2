# Skript_Lang_lab_2

<!DOCTYPE html>
<html>
<body>

  <p>Функция: forEach</p>

  <p>1. Получить сумму всех эдементоа массива</p>

<script>
var array = [10, 20, 30];         // инициализируем переменную, содержащую массив числовых значений 
var sum = 0;                      // инициализируем переменную, содержащую числовое значение 

array.forEach(                    // перебираем все элементы массива array
  function sumNumber( currentValue ) {
    sum += currentValue;
  }
);

console.log( sum );               // выводим значение переменной sum равное 60

</script>


<p>2. Получить корни квадоатные всех эдементоа массива</p>

<script>
var numbers = [2, 3, 4];           // инициализируем переменную, содержащую массив числовых значений 
var squared = [];                  // инициализируем переменную, содержащую пустой массив  
var myObject = {                   // инициализируем переменную, содержащую объект 
  square: function( currentValue ) { // метод объекта, который принимает значение  
    return currentValue * currentValue; // и возвращает его возведенным в квадрат 
  }
};

numbers.forEach(                   // перебираем все элементы массива numbers
  function( currentValue ) {
    squared.push( this.square( currentValue ) ); // добавляем в массив squared возвращаемое значение метода square объекта myObject
  }, myObject                      // объект, на который мы ссылаемся с использованием ключевого слова this 
);

console.log( squared ); // выводим значение переменной squared равное [4, 9, 16]
console.log("---------------------------------");
</script>


<p>Функция: Map</p>

<p>1. Умножить все элементы массива на 10</p>

<script>
var sample = [1, 2, 3]               
var mapped = sample.map(function(elem) {
    return elem * 10;                // Умножить все элементы массива на 10
// es5
})
// es6
var mapped = sample.map(elem => elem * 10)
console.log(mapped);

console.log("---------------------------------");
</script>


<p>Функция: Reduce</p>

<script>
var sample = [1, 2, 3]               
// es5
var sum = sample.reduce(function(sum, elem){
    return sum + elem;
})
// es6
var sum = sample.reduce((sum, elem) => sum + elem)
console.log(sum)
console.log("---------------------------------");
</script>


<p>Функция: ReduceRight</p>

<p>1. Отобразить 5ть элементов с "хвоста" массива</p>

<script>
var arr = [1,2,2,32,23,4,5,66,22,35,78,8,9,9,4,21,1,1,3,4,4,64,46,46,46,4,6,467,3,67];

function tailItems(num) {
    var num = num + 1 || 1;
    return arr.reduceRight(function(accumulator, curr, idx, arr) {
        if (idx > arr.length - num) {
            accumulator.push(curr);
        }
        return accumulator;
    }, []);
}

console.log(tailItems(5));             //=> [67, 3, 467, 6, 4]
console.log("---------------------------------");


</script>

<p>2. Отобразить индексы эллементов массива с права на лево</p>

<script>
var arr = [1,2,2,32,23];

arr.reduceRight(function(accumulator, curr, idx, arr) {
    console.log(idx);
}, '');                               // => 4,3,2,1,0
console.log("---------------------------------");
</script>


<p>Функция: Filter</p>

<p>1. Отфильтровать и вывести на экран только нечетные элементы</p>

<script>
var sample = [1, 2, 3] 
// es5
var result = sample.filter(function(elem){
    return elem !== 2;
})
console.log(result)
// es6
var result = sample.filter(elem => elem !== 2)
console.log("---------------------------------");
</script>


<p>2. Hайти конкретное значение в массиве объектов</p>

<script>
console.log(" = ОТФИЛЬТРОВАННЫЙ ПРИМЕР = ");
const users = [
    {id: 1, name: "Jonh", surname: "Green"},
    {id: 2, name: "Smith", surname: "Brown"},
    {id: 3, name: "David", surname: "White"}
];
const filtered = users.filter(item => item.id == 2);
console.log(filtered);
console.log("---------------------------------");
</script>

<p>Функция: Every / Some</p>

<script>

const data = [7, 14, 5, 12, 25]
const value1 = data.some(i => i > 10);
const value2 = data.some(i => i < 3);
console.log(" = НЕКОТОРЫЕ значения = ");
console.log(value1);                 //true
console.log(value2);                 //false
console.log("---------------------------------");
const value3 = data.every(i => i > 10);
const value4 = data.every(i => i > 3);
console.log(" = ВСЕ значения = ");
console.log(value3);                //false
console.log(value4);                //true
console.log("---------------------------------");
</script>


</body>
</html>
