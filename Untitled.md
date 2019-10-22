

```python
fib = lambda x : 1 if x <= 2 else fib(x - 1) + fib(x - 2)
fib(31)
```




    1346269




```python
n=4
for i in range(n):
    k = k+1
print(k)
```

    8
    


```python
n = int(input())
k = 0
for i in range(n):
    k = k+int(input())
print(k)
```

    3
    1
    2
    3
    6
    


```python
x = [1, 2, 3]
```


```python
print(id(x))
```

    2444651377224
    


```python
print(id([1, 2, 3]))
```

    2444650494984
    


```python
y = x
print(id(y))
```

    2444651377224
    


```python
x = [1, 2, 3]
y = x
y.append(4)

s = "123"
t = s
t = t + "4"

print(str(x) + " " + s)
```

    [1, 2, 3, 4] 123
    


```python
ans = []
objects = [1, 2, 1, 2, 3]

for x in objects:
    if x not in ans:
        ans.append(x)
               
print(len(ans))
```

    3
    


```python
objects = [1, 2, 1, 2, 3]
len(set(map(id, objects)))
```




    3




```python
def closest_mod_5 (x):    
        while x%5 != 0:             
            x = x+1
        return x
        
print(closest_mod_5(12))
```

    15
    


```python
def printab(a, b):
    print(a)
    print(b)
    
lst = [10, 20]
printab(*lst)
```

    10
    20
    


```python
def printab(a, b, **kwargs):
    print ('positional arguments a ', a)
    print ('positional arguments b ', b)
    print ('positional arguments  ')
    for key in kwargs:
        print(key, kwargs[key])
        
printab(3, 4, c = 20, d = 40, jimmy = 123)
```

    positional arguments a  3
    positional arguments b  4
    positional arguments  
    c 20
    d 40
    jimmy 123
    


```python
vs = (10, 10)
for v in vs:
        print(v)
```

    10
    10
    


```python
def s(a, *vs, b=10):
    res = a + b
    print(res)
    for v in vs:
        res += v
    return res
```


```python
def fib(x):
    if x == 0 or x == 1:
        return 1
    else:
        return fib(x-1) + fib(x-2)
print(fib(6))
```

    13
    


```python
n, k = map(int, input().split())

def combination(n, k):
    if k > n:
        return 0
    elif k == 0 or n == k:
        return 1                  
    elif n == 3 and k == 2:      
        return 3
        
    else:
        return combination(n - 1, k) + combination(n - 1, k - 1)
y = combination(n, k)
print(y)
```

    6 2
    15
    


```python
import math

n2, k2 = map(int, input().split())
def combination2(n2, k2):
    a = math.factorial(n2-k2)
    b = math.factorial(k2)
    c = math.factorial(n2)
    return c/(a*b)
print(int(combination2(n2, k2)))
```

    6 2
    15
    


```python
class Counter:
    def __init__(self, start = 10): #конструктор
        self.count = start

x = Counter(11)
y = Counter()
print(x.count)

x.count +=1
print(x.count)
print(y.count)
```

    11
    12
    10
    


```python
class Counter:
    def __init__(self):
        self.count = 0
    def inc(self):
        self.count += 1
    def reset(self):
        self.count = 0
```


```python
x = Counter()       
x.inc()
x.inc()
print(x.count)
```

    2
    


```python
class MoneyBox:
    def __init__(self, capacity=0):
        self.capacity = capacity
        self.count = 0

    def can_add(self, v):
        
        if self.capacity - self.count>= v:
            return True
        else: 
            return False        

    def add(self, v):
        
        if self.can_add(v):
            self.count += v
```


```python
c = MoneyBox(10)
c.add(6)
c.add(4)
c.count
```




    10




```python
class Buffer:
    def __init__(self):
        self.count = []        
    def add(self, *a):        
        self.a = list(a)
        self.count = self.count + (self.a)
        while len(self.count)>=5:
            summ = sum(self.count[0:5])
            print(summ)
            self.count = self.count[5:]                       
    def get_current_part(self):
        return self.count
        
```


```python
buf = Buffer()
buf.add(1, 2, 3)
buf.get_current_part() # вернуть [1, 2, 3]
buf.add(4, 5, 6) # print(15) – вывод суммы первой пятерки элементов
buf.get_current_part() # вернуть [6]
buf.add(7, 8, 9, 10) # print(40) – вывод суммы второй пятерки элементов
buf.get_current_part() # вернуть []
buf.add(1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1) # print(5), print(5) – вывод сумм третьей и четвертой пятерки
buf.get_current_part() # вернуть [1]
```

    15
    40
    5
    5
    




    [1]




