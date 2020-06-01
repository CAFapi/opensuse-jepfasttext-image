# openSUSE and JepFastText image

This project builds on the openSUSE JDK11 image [here](https://github.com/CAFapi/opensuse-java11-images/), Python 3, Jep and fastText are then installed on the image.  
**Jep** is a library used for executing python scripts from within java code, more information on Jep can be found [here](https://github.com/ninia/jep/blob/master/README.rst).  
**FastText** is an open-source, free, lightweight library that allows users to learn text representations and text classifiers for language detection, more information on fastText can be found [here](https://github.com/facebookresearch/fastText/).

### Tini
[Tini](https://github.com/krallin/tini) is pre-installed in the container.  If the image entrypoint is not overwritten then it will be automatically used.

### Startup Scripts
Any executable scripts added to the `/startup/startup.d/` directory will be automatically run each time the container is started (assuming the image entrypoint is not overwritten).

### Pre-Installed Startup Scripts

#### Certificate Installation
The image comes pre-installed with a startup script which provides a mechanism to extend the CA certificates which should be trusted.

### Pre-Installed Utility Scripts

#### Database Creation Script
The image comes pre-installed with a utility script which can be used to check if a PostgreSQL database exists and to create it if it does not.

When the script is called it must be passed an environment variable prefix for the service:

    /scripts/check-create-pgdb.sh SERVICE_

The script then reads the database details from a set of environment variables with the specified prefix:

| **Environment Variable**    |                                          **Description**                                               |
|-----------------------------|--------------------------------------------------------------------------------------------------------|
| `SERVICE_`DATABASE_HOST     | The host name of the machine on which the PostgreSQL server is running.                                |
| `SERVICE_`DATABASE_PORT     | The TCP port on which the PostgreSQL server is listening for connections.                              |
| `SERVICE_`DATABASE_USERNAME | The username to use when establishing the connection to the PostgreSQL server.                         |
| `SERVICE_`DATABASE_PASSWORD | The password to use when establishing the connection to the PostgreSQL server.                         |
| `SERVICE_`DATABASE_APPNAME  | The application name that PostgreSQL should associate with the connection for logging and monitoring.  |
| `SERVICE_`DATABASE_NAME     | The name of the PostgreSQL database to be created.                                                     |
