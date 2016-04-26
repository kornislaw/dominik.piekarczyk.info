Title: Dataworkshop #1
Subtitle: A machine learning meetup
Slug: dataworkshop-01
Category: Data science
Tags: machine learning, python
Date: 2016-04-23

Today we had a machine learning meetup organised by my colleague [Vlad](http://vova.me) from GE Healthcare.

It was an introductory workshop and we took the topic of ["Titanic: Machine Learning from Disaster"](https://www.kaggle.com/c/titanic), the classic
challenge at [Kaggle](http://kaggle.com).

However, the solution that we were discussing for several hours was the most comprehensive I have ever seen
for this challenge. Vlad made a great work and his Jupyter notebooks are a fantastic material for studies.

You can find [Titanic notebooks on Github](https://github.com/dataworkshop/titanic).

### How to run dataworkshop notebooks

If you want to run these notebooks (not only to read them), you should also clone the [prerequisite](https://github.com/dataworkshop/prerequisite) project and install required libraries.

Run `python prerequisites/run.py` after which you will most likely see a lot of red warnings.

It may be a bit tricky to get all green, so let me share explain what I had to do to install everything successfully.
This is valid for OSX, but I believe it will be helpful for other systems as well.

#### Make virtualenv
First thing to do is making a new virtualenv. Don't install new libraries into your system copy of python, otherwise sooner or later you will get into trouble.

`mkvirtualenv dataworkshop -p /usr/bin/python2.7`

I'm not happy with using `2.7` instead of `3.5`, by the way. But my rule of thumb is: *if it is not your project, use
what the author told you to use. If it's yours - make (at least) reasonable effort to keep it up to date with the current version.*

#### Install libraries

All libraries (except `xgboost`) you can install by running the following command:

`pip install seaborn ipython matplotlib ipython numpy pandas sklearn`

#### Install xgboost

Xgboost is a library that you need to clone from Github, then compile and set up as a library in your virtualenv.
There's [an installation guide](http://xgboost.readthedocs.org/en/latest/build.html) describing the process in detail.

What worked for me is the following:
```bash
git clone --recursive https://github.com/dmlc/xgboost
cd xgboost; cp make/config.mk ./config.mk; make -j4
./build.sh
cd python-package; python setup.py install
```

Then clean up:
```bash
cd ../..
sudo rm -rf xgboost
```

You should now see the library on the list by running: `pip list`


#### Matplotlib GUI issue with virtual envs
The biggest challenge I had was with installing `matplotlib` library under my virtual environment.
In [matplotlib's FAQ](http://matplotlib.org/faq/virtualenv_faq.html) I found information that *the GUI frameworks that matplotlib uses for interactive figures have some issues with virtual environments.*

In the FAQ there's a workaround for it, but a bit heavy for my taste.

Luckily, I found another solution on [StackOvervlow](http://stackoverflow.com/questions/21784641/installation-issue-with-matplotlib-python).
It is enough to create a file with a single setting.

```bash
mkdir ~/.matplotlib/
touch ~/.matplotlib/matplotlibrc
echo backend: TkAgg >~/.matplotlib/matplotlibrc
```

The notebook running matplotlib will warn you that this is an experimental feature,
but then everything works smoothly, so I wouldn't care much about it.