```python
class A:
    val = 1

    def foo(self):
        A.val += 2
        print(str(A.val) + 'foo')

    def bar(self):
        self.val += 1
        print(str(self.val) + 'bar')


a = A()
b = A()

a.bar()
a.foo()
b.foo()
c = A()

print(a.val)
print(b.val)
print(c.val)
```

    2bar
    3foo
    5foo
    2
    5
    5
    


```python
class A:
    val = 0
    def __init__(self):
        self.val = 1

    def foo(self):
        A.val += 2
        print(str(A.val) + 'foo')

    def bar(self):
        self.val += 1
        print(str(self.val) + 'bar')


a = A()
b = A()

a.bar()
a.foo()
b.foo()
c = A()

print(a.val)
print(b.val)
print(c.val)
print(A.val)
```

    2bar
    2foo
    4foo
    2
    1
    1
    4
    


```python
song1 = Song('1234', '4567')
song1.add_tags('A', 'B')

song2 = Song('qqq', 'www')
song1.add_tags('C', 'D')

song2.tags
```




    ['A', 'B', 'C', 'D', 'A', 'B', 'C', 'D']




```python
class myList(list):
    def even_length(self):
        return len(self) % 2 == 0
    
x = myList()
print(x)
x.extend([1, 2, 3, 4, 5])
print(x)
print(x.even_length())
x.append(6)
print(x.even_length())
```

    []
    [1, 2, 3, 4, 5]
    False
    True
    


```python
class D:
    pass
class E: pass
class B(D, E): pass
class C: pass
class A(B, C): pass

print(A.mro())
```

    [<class '__main__.A'>, <class '__main__.B'>, <class '__main__.D'>, <class '__main__.E'>, <class '__main__.C'>, <class 'object'>]
    


```python
class A:
    pass

class B(A):
    pass

class C:
    pass

class D(C):
    pass

class E(B, D, C):
    pass

print (E.mro())
```

    [<class '__main__.E'>, <class '__main__.B'>, <class '__main__.A'>, <class '__main__.D'>, <class '__main__.C'>, <class 'object'>]
    


```python
class A:
    def foo(self):
        print("A")

class B(A):
    pass

class C(A):
    def foo(self):
        print("C")

class D:
    def foo(self):
        print("D")

class E(B, C, D):
       pass

E().foo()
print (E.mro())
```

    C
    [<class '__main__.E'>, <class '__main__.B'>, <class '__main__.C'>, <class '__main__.A'>, <class '__main__.D'>, <class 'object'>]
    


```python
b = {}
b['C'] = []
b['C'].extend([1, 2])
b
```




    {'C': [1, 2]}




```python
def xyz(a, b):
    print(a)
    print(b)
    print(a*b)
    return a * b
y = [1, 2]
a = list(map(lambda x: xyz(x, y), y))
a
```

    1
    [1, 2]
    [1, 2]
    2
    [1, 2]
    [1, 2, 1, 2]
    




    [[1, 2], [1, 2, 1, 2]]




```python
def xyz(a):
    print(a)
    print(a*2)
    return a * 2
y = [1, 2]
a = list(map(lambda x: xyz(x), y))
a
```

    1
    2
    2
    4
    




    [2, 4]




```python
class EvenLengthMixin:
    def even_length(self):
        return len(self) % 2 == 0
    
class MyList(list, EvenLengthMixin):
    def pop(self):
        x = super(MyList, self).pop()
        print('last value is ', x)
        return x
    
ml = MyList([1, 2, 3])
z = ml.pop()
```

    last value is  3
    


```python
n = int(input())

parents = {}
for _ in range(n):
    a = input().split()
    parents[a[0]] = [] if len(a) == 1 else a[2:]

def is_parent(child, parent):
    return child == parent or any(map(lambda p: is_parent(p, parent), parents[child]))

q = int(input())
for _ in range(q):
    a, b = input().split()
    print("Yes" if is_parent(b, a) else "No")
```

    2
    A : B
    B : A
    2
    A B
    Yes
    B A
    Yes
    


```python
class ExtendedStack(list):
    
#     def __init__(self, spoil = 1):
#         self.spoil = spoil
        
    def sum(self):
        spoil = 1
        self.append(self.pop() + self.pop() - spoil)
        return self

    def sub(self):
        self.append(self.pop() - self.pop())

    def mul(self):
        self.append(self.pop() * self.pop())

    def div(self):
        self.append(self.pop() // self.pop())
        
k = [1, 2, 3]
ls = ExtendedStack(k)
s = ls.sum()
print(s)
```

    [1, 4]
    


```python
import time

class Loggable:
    def log(self, msg):
        print(str(time.ctime()) + ": " + str(msg))
        
class LoggableList(list, Loggable):
    
    def append(self, msg):
        #super(LoggableList, self).append(msg)
        list.append(self, msg)
        self.log(msg)
        
        
c = LoggableList()
c.append(3)
```


```python
k = [1, 2, 3]
g = list.append(k, 3)
print(k)
```

    [1, 2, 3, 3]
    


