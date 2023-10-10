# \[Task]freeCodeCamp

| 链接  | [https://chinese.freecodecamp.org/learn/](https://chinese.freecodecamp.org/learn/ "https://chinese.freecodecamp.org/learn/") |
| --- | ---------------------------------------------------------------------------------------------------------------------------- |
| 名称2 |                                                                                                                              |
| 介绍  |                                                                                                                              |
| 分类  | 学习,编程                                                                                                                        |

"You can, you should, and if you're [brave](brave_q2u8jxvccHKdJGbkk3BEwi.md "brave") [enough](enough_88kRSM74zHbu18FeaH6uEr.md "enough") to start, you will."
——Stephen King
“你能做到，你也可以成功，只要你有足够的勇气开始，你就可以。”
——斯蒂芬·金

If you're [getting](getting_uKnikhHUYKQeAnB8CkEHbJ.md "getting") a lot [out](out_84c8V1sDWVAh6DmzpQ5W1m.md "out") [of](of_mXNLGQJuXkWed8tNHEUzue.md "of") freeCodeCamp, now is a great time to donate to support our nonprofit's mission.

***

# 课程类别

-   [JavaScript](https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/ "JavaScript")算法和数据结构

    🔳⬜️⬜️⬜️⬜️⬜️⬜️⬜️⬜️⬜️ 10%
    -   [x] 基础JavaScript
        -   示例：递归代替循环
            -   解释

                递归是函数调用自身的操作。 为了便于理解，有如下任务：计算数组内元素前 `n` 的元素乘积。 使用 `for` 循环， 可以这样做：
                ```javascript
                  function multiply(arr, n) {
                    let product = 1;
                    for (let i = 0; i < n; i++) {
                      product *= arr[i];
                    }
                    return product;
                  }
                ```
                下面是递归写法，注意代码里的 `multiply(arr, n) == multiply(arr, n - 1) * arr[n - 1]`。 这意味着可以重写 `multiply` 以调用自身而无需依赖循环。
                ```javascript
                  function multiply(arr, n) {
                    if (n <= 0) {
                      return 1;
                    } else {
                      return multiply(arr, n - 1) * arr[n - 1];
                    }
                  }
                ```
                递归版本的 `multiply` 详述如下。 在 base case 里，也就是 `n <= 0` 时，返回 1。 在 `n` 比 0 大的情况里，函数会调用自身，参数 n 的值为 `n - 1`。 函数以相同的方式持续调用 `multiply`，直到 `n <= 0` 为止。 所以，所有函数都可以返回，原始的 `multiply` 返回结果。

                **注意：** 递归函数在没有函数调用时（在这个例子是，是当 `n <= 0` 时）必需有一个跳出结构，否则永远不会执行完毕。


            -   示例

                写一个递归函数，`sum(arr, n)`，返回递归调用数组 `arr` 从前 `n` 个元素和。

                `sum([1], 0)` 应该返回 0 。

                `sum([2, 3, 4], 1)` 应该返回 2 。

                `sum([2, 3, 4, 5], 3)` 应该等于 9。

                代码不能包含任意形式的循环（`for`、`while` 或者高阶函数如：`forEach`、`map`、`filter` 以及 `reduce`）。

                应该用递归解决这个问题。
                ```javascript
                function sum(arr, n) {
                  // 只修改这一行下面的代码
                  if (n<=0){
                    return 0;
                  } else {
                    return sum(arr, n-1) + arr[n-1];
                  }
                  // 只修改这一行上面的代码
                }
                //sum([1], 0)
                console.log(sum([2, 3, 4], 2) )
                ```
                > 📌比如`sum([2, 3, 4], 1)` 应该返回 2 。，if判断为否，执行else，sum函数调用了自身，此时arr是`[2, 3, 4]`，n是1，在被减一之后，变成0，进入函数，if判断是真，所以返回0。
                >
                > 之后的`+` 就计算出了arr\[1-1]的值是2



        -   示例：（练习)[**资料查找**](https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup "资料查找")

            我们有一个对象数组，里面存储着通讯录。

            `lookUpProfile` 函数已经写好了参数，需要 `name` 和属性 (`prop`) 参数。

            函数将会检查通讯录中是否存在一个 `firstName` 与传入的 `name` 相同的联系人。 如果存在，那么还需要检查对应的联系人中是否存在 `prop` 属性。

            如果它们都存在，函数返回 prop 属性对应的值。

            如果 `name` 不对应于任何联系人，然后返回字符串 `No such contact`。

            如果 `prop` 属性在匹配 `name` 的联系人里不存在，返回 `No such property`。
                const contacts = [
                  {
                    firstName: "Akira",
                    lastName: "Laine",
                    number: "0543236543",
                    likes: ["Pizza", "Coding", "Brownie Points"],
                  },
                  {
                    firstName: "Harry",
                    lastName: "Potter",
                    number: "0994372684",
                    likes: ["Hogwarts", "Magic", "Hagrid"],
                  },
                  {
                    firstName: "Sherlock",
                    lastName: "Holmes",
                    number: "0487345643",
                    likes: ["Intriguing Cases", "Violin"],
                  },
                  {
                    firstName: "Kristian",
                    lastName: "Vos",
                    number: "unknown",
                    likes: ["JavaScript", "Gaming", "Foxes"],
                  },
                ];
            ```

              for (let i = 0; i <= contacts.length; i++){
                if (i == contacts.length){
                  return "No such contact"
                } else if (name == contacts[i].firstName & contacts[i][prop] != undefined){
                    return contacts[i][prop]
                } else if (name == contacts[i].firstName & contacts[i][prop] == undefined){
                    return "No such property"
                }

            ```

        -   生成随机分数

            随机数非常适合用来创建随机行为。

            在 JavaScript 中，可以用 `Math.random()` 生成一个在`0`（包括 0）到 `1`（不包括 1）之间的随机小数。 因此 `Math.random()` 可能返回 `0`，但绝不会返回 `1`
                function randomFraction() {
                  // 只修改这一行下面的代码
                  return Math.random();
                  // 只修改这一行上面的代码
                }
        -   生成随机整数

            生成随机小数很棒，但随机数更有用的地方在于生成随机整数。
            1.  用 `Math.random()` 生成一个随机小数。
            2.  把这个随机小数乘以 `20`。
            3.  用 `Math.floor()` 向下取整，获得它最近的整数。
            记住 `Math.random()` 永远不会返回 `1`。同时因为我们是在向下取整，所以最终我们获得的结果不可能有 `20`。 这确保了我们获得了一个在 `0` 到 `19` 之间的整数。
            -   示例：我们先调用 Math.random()，把它的结果乘以 20，然后把上一步的结果传给 Math.floor()，最终通过向下取整获得最近的整数。
                ```
                Math.floor(Math.random() * 20);

                ```
            -   示例2：使用这个方法生成并返回 `0` 和 `9` 之间的随机整数。
                    function randomWholeNum() {

                      // 只修改这一行下面的代码

                      return Math.floor(Math.random() * 10);
                    }

        -   **生成某个范围内的随机整数**

            我们之前生成的随机数是在 0 到某个数之间，现在我们要生成的随机数是在两个指定的数之间。

            我们需要定义一个最小值 `min` 和一个最大值 `max`。
                Math.floor(Math.random() * (max - min + 1)) + min

            <!---->

                function randomRange(myMin, myMax) {
                  // 只修改这一行下面的代码
                  return Math.floor(Math.random() * (myMax - myMin + 1)) + myMin;
                  // 只修改这一行上面的代码
                }
        -   **使用 parseInt 函数**(返回一个整数)

            `parseInt()` 函数解析一个字符串返回一个整数。 下面是一个示例
            ```
            const a = parseInt("007");

            ```
            上述函数将字符串 `007` 转换为整数 `7`。 如果字符串中的第一个字符不能转换为数字，则返回 `NaN`。

            `convertToInteger` 中应该使用 `parseInt()` 函数。

            `convertToInteger("56")` 应该返回一个数字。

            `convertToInteger("56")` 应该返回 56。

            `convertToInteger("77")` 应该返回 77。

            `convertToInteger("JamesBond")` 应该返回 `NaN`。
                function convertToInteger(str) {
                  return parseInt(str)
                }

                convertToInteger("56");
        -   **使用 parseInt 函数并传入一个基数**(进制转换)
            ```
            parseInt(string, radix);

            ```
            ```
            const a = parseInt("11", 2);

            ```
            变量 radix 表示 `11` 是在二进制系统中。 这个示例将字符串 `11` 转换为整数 `3`。


        -   示例：**使用**\[JS]三元运算符`条件表达式?表达式1:表达式2;`

            条件运算符（ conditional operator,）（也称为三元运算符（ ternary operator））的就像写成一行的 if-else 表达式

            语法是：`a ? b : c`, where `a` 是条件，当条件返回 `true` 的时候运行代码 `b`，当条件返回 `false` 的时候运行代码 `c`。
            -   以下函数使用 `if/else` 语句来检查条件：
                ```
                 function findGreater(a, b) {
                  if(a > b) {
                    return "a is greater";
                  }
                  else {
                    return "b is greater or equal";
                  }
                }

                ```
            -   这可以使用三元运算符重写：
                ```
                function findGreater(a, b) {
                  return a > b ? "a is greater" : "b is greater or equal";
                }

                ```
            -   示例：在 `checkEqual` 函数中使用三元运算符检查两个数字是否相等。 函数应该返回 `Equal` 或字符串 `Not Equal`。
                    function checkEqual(a, b) {
                      return a===b ? "Equal" : "Not Equal"
                    }

                    checkEqual(1, 2);
        -   [**使用多个三元运算符**](https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-multiple-conditional-ternary-operators "使用多个三元运算符")

            在之前的挑战中，你使用了一个条件运算符。 你也可以将多个运算符串联在一起以检查多种条件。

            下面的函数使用 `if`，`else if` 和 `else` 语句来检查多个条件：
            ```
            function findGreaterOrEqual(a, b) {
              if (a === b) {
                return "a and b are equal";
              }
              else if (a > b) {
                return "a is greater";
              }
              else {
                return "b is greater";
              }
            }

            ```
            以上函数可以使用多个三元运算符重写：
            ```
            function findGreaterOrEqual(a, b) {
              return (a === b) ? "a and b are equal" 
                : (a > b) ? "a is greater" 
                : "b is greater";
            }

            ```
            -   示例

                在 `checkSign` 函数中使用多个三元运算符来检查数字是正数 ("positive")、负数 ("negative") 或零 ("zero")，使用 `findGreaterOrEqual` 里面的建议缩进格式。 函数应返回 `positive`、`negative` 或 `zero`。。 例如：
                    function checkSign(num) {
                      return (num > 0) ? "positive" : (num < 0) ? "negative" : "zero"
                    }

                    checkSign(10);

        -   (练习)[使用递归创建一个倒计时](https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-recursion-to-create-a-countdown "使用递归创建一个倒计时")

            在上一个[挑战](https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/replace-loops-using-recursion "挑战")，学习了怎样用递归来代替 `for` 循环。 现在来学习一个更复杂的函数，函数返回一个从 `1` 到传递给函数的指定数字的连续数字数组。

            正如上一个挑战提到的，会有一个 base case。 base case 告诉递归函数什么时候不再需要调用其自身。 这是简单 情况，返回得到的值。 还有 recursive call，继续用不同的参数调用自身。 如果函数无误，一直执行直到 base case 为止。
            -   比如，如果想写一个递归函数，返回一个数字 `1` 到 `n` 的连续数组。 这个函数需要接收一个参数 `n` 代表最终数字。 然后会持续的调用自身，传入一个比 `n` 更小的值一直到传入的值是 `1` 为止。 函数如下：
                ```
                function countup(n) {
                  if (n < 1) {
                    return [];
                  } else {
                    const countArray = countup(n - 1);
                    countArray.push(n);
                    return countArray;
                  }
                }
                console.log(countup(5));

                ```
                值 `[1, 2, 3, 4, 5]` 将显示在控制台中。
            -   练习
                    function countdown(n){
                      if ( n < 1 ){
                      return [];
                      } else {
                        const num = countdown(n-1);
                        num.unshift(n)
                        return num
                      }
                    }
        -   使用递归来创建一个数字序列

            已经定义好了 `rangeOfNumbers` 函数，包含两个参数。 函数应该返回一个连续数字数组，`startNum` 参数开始 `endNum` 参数截止。 开始的数字小于或等于截止数字。 函数必需递归调用自身，不能使用任意形式的循环。 要考虑到 `startNum` 和 `endNum` 相同的情况。
            -   练习

                函数应该返回一个数组。

                不能包含循环语句（`for` 或者 `while` 或者高阶函数比如 `forEach`、`map`、`filter` 或者 `reduce`）。

                `rangeOfNumbers` 应该使用递归函数（调用自身）来完成这个挑战。

                `rangeOfNumbers(1, 5)` 应该返回 `[1, 2, 3, 4, 5]`。

                `rangeOfNumbers(6, 9)` 应该返回 `[6, 7, 8, 9]`。

                `rangeOfNumbers(4, 4)` 应该返回 `[4]`。
                    function rangeOfNumbers(startNum, endNum) {
                      if ( endNum < startNum ){
                        return [];
                      } else {
                        const num = rangeOfNumbers(startNum, endNum-1);
                        num.push(endNum)
                        return num
                      }
                    }
        -   综合示例：请写一个函数实现 21 点算法。 它根据参数 `card` 的值（见表格，可能是数字或者字符串）来递增或递减全局变量 `count`。 然后函数返回一个由当前 count（计数）和 `Bet`（当 count > 0 时）或 `Hold`（当 count <= 0 时) 拼接的字符串。 注意 count（计数）和玩家的决定（`Bet` 或 `Hold`）之间应该有空格。\[[\[JS\]switch case](<\[JS]switch case_utqFWygNDEmajUBSzTTw9f.md> "\[JS]switch case")]
            ```javascript
            let count = 0;

            function cc(card) {
              // 只修改这一行下面的代码
              
              switch(card){
                case 2:
                case 3:
                case 4:
                case 5:
                case 6:
                  count ++;
                  break;
                case 10:
                case "J":
                case "Q":
                case "K":
                case "A":
                  count --;
                  break;
              }
              if (count > 0){
                return count + " Bet";
              } else {
                return count + " Hold";
              }
              // 只修改这一行上面的代码
            }

            cc(2); cc(3); cc(7); cc('K'); cc('A');
            cc(5)

            ```
            方式二
            ```javascript
            let count = 0;

            function cc(card) {
              // 只修改这一行下面的代码
              var regex = /[JQKA]/;
              if (card > 1 && card < 7){
                count++;
              } else if (card === 10 || regex.test(card)){
                count--;
              }
              if (count > 0){
                return count + " Bet";
              } else {1
                return count + " Hold";
              }

              return "Change Me";
              // 只修改这一行上面的代码
            }

            cc(2); cc(3); cc(7); cc('K'); cc('A');
            ```
    🔳🔳🔳🔳🔳🔳🔳🔳🔳🔳 100%

    进度：[https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/mutate-an-array-declared-with-const](https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/mutate-an-array-declared-with-const "https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/es6/mutate-an-array-declared-with-const")
    -   [x] 比较 var 和 let 关键字的作用域
    -   [x] 改变一个用 const 声明的数组
    -   [x] [防止对象改变 ](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/prevent-object-mutation "防止对象改变 ")
        -   示例：在这个挑战中，你将使用 `Object.freeze` 来防止数学常量被改变。 你需要冻结 `MATH_CONSTANTS` 对象，使得没有人可以改变 `PI` 的值，或增加或删除属性。
            ```react&#x20;jsx
            function freezeObj() {
              const MATH_CONSTANTS = {
                PI: 3.14
              };
              // 只修改这一行下面的代码
              freezeObj = Object.freeze(MATH_CONSTANTS)

              // 只修改这一行上面的代码
              try {
                MATH_CONSTANTS.PI = 99;
              } catch(ex) {
                console.log(ex);
              }
              return MATH_CONSTANTS.PI;
            }
            const PI = freezeObj();
            ```
    -   [x] [使用箭头函数编写简洁的匿名函数](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-arrow-functions-to-write-concise-anonymous-functions "使用箭头函数编写简洁的匿名函数")&#x20;
        -   示例：[使用箭头函数编写简洁的匿名函数](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-arrow-functions-to-write-concise-anonymous-functions "使用箭头函数编写简洁的匿名函数") \[箭头函数,匿名函数]
            ```react&#x20;jsx
            const magic = function() {
              return new Date();
            };
            ```
            ```react&#x20;jsx
            const magic = () => {
              return new Date()
            }

            ```
            ```react&#x20;jsx
            const magic = () => new Date()
            ```
    -   [x] 编写带参数的箭头函数&#x20;
        -   示例：编写带参数的箭头函数：将 `arr2` 的内容添加到 `arr1`。 \[箭头函数]
            ```react&#x20;jsx
            const myConcat = (arr1, arr2) => arr1.concat(arr2);

            console.log(myConcat([1, 2], [3, 4, 5]));
            ```
    -   [x] 设置函数的默认参数
        -   示例： \[参数的默认值]
            ```react&#x20;jsx
            const greeting = (name = "Anonymous") => "Hello " + name;

            console.log(greeting("John"));
            console.log(greeting());

            ```
            ```react&#x20;jsx
            const increment = (number, value=1) => number + value;
            ```
    -   [x] [将 rest 操作符与函数参数一起使用](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-the-rest-parameter-with-function-parameters "将 rest 操作符与函数参数一起使用")
        -   示例：修改 `sum` 函数，使用 rest 参数，使 `sum` 函数可以接收任意数量的参数，并返回它们的总和。`...`rest 操作符
            ```react&#x20;jsx
            const sum = (...args) => {
              // const args = [x, y, z];
              let total = 0;
              for (let i = 0; i < args.length; i++) {
                total += args[i];
              }
              return total;
            }
            ```
    -   [x] [使用 spread 运算符展开数组项](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-the-spread-operator-to-evaluate-arrays-in-place "使用 spread 运算符展开数组项")
        -   示例：使用展开操作符将 `arr1` 中的内容都复制到 `arr2` 中去。：展开数组 `...`Array
            ```react&#x20;jsx
            const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
            let arr2;

            arr2 = [...arr1];  // 修改这一行

            console.log(arr2);
            ```
    -   [x] [使用解构赋值来获取对象的值 ](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-extract-values-from-objects "使用解构赋值来获取对象的值 ")
        -   示例：[使用解构赋值来获取对象的值 ](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-extract-values-from-objects "使用解构赋值来获取对象的值 ")：把两个赋值语句替换成效果相同的解构赋值语句。 `today` 和 `tomorrow` 的值应该还是 `HIGH_TEMPERATURES` 对象中 `today` 和 `tomorrow` 属性的值。 解构赋值
            ```react&#x20;jsx
            const HIGH_TEMPERATURES = {
              yesterday: 75,
              today: 77,
              tomorrow: 80
            };

            // 只修改这一行下面的代码

            // const today = HIGH_TEMPERATURES.today;
            // const tomorrow = HIGH_TEMPERATURES.tomorrow;
            const {today, tomorrow} = HIGH_TEMPERATURES
            // 只修改这一行上面的代码
            ```
    -   [x] [使用解构赋值从对象中分配变量](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-assign-variables-from-objects "使用解构赋值从对象中分配变量")
        -   示例：[使用解构赋值从对象中分配变量](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-assign-variables-from-objects "使用解构赋值从对象中分配变量")：使用解构赋值语句替换两个赋值语句。 将 `HIGH_TEMPERATURES` 的 `today` 和 `tomorrow` 的值赋值给 `highToday` 和 `highTomorrow`。 解构赋值Object
            ```react&#x20;jsx
            const HIGH_TEMPERATURES = {
              yesterday: 75,
              today: 77,
              tomorrow: 80
            };

            // 只修改这一行下面的代码

            // const highToday = HIGH_TEMPERATURES.today;
            // const highTomorrow = HIGH_TEMPERATURES.tomorrow; 
            const {today:highToday,tomorrow:highTomorrow} = HIGH_TEMPERATURES
            console.log(HIGH_TEMPERATURES.tooday)
            // 只修改这一行上面的代码
            ```

    -   [x] [使用解构赋值从嵌套对象中分配变量](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-assign-variables-from-nested-objects "使用解构赋值从嵌套对象中分配变量")
        -   示例：[使用解构赋值从嵌套对象中分配变量](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-assign-variables-from-nested-objects "使用解构赋值从嵌套对象中分配变量")：将两个赋值语句替换成等价的解构赋值。 `lowToday` 和 `highToday` 应该为 `LOCAL_FORECAST` 中 `today.low` 和 `today.high` 的值。解构赋值Object
            ```react&#x20;jsx
            const LOCAL_FORECAST = {
              yesterday: { low: 61, high: 75 },
              today: { low: 64, high: 77 },
              tomorrow: { low: 68, high: 80 }
            };

            // 只修改这一行下面的代码

            // const lowToday = LOCAL_FORECAST.today.low;
            // const highToday = LOCAL_FORECAST.today.high;

            const {
                today:{low:lowToday , high:highToday }
              } = LOCAL_FORECAST
            // 只修改这一行上面的代码
            ```
    -   [x] [使用解构赋值从数组中分配变量](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-assign-variables-from-arrays "使用解构赋值从数组中分配变量")
        -   示例：[使用解构赋值从数组中分配变量](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-assign-variables-from-arrays "使用解构赋值从数组中分配变量")：使用数组解构来交换变量 `a` 与 `b` 的值，使 `a` 接收 `b` 的值，而 `b` 接收 `a` 的值。 解构赋值Array
            ```react&#x20;jsx
            let a = 8, b = 6;
            // 只修改这一行下面的代码
            [b, a] = [a, b]
            ```
    -   [x] 通过 rest 参数解构
        -   示例：解构数组的某些情况下，我们可能希望将剩下的元素放进另一个数组里面。Arrayrest 操作符`...`
            ```react&#x20;jsx
            function removeFirstTwo(list) {
              // 只修改这一行下面的代码
              const [a,b,...shorterList] = list; // 修改这一行
              // 只修改这一行上面的代码
              return shorterList;
            }

            const source = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
            const sourceWithoutFirstTwo = removeFirstTwo(source);
            console.log(sourceWithoutFirstTwo)  // [ 3, 4, 5, 6, 7, 8, 9, 10 ]

            ```
    -   [x] [使用解构赋值将对象作为函数的参数传递](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-pass-an-object-as-a-functions-parameters "使用解构赋值将对象作为函数的参数传递")
        -   示例：[使用解构赋值将对象作为函数的参数传递](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-destructuring-assignment-to-pass-an-object-as-a-functions-parameters "使用解构赋值将对象作为函数的参数传递")：对 `half` 的参数进行解构赋值，仅将 `max` 与 `min` 的值传进函数。 \[解构赋值,Object`{}`]
            ```react&#x20;jsx
            const stats = {
              max: 56.78,
              standard_deviation: 4.34,
              median: 34.54,
              mode: 23.87,
              min: -0.75,
              average: 35.85
            };

            // 只修改这一行下面的代码
            const half = ({max, min}) => (max + min) / 2.0; 
            console.log(half(stats))  // 28.015
            // 只修改这一行上面的代码
            ```
    -   [x] [使用模板字面量创建字符串](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/create-strings-using-template-literals "使用模板字面量创建字符串")
        -   示例：[使用模板字面量创建字符串](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/create-strings-using-template-literals "使用模板字面量创建字符串")：模板字符串(` `` `[)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Template_literals ")")`${}`|`for(a; b; c)``for in``for of`✧[Array](Array_xajeRHY5orWsGcjSKtn8QK.md "Array")
            ```react&#x20;jsx
            [ '<li class="text-warning">no-var</li>',
              '<li class="text-warning">var-on-top</li>',
              '<li class="text-warning">linebreak</li>' ]
            ```
            ```react&#x20;jsx
            const result = {
              success: ["max-length", "no-amd", "prefer-arrow-functions"],
              failure: ["no-var", "var-on-top", "linebreak"],
              skipped: ["no-extra-semi", "no-dup-keys"]
            };
            function makeList(arr) {
              // 只修改这一行下面的代码
              const failureItems = [];
              for(let i=0; i<arr.length; i++){
                failureItems.push(
                  `<li class="text-warning">${arr[i]}</li>`
                )
              }
              // 只修改这一行上面的代码
              return failureItems;
            }

            const failuresList = makeList(result.failure);
            console.log(failuresList)
            ```
            ```react&#x20;jsx
            const result = {
              success: ["max-length", "no-amd", "prefer-arrow-functions"],
              failure: ["no-var", "var-on-top", "linebreak"],
              skipped: ["no-extra-semi", "no-dup-keys"]
            };
            function makeList(arr) {
              // 只修改这一行下面的代码
              const failureItems = [];
              for(let i in arr){
                failureItems.push(
                  `<li class="text-warning">${arr[i]}</li>`
                )
              }
              // 只修改这一行上面的代码
              return failureItems;
            }

            const failuresList = makeList(result.failure);
            console.log(failuresList)
            ```
            ```react&#x20;jsx
            const result = {
              success: ["max-length", "no-amd", "prefer-arrow-functions"],
              failure: ["no-var", "var-on-top", "linebreak"],
              skipped: ["no-extra-semi", "no-dup-keys"]
            };
            function makeList(arr) {
              // 只修改这一行下面的代码
              const failureItems = [];
              for(let i of arr){
                failureItems.push(
                  `<li class="text-warning">${i}</li>`
                )
              }
              // 只修改这一行上面的代码
              return failureItems;
            }

            const failuresList = makeList(result.failure);
            console.log(failuresList)

            ```
    -   [x] [使用简单字段编写简洁的对象字面量声明](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/write-concise-object-literal-declarations-using-object-property-shorthand "使用简单字段编写简洁的对象字面量声明")
        -   示例：[使用简单字段编写简洁的对象字面量声明](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/write-concise-object-literal-declarations-using-object-property-shorthand "使用简单字段编写简洁的对象字面量声明")&#x20;
            ```react&#x20;jsx
            const createPerson = (name, age, gender) => {
              // 只修改这一行下面的代码
              return {
                name: name,
                age: age,
                gender: gender
              };
              // 只修改这一行上面的代码
            };
            ```
            ```react&#x20;jsx
            const createPerson = (name, age, gender) => {
              // 只修改这一行下面的代码
              return {
                name,
                age,
                gender
              };
              // 只修改这一行上面的代码
            };
            ```
    -   [x] [用 ES6 编写简洁的函数声明](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/write-concise-declarative-functions-with-es6 "用 ES6 编写简洁的函数声明")
        -   示例：[用 ES6 编写简洁的函数声明](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/write-concise-declarative-functions-with-es6 "用 ES6 编写简洁的函数声明") \[函数声明]
            ```react&#x20;jsx
            // 只修改这一行下面的代码
            const bicycle = {
              gear: 2,
              setGear: function(newGear) {
                this.gear = newGear;
              }
            };
            // 只修改这一行上面的代码
            bicycle.setGear(3);
            console.log(bicycle.gear);
            ```
            ```react&#x20;jsx
            // 只修改这一行下面的代码
            const bicycle = {
              gear: 2,
              setGear(newGear) {
                this.gear = newGear;
              }
            };
            // 只修改这一行上面的代码
            bicycle.setGear(3);
            console.log(bicycle.gear);
            ```

    -   [x] [使用 class 语法定义构造函数](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-class-syntax-to-define-a-constructor-function "使用 class 语法定义构造函数")
        -   示例：[使用 class 语法定义构造函数](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-class-syntax-to-define-a-constructor-function "使用 class 语法定义构造函数")\[`constructor`构造方法]
            ```react&#x20;jsx
            // 只修改这一行下面的代码

            // 只修改这一行上面的代码

            const carrot = new Vegetable('carrot');
            console.log(carrot.name); // 应该显示 'carrot'
            ```
            ```react&#x20;jsx
            // 只修改这一行下面的代码
            class Vegetable{
              constructor(name){
                this.name = name;
              }
            }
            // 只修改这一行上面的代码

            const carrot = new Vegetable('carrot');
            console.log(carrot.name); // 应该显示 'carrot'
            ```

    -   [x] [使用 getter 和 setter 来控制对象的访问 ](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-getters-and-setters-to-control-access-to-an-object "使用 getter 和 setter 来控制对象的访问 ")
        -   示例：[使用 getter 和 setter 来控制对象的访问 ](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-getters-and-setters-to-control-access-to-an-object "使用 getter 和 setter 来控制对象的访问 ")：使用 `class` 关键字创建一个 `Thermostat` class。 `constructor` 接收一个华氏温度。在 class 中，创建一个 `getter` 来获取摄氏温度和一个 `setter` 来设置温度值。 \[gettersetter]
            ```react&#x20;jsx
            // 只修改这一行下面的代码
            class Thermostat{
              constructor(t){
                this._t = t
              }
              get temperature(){
                return 5/9 * (this._t - 32)
              }
              set temperature(updata){
                this._t = updata * 9.0 / 5 + 32 
              }
            }
            // 只修改这一行上面的代码

            const thermos = new Thermostat(76); // 设置为华氏刻度
            let temp = thermos.temperature; // 24.44 摄氏度
            console.log(temp)   // 24.444444444444446
            thermos.temperature = 26;
            temp = thermos.temperature; // 26 摄氏度
            console.log(temp)   // 26
            ```
    -   [x] [创建一个模块脚本](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/create-a-module-script "创建一个模块脚本")

        起初，JavaScript 几乎只在 HTML web 扮演一个很小的角色。 今天，一切不同了，很多网站几乎全是用 JavaScript 所写。 为了让 JavaScript 更模块化、更整洁以及更易于维护，ES6 引入了在多个 JavaScript 文件之间共享代码的机制。 它可以导出文件的一部分供其它文件使用，然后在需要它的地方按需导入。 为了使用这一功能， 需要在 HTML 文档里创建一个 `type` 为 `module` 的脚本。
        -   示例：[创建一个模块脚本](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/create-a-module-script "创建一个模块脚本") \[模块脚本]
            ```react&#x20;jsx
            <script type="module" src="filename.js"></script>

            ```

    <!---->

    -   示例：假设有一个文件 `math_functions.js`，该文件包含了数学运算相关的一些函数。 其中一个存储在变量 `add` 里，该函数接受两个数字作为参数返回它们的和。 你想在几个不同的 JavaScript 文件中使用这个函数。 要实现这个目的，就需要 `export` 它。 \[`export`✧]
        ```javascript
        export const add = (x, y) => {
          return x + y;
        }
        ```
        上面是导出单个函数常用方法，还可以这样导出：
        ```javascript
        const add = (x, y) => {
          return x + y;
        }

        export { add };
        ```
        导出变量和函数后，就可以在其它文件里导入使用从而避免了代码冗余。 重复第一个例子的代码可以导出多个对象或函数，在第二个例子里面的导出语句中添加更多值也可以导出多项，例子如下：
        ```javascript
        export { add, subtract };
        ```
    -   示例：[用 export 来重用代码块](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use-export-to-share-a-code-block "用 export 来重用代码块") ：编辑框中有两个字符串相关的函数。 选用一种方法导出两个函数。 \[`export`]
        ```react&#x20;jsx
        const uppercaseString = (string) => {
          return string.toUpperCase();
        }

        const lowercaseString = (string) => {
          return string.toLowerCase()
        }
        export {uppercaseString, lowercaseString}
        ```


    <!---->

    -   [x] [通过 import 复用 JavaScript 代码](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/reuse-javascript-code-using-import "通过 import 复用 JavaScript 代码")
        -   示例：[通过 import 复用 JavaScript 代码](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/reuse-javascript-code-using-import "通过 import 复用 JavaScript 代码")：添加 `import` 语句，使当前文件可以使用你在之前课程里导出的 `uppercaseString` 和 `lowercaseString` 函数。 \[`import`]
            ```react&#x20;jsx
            const uppercaseString = (string) => {
              return string.toUpperCase();
            }

            const lowercaseString = (string) => {
              return string.toLowerCase()
            }
            export {uppercaseString, lowercaseString}
            ```
            ```react&#x20;jsx
            import {uppercaseString} from './string_functions.js'
            import {lowercaseString} from './string_functions.js'
            // 只修改这一行上面的代码

            uppercaseString("hello");
            lowercaseString("WORLD!");
            ```

    -   [x] [用 \* 从文件中导入所有内容](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use--to-import-everything-from-a-file "用 * 从文件中导入所有内容")&#x20;
        -   示例：[用 \* 从文件中导入所有内容](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/use--to-import-everything-from-a-file "用 * 从文件中导入所有内容") ：下面的代码需要从同目录下的 `string_functions.js` 文件中导入所有内容。 使用 `import * as` 语法将文件的所有内容导入对象 `stringFunctions`。 \[`import`]
            ```react&#x20;jsx
            import * as stringFunctions from "./string_functions.js";

            // 只修改这一行上面的代码

            stringFunctions.uppercaseString("hello");
            stringFunctions.lowercaseString("WORLD!");
            ```
    -   [x] [用 export default 创建一个默认导出](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/create-an-export-fallback-with-export-default "用 export default 创建一个默认导出")

        在 `export` 的课程中，你学习了命名导出语法， 这可以在其他文件中引用一些函数或者变量。

        还需要了解另外一种被称为默认导出的 `export` 的语法。 在文件中只有一个值需要导出的时候，通常会使用这种语法。 它也常常用于给文件或者模块创建返回值。\[`export default`]

        下面是使用 `export default` 的例子：
        -   示例：[用 export default 创建一个默认导出](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/create-an-export-fallback-with-export-default "用 export default 创建一个默认导出") \[`export default`]
            ```react&#x20;jsx
            export default function add(x, y) {
              return x + y;
            }

            export default function(x, y) {
              return x + y;
            }

            ```
            `export default` 用于为模块或文件声明一个返回值，在每个文件或者模块中应当只默认导出一个值。 此外，你不能将 `export default` 与 `var`、`let` 或 `const` 同时使用。
    -   [x] [导入一个默认的导出](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/import-a-default-export "导入一个默认的导出")
        -   示例：[导入一个默认的导出](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/import-a-default-export "导入一个默认的导出") \[`export default`]
            ```react&#x20;jsx
            import add from "./math_functions.js";

            ```
            这个语法有一处特别的地方， 被导入的 `add` 值没有被花括号（`{}`）所包围。 `add` 只是一个变量的名字，对应 `math_functions.js` 文件的任何默认导出值。 在导入默认导出时，可以使用任何名字。
    -   [x] 创建一个 JavaScript Promise
        -   示例1：创建一个 JavaScript Promise \[`Promise()`]
            ```react&#x20;jsx
            const promise = new Promise((resolve, reject) => {
              // 异步操作的代码
              // 可以是一个网络请求、文件读取等异步操作
              // 当异步操作完成时，调用 resolve 或 reject 函数
            });

            promise.then((result) => {
              // 当异步操作成功时，调用 then 方法的回调函数
            }).catch((error) => {
              // 当异步操作失败时，调用 catch 方法的回调函数
            });
            ```
    -   [x] [通过 resolve 和 reject 完成 Promise](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/complete-a-promise-with-resolve-and-reject "通过 resolve 和 reject 完成 Promise")
        -   示例2：[通过 resolve 和 reject 完成 Promise](https://www.freecodecamp.org/chinese/learn/javascript-algorithms-and-data-structures/es6/complete-a-promise-with-resolve-and-reject "通过 resolve 和 reject 完成 Promise") \[`Promise()`]

            Promise 有三个状态：`pending`、`fulfilled` 和 `rejected`。 上一个挑战里创建的 promise 一直阻塞在 `pending` 状态里，因为没有调用 promise 的完成方法。 Promise 提供的 `resolve` 和 `reject` 参数就是用来结束 promise 的。 Promise 成功时调用 `resolve`，promise 执行失败时调用 `reject`， 如下文所述，这些方法需要有一个参数。
            ```react&#x20;jsx
            const myPromise = new Promise((resolve, reject) => {
              if(condition here) {
                resolve("Promise was fulfilled");
              } else {
                reject("Promise was rejected");
              }
            });
            ```
        -   示例3： promise 可以处理成功和失败情况。 如果 `responseFromServer` 是 `true`，调用 `resolve` 方法使 promise 成功。 给 `resolve` 传递值为 `We got the data` 的字符串。 如果 `responseFromServer` 是 `false`， 使用 `reject` 方法并传入值为 `Data not received` 的字符串。 `Promise()`
            ```react&#x20;jsx
            const makeServerRequest = new Promise((resolve, reject) => {
              // responseFromServer 表示 模拟从服务器获得一个响应
              let responseFromServer;

              if(responseFromServer) {
                resolve('We got the data')
              } else {  
                reject('Data not received')
              }
            });
            ```
    -   [x] 用 then 处理 Promise 完成的情况
        -   示例4：当程序需要花费未知的时间才能完成时（比如一些异步操作），一般是服务器请求，promise 很有用。 服务器请求会花费一些时间，当结束时，需要根据服务器的响应执行一些操作。 这可以用 `then` 方法来实现， 当 promise 完成 `resolve` 时会触发 `then` 方法。 例子如下： \[`Promise()``then()`]
            ```react&#x20;jsx
            myPromise.then(result => {  // result 即传入 resolve 方法的参数

            }); 

            ```
            给 promise 添加 `then` 方法。 用 `result` 做为回调函数的参数并将 `result` 打印在控制台。
            ```react&#x20;jsx
            const makeServerRequest = new Promise((resolve, reject) => {
              // responseFromServer 设置为 true，表示从服务器获得有效响应
              let responseFromServer = true;

              if(responseFromServer) {
                resolve("We got the data");
              } else {  
                reject("Data not received");
              }
               makeServerRequest.then(result => {
                console.log(result) 
              });
            });
            ```
    -   [x] 使用 catch 处理 Promise 失败的情况
        -   示例5：给 promise 添加 `catch` 方法。 用 `error` 作为回调函数的参数，并把 `error` 打印到控制台。 \[`catch()`]
            ```react&#x20;jsx
            const makeServerRequest = new Promise((resolve, reject) => {
              // responseFromServer 设置为 false，表示从服务器获得无效响应
              let responseFromServer = false;

              if(responseFromServer) {
                resolve("We got the data");
              } else {  
                reject("Data not received");
              }
            });

            makeServerRequest.then(result => {
              console.log(result);
            }).catch((error) => {
              console.log(error)
            });
            ```

    <!---->

    -   [ ] 正则表达式
    -   [ ] 调试
    -   [ ] 基础数据结构
    -   [ ] 基础算法
    -   [ ] 面向对象编程
    -   [ ] 函数式编程
    -   [ ] 中级算法
    -   [ ] JavaScript 算法和数据结构项目


