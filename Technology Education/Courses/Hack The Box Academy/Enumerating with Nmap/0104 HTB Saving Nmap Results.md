# Saving Nmap Results

### Nmap Formats

We will need to save data from our scans each time we perform one in a professional setting. Nmap is able to generate save files in three formats:

- -oN for normal output with the extension .nmap
- -oG for Grepable output with the .gnmap file extension
- -oX for #XML output with the .xml extension
- -oA to save the results in all three formats 

We can save our nmap output in all three file formats in three files with their respective extension titled 'target' with the following command:

>sudo nmap 10.10.2.28 -p- -oA target

If you do not specify the file path at the end, the data will be saved to the current directory.

Use the ls command to list the three newly created files.

Use the cat command to read the data in the three newly created files:

>cat target.nmap

>cat target.gnmap

>cat target.xml

### Style Sheets

We can beautify our output results by using the XML file to generate an #HTML report that is easily readable. We use the xsltproc tool to achieve this with the following command:

>xsltproc target.xml -o target.html

We can now open this HTML file in our browser to view the nicely presented data.