```python
def f(x,y):
    try:
        return x/y
    except TypeError:
        print('TypeError')
    except ZeroDivisionError:
        print('Zero division')
f(5, 0)
```

    Zero division
    


```python
def f(x,y):
    try:
        return x/y
    except (TypeError, ZeroDivisionError) as e:
        print(type(e))
        print(e)
        print(e.args)

f(5, 0)
f(5, [])
```

    <class 'ZeroDivisionError'>
    division by zero
    ('division by zero',)
    <class 'TypeError'>
    unsupported operand type(s) for /: 'int' and 'list'
    ("unsupported operand type(s) for /: 'int' and 'list'",)
    


```python
try:
    foo()
except ZeroDivision:
    print("ZeroDivision")
except ArithmeticError:
    print("ArithmeticError")
except AssertionError:
    print("AssertionError")
```


```python
class BadName (Exception):
    pass

def greet(name):
    if name[0].isupper():
        return 'Hello ' + name
    else:
        raise BadName('for ' + name + ' you need a capital letter '+ "'" +name[0].upper() + "'")
        
print(greet('Denis'))       
print(greet('denis'))
```

    Hello Denis
    


    ---------------------------------------------------------------------------

    BadName                                   Traceback (most recent call last)

    <ipython-input-4-d349e70295e0> in <module>
          9 
         10 print(greet('Denis'))
    ---> 11 print(greet('denis'))
    

    <ipython-input-4-d349e70295e0> in greet(name)
          6         return 'Hello ' + name
          7     else:
    ----> 8         raise BadName('for ' + name + ' you need a capital letter '+ "'" +name[0].upper() + "'")
          9 
         10 print(greet('Denis'))
    

    BadName: for denis you need a capital letter 'D'



```python
def greet(name):
    if name[0].isupper():
        return 'Hello, ' + name
    else:
        raise ValueError('for ' + name + ' you need a capital letter '+ "'" +name[0].upper() + "'")
        
while True:
    try:
        name = input('Please enter your name: ')
        greeting = greet(name)
        print(greeting)
    except ValueError:
        print('try again please using capital letter for: ' + name[0])
    else: 
        break
```

    Please enter your name: denis
    try again please using capital letter for: d
    Please enter your name: Denis
    Hello Denis
    


```python
class NonPositiveError(Exception):
    pass
    
class PositiveList(list):
    def append(self, x):  
        if x>0:           
            super(PositiveList, self).append(x)
        else:
            raise NonPositiveError
            
a = PositiveList()
a.append(-4)
a                  
```


    ---------------------------------------------------------------------------

    NonPositiveError                          Traceback (most recent call last)

    <ipython-input-16-9ddb7ba59e7e> in <module>
         10 
         11 a = PositiveList()
    ---> 12 a.append(-4)
         13 a
    

    <ipython-input-16-9ddb7ba59e7e> in append(self, x)
          7             super(PositiveList, self).append(x)
          8         else:
    ----> 9             raise NonPositiveError
         10 
         11 a = PositiveList()
    

    NonPositiveError: 



```python
from datetime import datetime, timedelta
a = datetime(2010, 12, 12)
b = timedelta(days=1, hours=2, seconds=15)
str(a)
str(a+b)
```




    '2010-12-13 02:00:15'




```python
from datetime import datetime, timedelta

year, month, day  = map(int, input().split())
delta = int(input())

datetime = datetime(year, month,day)
deltadays = timedelta(days = delta)
dateFinal = datetime + deltadays
print(dateFinal.year, dateFinal.month, dateFinal.day)
```

    2016 10 10
    10
    2016 10 20
    


```python
import datetime

y, m, d = map(int, input().split())
days = int(input())

current = datetime.date(year=y, month=m, day=d)
current += datetime.timedelta(days=days)

print("{a} {b} {c}".format(a = current.year, b = current.month, c = current.day))
```

    2019 10 10
    20
    2019 10 30
    


```python

```


```python
from simplecrypt import decrypt, DecryptionException


with open(r'C:\Users\denis.gorev\Desktop\life\stepik\encrypted.bin', 'rb') as inp:
    encrypted = inp.read()
with open(r'C:\Users\denis.gorev\Desktop\life\stepik\passwords.txt', 'r') as tx:
    passwords = tx.read()
for p in passwords.split():
    try:
        s = decrypt(p, encrypted)
    except DecryptionException:
        print('not this password')
    else:
        print(s) 
```

    not this password
    not this password
    not this password
    not this password
    b'Alice loves Bob'
    not this password
    not this password
    not this password
    not this password
    not this password
    


```python
lst = [1, 2, 3, 4, 5]
book = {
    'title':'The langoliers',
    'author':'Stephen King',
    'year published':1990
}
string = 'Hello world'

for i in book:
    print(i)
    
it = iter(book)
while True:
    try:
        i = next(it)
        print(i)
    except StopIteration:
        break
```

    title
    author
    year published
    title
    author
    year published
    


