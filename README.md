# MxNet OSX Build

This project provides off-the-shelf binary packages of MxNet. ``Both Python 2.7 and 3.7 are supported now!``


# Releases


You can find releases in  [release page](https://github.com/TomHeaven/mxnet_osx_build/releases).

# Install Depenency

Install depenencies using Homebrew:

```
brew install openblas
brew install graphviz
```


# Installation for Python 2.7

First, ensure your CUDA driver and cudnn is installed properly, and copy dependencies in folder `usr_local_lib` to path `/usr/local/lib`. Also, install OpenMP using Homebrew.

```
sudo mkdir /usr/local
sudo mkdir /usr/local/lib
sudo cp usr_local_lib/* /usr/local/lib/
brew install libomp
brew link --overwrite libomp
```


Install the wheel package from this project:

```
pip install mxnet-XXX-pyX-none-any.whl

```

At last, you need to fix `libmxnet.so` path. It's installed to `/System/Library/Frameworks/Python.framework/Versions/2.7/mxnet/` for Python2 and `/usr/local/mxnet/` for Python3. We need to create a link of it to the Python site directory.

```
ln -s /System/Library/Frameworks/Python.framework/Versions/2.7/mxnet/libmxnet.so /Library/Python/2.7/site-packages/mxnet/libmxnet.dylib
```

The site path might be different if you are using Anaconda or Python2 from Homebrew. To identify an accurate installation path of your mxnet, try uninstall it by 

```
pip uninstall mxnet
```
Then replace `/Library/Python/2.7/site-packages/` in the command by your correct site path.




# Installation for Python 3

Install the wheel package from this project:


```
pip3 install mxnet-XXX-pyX-none-any.whl

ln -s /usr/local/mxnet/libmxnet.so /usr/local/lib/python3.7/site-packages/mxnet/libmxnet.dylib
```


Enjoy!


# Source Code

Source code from: [https://github.com/apache/incubator-mxnet](https://github.com/apache/incubator-mxnet)

# Related Links

If you need Tensorflow builds for osx, go to this page: [https://github.com/TomHeaven/tensorflow-osx-build](https://github.com/TomHeaven/tensorflow-osx-build)

If you need Pytorch builds for osx, go to this page: [https://github.com/TomHeaven/pytorch-osx-build](https://github.com/TomHeaven/pytorch-osx-build)

