# Linux File Permissions

## Scenario:
You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure.

Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.

*[Google Docs Link](https://docs.google.com/document/d/1kNKLL0se_poximmwKpfahA_LdXjkcCsaepFtWx_BYcE/edit?usp=sharing)*

## The Project in Markdown Form

### Project description
I am mainly working with their research team to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure. My task is to examine existing permissions on the file system, and apply changes when necessary. To complete this task, I performed the following tasks:

#### Check file and directory details 
To check the details of files and directories, you can use the command:

`ls -l`

To check for hidden files in a directory, you can use the command:

`ls -a`

You can combine the two commands to display the details of all the files and directories, including the hidden files.

`ls -la`

### Describe the permissions string
a 10-character string begins each entry and indicates how the permissions on the file are set.

- The 1st character indicates the file type. The d indicates it’s a directory. When this character is a hyphen (-), it's a regular file.

- The 2nd-4th characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.

- The 5th-7th characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.

- The 8th-10th characters indicate the read (r), write (w), and execute (x) permissions for the owner type of other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for others.

- The second block of text in the expanded directory listing is the user who owns the file. The third block of text is the group owner of the file.

For Example:

```
-rw-rw-rw- 1 researcher2 research_team 46 Oct 14 18:40 project_k.txt
```

* '-' in the beginning means that it is a file.
* The 2nd-4th characters indicate the permissions for the User. In this case, the user (researcher2)  has permissions to read and write the file and doesn’t have permission to execute it, indicated by the hyphen (-) in the 4th character.
* The 5rd-7th characters indicate the permission for a Group. In this case, the group (research-team) has permissions to read and write the file.
* The 8th-10th characters indicate the permissions for Other. In this case, they have permission to also read and write the file.
In this specific file, all owner types have the same permissions.

### Change file permissions
To change the file permissions of a file, you can use the following command:

`chmod`

The chmod command requires two arguments. The first argument indicates how to change permissions, and the second argument indicates the file or directory that you want to change permissions for.

There are various ways you can use this command. By using math operators (+/-),
You can either add(+) or remove(-)  permissions to a file or directory. 

The organization does not allow others to have write access to any files. So let’s change the file permissions, and after looking back at the list, this is the file that we need to change the permissions of:

```
-rw-rw-rw- 1 researcher2 research_team 46 Dec 29 10:34 project_k.txt
```

I used the command: 

`chmod o-w project_k.txt`

In this command, there are two arguments:

In the first one, we are removing permissions to write(w) to others using the (-) symbol. To add or remove from the owner type of other, you use the keyword o.

Then in the second argument, we indicate the file in which we want to change the permissions of. In this case: project_k.txt.

### Change file permissions on a hidden file

The research team has archived .project_x.txt, which is why it’s a hidden file. This file should not have write permissions for anyone, but the user and group should be able to read the file. 

These are the current permissions:

```
-rw--w---- 1 researcher2 research_team 46 Dec 29 10:34 .project_x.txt
```

To change the permissions so that there are no write permissions for anyone, and to add a permission for the group for reading the file, i used this command:

`chmod u-w,g+r-w .project_x.txt`

In this command, the permission to write for the user is removed with u-w. Then, separated by the comma, the permission to read is added, and to write is removed for the group. 
Always be sure to start the name of a hidden file with a period (.).

### Change directory permissions
The files and directories in the projects directory belong to the researcher2 user. Only researcher2 should be allowed to access the drafts directory and its contents.

This is the drafts directory’s current permissions:
```
drwx--x--- 2 researcher2 research team 4096 Dec 29 10:34 drafts
```

To change the permissions so that only researcher2 can access the directory, We need to remove the execute permission for the group from the drafts directory. I used the following command:

`chmod g-x drafts`

In this command, g indicates the group owner type, and -x indicates that the permission to access the directory is removed for the group. Then it is followed by the name of the directory, In this case it is drafts.

Summary
I reviewed the permissions for files and directories in the projects directory by running `ls -la` to gather the necessary information. Based on this, I adjusted the permissions to align with my organization's authorization requirements by using the `chmod` command multiple times.
