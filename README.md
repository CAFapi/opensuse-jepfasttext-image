# openSUSE and JepFastText image

This project builds on the openSUSE JDK8 image [here](https://github.com/CAFapi/opensuse-java8-images/blob/develop/src/main/docker/jdk/Dockerfile), Python 3, Jep and fastText are then installed on the image.  
**Jep** is a library used for executing python scripts from within java code, more information on Jep can be found [here](https://github.com/ninia/jep/blob/master/README.rst).  
**FastText** is an open-source, free, lightweight library that allows users to learn text representations and text classifiers for language detection, more information on fastText can be found [here](https://github.com/facebookresearch/fastText/).

### Tini
[Tini](https://github.com/krallin/tini) is pre-installed in the container.  If the image entrypoint is not overwritten then it will be automatically used.

### Startup Scripts
Any executable scripts added to the `/startup/startup.d/` directory will be automatically run each time the container is started (assuming the image entrypoint is not overwritten).

### Pre-Installed Startup Scripts

#### Certificate Installation
The image comes pre-installed with a startup script which provides a mechanism to extend the CA certificates which should be trusted.

#### 