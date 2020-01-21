# Title
> summary


```python
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
```

```python
def make_stock(length=100, num_stocks=2):
    alpha = 0.9
    k = 2
    cov = np.random.normal(0, 5, [num_stocks, num_stocks])
    cov = cov.dot(cov.T) # This is a positive semidefinite matrix, e.g. a covariance matrix
    A = np.random.multivariate_normal(np.zeros(num_stocks), cov, size=[length]) # sample noise, with covariance 
    B = np.random.multivariate_normal(np.zeros(num_stocks), cov, size=[length]) # sample another noise, with covariance
    bs = [np.zeros(shape=num_stocks)] # 
    ps = [np.zeros(shape=num_stocks)] # The prices

    for a, b in zip(A, B):
        bv = alpha * bs[-1] + b # calculate some trend
        bs.append(bv)
        pv = ps[-1] + bs[-2] + k * a # Previosu price + previous trend factor, plus some noise
        ps.append(pv)

    #     ps = [0]
    #     for a,b,common in zip(A,BB,commonNoise):
    #         ps.append(ps[-1]+b+k*a+2*common)
    #     P = np.array(ps)
    #     P = np.exp(P/(P.max()-P.min()))
    ps = np.array(ps).T # reshape it so that its [length,stocks] 
    R = ps.max(1) - ps.min(1) # Scale factor
    prices = np.exp(ps.T / (R)) *np.random.uniform(10,250,num_stocks) # Normalize, exponantiate then make the prices more varied
    return prices
```

```python
def sin_func(num_stocks,length):
    a = np.array(range(length+1))
    a.shape= [length+1,1]
    a = a/(2*np.pi)
    a = np.sin(a)
    return a+5.0001
```

```python
D = pd.DataFrame(make_stock(1000,10)*np.random.uniform(2,4,10))
```

```python
plt.xkcd()
D.plot(figsize=(20,10),title='My make believe market for 10 stocks')
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f9fd8884e10>



    /usr/local/lib/python3.6/dist-packages/matplotlib/font_manager.py:1241: UserWarning: findfont: Font family ['xkcd', 'xkcd Script', 'Humor Sans', 'Comic Sans MS'] not found. Falling back to DejaVu Sans.
      (prop.get_family(), self.defaultFamily[fontext]))



![png](MagicMarket_files/output_4_2.png)


```python
xklgfjhnx;gb;xg;lk
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-6-806d91c97157> in <module>()
    ----> 1 xklgfjhnx;gb;xg;lk
    

    NameError: name 'xklgfjhnx' is not defined

