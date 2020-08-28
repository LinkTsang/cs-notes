# JavaScript

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