```python
from random import random

class RandomIterator:
    
    def __iter__(self):
        return self
    
    def __init__ (self, k):
        self.k = k
        self.i = 0
        
    def __next__ (self):
        if self.k > self.i:
            self.i+=1
            return random()
        else:
            raise StopIteration
    
k = int(input())   

for x in RandomIterator(k):
    print(x)
# x = RandomIterator(k)
# print(next(x))

# try:
#     i = next(x)
#     print(i)
# except StopIteration:
#     print("that's it")
```

    4
    0.4024101008576757
    0.8665737030315663
    0.5532812594556754
    0.8475140203385976
    


```python
class DoubleElementListIterator:   
    
    def __init__ (self, lst):
        self.lst = lst
        self.i = 0
        
    def __next__ (self):
        if len(self.lst) > self.i:
            self.i+=2
            return self.lst[self.i - 2], self.lst[self.i - 1]
        else:
            raise StopIteration
            
class MyList(list):
    def __iter__(self):
        return DoubleElementListIterator(self)
    
for pair in MyList([1, 2, 3, 4]):
    print(pair)
```

    (1, 2)
    (3, 4)
    


```python
def random_generator(k):
    for i in range(k):
        yield random()

gen = random_generator(4)
for i in gen:
    print(i)
```

    0.5498793921521826
    0.7972204239695131
    0.08146132323627309
    0.5014053186418486
    


```python
class multifilter:
    def judge_half(pos, neg):
        return pos >=neg
        # допускает элемент, если его допускает хотя бы половина фукнций (pos >= neg)

    def judge_any(pos, neg):
        return pos >= 1
        # допускает элемент, если его допускает хотя бы одна функция (pos >= 1)

    def judge_all(pos, neg):
        neg == 0
        # допускает элемент, если его допускают все функции (neg == 0)

    def __init__(self, iterable, *funcs, judge=judge_any):
        self.iterable = iterable
        self.funcs = funcs
        self.judge = judge

    def __iter__(self):
        for i in self.iterable:
            pos = 0
            neg = 0
            for func in self.funcs:
                if func(i):
                    pos += 1
                else:
                    neg += 1
            if self.judge(pos, neg):
                yield i                     
        # возвращает итератор по результирующей последовательности
        
def mul2(x):
    return x % 2 == 0

def mul3(x):
    return x % 3 == 0

def mul5(x):
    return x % 5 == 0


a = [i for i in range(31)] # [0, 1, 2, ... , 30]

print(list(multifilter(a, mul2, mul3, mul5))) 
# [0, 2, 3, 4, 5, 6, 8, 9, 10, 12, 14, 15, 16, 18, 20, 21, 22, 24, 25, 26, 27, 28, 30]

print(list(multifilter(a, mul2, mul3, mul5, judge=multifilter.judge_half))) 
# [0, 6, 10, 12, 15, 18, 20, 24, 30]

print(list(multifilter(a, mul2, mul3, mul5, judge=multifilter.judge_all))) 
# [0, 30]
```

    [0, 2, 3, 4, 5, 6, 8, 9, 10, 12, 14, 15, 16, 18, 20, 21, 22, 24, 25, 26, 27, 28, 30]
    [0, 6, 10, 12, 15, 18, 20, 24, 30]
    []
    


```python
import math
def fac(i):
    return (math.factorial(i-1)+1)%i == 0 and i != 1 and i>0

fac(4)
```




    False




```python
(math.factorial(4-1)+1)%4 == 0
```




    False




```python

```


```python

```


```python
import math
import itertools

def primes():
    i = 2
    while True:
        if (math.factorial(i-1)+1)%i == 0 and i != 1 and i>0:
            yield i
        i = i+1
        

print(list(itertools.takewhile(lambda x: x <= 31, primes())))
```

    [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31]
    


```python
with open('test.txt', 'r') as tx, open('test_copy.txt', 'w') as tx_copy:
    for line in tx:
        #line = line.rstrip()
        print(line)
```

    First line
    
    Second line
    
    Third line
    


```python
with open('test.txt', 'r') as tx, open('test_copy.txt', 'w') as tx_copy:
    for line in tx:
        tx_copy.write(line)

#         line = line.rstrip()
#         print(line)


```


```python
l = []
with open('dataset_24465_4.txt', 'r') as ts, open('task_ext.txt','w') as ext:

    for line in ts:     
        l.append(line.rstrip())
    l = l[::-1]
    content = '\n'.join(l)
    ext.write(content)
        



```


```python
import os
import os.path
```


