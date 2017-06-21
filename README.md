$ mkdir my-scikit-learn
$ cd my-scikit-learn/
my-scikit-learn$ conda create --name my-scikit-learn python=3
Fetching package metadata .........
Solving package specifications: .

Package plan for installation in environment /path/to/anaconda3/envs/my-scikit-learn:

The following NEW packages will be INSTALLED:

    openssl:    1.0.2l-0     
    pip:        9.0.1-py36_1 
    python:     3.6.1-2      
    readline:   6.2-2        
    setuptools: 27.2.0-py36_0
    sqlite:     3.13.0-0     
    tk:         8.5.18-0     
    wheel:      0.29.0-py36_0
    xz:         5.2.2-1      
    zlib:       1.2.8-3      

Proceed ([y]/n)? y

#
# To activate this environment, use:
# > source activate my-scikit-learn
#
# To deactivate this environment, use:
# > source deactivate my-scikit-learn
#

my-scikit-learn$ source activate my-scikit-learn
(my-scikit-learn) my-scikit-learn$ conda install --name my-scikit-learn scikit-learn
Fetching package metadata .........
Solving package specifications: .

Package plan for installation in environment /path/to/anaconda3/envs/my-scikit-learn:

The following NEW packages will be INSTALLED:

    libgfortran:  3.0.0-1           
    mkl:          2017.0.1-0        
    numpy:        1.13.0-py36_0     
    scikit-learn: 0.18.1-np113py36_1
    scipy:        0.19.0-np113py36_0

Proceed ([y]/n)? y

numpy-1.13.0-p 100% |#######################################################################################| Time: 0:00:04   1.79 MB/s
scipy-0.19.0-n 100% |#######################################################################################| Time: 0:00:09   4.00 MB/s
scikit-learn-0 100% |#######################################################################################| Time: 0:00:04   2.51 MB/s
(my-scikit-learn) my-scikit-learn$ conda install --name my-scikit-learn matplotlib
Fetching package metadata .........
Solving package specifications: .

Package plan for installation in environment /path/to/anaconda3/envs/my-scikit-learn:

The following NEW packages will be INSTALLED:

    cycler:           0.10.0-py36_0    
    dbus:             1.10.10-0        
    expat:            2.1.0-0          
    fontconfig:       2.12.1-3         
    freetype:         2.5.5-2          
    glib:             2.50.2-1         
    gst-plugins-base: 1.8.0-0          
    gstreamer:        1.8.0-0          
    icu:              54.1-0           
    jpeg:             9b-0             
    libffi:           3.2.1-1          
    libgcc:           5.2.0-0          
    libiconv:         1.14-0           
    libpng:           1.6.27-0         
    libxcb:           1.12-1           
    libxml2:          2.9.4-0          
    matplotlib:       2.0.2-np113py36_0
    pcre:             8.39-1           
    pyparsing:        2.1.4-py36_0     
    pyqt:             5.6.0-py36_2     
    python-dateutil:  2.6.0-py36_0     
    pytz:             2017.2-py36_0    
    qt:               5.6.2-4          
    sip:              4.18-py36_0      
    six:              1.10.0-py36_0    

Proceed ([y]/n)? y

six-1.10.0-py3 100% |#######################################################################################| Time: 0:00:00 554.67 kB/s
(my-scikit-learn) my-scikit-learn$ python
Python 3.6.1 |Continuum Analytics, Inc.| (default, May 11 2017, 13:09:58) 
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import matplotlib.pyplot as plt
>>> from sklearn import datasets, svm, metrics
>>> iris = datasets.load_iris()
>>> digits = datasets.load_digits()
>>> digits.data
array([[  0.,   0.,   5., ...,   0.,   0.,   0.],
       [  0.,   0.,   0., ...,  10.,   0.,   0.],
       [  0.,   0.,   0., ...,  16.,   9.,   0.],
       ..., 
       [  0.,   0.,   1., ...,   6.,   0.,   0.],
       [  0.,   0.,   2., ...,  12.,   0.,   0.],
       [  0.,   0.,  10., ...,  12.,   1.,   0.]])
>>> digits.target
array([0, 1, 2, ..., 8, 9, 8])
>>> digits.images[0]
array([[  0.,   0.,   5.,  13.,   9.,   1.,   0.,   0.],
       [  0.,   0.,  13.,  15.,  10.,  15.,   5.,   0.],
       [  0.,   3.,  15.,   2.,   0.,  11.,   8.,   0.],
       [  0.,   4.,  12.,   0.,   0.,   8.,   8.,   0.],
       [  0.,   5.,   8.,   0.,   0.,   9.,   8.,   0.],
       [  0.,   4.,  11.,   0.,   1.,  12.,   7.,   0.],
       [  0.,   2.,  14.,   5.,  10.,  12.,   0.,   0.],
       [  0.,   0.,   6.,  13.,  10.,   0.,   0.,   0.]])
>>> plt.figure(1, figsize=(3, 3))
<matplotlib.figure.Figure object at 0x7f1055a63e48>
>>> plt.imshow(digits.images[-1], cmap=plt.cm.gray_r, interpolation='nearest')
<matplotlib.image.AxesImage object at 0x7f1049597630>
>>> plt.show()
>>> clf = svm.SVC(gamma=0.001, C=100.)
>>> clf.fit(digits.data[:-1], digits.target[:-1])
SVC(C=100.0, cache_size=200, class_weight=None, coef0=0.0,
  decision_function_shape=None, degree=3, gamma=0.001, kernel='rbf',
  max_iter=-1, probability=False, random_state=None, shrinking=True,
  tol=0.001, verbose=False)
>>> clf.predict(digits.data[-1:])
array([8])
>>> quit()
(my-scikit-learn) my-scikit-learn$ 
