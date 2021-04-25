# JavaScript

- [JavaScript](#javascript)
  - [Number](#number)
    - [属性](#属性)
    - [方法](#方法)
    - [Prototype 实例](#prototype-实例)
    - [数值转换技巧](#数值转换技巧)
  - [Math](#math)
  - [String](#string)
    - [Prototype](#prototype)
  - [Array](#array)
    - [prototype](#prototype-1)
      - [修改原数组](#修改原数组)
      - [不修改原数组](#不修改原数组)
      - [迭代](#迭代)
    - [例子](#例子)
      - [复制数组](#复制数组)
  - [Map](#map)
    - [Object 对比](#object-对比)
    - [prototype](#prototype-2)
  - [Set](#set)
    - [prototype](#prototype-3)


## Number
双精度IEEE 754 64位浮点
64 = 1 + 11 + 52

### 属性
```javascript
Number.EPSILON // 2^-52
Number.MAX_SAFE_INTEGER // 2^53 - 1
Number.MAX_VALUE
Number.MIN_SAFE_INTEGER // 
Number.MIN_VALUE
Number.NaN
Number.NEGATIVE_INFINITY
Number.POSITIVE_INFINITY
```

### 方法
```
Number.isNaN()
Number.isFinite()
Number.isInteger()
Number.isSafeInteger()
Number.parseFloat()
Number.parseInt()
```

### Prototype 实例
```javascript
toPrecision(precision) // precision /in [1, 100]
toExponential(fractionDigits) // fractionDigits /in [0, 20]
toFixed(digits) // digits /in [0, 20]
toString([radix])  // radix /in [2, 36]
```


### 数值转换技巧
```javascript
let n = +s;
```

## Math
```javascript
abs(x)
pow(x, y)
sqrt(x)
sign(x)
max(…x)
min(…x)
round(x)
floor(x)
ceil(x)
trunc(x)

random() => [0, 1)
```

## String
immutable string

### Prototype
```javascript
length
.[N]

charAt(index) => string // out of range => ""
charCodeAt(pos) => 2 bytes UTF-16 number // out of range => NaN
codePointAt(pos) => Unicode point number, supports 4 bytes // out of range => NaN
[@@iterator]() // string[Symbol.iterator]()

includes(searchString[, position]) => boolean
startsWith(searchString[, position]) => boolean
endsWith(searchString[, length]) => boolean

indexOf() => index | -1
lastIndexOf() => index | -1
search(regexp) => index | -1
match(regexp) => groups | undefined, index, input
replace(regexp|substr, newSubStr|function) => String
replaceAll(regexp|substr, newSubStr|function) => String

function replacer(match, p1, p2, ..., offset, string /* source string */, NamedCaptureGroup);


padStart(targetLength [, padString]) => String // default padString=" "(U+0020)
padEnd(targetLength [, padString]) => String // default padString=" "(U+0020)

repeat(count) => String // count /in [0, +Inf]
split([separator[, limit]]) => Array
slice(beginIndex[, endIndex]) => String // supports negative index
substring(indexStart[, indexEnd]) => String // not supports negative index

trim() => string
trimStart() => string
trimLeft() => string
trimEnd() => string
trimRight() => string


toLocaleLowerCase() => string
toLocaleUpperCase() => string
toLowerCase() => string
toUpperCase() => string

concat(str2, [, ...strN]) => new string // use +, += instead

// For integrity only
substr(start[, length]) // Deprecated
localeCompare(compareString[, locales[, options]]) => -1 | 0 | 1
quote()
normalize() => string
toSource() => string
toString() => string
valueOf() => string

```

## Array
```javascript
new Array(element0, element1[, ...[, elementN]])
new Array(arrayLength)

length => number

Array.from(iterable) => Array
Array.isArray(v) => true/false (typeof [] === 'object')
Array.of(element…) => Array
```


### prototype

#### 修改原数组

```javascript
push(x…) => new length
pop() => element
shift() => element
unshift(x…) => new length
splice(start[, deleteCount[, item1[, item2[, ...]]]]) => [deleted elements]

sort([cmp]) => array // inplace
reverse() => array // inplace
```

#### 不修改原数组
```javascript
join([separator]) => string

slice([begin[, end]]) => shallow copy string // support negative index

includes(x) => true/false
indexOf(x) => -1/index
laseIndexOf(x) -1/index

concat(x…) => new array // out of space
```

#### 迭代
```javascript
forEach(callback(currentValue [, index [, array]])[, thisArg])
entries()
keys()
values()
[@@iterator]()

every(callback(element[, index[, array]])[, thisArg]) => boolean
some(callback(element[, index[, array]])[, thisArg])  => boolean
filter(callback(element[, index[, array]])[, thisArg])=> array

find() => element/undefined
findIndex() => index/-1

map(function callback(currentValue[, index[, array]]) {
 // Return element for new_array 
}[, thisArg])
reduce(callback(accumulator, currentValue[, index[, array]])[, initialValue]) => value
reduceRight(callback(accumulator, currentValue[, index[, array]])[, initialValue]) => value
```

### 例子
#### 复制数组

浅拷贝
```javascript
arr.slice()
[…arr]
```


## Map
### Object 对比
- Object 的键只能是 整数、字符串、Symbol，不保证元素插入顺序

>Most Browsers iterate object properties as:
>	1. Integer keys in ascending order (and strings like "1" that parse as ints)
>	2. String keys, in insertion order (ES2015 guarantees this and all browsers comply)
>	3. Symbol names, in insertion order (ES2015 guarantees this and all browsers comply)

来自 <https://stackoverflow.com/questions/5525795/does-javascript-guarantee-object-property-order> 



- Map 对象保存键值对，并且能够记住键的原始插入顺序。
键的比较是基于 sameValueZero 算法
虽然 `NaN !== NaN`， 但是 `NaN` 作为 Map 的键来说是没有区别的

```javascript
new Map([iterable])
length=0
```
### prototype

```javascript
size
clear()

get(key) => value/undefined
set(key, value) => map
delete(key)  => true/false
has(key)  => true/false

keys() => Iterator[[key]]
values() => Iterator[[value]]
entries() => Iterator[[key, value]]
[@@iterator]()  => Iterator[[key, value]]

forEach(callback[, thisArg])
```

## Set
按插入顺序

```
new Set([iterable])
```

### prototype

```javascript
size

add(value) => set
clear()
delete(value) => true/false
has(value) => true/false
```


```javascript
entries() => Iterator[[value, value]]
keys() => Iterator[value]
values() => Iterator[value]
[@@iterator]()  => Iterator[value]
```