```python
print(os.listdir())
print(os.getcwd())
#print(os.listdir(r'C:\Users\denis.gorev\Desktop\life'))

print(os.path.exists('test.txt'))
print(os.path.exists('tests.txt'))

print(os.path.isfile('test.txt'))
print(os.path.isdir(r'C:\Users\denis.gorev\Desktop\life\Stepik'))
```

    ['.ipynb_checkpoints', 'dataset_24465_4.txt', 'encrypted.bin', 'module2', 'passwords.txt', 'task_ext.txt', 'test.txt', 'test_copy.txt', 'Untitled.ipynb']
    C:\Users\denis.gorev\Desktop\life\stepik
    True
    False
    True
    True
    


```python
print(os.path.abspath('test.txt'))
```

    C:\Users\denis.gorev\Desktop\life\stepik\test.txt
    


```python
os.chdir(r'C:\Users\denis.gorev\Desktop\life\stepik\module2')
print(os.listdir())
```

    ['comprehension.py', 'files.py', 'files_append.py', 'files_write.py', 'generators.py', 'iterating.py', 'iteration.py', 'lst.py', 'operators.py', 'os_practice.py', 'partial.py', 'range.py', 'simple.py', 'tests', 'with.py']
    


```python
os.chdir(r'C:\Users\denis.gorev\Desktop\life\stepik')
for current_dir, dirs, files in os.walk('.'):
    print(current_dir, dirs, files)
```

    . ['.ipynb_checkpoints', 'module2'] ['dataset_24465_4.txt', 'encrypted.bin', 'passwords.txt', 'task_ext.txt', 'test.txt', 'test_copy.txt', 'Untitled.ipynb']
    .\.ipynb_checkpoints [] ['Untitled-checkpoint.ipynb']
    .\module2 ['tests'] ['comprehension.py', 'files.py', 'files_append.py', 'files_write.py', 'generators.py', 'iterating.py', 'iteration.py', 'lst.py', 'operators.py', 'os_practice.py', 'partial.py', 'range.py', 'simple.py', 'with.py']
    .\module2\tests ['tests'] ['test.txt', 'test1.txt', 'test2.txt', 'test_append.txt', 'test_copy.txt']
    .\module2\tests\tests [] ['test.txt', 'test1.txt', 'test2.txt', 'test_append.txt', 'test_copy.txt']
    


```python
import zipfile

         
fantasy_zip = zipfile.ZipFile(r'C:\Users\denis.gorev\Desktop\life\stepik\main.zip')
fantasy_zip.extractall(r'C:\Users\denis.gorev\Desktop\life\stepik\main2')
 
fantasy_zip.close()

```


```python
print(os.listdir())
```

    ['aelpx.txt', 'afkgv', 'ddiqo', 'dshyt.txt', 'fjcnm.py', 'fpyfb.py', 'frtrl', 'hgyoc', 'iswbd.txt', 'ivcpr.txt', 'ivdfa.txt', 'ivkih.txt', 'iwohr.py', 'jogpz.py', 'jrczb', 'kqgeg.txt', 'ksuvk', 'lmrrz.txt', 'lqbli', 'lzccb.py', 'mdwam.txt', 'mwgax.txt', 'mwhci', 'myjqk.py', 'nelpv.py', 'nrlqk.py', 'oizxq.txt', 'olmhl', 'qbarq.txt', 'qcdrm.py', 'qdbhh.txt', 'qhjmz.txt', 'qkseh', 'rlvgd.txt', 'rpuyq.txt', 'sgeru.txt', 'sidxx.txt', 'sitdc', 'soldv.txt', 'suvtu.py', 'taivr', 'tgwey', 'uvvuz', 'vaxyw.txt', 'wkwll', 'wvere.txt', 'wxhtw.py', 'xmffa.txt', 'ybebm', 'yohuh.txt', 'yvgwm.py', 'zduna', 'zgwye.txt', 'zyczx']
    


```python
lst = []
os.chdir(r'C:\Users\denis.gorev\Desktop\life\stepik\main2')
for current_dir, dirs, files in os.walk('main'):
    if any ([file[-3:] == '.py' for file in files]):
            lst.append(current_dir)
with open (r'C:\Users\denis.gorev\Desktop\life\stepik\file.txt', 'w') as fl:
    content = '\n'.join(lst)
    fl.write(content)
```


```python
os.chdir(r'C:\Users\denis.gorev\Desktop\life\stepik\main2')
with open('file.txt', 'a') as f:
    for current_dir, dirs, files in os.walk('main'):
        if list(filter(lambda x: x.endswith('.py'), files)):
            f.write('{}\n'.format(current_dir))
```


```python
xs = list(map(int, input().split()))

    
even = list(filter(lambda x: x%2==0, xs))
even
```

    3 4 5 6 78 9
    




    [4, 6, 78]




