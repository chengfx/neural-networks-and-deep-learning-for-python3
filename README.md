#Introduction
This repository contains code samples for Michael Nielsen's book [Neural Networks and Deep Learning][1].

The code is modified or python 3.x. The original code is written for Python 2.6 or Python 2.7 and you can find the original code at [github][2]. The origin purpose for which I create this repository is to study Neural Network and help others who want to study it and need the source code. I'm quite willing to discuss it with anyone.
##Installing python3.x
You should install [python interpreter][3] on your computer before you clone this repository. The latest version of python now is python3.5.2 which is intalled on my computer. The steps of intalling python are very easy and you can use [Google][4] if you have any question about it.
##Installing NumPy and SciPy
It is a little difficult for python3.x to install [NumPy][5] and [SciPy][7]. 

Numpy is the fundamental package for scientific computing with python. it contains among other things:
* a powerful N-dimensional array object
* sophisticated(broadcasting) funcions
* tools for integrating C/C++ and Fortran code
* useful linear algebra, Fourier transform, and random number capabilities

The NumPy installation package can be found [here][6]. The names of intallation packages are follow the following rules:

	cpxx_OperatingSystem_The architecture of CPU

cpxx means the interpreter of python whose verison is python x.x is written by C. OperatingSystem can be Macoxsx,linux or win. The architecture of CPU can be x86, amd64 or i686.

SciPy is open-source software for mathematics, science, and engineering. The SciPy library depends on NumPy.The SciPy library is built to work with NumPy arrays, and provides many user-friendly and efficient numerical routines for numerical integration and optimization. The rule of name of SciPy is similar to that of Numpy.

So choose the version which is suitable for your computer and the interpreter of python.

##Installing matplotlib
matplotlib is very easy to be installed in order to plot some figures using MATLAB syntax. The only thing you need to do is just type the following command in your bash

	pip install matplotlib

##Modifying code samples for python 3.x
Now we could make some changes for code samples in order to run our code samplesthrough python 3.x interpreter after some fundamental packages has been installed. The differences between files for python 2.x and python 3.0 will be listed below and some descriptions have been added for this changes.

###mnist_loader.py
The functions of [mnist_loader.py][8] file are load the training data, validation data and test data and change their form which is conveniently manipulated by python. The codes we have changed are

> [Line 13][9]:    import pickle

> Unmodified: import cPickle

> [Line 43][10]:    training_data, validation_data, test_data = pickle.load(f,encoding='iso-8859-1')

> Unmodified: training_data, validation_data, test_data = cPickle.load(f)

> [Line 71][11]:    training_data = list(zip(training_inputs, training_results))

> Unmodified: training_data = zip(training_inputs, training_results)

> [Line 73][12]:    validation_data = list(zip(validation_inputs, va_d[1]))

> Unmodified: validation_data = zip(validation_inputs, va_d[1])

> [Line 75][13]:    test_data = list(zip(test_inputs, te_d[1]))

> Unmodified: test_data = zip(test_inputs, te_d[1])

Module cPickle is written by c for python 2.x and it has been cancelled in python 3.x. So we instead use statement "import pickle". The effects of module pickle are depend on the version of python. If we don't pass the encoding argument python 3.x will throw an exception. For Line 71,73,75 the only thing we need to do is just make a convertion. In python 3.x the object returned by zip() isn't a list. It is an object which returns the successive items of the desired sequence when we iterate over it. It doesn't really make the list, thus saving space. we say such an object is iterable, that is, suitable as a target for functions and constructs that expect something from which they can obtain successive items until the supply is exhausted. So such "len(iterable object)" is wrong and we have to convert it into a list using "list(len(iterable object))".


[1]: http://neuralnetworksanddeeplearning.com/
[2]: https://github.com/mnielsen/neural-networks-and-deep-learning
[3]: https://www.python.org/downloads/
[4]: https://www.google.com
[5]: http://www.numpy.org/
[6]: https://pypi.python.org/pypi/numpy
[7]: https://pypi.python.org/pypi/scipy
[8]: ./mnist_loader.py
[9]: ./mnist_loader.py#L13
[10]: ./mnist_loader.py#L43
[11]: ./mnist_loader.py#L71
[12]: ./mnist_loader.py#L73
[13]: ./mnist_loader.py#L75



