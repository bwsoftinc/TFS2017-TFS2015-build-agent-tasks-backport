---
title: Copy Files over SSH TFS build agent task
---

 #Copy Files over SSH (SCP)

Copy files from a source folder to a target folder on a remote machine over a SSH connection.

Connect to a remote machine using SSH and copy source files matching _minimatch_ patterns to a target folder on a remote machine.  
File transfer protocols supported:
* SFTP
* SCP over SFTP

## Requirements

Target maching running SSH server that accepts username/password combo.

## Options

|**Option**|**Description**|
|----------|---------------|
|SSH endpoint|The hostname or ip address of the remote machine|
|SSH username|The username credential for connecting to the remote machine|
|SSH password|The password credential for connecting to the remote machine|
|SSH port|The port number the SSH service is running on the remote machine|
|Source folder|The source folder for the files to copy to the remote machine. Empty is the root of the repo<br/><ul><li>Use [variables](https://go.microsoft.com/fwlink/?LinkID=550988) if files are not in the repo.</li><li>Example: `$(agent.builddirectory)`</li><li>Names containing wildcards such as `*.zip` are not supported</li></ul>|
|Contents|File paths to include as part of the copy.<br/><ul><li>Supports multiple lines of minimatch patterns.</li><li>Default is `**` which includes all files (including sub folders) under the source folder.</li><li>Example: `**/*.jar \n **/*.war` includes all jar and war files (including sub folders) under the source folder.</li><li>Example: `** \n !**/*.xml` includes all files (including sub folders) under the source folder but excludes xml files.</li></ul>|
|Target folder|Target folder on the remote machine to where files will be copied.<br/><ul><li>Example: `/home/user/MySite`</li></ul>|
|Clean target folder|If this option is selected, all existing files in the target folder will be deleted before copying.|
|Overwrite|If this option is selected (the default), existing files in the target folder will be replaced.|
|Flatten folders|If this option is selected, the folder structure is not preserved and all the files will be copied into the specified target folder on the remote machine.|
