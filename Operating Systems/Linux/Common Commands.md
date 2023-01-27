# **GENERAL STUFF**
**Echo** -> Prints to screen

# **DIRECTORY/FILE STUFF**
**Ls** -> lists files and folders
**ls -a**: List all files, including hidden files:
**CD** -> Change Directory
**Pwd** -> Print your current Directory
**Mkdir** -> Make a new folder
-**p** : Make a folder hierarchy: mkdir /tmp/test/test/potatofolder
**Rm** -> deletes a file
-**r** : Deletes a folder
**Cp**  -> copy file to another location
-**r** : copy folder to another location
**Mv** -> move file to another location (include file name, can rename if want)
**Touch** -> create a file
**Cat** -> show file contents

# **USER STUFF**
**Whoami** -> shows current user
**Id** -> show current users id
**Su** `user` -> change to another user
**Sudo** -> run whatever command as root user

# API Stuff
### cURL
`sudo apt install curl` or
`brew install curl`

curl (short for "Client URL") is a command line tool that **enables data transfer over various network protocols**. It communicates with a web or application server by specifying a relevant URL and the data that need to be sent or received.

```bash
#Example command
curl --request POST \\
  --url <https://api.sendgrid.com/v3/mail/send> \\
  --header 'Authorization: Bearer YOUR_API_KEY' \\
  --header 'Content-Type: application/json' \\
  --data '{"personalizations": [{"to": [{"email": "recipient@example.com"}]}],"from": {"email": "sendeexampexample@example.com"},"subject": "Hello, World!","content": [{"type": "text/plain", "value": "Heya!"}]}'
```

# Misc
You can separate commands by ; if you want to use multiple.
Example: cd <location>; mkdir <folder>; pwd (changes directory, makes a folder, prints directory)