# Python

## 输入与输出

### 输入

```python
# 多个数字
x, y = list(map(int, input().split()))
```

注：当读取到 EOF 时，则触发 EOFError。

### 输出

```python
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```

输出格式

## 常用内置函数

```python
abs(x)
all(iterable)
any(iterable)
max(iterable, *[, key, default])
max(arg1, arg2, *args[, key])
min(iterable, *[, key, default])
min(arg1, arg2, *args[, key])
pow(base, exp[, mod])
round(number[, ndigits])
sum(iterable, /, start=0)

chr(i)           # 返回 Unicode 码位为整数 i 的字符的字符串格式。例如，chr(97) 返回字符串 'a'。
ord(c)           # 对表示单个 Unicode 字符的字符串，返回代表它 Unicode 码点的整数。例如 ord('a') 返回整数 97。
float([x])       # 返回从数字或字符串 x 生成的浮点数。
int([x])         # 返回一个基于数字或字符串 x 构造的整数对象，或者在未给出参数时返回 0。
int(x, base=10)
bin(x)           # 将一个整数转变为一个前缀为“0b”的二进制字符串。
hex(x)           # 将整数转换为以“0x”为前缀的小写十六进制字符串。
oct(x)           # 将一个整数转变为一个前缀为“0o”的八进制字符串。

len(s)
range(stop)
range(start, stop[, step])
reversed(seq)
sorted(iterable, *, key=None, reverse=False)
zip(*iterables)
```

## 字符串

### 常量

```python
string.ascii_letters
string.ascii_lowercase
string.ascii_uppercase
string.digits
string.hexdigits
string.octdigits
string.punctuation
string.printable
string.whitespace
```

### 格式化

[Python DOCS: Format Strings](https://docs.python.org/zh-cn/3/library/string.html#formatstrings)

语法

```BNF
replacement_field ::=  "{" [field_name] ["!" conversion] [":" format_spec] "}"
field_name        ::=  arg_name ("." attribute_name | "[" element_index "]")*
arg_name          ::=  [identifier | digit+]
attribute_name    ::=  identifier
element_index     ::=  digit+ | index_string
index_string      ::=  <any source character except "]"> +
conversion        ::=  "r" | "s" | "a"
format_spec       ::=  <described in the next section>
```

format_spec

```
format_spec     ::=  [[fill]align][sign][#][0][width][grouping_option][.precision][type]
fill            ::=  <any character>
align           ::=  "<" | ">" | "=" | "^"
sign            ::=  "+" | "-" | " "
width           ::=  digit+
grouping_option ::=  "_" | ","
precision       ::=  digit+
type            ::=  "b" | "c" | "d" | "e" | "E" | "f" | "F" | "g" | "G" | "n" | "o" | "s" | "x" | "X" | "%"
```

转换

```python
'{!s}'  # str()
'{!r}'  # repr()
'{!a}'  # ascii()
```

数字格式

```python
'{:03.14}'
```

### 常用接口

## 列表

### 常用接口

```python
# 在列表的末尾添加一个元素。相当于 a[len(a):] = [x] 。
list.append(x)

# 使用可迭代对象中的所有元素来扩展列表。相当于 a[len(a):] = iterable 。
list.extend(iterable)

# 在给定的位置插入一个元素。第一个参数是要插入的元素的索引，所以 a.insert(0, x) 插入列表头部， a.insert(len(a), x) 等同于 a.append(x) 。
list.insert(i, x)

# 移除列表中第一个值为 x 的元素。如果没有这样的元素，则抛出 ValueError 异常。
list.remove(x)

# 删除列表中给定位置的元素并返回它。如果没有给定位置，a.pop() 将会删除并返回列表中的最后一个元素。（ 方法签名中 i 两边的方括号表示这个参数是可选的，而不是要你输入方括号。你会在 Python 参考库中经常看到这种表示方法)。
list.pop([i])

# 移除列表中的所有元素。等价于``del a[:]``
list.clear()

# 返回列表中第一个值为 x 的元素的从零开始的索引。如果没有这样的元素将会抛出 ValueError 异常。
# 可选参数 start 和 end 是切片符号，用于将搜索限制为列表的特定子序列。返回的索引是相对于整个序列的开始计算的，而不是 start 参数。
list.index(x[, start[, end]])

# 返回元素 x 在列表中出现的次数。
list.count(x)

# 对列表中的元素进行排序
## 原地排序
list.sort(key=None, reverse=False)
## 非原地排序
sorted(iterable, *, key=None, reverse=False)

# 翻转列表中的元素。
list.reverse()

# 返回列表的一个浅拷贝，等价于 a[:]。
list.copy()

```

### 栈、队列

## 字典

## 集合
