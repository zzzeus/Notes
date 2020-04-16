# A note about python

## Contents
1. [strings](#strings)
2. [deal with dict](#deal-with-dict)

#### Strings
```python
a=r'This is a text.'

# get a part of text
# slice
a[1]
a[1:5:2]
a[::-1]

# parse html to string
from html.parser import HTMLParser
HTMLParser().unescape(videopath)

# change PINGYIN to Alph
import unicodedata
unicodedata.normalize('NFKD', text).encode('ascii','ignore')

```
#### deal with dict
```python
people={'Jack':25,'Mike':33,'Zeus':25}
# slice dict
{k: people[k] for k in list(people.keys())}
```



