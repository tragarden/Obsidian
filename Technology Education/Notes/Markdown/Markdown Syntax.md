# Markdown Syntax


### Headers

To indicate header size in Markdown language, between 1 - 6 hashtags are placed before the Heading, separated by a space.  This is the same as using \<h1>\ to indicate headers in HTML.

- Rules for Headers

	- always put a space to separate the hashtag from the header

	- put a blank line before and after your header

	-	''### okay" would be like writing \<h3>\ okay 

	-  placing " ===== " under a header is an alternative way to do this
		- ======= indicates a level 1 header
		- ------------ indicates a level 2 header


### Paragraphs

Paragraphs are indicated by using a blank line to separate lines of text.  Think of the line break as the means of separation, similar to using \<p>\ in HTML. 

Unless you are putting paragraphs into lists, DO NOT tab or space before your paragraphs.  This keeps everything left-aligned for neatness.  If you place tabs, this will result in unexpected formatting problems.


### Line Breaks

A line break is indicated by ending a line with two or more spaces and then pressing return. Ending a line in this manner is referred to as 'trailing whitespace'. This has the same affect as using \<br> in HTML. 

Some users may not want to use trailing whitespace, as many people intentionally or accidentally double-space when completing a sentence. Alternatively, you can use a backslash ( \\ ) but this format is not universal across Markdown apps. 


### Emphasis

Bold is indicated by wrapping the expression in double asterisks or double underscores. This is similar to using \<strong> in HTML.
	- \**bold text**
	- \__bold text__
		Using asterisks is preferred as underscores may cause issues when used between words.

Italic is indicated by wrapping the expression in single asterisks or single underscores.  This is similar to using \<em> in HTML.
	- \*italicized text*
	- _italicized text_
		*Using asterisks is preferred as underscores may cause issues when used between words.

Bold AND Italics are indicated by wrapping the expression in triple asterisks or triple underscores.  This is similar to using \<em>\<strong> in HTML.
	-\***bold and italicized text***
	- \___bold and italicized text___
	- *Using asterisks is preferred as underscores may cause issues when used between words.


### Blockquotes

Blockquotes are indicated by placing a \> symbol in front of a paragraph.  Blockquotes can contain multiple paragraphs with each line having a \> symbol in front of it, including the blank lines.

Put blank lines before and after your blockquotes.

Nested Blockquotes are indicated by placing \>> in front of the paragraph you want to nest. 

> Here is my first line of blockquotes.
> 
>> This is my nested line of blockquotes.
>
>Here is another line that is not nested.
>
> #### Here is a nested header.
> 
> - This is list line one.
> - This is list line two.
> 
> *I hope* this is **working well**.


### Lists

*Ordered Lists*
An ordered list is created by adding line items followed by periods.  This is similar to using \<ol> in HTML. 
	While you can create ordered lists using parenthesis, this is less compatible than using periods.

*Unordered Lists*
An unordered list is created by preceding line items with a dash (-), asterisk (\*), or plus (+). This is similar to using \<ul> in HTML.
	If you need to include an unordered list item using a number followed by a period, the period must be escaped using the backslash ( \\ ).
		i.e. - 1969\. was when my mom was born.
	DO NOT mix delimiter usage within a document.

CHECK HOW TO ADD ELEMENTS TO A LIST FOR SPECIFIC CASES.


### Code

Backticks (  \` ) are used to denote any code in your notes by wrapping the expression in backticks . This is similar to using \<code> in HTML.

If your word is already wrapped in backticks for stylistic purposes, use double backticks.

Code Blocks are created by indenting every line within the block with tab or 4 spaces.


### Horizontal Rules

Horizontal Rules are created by using three or more asterisks ( \* ), dashes ( - ), or underscores ( _ ) on a line by themselves.  Put blank lines before and after a Horizontal Rule.
	***
	---
	___


### Links

Links are created by wrapping the link text in brackets and then including the link URL within parentheses as seen in the example below.  A title can be added by wrapping text in quotations after the URL.

Formatted as:
	- Here is a link to a search engine \[Duck Duck Go]\(https://duckduckgo.com "It's a search engine for increased privacy."	)

Rendered as:
	- Here is a link to a search engine [Duck Duck Go](https://duckduckgo.com "It's a search engine for increased privacy."	)

Turning a written URL or email into a hyperlink by wrapping the text in angle brackets.
	- \<mmyemail@gmail.com\>
	- <myemail@gmail.com>

Created links can be wrapped in asterisks to either italicize or embolden the link text.

Reference-Style Links use two sets of brackets - the first denotes the text to be linked and the second denotes a 'pointer' label that links to where you store links elsewhere.
	- \[link I made] \[1]

Formatting for the second part of the link means placing a colon ( : ) directly after the second set of brackets, followed by one space and then the URL and title.  The URL may be a line of text or enclosed in angled brackets. 
	- \[another link] \[2] : \https://urlimadeup.com \"this is a site i made up"

*Not all Markdown applications handle spaces the same way. Alternatively you should use %20 within a URL to indicate a space.*

*Parentheses can also cause problems within a URL - use %28 to indicate opening ( ( ) and %29 to indicate closing ( ) )*


### Images

You can link to an image by enclosing the Markdown language in brackets and then include the link within parentheses. 

- \[!\[A picture of a rock]\(/assets/images/rock.jpg "this is the rock picture")](\https://flickr.com/rockpicsandotherstuffrelatedtothisURLimadeup)


### Escape Characters

The escape character in Markdown is the backslash ( \\ ) to display the literal character instead of a format indicator. 


### HTML

To use HTML within Markdown language, simply include the HTML scripts in your text file. If you chose to use Markdown this way, make sure you use blank lines to separate block-level HTML elements and DO NOT tab indent as this can interfere with clean formatting.

### Related: 
- [Markdown Basic Syntax](https://www.markdownguide.org/basic-syntax/ "This is the page I used for this outline.")

#PKM #concept #study #markdown #formatting #syntax
