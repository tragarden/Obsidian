# Improving Python Code

If we consider trying to apply the code in [[0922 HTB Python First Iterations]] to two different web pages, this would require a large repeating block of code to accomplish this two different times. 

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

Alternatively, we can refactor this code and place the word counting feature into a new function count_occurrences_in:

>def count_occurrences_in(word_list):
>	word_count = {}
>	for word in word_list:
>		if word not in word_count:
>			word_count\[word] = 1
>		else:
>			current_count = word_count.get(word)
>			word_count\[word] = current_count + 1
>	return word_count

This code has effectively used the variable word_list as a parameter that can be iterated over. The return statement will return the results of processing word_list.

We can also reassign the variable definitions block after the first function to it's own function:

>html = get_html_of(PAGE_URL)
>soup = BeautifulSoup(html, 'html.parser')
>raw_text = soup.get_text()
>all_words = re.findall(r'\\w+', raw_text)

We will define a new function get_all_words_from and include these lines of codes within:

>def get_all_words_from(url):
>	html = get_html_of(url)
>	soup = BeautifulSoup(html, 'html.parser')
>	raw_text = soup.get_text()
>	return = re.findall(r'\\w+', raw_text)
>	
>all_words = get_all_words_from(PAGE_URL)

This code block can be refactored AGAIN to be a bit more concise:

>def get_top_words_from(url):
	all_words = get_all_words_from(url)
	occurrences = count_occurrences_in(all_words)
	return sorted(occurrences.items(), key=lambda item: item\[1], reverse=True)

### Completed Code

>import requests
>import re
>from bs4 import BeautifulSoup
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
>def count_occurrences_in(word_list):
>	word_count = {}
>	
>	for word in word_list:
>		if word not in word_count:
>			word_count\[word] = 1
>		else:
>			current_count = word_count.get(word)
>			word_count\[word] = current_count + 1
>	return word_count
>		
>def get_all_words_from(url):
>	html = get_html_of(url)
>	soup = BeautifulSoup(html, 'html.parser')
>	raw_text = soup.get_text()
>	return re.findall(r'\\w+', raw_text)
>	
>def get_top_words_from(all_words):
>	occurrences = count_occurrences_in(all_words)
>	return sorted(occurrences.items(), key=lambda item: item\[1], reverse=True)
>	
>all_words = get_all_words_from(PAGE_URL)
>top_words = get_top_words_from(all_words)
>
>for i in range(10):
>	print(top_words\[i]\[0])

