# class101
simple django openshift tutorial

This demo is written for working from a RHEL 7 client.

## Prework for Week #1

Nice to have (but not required):

* Create a public Github repo, e.g. class101
* Create your ssh keys, e.g. id_rsa_git and id_rsa_git.pub
* Add your public key to Git (Settings -> SSH and GPG keys)
* Add this stanza to your ~/.ssh/config

```
Host github.com
User <your github user>
IdentityFile ~/.ssh/id_rsa_git
ForwardX11 no
```

* Test your github ssh keys

```
ssh -T git@github.com
You've successfully authenticated, but GitHub does not provide shell access.
```

## Week #1
What will be covered:

* discussion on modern web development
* setup python on RHEL7 (on windows or free pythonanywhere account left to the user)

```

virtualenv ~/.virtualenvs/class101
source ~/.virtualenvs/class101/bin/activate
echo '# Using python 2.7.5' > requirements.txt
pip install pip --proxy <proxy> --upgrade

```