```python
x = [
    ('Guido', 'van', 'Rossum'),
    ('Haskell', 'Curry'),
    ('John', 'Backus')
]

lst = list(map(lambda name: len(' '.join(name)), x))
x.sort(key = lambda name: len(' '.join(name)))
print(x)
```

    [('John', 'Backus'), ('Haskell', 'Curry'), ('Guido', 'van', 'Rossum')]
    


```python
import operator as oper
x = [
    ('Guido', 'van', 'Rossum'),
    ('Haskell', 'Curry'),
    ('John', 'Backus')
]
x.sort(key=oper.itemgetter(-1))
x
```




    [('John', 'Backus'), ('Haskell', 'Curry'), ('Guido', 'van', 'Rossum')]




```python
oper.itemgetter(-1)('ABCDEFG')
```




    'G'




```python
from functools import partial
x = int("1101", base = 2)
print(x)
int_2 = partial(int, base = 2)
x = int_2('0100')
print(x)
```

    13
    4
    


```python
x = [
    ('Guido', 'van', 'Rossum'),
    ('Haskell', 'Curry'),
    ('John', 'Backus')
]
sorted_by_last = partial(list.sort, key = oper.itemgetter(-1))
sorted_by_last(x)
print(x)
```

    [('John', 'Backus'), ('Haskell', 'Curry'), ('Guido', 'van', 'Rossum')]
    


```python
def mod_checker(x, mod = 0):
    return lambda y: True if y%x == mod else False

mod_3 = mod_checker(3)
print(mod_3(3))
```

    True
    


```python
# str1 = 'abababcda'
# str2 = 'cda'
# print(str1.find(str2))

# str1 = 'The man in black fled across the desert, and the gunslinger followed'
# print(str1.startswith(('The man in black', 'The woman in black', 'The cat in black')))

# str1 = 'image.png'
# str1.endswith('png')

# str1 = 'abababcda'
# str2 = 'ab'
# print(str1.count(str2))

# str1 = 'The man in black fled across the desert, and the gunslinger followed'
# print(str1.count('the'))
# print(str1.lower().count('the'))

# str1 = '1,2,3,4'
# str1.replace(',', ' ')
# print(str1.replace.__doc__)

# str1 = '   1 2  3    4    '
# print(repr(str1))
# str1 = str1.strip()
# print(repr(str1))
# str1 = str1.split()
# print(repr(str1))

# str1 = '__*_1, 2, 3, 4*__'
# str1.strip('*__')

str1 = [1, 2, 3, 4, 5]
numbers = map(str, str1)
print(repr(' '.join(numbers)))
```

    '1 2 3 4 5'
    


```python
n='o'
template = '{} is the capital of {}'
while True:
    try:
        n, m = input().split()
        print(template.format(n, m))
    except ValueError:
        print('the end of input')
        break
```

    
    the end of input
    


```python
import requests
res = requests.get('https://docs.python.org/3.7/')
k = res.headers['Content-Type']
template = 'Response from {0.url} with code {0.status_code} with content type {a}'

print(template.format(res,a = k))
```

    Response from https://docs.python.org/3.7/ with code 200 with content type text/html
    


```python
pic = requests.get('https://docs.python.org/3.7/_static/py.png')
pic.headers

with open('pythonpic.png', 'wb') as pics:
    pics.write(pic.content)
```


```python
import requests
res = requests.get('https://docs.python.org/3.7/')
print(res.status_code)
print(res.headers['Content-Type'])

#print(res.text)
#print(res.content)
```

    200
    text/html
    


```python
s = input()
a = input()
b = input()
k = 0

while s.find(a) >= 0:
    if k<=999:
        s = s.replace(a, b)
        k = k+1       
        
    else:
        print('Impossible')
        break
if k < 999:
    print(k)
```

    ababac
    c
    c
    Impossible
    


```python
s = input()
t = input()
k = 0
i = 0
for st in s:
    if s.startswith(t, i):
        k+=1
        i+=1
    else:
        i+=1
print(k)
```

    ababababa
    aba
    4
    


```python
str1 = 'abababcda'
str2 = 'aba'
print(str1.find(str2, 3))
```

    -1
    


```python
s = 'ababababa'
s='aba'
s.startswith(t, 1)
```




    False




```python
import re
print(re.match)
print(re.search)
print(re.findall)
print(re.sub)
```

    <function match at 0x000001772A6E9AE8>
    <function search at 0x000001772A735620>
    <function findall at 0x000001772A735840>
    <function sub at 0x000001772A7356A8>
    


```python
pattern = r'a[abc]c'
string = 'acc'
match_object = re.match(pattern, string)
print(match_object)

string = 'aac, abc, acc, aabcc'
all_inclusions = re.findall(pattern, string)
print(all_inclusions)

fixed_typos = re.sub(pattern, 'abc', string)
print(fixed_typos)
```

    <re.Match object; span=(0, 3), match='acc'>
    ['aac', 'abc', 'acc', 'abc']
    abc, abc, abc, aabcc
    


