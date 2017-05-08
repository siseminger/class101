## class101
simple django openshift tutorial

This demo is written for working from a RHEL 7 client.

### Prework for Week #1

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

### Notes on python
Python is space sensitive.  To make your life easier, and to follow recommended style

* Don't use tabs
* Indent 4 spaces
* To facilate this add this line to your `~/.vimrc`:

```
set ai et ts=4 sw=4 sts=4 nu ru

# Or, put this one line here 
set modeline
# and add a line to each file as shown here

```


### Week #1
What will be covered:

* discussion on modern web development
* setup python on RHEL7 (on windows or free pythonanywhere account left to the user)

```
git clone git@github.com:johnedstone/class101.git
cd class101
git config user.name "johnedstone"
git config user.email "johnedstone@gmail.com"
git config push.default simple

virtualenv ~/.virtualenvs/class101
source ~/.virtualenvs/class101/bin/activate
echo '# Using python 2.7.5' > requirements.txt
pip install pip --proxy <ip:ort> --upgrade
deactivate

source ~/.virtualenvs/class101/bin/activate
pip install --proxy <ip:port>  django
pip freeze
echo 'Django==1.11.1' >> requirements.txt

# https://docs.djangoproject.com/en/1.11/intro/tutorial01/
django-admin startproject mysite

python manage.py runserver
# Log into to your server from elsewhere with ssh -x -C -L 8000:127.0.0.1:8000
# and then request from browser http://127.0.0.1:8000

# Alternative, edit mysite/mysite/settings and set ALLOWED_HOST = ['*']
python manage.py runserver 0.0.0.0:8000
# request from browser http://fqdn:8000

git branch -a
git remote -v
git status
git add .
git commit -m 'my first commit'
# git commit -am 'my first commit'
git push origin master
# git push
```


#### If we have time in in Week #1
* lets look at the `mysite/mysite/settings`:
    * database
    * other stuff
* let's look at mysite/mysite/urls.py
* And ...

```
    cd mysite
    python manage.py makemigrations
    python manage.py makemigrations
    python manage.py migrate
    python manage.py createsuperuser
    python manage.py runserver

    # Browse to /admin
    # And then let's look at the uncoupling

    vim mysite/mysite/urls.py
    python manage.py runserver
```

##### vim: ai et ts=4 sts=4 sw=4 nu ru
