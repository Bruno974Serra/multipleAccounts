# Multiple Accounts On The Same Machine | Mac

## Check if there is any changes to the SSH github docs

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

## Open terminal and paste command to generate ssh key, but using github email address.

`ssh-keygen -t ed25519 -C "your_email@example.com"`

### You will get a prompt to enter a file path to save the key.

**Enter file in which to save the key (/Users/your_directory/.ssh/id_ed25519):**

Enter the complete path as below:
`/Users/your_directory/.ssh/name_of_your_company_or_personal_account`

## You will get a prompt to add a passphrase for more security

1. Enter passphrase (empty for no passphrase):
2. Enter same passphrase again:

## You will get a prompt as Your identification has been saved in the path given. There will be 2 files.

1. private key:

`/Users/your_directory/.ssh/name_of_your_company_or_personal_account`

2.  public key:

`Your public key has been saved in /Users/your_directory/.ssh/name_of_your_company_or_personal_account.pub`

## Add the private key to the ssh-agent

`ssh-add ~/.ssh/name_of_your_company_or_personal_account`

# Modify config file
>This automatically load keys into the ssh-agent and store passphrases in your keychain.

## First, check to see if your ~/.ssh/config file exists in the default location.

`open ~/.ssh/config`

## If the file doesn't exist, create the file.

`touch ~/.ssh/config`

## Open your ~/.ssh/config file, then modify the file to contain the following lines. If your SSH key file has a different name or path than the example code, modify the filename or path to match your current setup.

`# Bruno Personal
Host personal.github.com
HostName github.com
User git
IdentityFile ~/.ssh/name_of_your_company_or_personal_account`
