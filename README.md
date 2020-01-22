# vps_config

Automate VPS configuration with Ansible

## Requrements

I assume that pass manages all credentials in your local environment and provides Ansible with them. gpg also needs to ahtorize when retrieving stored passwords from its list. I used the following libraries:

* [pass](https://www.passwordstore.org/)
* [GPG Suite](https://gpgtools.org/)

Please consult the homepages, how to install and use each library.

## Example of pass

Before using pass, don't forget to generate gpg key.

```bash
brew install pass
pass init example@email.com
```