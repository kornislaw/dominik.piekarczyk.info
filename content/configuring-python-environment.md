Title: Python env for DS
Subtitle: So if I don't write anything here, the tags' div will not be in line...
Date: 2015-10-19 17:20
Category: Data Science
Tags: programming, python, environment
Illustration: vim.jpg


### virtualenv and virtualenvwrapper

#### Set up


Adding settings to `.zshrc`:

```bash
echo "export WORKON_HOME=~/.virtualenvs" >> ~/.zshrc
echo "source /usr/local/bin/virtualenvwrapper.sh" >> ~/.zshrc 
```
(note: you may be using Bash, then it should be `.bashrc`, not `.zshrc`)


#### Usage

* Create a new env:
 * `mkvirtualenv your_env_name`
* Switch to an env:
 * `workon ` [TAB] and choose an env
* Use Python 3:
  * `mkvirtualenv -p /usr/local/bin/python3.4 <virt-env-name>`


#### More info

* [StackOverflow: Where should virtualenvs be created?](http://stackoverflow.com/questions/12184846/where-should-virtualenvs-be-created)
* [virtualenvwrapper docs](http://virtualenvwrapper.readthedocs.org/en/latest/)
* [A non-magical introduction to Pip and Virtualenv for Python beginners](http://www.dabapps.com/blog/introduction-to-pip-and-virtualenv-python/)
  * A very verbose introduction to virtualenv


### BitBucket

* Generate keys: `ssh-keygen -f ~/.ssh/id_rsa -C "id_rsa"`
* Copy public key: `cat ~/.ssh/bitbucket.pub  | pbcopy`
* Paste here: `https://bitbucket.org/account/user/[username]/ssh-keys/`
* Test connection: `ssh -Tv git@bitbucket.org`
* Set up the the remote master: `git remote add origin git@bitbucket.org:[username]/[repo].git`
* Push to the master repo: `git push -u origin --all`

#### More info
* [Get code into Bitbucket fast using Atlassian SourceTree or the command line](https://answers.atlassian.com/questions/135886/how-to-push-repo-from-git)


## Backlog 

(to be moved somewhere else)

```bash
pip install -r requirements.txt
```