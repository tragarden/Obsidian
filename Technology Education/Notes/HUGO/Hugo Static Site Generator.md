# Hugo 

#Hugo is a *static site generator* that is known for its **lightweight design** making it one of the fastest loading site frameworks available. Hugo is based on the #GO coding language, allowing it to use the native **multithreading** that GO provides.

#### Static Sites

Hugo is a *static site* - meaning that it will **present the same for any user** that views one of its pages. These **pages are hardcoded**, meaning that there is no interactive or algorithm-based changes that occur each time a page is loaded. This is very different from a dynamic site like Facebook - every page on Facebook is always changing and when you refresh a site page - it will not be the same as the last refresh.

#### Languages

Hugo is designed to use #markdown language as an alternative to #HTML, although html is still an acceptable language for design.

### Installing Hugo

To install Hugo, we need to **go to our C: drive** and **create a folder within that directory named 'Hugo'**. Once that folder is created, **create another folder within named 'bin'**. 

From here we can **go to the 'Releases' page on the Hugo GitHub** and seek out the Windows **AMDx64 zip file for download**. 

Once you download the zip folder for Hugo, **extract all files to C:\\Hugo\\bin\\** 

Now we can **open command prompt** ( #cmd ) and if we are in the C:\\Hugo\\bin\\ directory, we can ***run the following command*** to see if Hugo is recognized by the #OS.

> hugo version

While this may work - *change to a different directory and execute the same command*. You will notice that ***command prompt is unable to run the executable because it cannot be found***. This is because in our current state the OS can only run Hugo if we are in the exact directory Hugo is contained within. In order to execute from any directory, **we need to modify the path variable** to include Hugo.

#### Changing Path Variables

Go to #Windows search and type in 'environ' and select the application "**Edit the system environment variables**".

**Select "Environmental Variables..."** near the bottom of the window. This will list the User and System variables for your machine. 

Under User Variables, double-click "Path" or **select "Path" and choose "Edit..."**.

A new windows titled "Edit environment variable" should now be displayed. You will **select "New" and submit the following directory** as your new path:

> C:\\Hugo\\bin\\

Once you do that, close the three windows related to Environment variables and the command prompt window. ***IT IS IMPORTANT TO NOTE THAT THE PATH WILL NOT UPDATE UNTIL YOU OPEN A NEW COMMAND PROMPT WINDOW.***

You should now be able to execute Hugo from any directory on your operating system.

In your new command prompt, leave the C:\\Hugo\\bin\\ and submit the following to see if your pathing update was successful:

> hugo version

### Running Hugo

To begin working with Hugo, we can use the following command to **create our first site content folder**:

> hugo new site first_site

This will generate a new folder within the C:\\Hugo\\bin\\ directory called "first_site".

#### Site Directory Content

Within this folder you will see several new folders which include:

- archetypes
- assets
- content
- data
- i18n
- layouts
- static
- themes
- hugo.toml (file not folder)

#### Content Explanation

The '*content*' directory *holds all of your site content*. Any code that is used to build your site is stored within this folder.

The '*data*' folder can **serve as a #database** for your site. You can place files within this folder that contain data you want to display or utilize with your site.

The '*layouts*' folder is used to **generate universal designs that apply to all of the pages** of your site. For instance, if you created a default header, footer, or a navigation bar that you want to apply to every page on your site - place it within this folder.

The '*static*' folder **stores any static settings or images** that you want to apply to every page of your site. This is different than the layouts folder - think of it as a way you could apply an image or watermark to each page of your site. It is **unchanging and applied to each page** by default.

The '*themes*' folder allows you to **import a pre-designed theme** that you want to apply to all of your pages. 

'*hugo.toml*' is the **configuration file** for your site. You can manage the settings here.

### Themes

*Themes* are a way you can **use a pre-built site template**. You can use one of these themes as a base for your site and modify it if you are lacking a skillset in #HTML and #CSS. 

On the theme page from Hugo, you can find a theme that you like and click 'Download' which will take you to the GitHub page for the related code. You can **download the entire GitHub file straight into your themes folder** on your Hugo site project folder.

Click on the '*Clone or Download*' button at the top right of the GitHub page for the theme you are selecting. This **will generate the #HTTPS link to the repository** that you can **place within your themes folder**.

Alternatively you can **download a zip file and extract the contents into the themes folder**.

### Related:

- [Hugo](https://gohugo.io/ 'Hugo Site Generator Homepage')
- [Giraffe Academy YouTube Guide](https://www.youtube.com/watch?v=qtIqKaDlqXo&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3 'A guide I followed to learn Hugo')
- [Hugo Themes](https://themes.gohugo.io/ "Hugo Official Theme Page")
- [Giraffe Academy Theme](https://github.com/giraffeacademy/ga-hugo-theme)