```python
pattern = r'abc'
string = 'babctycpabcseewqabc'
match_object = re.findall(pattern, string)
print(match_object)
```

    ['abc', 'abc', 'abc']
    


```python
#pattern = r'a[a-c]c'
#pattern = r'a[a-zA-Z]c'
#pattern = r'a[^a-zA-Z]c'
#pattern = r'a\wc'
# pattern = r'a[.\w\-]c'
pattern = r'a.c'
string = 'acc'
match_object = re.match(pattern, string)
print(match_object)

string = 'aac, abc, acc, aZc, ajc, a.c, a-c'
all_inclusions = re.findall(pattern, string)
print(all_inclusions)

fixed_typos = re.sub(pattern, 'abc', string)
print(fixed_typos)
```

    <re.Match object; span=(0, 3), match='acc'>
    ['aac', 'abc', 'acc', 'aZc', 'ajc', 'a.c', 'a-c']
    abc, abc, abc, abc, abc, abc, abc
    


```python
#pattern = r'ab*a'
# pattern = r'ab{2,4}a'
pattern = r'ab+a'
string = 'aa, aba, abba, abbba, abbbba'
all_inclusions = re.findall(pattern, string)
print(all_inclusions)
```

    ['aba', 'abba', 'abbba', 'abbbba']
    


```python
# pattern = r'[ab]+a'
pattern = r'[ab]+?a'
string = 'abaaba'
print(re.match(pattern, string))
print(re.findall(pattern, string))
```

    <re.Match object; span=(0, 3), match='aba'>
    ['aba', 'aba']
    


```python
pattern = r'\bcat\b'
line = 'catapult and cat'
re.findall(pattern, line)
```




    ['cat']




```python
re.sub.__doc__
```




    "Return the string obtained by replacing the leftmost\n    non-overlapping occurrences of the pattern in string by the\n    replacement repl.  repl can be either a string or a callable;\n    if a string, backslash escapes in it are processed.  If it is\n    a callable, it's passed the Match object and must return\n    a replacement string to be used."




```python
import re
pattern = r'"id"'
num = 0
count = 0
with open(r'C:\Users\denis.gorev\Desktop\work\ГПБ\Автокредиты\ОМНИ\1.txt', 'r') as json, open(r'C:\Users\denis.gorev\Desktop\work\ГПБ\Автокредиты\ОМНИ\2.txt', 'r') as tx:
    for line in json:
        if re.findall(pattern, line): #находим строку, начинающуюся с id
            pattern = r'("id": )' 
            line = re.sub(pattern, '', line) #убираем id
           # print(line)
            line = line.strip() #убираем пробелы
            line = line.replace('"', '') #убираем кавычки
            line = line.replace(',', '') #убираем запятые
            
            pattern = r'\b\w+\.'
            line = re.sub(pattern, '', line)
            #print(repr(line))                       
            for string in tx:
                if string.find(line) !=-1:
                    count += 1
            if count > 0:
                count = 0
                tx.seek(0)
            else: 
               # print('элемент отсутствует')
               # print(string.find(line))
```


      File "<ipython-input-132-272cbaadbb8a>", line 26
        # print(string.find(line))
                                  ^
    SyntaxError: unexpected EOF while parsing
    



```python
pattern = r'<a href='
pattern2 = r'>\w</a>'
link = '<a href="https://stepic.org/media/attachments/lesson/24472/sample1.html">1</a>'
string = re.sub(pattern, '', link)
string = re.sub(pattern2, '', string)
string = string.replace('"', '')
print(string)
```

    https://stepic.org/media/attachments/lesson/24472/sample1.html
    


```python
import requests
import re

# link = input()
# link2 = input()

link = 'https://stepic.org/media/attachments/lesson/24472/sample0.html'
link2 = 'https://stepic.org/media/attachments/lesson/24472/sample1.html'
found = False

pattern = r"<a href=\"(.*)\""
res = requests.get(link).text

for link in re.findall(pattern, res):
    res1 = requests.get(link).text
    
    for link in re.findall(pattern, res1):
        if link == link2:
            #print('i')
            found = True
            break
print('Yes' if found else 'No')


```

    No
    


```python
link = 'https://stepic.org/media/attachments/lesson/24472/sample0.html'
res1 = requests.get(link) 
print(res1.text)
for link in re.findall(r"<a href=\"(.*)\"", res1.text):
    print(str(link))
    print(type(link))

```

    <a href="https://stepic.org/media/attachments/lesson/24472/sample1.html">1</a>
    
    https://stepic.org/media/attachments/lesson/24472/sample1.html
    <class 'str'>
    


