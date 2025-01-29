# SSH-Key Authentication

Check if there's an existing SSH Key active in GitHub account. If there's none, follow the steps below.

- Go to your Github `Settings > SSH and GPG keys`

### How to [generate a new SSH key and add to ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

1. Open terminal

2. Paste the text below, replacing the email used in the example with your GitHub email address.

- `ssh-keygen -t ed25519 -C "your_email@example.com"`

3. Add a passphrase of you choice. It should be long, complex and not easily guessable.

- Remember to store your passphrase securely and do not share it with others. If you find it difficult to create a passphrase, you can use a passphrase generator tool to help you generate a secure passphrase.

4. A public key is now saved in your local drive. A key fingerprint will be given as an example below.

- `SHA256:*******...`

5. Convert the public key to `OpenSSH public key format`. Open a terminal and run the following command to convert your SSH key to the OpenSSH public key format:

- `ssh-keygen -y -f ~/.ssh/id_rsa > ~/.ssh/id_rsa.pub`

6. Verify the Converted Public Key: You can view the contents of the converted public key to ensure it is in the correct format:

- `cat ~/.ssh/id_rsa.pub`

* Here's an example of what the commands and output might look like:
  `$ ssh-keygen -y -f ~/.ssh/id_rsa > ~/.ssh/id_rsa.pub`
  `$ cat ~/.ssh/id_rsa.pub`
  `ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEArU1N6k... your_email@example.com`

7. Copy the converted key and paste it to your SSH key Github account.

## Reference

- [Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- [https://docs.github.com/en/authentication](Github Authentication)
