##  连分数

```python
def solve(a, b):
    g=[]
    while(a!=1):
        g.append(a//b)
        a,b=b,a%b
    g.append(b)
    return g
def simplify(x):
    n,d=0,1
    for i in x[::-1]:
        n,d=d,i*d+n
    return n,d
def getmidfrac(x):
    r=[]
    for i in range(1,len(x)):
        r.append(simplify(x[:i]))
    return r
g=solve(h1,h2)
g=getmidfrac(g)
q1,q2=None,None
for (a,b) in g:
    if b==0:
        continue
    if h1%b==0 and b-1 and b-h1:
        q1=b
        q2=a
        break
```

### pell  formulation

```python
def solve_pell (N , numTry = 1000):
    sols = []
    cf = continued_fraction ( sqrt ( N ))
    for i in range ( numTry ):
        denom = cf . denominator ( i )
        numer = cf . numerator ( i )
        if numer ^2 - N * denom ^2 == 1:
            sols.append((ZZ(numer) , ZZ(denom)))
    return sols
```

