# iPython Install for Mac
virtualenv 환경에서 iPython 설치


```shell
# 1.Homebrew 설치
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# 2. python 설치 (PATH는 달라질 수 있음)
$ brew install python 
$ vim ~/.bash_profile
export PATH=/usr/local/bin:$PATH

# 3. virtualenv 설치
$ pip install virtualenv
$ cd ~/Desktop
$ virtualenv venv
$ source venv/bin/activate

# 4. numpy 설치
(venv) $ pip install numpy

# 5. SciPy 설치
(venv) $ brew install gcc
(venv) $ pip install scipy

# 6. mataplotlib 설치
(venv) $ pip install matplotlib

# 7. iPython 설치
(venv) $ pip install ipython
(venv) $ ipython
Python 3.6.0 (default, Mar  4 2017, 12:32:34) 
Type 'copyright', 'credits' or 'license' for more information
IPython 6.2.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: 

# (Addon). iPython notebook 설치
(venv) $ pip install ipython[zmq,qtconsole,notebook,test]
```

