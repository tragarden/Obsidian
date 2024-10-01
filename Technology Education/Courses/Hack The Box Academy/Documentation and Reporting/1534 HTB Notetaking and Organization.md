# Notetaking

Notetaking should be performed in an organized way that results in a repeatable process. This will save time and allow our content to be read, understood, and navigated by others. Writing a final report is much easier when all of the precursory notes are well presented in an organized way.

### Details

When taking notes, it is advantageous to be detailed and verbose when writing them. It is infrequent for more information to be harmful. In the event that these notes need to be shared with teammates, it makes more sense to have an abundance of information that can be pared down than a lack of information.

### Methods

Each author will have their own preferred methods of notetaking and workflow for the various projects they will embark upon. These may be tweaked depending on circumstances specific to each scenario.

#### Suggested Structure

Hack the Box provides a suggested structure for taking notes and organizing the results and information revealed during penetration tests. 

The suggested structure is as follows:

- Attack Path - outline the path for an external test or for compromised hosts during an internal test. Include screenshots and command line ( #CLI) output at this stage so it can easily be copied and transferred to a final report

- Credentials - a collection of compromised credentials and login methods kept in a centralized location.

- Findings - create a subfolder for each finding that includes a written explanation paired with uncovered evidence like screenshots and command line output.

- Vulnerability Scan Research - a central sub-folder containing the discovered vulnerabilities and any research you conducted related to them. This will prevent you from performing the research a second time. 

- Service Enumeration Research - notes on services you have investigated paired with failed exploitation attempts along with possible vulnerabilities and misconfigurations.

- Web Application Research - notes on the related web applications you encounter during testing. These may be found through methods like sub-domain brute-force attempts. Externally enumerating sub-domains, scanning for web ports, and using Aquatone or EyeWitness to screenshot these discoveries are all procedures you should be documenting in this folder. This is also a great place to store default admin credentials for the discovered apps. 

- AD Enumeration Research - a record of the step-by-step process taken to enumerate the Active Directory.

- OSINT - notes on related information discovered through #OSINT.

- Administrative Information - having a central folder for contacting information related to other project stakeholders can be very useful. Project Managers ( #PM) and Points of Contact ( #POC), objectives and flags from the Rules of Engagement ( #ROE), and to-do lists should be stored here. This can serve as a repository for brainstorming ideas to be reviewed at a later time. 

- Scoping Information - information related to the scope of the project like #IP addresses and #CIDR ranges, #URL, #VPN, or Active Domain ( #AD) information. This folder will help you remain within the designated scope of the project.

- Activity Log - a high-level view of project tracking to make correlations and prevent repetition of tasks.

- Payload Log - track the payloads used throughout the project with file hashes for uploads and information about the upload location. This will help you keep track of the client environment.

### Tools

Choosing tools is often related to personal preference and each professional should use a combination of local and cloud solutions for various tools. There are pros and cons to both local and cloud solutions.

Cloud solutions may only be suitable for training and practice courses like #CTF exercises and labs. Outline is considered a great tool for cloud-based solutions with a local alternative as well.

Local solutions should be used for client engagements and managing their data during testing. Obsidian is considered a great tool for local data storage.

#Markdown language is standard for many of these tools so learning how to take notes using this format is standard.

The organization you are working within will have policy or contractual obligations about data storage methods and notetaking tools.

A list of tools is provided by hack the box and is shown below:

- CheeryTree
- Notion
- Notepad++
- Obsidian
- Visual Studio Code
- GitBook
- OneNote
- Cryptpad
- Evernote
- Sublime Text
- Outline
- Standard Notes

### Logging

All output from scans and attacks need to be logged and the raw output from tools used to do so must be stored. Being able to review log data is invaluable for correlation and correcting misunderstandings before publishing a final report.

#### Logging Exploits

The #Tmux application offers great logging features that will monitor and stored anything that has been typed into Tmux terminals. This will allow you to track exploitation attempts in order to correlate events later in your process. **If you do NOT have this information available, it will make you appear unprofessional and inexperienced to clients and peers.** 

Keeping track of failures and incomplete attempts is also worth logging. If you have little to no findings, this can act as evidence that you performed tests that did not yield useful results in the case that no real vulnerabilities or configuration problems are detected. This is useful in the final report so you can demonstrate the **lack** of issues with the client's networks so they can understand their current level of protection.

#### Tmux Configuration

Setting up Tmux can be done through the following methods:

- First, clone the Tmux Manager to the home directory:

>git clone \https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

- Next, create a .tmux.conf file in the home directory:

>touch .tmux.conf

- Next, cat this file out and ensure it contains the following contents:

>cat .tmux.conf

># List of plugins
>
>set -g \@plugin 'tmux-plugins/tpm'
>set -g \@plugin 'tmux-plugins/tmux-sensible
>set -g \@plugin 'tmux-plugins/tmux-logging
>
># Initialize TMUX plugin manager (keep at bottom)
>run '~/.tmux/plugins/tpm/tpm'

After this file is created and the contents are confirmed to be present, the file must be executed in the current session to inact the settings. 

#### Opening Tmux

Use the source command to allow the file settings to take effect:

>tmux source ~/.tmux.conf

Now you can begin a Tmux session with the following command:

>tmux new -s setup

### Working in Tmux

#### Installing Plugins

Once the session has been opened press the following key combinations to install the plugins:

>Ctrl + B
>Shift + I

#### Initiate Logging

Once the plugins are installed, you can begin logging the current session by pressing the following:

>Ctrl + B
>Shift + P

If logging has been successfully initialized, you will see a message stating that logging has been enabled and the associated output file.

#### Stop Logging

To stop logging, press the same key combination used to initiate logging:

>prefix + Shift + P

or use the exit command to end the current session:

>exit

Note that the log file will not populate until either logging is ended or the session is terminated. Once either of these occurs, the log file will show all commands and the related output in the log files.

#### Retroactive Logging

If you find yourself well into a session and realize that you never initiated logging, you can do so retroactively by pressing the following key combinations:

>Ctrl + B
>Alt + Shift + P

This will save the current pane in it's entirety. Please note however that Tmux does have a history-limit which only allows for a finite amount of lines to be saved when not actively logging input and output. This number can be increased or decreased by modifying the Tmux scrollback buffer. This is recommended as the default limits for the scrollback buffer are relatively small and may lead to lost data if not immediately modified. 

Add the following lines to the .tmux.conf file to extend the limits on the scrollback buffer:

>set -g history-limit 50000

#### Screenshots

Copy and pasting can be problematic when working with Tmux as the pasted version can be messy and confusing, especially if you are using multiple panes.

Take screen captures in Tmux with the following key combinations:

>Ctrl + B
>Alt + P 

This will output the screen capture of the Tmux panes to the designated file.

#### Pane Manipulation

You can split the main pane in Tmux by using the following key combinations:

To perform a vertical split:

>Ctrl + B + Shift + %

To perform a horizontal split:

>Ctrl + B + Shift + "

Move from pane to pane:

>Ctrl + B + 0

Clear pane history:

>Ctrl + B
>Alt + C

### Configuration of Tmux

The Tmux tool offers a lot of customization like changing the logging path, changing key bindings, opening with multiple panes, running multiple sessions, and many more features.

#### Additional Plugins

Some Tmux plugins recommended by Hack the Box include:

- tmux-sessionist - a tool for manipulating Tmux sessions from within the current session. This allows you to switch sessions, create new named sessions, terminating sessions without detaching Tmux, moving the current pane to a new session, among more options.

- tmux-pain-control - controls pains and provides intuitive key bindings for movement, sizing, and splitting panes.

- tmux-resurrect - a tool for restarting a Tmux environment after host restart with the ability to restore all previous sessions, windows, panes, running programs, Vim sessions, and more.

For more Tmux plugins, check out this extensive [Plugin List](https://github.com/tmux-plugins/list 'list of many tmux plugins').

For more information about Tmux, check out this [Cheat Sheet](https://mavericknerd.github.io/knowledgebase/ippsec/tmux/ 'tmux cheat sheet')and [YouTube Video](https://www.youtube.com/watch?v=Lqehvpe_djs 'video guide to Tmux').

### Artifacts

Artifacts are the traces, tracks, or footprints left behind after conducting scans and tests on a target host. This might mean files or accounts that were created, payloads that were executed, or any other evidence that someone was active on a host network. 

Artifacts need to be documented by what was used, where it was used, the file path used, and the removal status. All artifacts should be documented via file hashing and removed after testing is completed. Best practices mean documenting everything even in the case of removed items like web shells, payloads, and tools.

#### Accounts and Modifications

In the case of account creation or modification of system settings, these items should be tracked in the case that they cannot be reverted after testing is performed.

Some modifications to be aware of include:

- IP addresses that were changed
- Timestamps for changes
- Descriptions of changes
- Locations where changes were made
- Name of applications or services that were modified
- Name of accounts and passwords that were used or modified

Make sure you have written approval from a client before making any system modifications or performing any assessing that may change system stability or availability. This should be discussed during a project kickoff call to determine thresholds that the client accepts.

#### Evidence

In order to provide a useful final report deliverable, issues discovered should be clearly communicated along with the evidence that supports their validation and reproduction. Without this information, the security teams, developers, and system administrators will be challenged or unable to reproduce the tests you performed or implement fixes for the issues. They may not even be able to interpret the report without strong evidence and examples of the assessments and tests you performed.

#### What to Provide

Collect evidence of all tests performed even if they were unsuccessful. This will reveal to the client your thoroughness when testing their network. 

If you are only working through the command line, logging from Tmux may suffice as adequate evidence although this information will likely need to be formatted and cleaned up since literal terminal output may be difficult to interpret. For all other cases, you will need to provide screenshots of your work and output.

#### Storage

Storing evidence can be stored in a framework that is very similar to the system used for storing notes as previously described in this module. Having structured storage prevents forgetfulness, violation of the Rules of Engagement, and repetition.

Hack The Box has provided a base structure for tracking this information, which will likely need to be modified based on the needs of the user or specific circumstances.

The folder hierarchy is shown below:

- Admin
	- Scope of Work ( #SoW) that you are using, including notes from kickoff meetings, status reports, vulnerability notifications, and more.

- Deliverables
	- Contains deliverables to be included in the final report as you work through them. This is a skeletal version of your report and may include supplemental spreadsheets, slide decks, and more depending on client requirements.

- Evidence
	- Findings - contains each finding to be included in the final report to containerize evidence and piece together the walkthrough for the final report.

	- Scans 
		- Vulnerability Scans - export files when scanning for vulnerabilities.
		- Service Enumeration - Export files from enumeration tools like Nmap and Masscan, etc.
		- Web - export files from tools like Zap, Burp, EyeWitness, Aquatone, etc.
		- AD Enumeration - export #JSON files from BloodHound, #CSV files from PowerView or ADRecon, data from Ping Castle, Snaffler log files, CrackMapExec logs, Impacket logs, etc.

	- Notes - all notes related to the project.

	- OSINT - OSINT output from Intelx and Maltego that doesn't belong with Notes.

	- Wireless - for when wireless testing is not within the scope of the project.

	- Logging Output - logs from Tmux, Metasploit, or anything that doesn't belong with other Scan directories.

	- Misc Files - any Web Shells, payloads, scripts, or other files.

- Retest 
	- optional folder in case you will need to return after the initial assessment. This might be a replication of the original folder structure you used so that you can produce congruent documentation for easier comparison and correlation. This can be used to keep your retest data separate from your first test.


#### Script for Hierarchy

The following script can be run to generate the file structure defined above with the following command:

>mkdir -p ACME-IPT/{Admin,Deliverables,Evidence/{Findings,Scand/{Vuln,Service,Web,'AD Enumeration'},Notes,OSINT,Wireless,'Logging output','Misc Files'}, Retest}

This would create the following directory structure:

![[Pasted image 20240326131045.png]]

#### Obsidian

Obsidian allows us to combine folder structure and notetaking structure so that we can interact with notes and folders from the command line or from within Obsidian.

As we create files with either CLI or Obsidian, we will see the tree command output become populated with Markdown pages.

### Format and Redaction

There are times when censorship should be implemented in our screenshotting and documentation. This is needed when Credentials and Personally Identifiable Information ( #PII) is included and this information must be redacted along with obscene comments, language, and images.

When things are redacted, you can use annotations like arrows or highlighting to indicate where attention should be focused within the materials you produce.

Adding a border around an image can make it stand out from the background of the document.

Cropping out irrelevant information in screenshots is often performed.

Including the address / URL bar from the browser is useful for showing the URL you are interacting with.

#### Screenshots

It is advised that you avoid screenshots of terminal output and instead include terminal output in raw text form. This makes it easier to redact, keeps the information searchable, and to highlight the important aspects of the output. This lowers the size of the files and has a neater presentation in the end result. Clients should be able to copy and paste commands so they can easily reproduce your results.

It is important to ensure that terminal output has not been modified when it is presented as we want to have an exact representation of our work. Sometimes editing this output to shorten or remove unecessary output is acceptable if indicated by \<SNIP>. 

Never alter output or add content to terminal output.

Screenshots can be redacted through pixelation or blurring via tools like Greenshot, although this method is not foolproof and this blurring technique can be reversed to reveal the original content. Tools like Unredacter can be used to reverse these techniques.

Instead of blurring, black bars should be placed over sensitive information to ensure that it remains redacted. Ensure that the image is edited directly and doesn't simply have an additional layer placed onto the original image.

Using HTML/CSS to obscure text is not advised as this can easily be viewed by highlighting text or editing the page source.

### Terminal

When posting content from the terminal, usually only credential information should be redacted, including password hashes. In the case of hashes, the entire hash does not need to be censored - it is fairly standard to leave the last four characters of the hash to indicate that it is indeed a hash value.

Replace any credentials included within a block of text with the placeholders \<REDACTED> or \<PASSWORD REDACTED>.

Color coding within the terminal output can be used to highlight commands and relevant terminal output resulting from the command. This shows the audience the important parts of the output and what evidence they should be aware of. This simplifies the ability of the reader to implement the commands in their own attempts at performing your tests.

### What to Avoid

When performing tests for a client, we will likely view sensitive information like credentials, PII, criminal information, and legally discoverable information. When screenshotting and recording information, make sure that you do not include any sensitive information in your data storage and reporting.

### Resources:

- [HackTheBox Home Page](https://academy.hackthebox.com/ 'the home page for hack the box')
- [HTB 1534 Notetaking and Organization](https://academy.hackthebox.com/module/162/section/1534 'the page for this hack the box module 1534')
