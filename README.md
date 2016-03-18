# tensorflow_installation_ubuntu
###All the process can be found from:   
[Tensorflow os setup](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/g3doc/get_started/os_setup.md)


###Update python related packages.   
```
sudo apt-get install python-pip python-dev
```
###Clone tensorflow to local
```
git clone --recurse-submodules https://github.com/tensorflow/tensorflow
```
###Install dependences for Bazel:   
#####If in ubuntu 14.04, do below:   
```
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
```
#####if in ubuntu 15.10, do below:   
```
sudo apt-get install openjdk-8-jdk
```
#####And then both on 14.04 or 15.10, do below:   
```
sudo apt-get install pkg-config zip g++ zlib1g-dev unzip
```
#####Installing bazel:   
```
wget https://github.com/bazelbuild/bazel/releases/download/x.x.x/bazel-x.x.x-installer-<os>-<arch>.sh
chmod 764 bazel-x.x.x-installer-<os>-<arch>.sh
./bazel-x.x.x-installer-<os>-<arch>.sh --user
echo "export PATH=${PATH}:${HOME}/bin"
```
#####Create pip package and install
```
bazel build -c opt //tensorflow/tools/pip_package:build_pip_package
```
>>That's really take time if the network is pool...
