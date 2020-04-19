[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

![web_scraping](https://user-images.githubusercontent.com/19520346/79702497-a0cc7980-82e8-11ea-9e6a-07f6180c2ed6.png)

# BEAUTIFUL SOUP
```
import requests
from bs4 import BeautifulSoup

webpage_response = requests.get('https://s3.amazonaws.com/codecademy-content/courses/beautifulsoup/shellter.html')

webpage = webpage_response.content
soup = BeautifulSoup(webpage, "html.parser")
```
- easily and quickly take information from a website and put it into a DataFrame

### Rules of Scraping
1. Check website terms and conditions
- the data you scrape should not be used for commercial purposes
2. Do not spam the website with a ton of requests. 
- A large number of requests can break a website that is unprepared for that level of traffic. 
- As a general rule of good practice, make one request to one webpage per second.
3. Check if layout has changed
- If the layout of the website changes, you will have to change your scraping code to follow the new structure of the site.

## Requests
```
import requests

webpage_response = requests.get('https://www.codecademy.com/articles/http-requests')
```
- In order to get the HTML of the website, we need to make a request to get the content of the webpage.
- `webpage_response.content` : see content of HTML

## Object
```
from bs4 import BeautifulSoup

BeautifulSoup("html_filename.html", "html.parser")
```
-  breaks the HTML page into several types of objects.
- "html.parser" is one option for parsers we could use (others are "lxml" and "html5lib" that have different advantages and disadvantages)
OR
```
webpage = requests.get("http://rainbow.com/rainbow.html", "html.parser")
soup = BeautifulSoup(webpage.content)
```

### Tags
- corresponds to an HTML Tag in the original document
- `soup_object_name.div.name` : name of the tag
- `soup_object_name.div.attrs` : a dictionary representing the attributes of the tag

### Navigable Strings
- the pieces of text that are in the HTML tags on the page. 
- `soup_object_name.div.string` : the string inside of the tag


## Navigation

### By Tags
```
soup_object_name.h1
soup_object_name.ul.children
soup_object_name.div.children
soup.li.parents

```
- To navigate through a tree, we can call the tag names themselves

### Find all
```
soup.find_all("h1")
```
1. REGEX - to find every `<ol>` and `<ul>`
```
soup.find_all(re.compile("[ou]l"))
soup.find_all(re.compile("h[1-9]"))
```

2. LIST - specify all of the elements we want to find
```
soup.find_all(['h1', 'a', 'p'])
```

3. ATTRIBUTES - match the elements with relevant attributes
```
soup.find_all(attrs={'class':'banner'})
soup.find_all(attrs={'class':'banner', 'id':'jumbotron'})
```

4.  FUNCTIONS - find all of the occurrences of a tag
```
def has_banner_class_and_hello_world(tag):
    return tag.attr('class') == "banner" and tag.string == "Hello world"

soup.find_all(has_banner_class_and_hello_world)
```
