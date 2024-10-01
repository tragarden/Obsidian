### Overview

You will create a portfolio document that demonstrates your ability to manage and examine file permissions. You will explain the commands used and answer questions related to the process.

### Scenario

The following description is about a lab where we managed owner permissions based on the following premise:

You are a security professional for an organization that oversees a research team. You need to set authorization rules and permissions abiding by the principle of least privilege. This will involve modifying permissions to authorize the correct users and groups for access.

### Project 

This project will examine the permissions associated with the directory /home/researcher2/projects.

#### Examine Directory Permissions

If we use the 'pwd' command, we can see that the lab begins in the /home/researcher2 directory:

>pwd
>/home/researcher2

We will then move into the projects subdirectory:

>cd projects
>pwd
>/home/researcher2/projects

Then we will list all the contents within the ~/projects directory with their permissions, including hidden directories:

>ls -la

This will produce output describing one directory and five files. One of the files is hidden:

>drwx--x--- 2 researcher2 research_team 4096 Feb 10 13:34 drafts
>-rw-rw-rw- 1 researcher2 research_team 46 Feb 10 13:34 project_k.txt
>-rw-r----- 2 researcher2 research_team 46 Feb 10 13:34 project_m.txt
>-rw-rw-r-- 1 researcher2 research_team 46 Feb 10 13:34 project_r.txt
>-rw-rw-r-- 1 researcher2 research_team 46 Feb 10 13:34 project_t.txt
>-rw--w---- 1 researcher2 research_team 46 Feb 10 13:34 .project_x.txt

#### Permissions String

The permissions string takes on the following format for full directory privileges to all owners:

>drwxrwxrwx

The 'd' indicates that the item is a directory. If this were a hyphen ( - ), it would indicate a file instead.
The first set of 'rwx' indicates enabled read, write, and executable privileges for the owner 'user'.
The first set of 'rwx' indicates enabled read, write, and executable privileges for the owner 'group'.
The first set of 'rwx' indicates enabled read, write, and executable privileges for the owner 'other'.

If any of the characters in the 'rwx' triplets were to be a hyphen ( - ), this would indicate that the owner does not have privileges for that specific case.


#### Change Permissions

We need to remove any write permissions for 'other' for any of these files or directories. We can see that the file 'project_k.txt' grants write permissions to the owner 'other'. This is a security risk as any user on the system would be able to create content within this file. 

We can change the permissions of the 'other' user for this file with the following command:

>chmod o-w project_k.txt

Now we have removed the ability for the owner 'other' to modify the contents of project_k.txt.

We also need to remove the read permission for the owner 'group' on the project_m.txt file as this should be a restricted file only accessed by the owner 'user' researcher2:

>chmod g-r project_m.txt

This command should have successfully removed the read permissions for the owner 'group'. We can check our changes with the following command:

>ls -la

This will output the following output with the correct changes to permissions:

>drwx--x--- 2 researcher2 research_team 4096 Feb 10 13:34 drafts
>-rw-rw-r-- 1 researcher2 research_team 46 Feb 10 13:34 project_k.txt
>-rw------- 2 researcher2 research_team 46 Feb 10 13:34 project_m.txt
>-rw-rw-r-- 1 researcher2 research_team 46 Feb 10 13:34 project_r.txt
>-rw-rw-r-- 1 researcher2 research_team 46 Feb 10 13:34 project_t.txt
>-rw--w---- 1 researcher2 research_team 46 Feb 10 13:34 .project_x.txt

#### Change Hidden File Permissions

We know that the file .project_x.txt is the hidden file in question, as indicated by the dot ( . ) at the beginning of the file name. This file has read and write privileges for the owner 'user' and write privileges for the owner 'group'.

We want to change permissions so that the owners 'user' and 'group' have read permissions but not write permissions. We can do this with the following command:

>chmod u-w,g-w,g+r .project_x.txt

This command should have removed write privileges for the owners 'user' and 'group', while adding the read privilege for the owner 'group' and the output for this file's permissions should be as follows:

>ls -la
>-r--r----- 1 researcher2 research_team 46 Feb 10 13:34 .project_x.txt

#### Manage Directory Permissions

Now we will modify the permissions of the directory '/home/researcher2/projects/drafts' so that only the owner 'user' researcher2 is able to access the drafts directory and all contents within it.

Once again you can check the permissions of the drafts directory and all contents with the following command:

>ls -la

This will output the following information about the drafts directory:

>drwx--x--- 2 researcher2 research_team 4096 Feb 10 13:34 drafts

The owner 'group' has execute permissions within this directory. We can remove them with the following command:

>chmod g-x drafts

This should have successfully removed the execution rights for the owner 'group' for the drafts directory. We can check our modification with the following command:

>ls -l

The entry for the directory 'drafts' should now reveal that owner 'group' no longer has executable permissions:

>>drwx------ 2 researcher2 research_team 4096 Feb 10 13:34 drafts

### Summary

This lab was about managing permissions using the 'chmod' command and checking the current state of all directories and files, including hidden files, using the 'ls -la' command. 

We removed the owner 'other' permissions for modifying the project_k.txt file. 

Removed read permissions for the owner 'group' on the project_m.txt to make the file restricted.

Removed write permissions for the owners 'user' and 'group' for the hidden file .project_x.txt while adding read permissions for the owner 'group'.

We lastly removed executable permissions for the owner 'group' within the 'drafts' directory.

This was an exercise to learn permission management, reading permissions, and revealing hidden files.

