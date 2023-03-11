Creating a new ssh key

*Run command: ~/.ssh first. This will navigate you to your ssh folder. This is where you will save your keys*

1. Run command:  ssh-keygen -t ed25519 -C “comment name”
* First prompt is for ssh key name
* Next prompt is for password (optional)


2. Cd to ~/.ssh folder 
3. There will be two keys in the folder (one private {ssh keyname} and one public {ssh keyname.pub} )
4. Run command: cat (ssh key name).pub
5. Copy ssh public key to clipboard
6. Navigate to Github settings
7. Go to SSH and GPG Keys tab
8. Click on New SSH key and name your key
9. Paste your key into the description (make sure the beginning of your key starts with ‘ssh’
10. Click Add SSH key
11. Go back to terminal and run command: chmod 400 {private key name}
12. Run command: Ssh-add {private key} (This authenticates the ssh key with our ssh agent)
13. Run Command: touch config  && chmod 600 config
14. Run Command: nano config
15. Type in the following information in config file: 
Host Github
User [Github Name]
        Port 22 (For ssh)
        IdentityFile ~/.ssh/”(your private Github key)”
        HostName https://www.github.com/
16. Save file and exit using command O to save, then command X to exit.


17. Run command: ssh git@github.com -T (This successfully authenticates connection between local host and remote host)Testing
