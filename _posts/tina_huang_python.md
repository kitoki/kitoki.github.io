title : 5 unique python projects (beginner to intermediate)

`when you start project, dont have like a super grand idea and feel really overwhelmed when implementing it`, start with something small, and after you get that working, then build on more features, amd more functionalities, and before you know it, you have project that able do so many more thing

#### recommended system / automating decision making
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


- skill :
  - python
  - list
  - random module
  - input()

- advance skill :
  - panda (data frame)
  - APIs (to interface someone else software)
    - utilitze APIs for automation (jikan.py)
      - recommended system

`nested list not best approach, use panda to create table (dataframe) when in  CLI more encourage`



#### personal finance dashboard
