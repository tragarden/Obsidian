# Improving Python Further

If our code from [[0922 HTB Python First Iterations]] and [[0923 HTB Improving Code]] were to be imported, this code would run as soon as it is imported. We can avoid this occurrence by putting all code that 'does something' into a 'main' block:

>if \_\_name\_\_ == '\_\_main\_\_':
>	page_url = '\http://target:port'
>	the_words = get_all_words_from(page_url)
>	top_words = get_top_words_from(the_words)
>	
>	for i in range(10):
>		print(top_words\[i]\[0])

This block of code will only execute now when the code is run - not when it is imported as previously defined.

We can also remove the PAGE_URL constant. If we do this, we can make the script more flexible by accepting an input argument when we run Python and subsequently the script.

The arguments will be able to be provided using named parameters in the command:

>python3 wordextractor.py --url \http://foo.bar/baz

This means we could further extend the program by incorporating a word-length limit that avoids common words like 'the', 'and', and 'that'.

A module that we could use for this purpose is known as 'click', which is a type of 'decorator'. Decorators are used for decorating functions and are indicated with the \@ prefix. In the following example, these allowed us to set up command-line arguments. 

Install click with the following command:

>pip3 install click

Now we can import click and use it's methods in the following code:

>import click
>
>\@click.command()
>\@click.option('--count', default=1, help='Number of Greetings.')
>\@click.option('--name', prompt='Your Name', help='The person you greet.')
>def hello(count, name):
>	for i in range(count):
>		click.echo('Hello %s!' % name)
>		
>if \_\_name\_\_ == '\_\_main\_\_':
>	hello()

The decorators include:

\@click.command() indicates that we will have command-line inputs.
\@click.option() is then used to set up the two named parameters, --name and --count.
This command will set the count to a default number and prompt the user to enter their name as an argument if one was not supplied.

The following commands are examples of how the command takes arguments:

>C:\\Users\\trag> python click_test.py

Output:
>Your name: trag
>Hello trag!

Using named parameters:

>python click_test.py --name trag

Output:
>Hello trag!

Using the count parameter:

>python click_test.py --name trag --count 4

Output:
>Hello trag!
>Hello trag!
>Hello trag!
>Hello trag!

Using the --help parameter:

>python click_test.py --help

Output:
>Usage: click_test.py [OPTIONS]
>
>Options:
>--count INTEGER  Number of greetings.
>--name TEXT      The person to greet.
>--help           Show this message and exit.

Since the data types were not assigned when setting up the click methods, click will assume the correct type indicated by the 'INTEGER' and 'TEXT' next to the named parameters.

### Creating main()

Now that we have set up click, we can move the main body of the previous function into the newly defined main() function:

>def main():
>	page_url = '\http://target:port'
>	the_words = get_all_words_from(page_url)
>	top_words = get_top_words_from(the_words)
>	
>	for i in range(10):
>		print(top_words\[i]\[0])
>		
>if \_\_name\_\_ == '\_\_main\_\_':
>	main()

### Adding Click Options

Now we can integrate click options for our main() function:

>\@click.command()
>\@click.option('--url', '-u', prompt='Web URL', help='URL of webpage to be extracted from.')
>\@click.option('--length', '-l', default=0, help='Minimum word length (default: 0, no limit).')
>def main(url, length):
>	the_words = get_all_words_from(url)
>	top_words = get_top_words_from(the_words, length)

This used the click methods to add the parameters 'url' and 'length' which can be used instead of hardcoding a url into the function block. 

### Passing in Arguments

The variable from the command needs to be passed into the get_top_words_from function and then pass it to the count_occurrences_in function.

We would update these two functions as shown below:

>def count_occurrences_in(word_list, min_length):
>	word_count = {}
>	
>	for word in word_list:
>		if len(word) < min_length:
>			continue
>		if word not in word_count:
>			word_count\[word] = 1
>		else:
>			current_count = word_count.get(word)
>			word_count\[word] = current_count + 1
>	return word_count
>	
>def get_top_words_from(all_words, min_length):
>	occurrences = count_occurrences_in(all_words, min_length)
>	return sorted(occurrences.items(), key=lambda item: item\[1], reverse=True)

### Final Script

>import click
>import requests
>import re
>from bs4 import BeautifulSoup
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
>def count_occurrences_in(word_list, min_length):
>	word_count = {}
>	
>	for word in word_list:
>		if len(word) < min_length:
>			continue
>		if word not in word_count:
>			word_count\[word] = 1
>		else:
>			current_count = word_count.get(word)
>			word_count\[word] = current_count + 1
>	return word_count
>	
>get_all_words_from(url):
>	html = get_html_of(url)
>	soup = BeautifulSoup(html, 'html.parser')
>	raw_text = soup.get_text()
>	return re.findall(r'\\w+', raw_text)
>	
>def get_top_words_from(all_words, min_length):
>	occurrences = count_occurrences_in(all_words, min_length)
>	return sorted(occurrences.items(), key=lambda item: item\[1], reverse=True)
>	
>\@click.command()
>\@click.option('--url', '-u', prompt='Web URL', help='URL of webpage to be extracted from.')
>\@click.option('--length', '-l', default=0, help='Minimum word length (default: 0, no limit).')
>def main(url, length):
>	the_words = get_all_words_from(url)
>	top_words = get_top_words_from(the_words, length)
>	
>	for i in range(10):
>		print(top_words\[i]\[0])
>		
>if \_\_name\_\_ == '\_\_main\_\_':
>	main()


