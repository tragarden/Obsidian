# Code Obfuscation

Code #Obfuscation is a method of modifying existing code to make it more difficult to read by humans. This may make the code slower during processing as well, however. This is done using a dictionary style reference system that exchanges each known term for the matching term from the obfuscation dictionary.

JavaScript is usually obfuscated because it is presented to users across the internet via front end source code on the client side. This means that anyone can look at the source code and see what was done to create the web page they are viewing. Developers obfuscate code to prevent others from using or copying it in attempts to reverse engineer site design. Additionally this makes the site more secure and protected from code injection attacks. 

It is advisable to put any authentication or encryption methods on the back-end because client-side code is vulnerable to attack.

Alternatively and attacker can use code obfuscation to make their attack payloads less obvious to Intrusion Detection and Prevention systems ( #IDS / #IPS). 

### Basic Obfuscation

Almost all obfuscation is done through automation, although there may be some cases where a developer painstakingly did so manually. Developers making their own obfuscation automation applications is quite common so they have their own unique obfuscation dictionary to defend against attack and theft.

### Minification

Minification is a simple method of writing a long piece of code as a single line instead of modular block format. This is done to make the code less readable and more difficult to work with. When code is minified through an application, it is stored as a .min.js file extension. 

### Packing

After writing JavaScript code, we can import it into a web app like BeautifyTools and obfuscate the code. After you obfuscate, you can run it back through JSconsole and see that it still works although it looks entirely different. 

A packer tool converts all the words in a script into the dictionary translation and then uses the (p,a,c,k,e,d) function to rebuild the code into its original form.

### Advanced Obfuscation

Using the previously described methods of obfuscation we will still have words that remain presented as clear-text. We can further obfuscate this text by converting from String Array Encoding to #Base64 that will make it much harder to determine what our code means.

Web apps like obfuscator.io can be used to further complicate our code with customizable methods. We can take it so far that our code is only represented by symbols, but will still render and work within JSconsole.

### Deobfuscation

When we encounter or produce obfuscated code, we can Beautify it using a variety of tools like Browser Dev Tools, Pretty Print, Prettier, UnPacker, or Beautifier. Although these automated tools are great at making the code readable again, they are limited in their function and may struggle if you are working with a custom code obfuscator. 

### Code Analysis

When analyzing a block of code that contains JavaScript functions, it is useful to perform a web search on their function names to learn about what they do. A function like XMLHttpRequest is used by JavaScript to perform web requests such as GET and POST requests. The variables xhr.open and xhr.send are used to read and send GET and POST web requests. The function generateSerial sends a post request to the /serial.php #URL. 

### HTTP Requests

#### POST

We can use the #cURL tool to send a POST request when we use the -X switch and the POST parameter. The -s flag is also included in the following command to reduce the output to a manageable and readable amount.

>curl -s \http://SERVER_IP:PORT/ -X POST

The above command would only send a blank POST request. WE can include content using the -d switch and the content 'param1=sample':

>curl -s \http://SERVER_IP:PORT/ -X POST -d "param1=sample"

The result from sending this POST request to the server address /serial.php returns the following output:

>N2gxNV8xNV9hX3MzY3IzN19tMzU1NGcz

This is encoded data that has undergone obfuscation.

### Decoding

We are presented with another example of an encoded POST response with the output:

>ZG8gdGhlIGV4ZXJjaXNlLCBkb24ndCBjb3B5IGFuZCBwYXN0ZSA7KQo=

Again - this is encoded data that has been obfuscated by the server. It is likely that this is encoded by one of three common methods of encoding:

- #base64 
- #hexadecimal
- #rot13

### Base64

Base64 encoding is often used in the case where we want to avoid the presentation of special characters. Base64 converts all characters to alphanumeric values with the exception of + and -. 

An indicator that base64 is being used is the presence of an equals sign ( = ) used as padding. Base64 strings occur in multiples of four - if there are only three characters present, the last character will be represented by the equals sign ( = ). 

To encode text into base64 within #Linux, we echo the text and then pip it into the 'base64' command like the following example:

>echo \https://www.hackthebox.eu | base64

This would output the following encoded string:

>aHR0cHM6Ly93d3cuaGFja3RoZWJveC5ldS8K

Similarly, we can decode this same string by using the 'base64' command and the -d switch:

>echo aHR0cHM6Ly93d3cuaGFja3RoZWJveC5ldS8K | base64 -d

Which would return the predicted output:

>\https://www.hackthebox.eu

### Hexadecimal

#Hexadecimal or #hex encoding encodes each character into its corresponding #ASCII value from a table. You can view this table using the 'man ascii' command in #Linux. Hexadecimal can be recognized by the characters used - it will only include numbers 0-9 and letters a-f. 

In Linux, we can encode a string into hex by echoing it into the xxd -p command and switch:

>echo \https://www.hackthebox.eu/ | xxd -p

This would return the following output:

>68747470733a2f2f7777772e6861636b746865626f782e65752f0a

Similarly, we can decode this value with the -r switch:

> echo 68747470733a2f2f7777772e6861636b746865626f782e65752f0a | xxd -p -r

This would output our initial input:

>\https://www.hackthebox.eu/

### Caesar/Rot13

Caesar cipher is a very old method of obfuscation that shifts each character by a fixed number. This means a cipher of 1 will shift a to b and b to c. The rot13 cipher is very common and shifts each character 13 characters forward.

>In rot13 \http://www would become uggc://jjj

It is detectable by recognizing the patterns in text, but there is no sure way to know just by looking at it. There are online tools that can be used to decode this encoding method.

There is no default method of encoding to rot13 in Linux, but we can use the following command to do so:

>echo \http://www.hackthebox.eu/ | tr 'A-Za-z' 'N-ZA-Mn-za-m'

This would produce the following output:

>uggcf://jjj.unpxgurobk.rh/

Similarly we can decode it with the same command since there are 26 characters and the shift is 13:

>echo uggcf://jjj.unpxgurobk.rh/ |  tr 'A-Za-z' 'N-ZA-Mn-za-m'

### Cipher Identifier

If we come across text that we believe has been encoded, we can submit it to a tool like [Cipher Identifier](https://www.boxentriq.com/code-breaking/cipher-identifier 'cipher identification tool') to determine the type of encoding used.

### Encryption

Encryption is a key based method of encoding that further complicates the obfuscation process and is not compatible with the decoding and encoding methods listed above.