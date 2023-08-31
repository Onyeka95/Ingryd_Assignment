```python
#mean, median and mode and range
#variance, standard divistion, mean division

```


```python
#Mean using python
temp = [23,45,55,76,24,48,22,28,29,30,31,32,33,34,35,36,37,38,40,41]

#Summation of the list items
total_num = sum(temp)

#Getting the total lenght of the list
lenght = len(temp)

#Getting the mean which is sum of all the values divided by the number of values
mean = total_num / lenght

print(f" Mean: {mean: .2f}")
```

     Mean:  36.85
    


```python
#Median 
temp = [23,45,55,76,24,48,22,28,29,30,31,32,33,34,35,36,37,38,40,41]

#lenght on the temperature list
n = len(temp)

#sorting the list in ascendind order
temp.sort()

#for loop to check if the median number is even
if n % 2 == 0:
    first_middle_num = temp[n//2] #for the fist middle number if its equal to zero means it is even
    second_middle_num = temp[n//2 - 1] # second middle number if it is equal to zero means even
    median = (first_middle_num + second_middle_num)/ 2 #here if the first and second middle num is even, you divide by 2 to get the average
else:
    median = temp[n//2] #if the middle number is not even then given it to us as the median

print(f" Median: {median: .2f}")
    
    

```

     Median:  34.50
    


```python
#Mode
temp = [22,45,55,76,24,48,22,28,29,30,31,32,33,34,35,33,37,38,40,41]
#sorted the list of temperature
temp.sort()
#This is an empty list to append the count of the occurrence of each number on the list
num = []
a = 0 #A varial that will help us loop through the temp list

while a < len(temp):
    num.append(temp.count(temp[a]))
    a += 1
    
#zip the temp values and the number of occurrences of each then cast it to a dict which will put our temp and number of occurence into 
#key, value pair.

mode1 = dict(zip(temp, num))

#list comprehension: we loop through dict items (key, value) pair and choose the one that has the maximum occurrence value.
mode = { k for (k,v) in mode1.items() if v == max(num)}
print(f" The Mode is/are: {mode}")




```

     The Mode is/are: {33, 22}
    


```python
#Range
temp = [22,45,55,76,24,48,22,28,29,30,31,32,33,34,35,33,37,38,40,41]
#Get max temp minus minimum temp
find_range = max(temp) - min(temp)
print(f" The range of the temperature list: {find_range}")
```

     The range of the temperature list: 54
    


```python
#Variance calculates the square difference from the mean

def variance(x):
    #the number of observation
    n = len(x)
    #mean of the data
    mean = sum(x)/n
    # square deviations
    deviations = [(y - mean) ** 2 for y in x]
    #variance
    variance = sum(deviations)/n
    return variance

variance([22,45,55,76,24,48,22,28,29,30,31,32,33,34,35,33,37,38,40,41])
```




    148.6275




```python
#Standard deviation is the square root of variance
# use a python model called math

import math

def variance(data, ddof = 0): 
    n = len(data)
    mean = sum(data) / n
    return sum((x - mean) ** 2 for x in data) / (n - ddof)

def standard_dev(data):
    var = variance(data)
    std_dev = math.sqrt(var)
    return std_dev

standard_dev([22,45,55,76,24,48,22,28,29,30,31,32,33,34,35,33,37,38,40,41])


```




    12.191287872903338




```python
# mean deviation
temp = [23,45,55,76,24,48,22,28,29,30,31,32,33,34,35,36,37,38,40,41]

#Summation of the list items
total_num = sum(temp)

#Getting the total lenght of the list
lenght = len(temp)

#Getting the mean which is sum of all the values divided by the number of values
mean = total_num / lenght

# Calculate the absolute differences from the mean
mean_dev = [abs (x - mean) for x in temp]

mean_deviation = sum(mean_dev) / lenght

print(f"The Mean deviation is: {mean_deviation}")
```

    The Mean deviation is: 8.52
    


```python

```
