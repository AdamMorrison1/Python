

```python
import pandas as pd #import the pandas library

dict = {
  "country": ["Brazil", "Russia", "India", "China", "South Africa"],
  "capital": ["Brasilia", "Moscow", "New Dehli", "Beijing", "Pretoria"],
  "area": [8.516, 17.10, 3.286, 9.597, 1.221],
  "population": [200.4, 143.5, 1252, 1357, 52.98] 
}

data = pd.DataFrame(dict) #convert dictionary to a pandas table
#from now on we refer to the dictionary dict, as data. i.e. print(data)

```


```python
print(data) # Print out the Pandas data.
```

            country    capital    area  population
    0        Brazil   Brasilia   8.516      200.40
    1        Russia     Moscow  17.100      143.50
    2         India  New Dehli   3.286     1252.00
    3         China    Beijing   9.597     1357.00
    4  South Africa   Pretoria   1.221       52.98



```python
data.index = ["BR", "RU", "IN", "CH", "SA"] #Replace the index values with meaningful characters
print(data) #Print out the data with new index values - default is 0,1,2
```

             country    capital    area  population
    BR        Brazil   Brasilia   8.516      200.40
    RU        Russia     Moscow  17.100      143.50
    IN         India  New Dehli   3.286     1252.00
    CH         China    Beijing   9.597     1357.00
    SA  South Africa   Pretoria   1.221       52.98



```python
print( data["capital"] ) #print all the data within the capital row
```

    BR     Brasilia
    RU       Moscow
    IN    New Dehli
    CH      Beijing
    SA     Pretoria
    Name: capital, dtype: object



```python
print( data["population"].sum() ) #sum of values in population row
print( data["population"].max() ) #maxiumum value in population row
print( data["population"].min() ) #minimum value in population row
print( data["population"].mean() ) #mean value of population row
print( data["population"].median() ) #median value of population row
```

    3005.88
    1357.0
    52.98
    601.176
    200.4



```python
print( data["area"].describe() ) #generic statistics
```

    count     5.000000
    mean      7.944000
    std       6.200557
    min       1.221000
    25%       3.286000
    50%       8.516000
    75%       9.597000
    max      17.100000
    Name: area, dtype: float64



```python
print(data.head(2)) #print the first n rows
print(data.tail(3)) #print the last n rows
```

       country   capital    area  population
    BR  Brazil  Brasilia   8.516       200.4
    RU  Russia    Moscow  17.100       143.5
             country    capital   area  population
    IN         India  New Dehli  3.286     1252.00
    CH         China    Beijing  9.597     1357.00
    SA  South Africa   Pretoria  1.221       52.98



```python
print(data[["country", "population"]]) #print the data frame with only the 2 columns specified
```

             country  population
    BR        Brazil      200.40
    RU        Russia      143.50
    IN         India     1252.00
    CH         China     1357.00
    SA  South Africa       52.98



```python
print(data.loc['BR']) #print the values in row BR
```

    country         Brazil
    capital       Brasilia
    area             8.516
    population       200.4
    Name: BR, dtype: object



```python
print( data.loc['BR','population'] ) #print the value in row BR, column population
```

    200.4



```python
print( data.loc[ data['country'] == 'China'] ) #get data where value in column country is equal to China
```

       country  capital   area  population
    CH   China  Beijing  9.597      1357.0



```python
print( data.loc[ data['population'] < 200 ] ) #get data that has a population of less than 200
```

             country   capital    area  population
    RU        Russia    Moscow  17.100      143.50
    SA  South Africa  Pretoria   1.221       52.98



```python
# The logical & operator allows you to find data where 2 or more conditions need to be true
# The example below selects everything from data that conforms to the following conditions...
# ...population is less than 500 AND area is greater than 7

print( data.loc[ (data['population'] < 500) & (data['area'] > 7) ] )
```

       country   capital    area  population
    BR  Brazil  Brasilia   8.516       200.4
    RU  Russia    Moscow  17.100       143.5



```python
# The logical | operator is equivalent to OR
# Only one of the conditions need to be true for it to select the data

print( data.loc[ (data['population'] < 500) | (data['area'] > 7) ] )
```

             country   capital    area  population
    BR        Brazil  Brasilia   8.516      200.40
    RU        Russia    Moscow  17.100      143.50
    CH         China   Beijing   9.597     1357.00
    SA  South Africa  Pretoria   1.221       52.98



```python

```