```python
# link_doc = input()
# doc = requests.get(link_doc)

pattern = r"<a href=\"(.*)\""
lst = []

# with open('doc.txt', 'w') as docs:
#     docs.write(doc.content)

with open ('doc.txt', 'r') as docs:
    for line in docs:
        lst.append(re.findall(pattern, line))
        
print(lst)
        
        
```

    [['http://stepic.org/courses'], [], [], ['ftp://mail.ru/distib'], ['ya.ru'], ['www.ya.ru'], ['../skip_relative_links']]
    


```python
pic = requests.get('https://docs.python.org/3.7/_static/py.png')
pic.headers

with open('pythonpic.png', 'wb') as pics:
    pics.write(pic.content)
    

```


```python
df = pd.read_csv('Crimes.csv')
df.head()
df['Year'] = df['Date'].map(lambda x: x.split('/')[2][0:4])
df.loc[df['Year']=='2015']['Primary Type'].value_counts().idxmax()
```




    'THEFT'




```python
city = input('Type the city ')

api_url = 'https://api.openweathermap.org/data/2.5/weather'

params = {
    'q':city,    
    'appid':'11c0d3dc6093f7442898ee49d2430d20',
    'units':'metric'
}

res = requests.get(api_url, params = params)
print(res.status_code)
print(res.headers['Content-Type'])
print(res.json())

data = res.json()
template = 'Current temperature in {} is {}'
print(template.format(city, data['main']['temp']))
```

    Type the city Rome
    200
    application/json; charset=utf-8
    {'coord': {'lon': 12.48, 'lat': 41.89}, 'weather': [{'id': 800, 'main': 'Clear', 'description': 'clear sky', 'icon': '01n'}], 'base': 'stations', 'main': {'temp': 14.41, 'pressure': 1018, 'humidity': 82, 'temp_min': 12.22, 'temp_max': 16.67}, 'visibility': 10000, 'wind': {'speed': 1.5, 'deg': 100}, 'clouds': {'all': 0}, 'dt': 1571522887, 'sys': {'type': 1, 'id': 6792, 'message': 0.0085, 'country': 'IT', 'sunrise': 1571549245, 'sunset': 1571588528}, 'timezone': 7200, 'id': 6539761, 'name': 'Rome', 'cod': 200}
    Current temperature in Rome is 14.41
    


```python
api_url = 'http://numbersapi.com/{}/math?json=true'

with open('dataset_24476_3.txt', 'r') as test:
    for line in test:
        res = requests.get(api_url.format(line.strip()))

        data = json.loads(res.text)

        if data['found'] == False:
            print('Boring')
        else: print('Interesting')
```

    Boring
    Boring
    Interesting
    Boring
    Interesting
    Interesting
    Interesting
    Boring
    Boring
    Boring
    Interesting
    Boring
    Boring
    Interesting
    Interesting
    


```python
import requests
import json
import operator as oper

client_id = '3eeebec1950927f3b016'
client_secret = '7ada4321e69ccc9018b62e4b8bf107c3'
artsy = []

# инициируем запрос на получение токена
r = requests.post("https://api.artsy.net/api/tokens/xapp_token",
                  data={
                      "client_id": client_id,
                      "client_secret": client_secret
                  })

# разбираем ответ сервера
j = json.loads(r.text)
# достаем токен
token = j["token"]
# создаем заголовок, содержащий наш токен
headers = {"X-Xapp-Token" : token}
# инициируем запрос с заголовком
with open ('dataset_24476_4.txt', 'r') as art:
    for r in art:
        api_url = "https://api.artsy.net/api/artists/{}"
        r = requests.get(api_url.format(r.strip()), headers=headers)
        r.encoding = 'utf-8'
        # разбираем ответ сервера
        j = json.loads(r.text)
        name = j['sortable_name']
        birthday = j['birthday']
        artsy.append({'name':name, 'birthday':birthday})
        
artsy.sort(key=oper.itemgetter('birthday', 'name')) 
for i in artsy:
    for k in i:
        print(i[k])
```

    Abraham de Bruyn
    1538
    Abraham van Diepenbeeck
    1596
    Abraham Roentgen
    1711
    Abbey Edwin Austin
    1852
    Abedin Zainul
    1914
    Abbott Mary
    1921
    Adach Adam
    1962
    Acea Francis
    1967
    Acetelli Mark
    1969
    Abraham Poincheval
    1972
    Acosta Scoli
    1973
    Acharya Dhruvi
    1975
    3TTMan
    1978
    Ackerman Fiona
    1978
    Aaron Flint Jamison
    1979
    


```python

```


```python
dicts = {}
# k = 0
for i in range(5):
    k = 'a'
    dicts[k]=i
    
print(dicts)
```

    {'a': 4}
    


```python
r = requests.get("https://api.artsy.net/api/artists/4d8b92b34eb68a1b2c0003f4", headers=headers)
r.encoding = 'utf-8'
# разбираем ответ сервера
j = json.loads(r.text)
#print(j)
```


```python

```
