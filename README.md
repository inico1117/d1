# d1
practice

#map()
name=['adam', 'LISA', 'barT']
def normalize(name):
    return name[:1].upper()+name[1:].lower()
list(map(normalize,name))

#reduce()
def prod(L):
    return reduce(lambda x,y:x*y,L)

#reduce-map()
from functools import reduce
def str2float(s):
    a=s.index('.')
    def f(x,y):
        return x*10+y
    def char2num(s):
        digits = {'0': 0, '1': 1, '2': 2, '3': 3, '4': 4, '5': 5, '6': 6, '7': 7, '8': 8, '9': 9}
        return digits[s]
    s=s[:a]+s[a+1:]
    return reduce(f,map(char2num,s))/pow(10,len(s)-a)
    
#filter()
def is_palindrome(n):
    return str(n)==str(n)[::-1]
filter(is_palindrome,range(1,1000))  

#sorted()
L = [('Bob', 75), ('Adam', 92), ('Bart', 66), ('Lisa', 88)]
def by_name(t):
    return t[0]
def by_score(t):
    return t[1]
return sorted(L,key=by_name)
return sorted(L,key=by_score,reverse=True)

#返回函数
def createCounter():
    def iter():
        i=1
        while True:
            yield i
            i=i+1
    it=iter()
    def counter():
        return next(it)
    return counter
    
#lambda()
L = list(filter(lambda n:n%2==1, range(1, 20)))
