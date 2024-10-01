# First Iterations

Creating first iterations of code before assembling it as a whole is a good idea even in cases where you think you know what the final result will look like.

In the context of creating a program that fetches all words from a web page: let's break this down into basic steps describing pseudocode so that conceptually we have a greater understanding of the process.

- The code will download and print the entire HTML code for a webpage.
- The URL of the page is fixed within this code.
- The code will be written in simplest form with pieces added as needed.
- We will use the requests library to do this.

Using the requests library, we will store the target URL in a variable and return the HTML code from this URL:

>import requests
>
>
>PAGE_URL = '\http://target:port'
>	
>resp = requests.get(PAGE_URL)
>html_str = resp.content.decode()
>print(html_str)

### 404 Error in IDLE

If we supply the incorrect URL with the requests library features, we will have a 404 response.

Here is the code supplying the incorrect URL:

>r = requests.get('\http://target:port/missing.html')
>r.status_code
>
>print(r.content.decode())

![[404 Error Status Code.png]]

#### Error Handling

We can now implement a function handling HTTP status errors in our code:

>import requests
>
>
>PAGE_URL = '\http://target:port'
>
>def get_html_of(url):
>	resp = requests.get(url)
>	
>	if resp.status_code != 200:
>		print(f'HTTP status code of {resp.status_code} returned, but 200 was expected. Exiting...')
>		exit(1)
>	
>	return resp.content.decode()
>	
>print(get_html_of(PAGE_URL))

#### Next steps

Now that we have a function that can manage the most basic aspects of our process, we need to outline the next steps in pseudocode statements to help us think it through:

- Find all words on the page
- Ignore HTML tags and metadata
- Perform a word count and record it
- Sort by occurrence
- Print the most frequently occurring words

BeautifulSoup has a function get_text() to retrieve all text on a webpage as string data.

#### Vending Machine Analogy

Older vending machines used a slot system to determine what coin was submitted by assessing it's size and shape. The large coins will bypass smaller holes because they do not fit, and this hierarchical sorting method can be applied to words on a page as well.

This can be done by having a dictionary of word occurrences, mapping the word to the dictionary, and then checking each following word to determine if it has been recorded previously.

We can then sort by number of occurrences and print the ten most occurring words.

### Regex

Now we can use the 're' library to implement regular expressions with the get_text() function from the requests library. The re library has a .findall() method that utilizes a regex string and other string parameters. We can use this method with the regex string \\w+ to search and sort through the contents returned by the get_text() function.

### Finding All Words

We can add to our existing code to use the .findall() method:

>import requests    # imports the requests library
>import re     # imports the regex library
>from bs4 import BeautifulSoup    # imports the beautifulSoup4 library
>
>
>PAGE_URL = '\http://target:port'
>
>def get_html_of(url):
>	resp = requests.get(url)
>	
>	if resp.status_code != 200:
>		print(f'HTTP status code of {resp.status.code} returned, but 200 was expected. Exiting...')
>		exit(1)
>		
>	return resp.content.decode()
>	
>html = get_html_of(PAGE_URL)
>soup = BeautifulSoup(html, 'html.parser')
>raw_text = soup.get_text()
>all_words = re.findall(r'\\w+', raw_text)

### Counting Word Occurrences

We can now create a new variable word_count that will serve as our dictionary. This will contain all the key-value pairs that are observed in all_words. If a word does not exist - it's key will be assigned a value of 1. If it does exist, this number value will iterate +1 each time the word is returned again.

># ...continued
>
>all_words = re.findall(r'\\w+', raw_text)
>
>word_count = {}
>
>for word in all_words:
>	if word not in word_count:
>		word_count\[word] = 1
>	else:
>		current_count = word_count.get(word)
>		word_count\[word] = current_count + 1

### Sorting List Words

We can use the following code to sort the list word_count.items() and store them in the variable top_words:

>top_words = sorted(word_count.items(), key=lambda item: item\[1], reverse=True)
>for i in range(10):
>	print(top_words\[i])

This will return key-value tuples in the form (word, occurrence) by selecting the first element of each tuple (top_words\[i]\[0])

### All Iterations

When we combine all iterations throughout this exercise and tutorial, we get the following code block:

>import requests
>import re
>from bs4 import BeautifulSoup
>
>
>PAGE_URL = '\http://target:port'
>
>def get_html_of(url):
>	resp = requests.get(url)
>	
>	if resp.status_code != 200:
>		print(f'HTTP status code of {resp.status_code} returned, but 200 was expected. Exiting...')
>		exit(1)
>		
>	return resp.content.decode()
>	
>html = get_html_of(PAGE_URL)
>soup = BeautifulSoup(html, 'html.parser')
>raw_text = soup.get_text()
>all_words = re.findall(r'\\w+', raw_text)
>
>word_count = {}
>
>for word in all_words:
>	if word not in word_count:
>		word_count\[word] = 1
>	else:
>		current_count = word_count.get(word)
>		word_count\[word] = current_count + 1
>		
>top_words = sorted(word_count.items(), key=lambda item: item\[1], reverse=True)
>
>for i in range(10):
>	print(top_words\[i]\[0])

