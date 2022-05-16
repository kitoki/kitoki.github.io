title : 5 unique python projects (beginner to intermediate)

#### recommended system
```python
from random import choice

# create list of animes
animes = [['naruto', 'pepehype', 'forever', 'series'],
          ['haikyuu', 'sports', 'short', 'series'],
          ['mushishi', 'chill', 'short', 'series'],
          ['march come in like a lion', 'slice of life', 'short', 'series']]

# input mood
print('what mood you currently in?')
mood = input()

# loop through and find a matching mood
for item in animes:
    if item[1] == mood:
       print(mood + ' anime: ' + item[0])
```

#### personal finance dashboard
