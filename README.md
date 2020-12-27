# Python Katas
This repository provides some simple code katas in Python and an instruction on how to set up a Python project with a testing environment on your local (mac).

# Usage

## Install Python
Go to any directory and type
```
$ brew install python3
```
Use Python in the command line (and find joy in reading the Zen of Python by Tim Peters)
```
$ python3 
>>> import this
>>> quit()
```
Or play with Python on [Jupyter Notebook](https://jupyter.org/install) preferably on your local
```
$ pip install notebook
$ jupyter notebook
```
Then in your browser on [http://localhost:8888/](http://localhost:8888/) go to **New** -> **Python3** and start coding without tests :)

## Install a virtual environment
```
$ pip3 install virtualenv
```
Create your project directory
```
$ mkdir projectname
$ cd projectname
```
Inside your project directory create a virtual environment (that is a directory `venv` where all libraries of your project live)
```
$ virtualenv -p python3 venv
```
Activate the virtual env
```
$ . venv/bin/activate
```

## Install packages on your project
Create a file [requirements.txt](https://github.com/alexandrajulius/pythonKatas/blob/master/requirements.txt) and add your favourite packages to it. For now those will be:
* **pytest**: unit test framework
* **pyhamcrest**: matcher objects in assert statements
* **flake8**: static analysis / linters
* **mypy**: type annotation checks 

(`mypy` validates simple types such as `int`, `str`, `float`, `bool` out of the box. To validate more complex types such as `list`, `tuple`, `dict`, we have to import the types from the build-in library in the code, e.g. `from typing import Tuple`.)

Install the packages with
```
$ pip install -r requirements.txt
```
By running the this command the above packages will be installed only on your project. In this way you can provide different versions per project.

Add the created `venv` directory to your `.gitignore`. Developers who will work on your project will pull the `requirements.txt` from your repository and install all required packages with the above command.

## How to test
Run the test suites in your root directory
```
$ venv/bin/pytest -vvv
$ venv/bin/pytest binary_search/test_binary_search.py -vvv
```

## Author Contact
[alexandra.julius@gmail.com](mailto:alexandra.julius@gmail.com)
