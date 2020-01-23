# vps_config

Automate VPS configuration with Ansible

## Requrements

You must install ansible.

```bash
brew install ansible
```

I also use the following libraries:

* [pass](https://www.passwordstore.org/)
* [GPG Suite](https://gpgtools.org/)

I assume that pass manages all credentials in your local environment and provides Ansible with them. gpg also needs to ahtorize when retrieving stored passwords from its list. 

To know how to install and use each library, please consult the homepages  In addition to those, pyenv is useful to manage the different versions of python. See [pyenv repository](https://github.com/pyenv/pyenv). 

## Example of pass

Before using pass, don't forget to generate gpg key that is recognized by email.

```bash
brew install pass
pass init example@email.com
pass init -p host_name example@email.com
```

To insert the password you already have, use insert subcommand.

``` bash
pass insert host_name/root
```

You can be easy to get password from password-store.

```bash
pass host_name/root
```

## Usage

After git cloning, you get to the project folder and run the following command.

```bash
ansible-playbook -i hosts setup.yml
```

You enter a host name, a user name, and  an email address. The playbook manages ssh-related configuration from key generation to key distributeion.

## Note

I hired the interactive way to avoid credentials information to be stored in the git repository.