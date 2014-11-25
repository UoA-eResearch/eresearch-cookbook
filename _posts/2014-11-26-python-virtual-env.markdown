---
layout: post
title:  "Python Virtual Environments"
date:   2014-11-26 12:04:29
categories: Recipe
---

### How to connect create a Python Virtual Environment

> *It is often useful to have one or more Python environments where you can experiment with different combinations of packages without affecting your main installation. Python supports this through virtual environments. The virtual environment is a copy of an existing version of Python with the option to inherit existing packages. A virtual environment is also useful when you need to work on a shared system and do not have permission to install packages as you will be able to install them in the virtual environment.* 

## Outline 

* Open a terminal 
* Setup the pip package manager
* Install the virtualenv package
* Create the virtual environment
* Activate the virtual environment
* Deactivate the virtual environment
* Optional: Make the virtual environment your default Python
* More: Python virtualenv documentation

## Requirements

* An installation of Python

## Jargon

Link to Jargon page with terms: terminal 

## Open a terminal 

The method you use to open a terminal depends on your operating system.

# Windows

Open the Windows Command Prompt (show path via Start menu and keyboard shortcuts)

# Mac OS / Linux

Open the Terminal program. This is usually found under Utilities or Accessories.

## Setup the pip package manager

Check to see if your Python installation has pip. Enter the following in your terminal:

{% highlight bash %}
pip -h
{% endhighlight %}

If you see the help text for pip then you have pip installed, otherwise [download and install pip](https://pip.pypa.io/en/latest/installing.html)

## Install the virtualenv package 

The virtualenv package is required to create virtual environments. You can install it with pip:

{% highlight bash %}
pip install virtualenv
{% endhighlight %}

## Create the virtual environment 

To create a virtual environment, you must specify a path. For example to create one in the local directory called 'mypython', type the following:

{% highlight bash %}
virtualenv mypython
{% endhighlight %}

## Activate the virtual environment

You can activate the python environment by running the following command:

# Mac OS / Linux

{% highlight bash %}
source mypython/bin/activate
{% endhighlight %}

# Windows

{% highlight bash %}
mypthon\Scripts\activate
{% endhighlight %}

You should see the name of your virtual environment in brackets on your terminal line e.g. (mypython).

Any python commands you use will now work with your virtual environment

## Deactivate the virtual environment

To decativate the virtual environment and use your original Python environment, simply type 'deactivate'.

{% highlight bash %}
deactivate
{% endhighlight %}

## Optional: Make the virtual environment your default Python



## More: Python virtualenv documentation

For more detailed information, see the offical [virtualenv documentation](http://virtualenv.readthedocs.org/en/latest/virtualenv.html)
