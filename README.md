sso-demo-docker
=============

This Docker image contains a fully built Ldap, CAS Server 3.5.X, and Shibboleth IdP 2.4.X environment.

This image does not follow best Docker practices. It is intended from demo/class usage. It may also be good for app development purposes.

To run the container:

```
$ docker run -d -p 10389:389 -p 8443:8443 -p 5005:5005 --name="sso-demo" jtgasper3/sso-demo
```

Serveral user accounts are available for various purposes:

- jsmith/password: Normal User
- banderson/password: Expired Password
- jgasper/password: Disabled Account
- kmiller/password: Password Attemps Exceeded (locked out)

The LDAP admin bind account is "cn=Directory Manager" (password). 

## Building
Gradle is used to build the prerequisite CAS library, then build the Docker image.

> Most of these task require the Docker client be available. It should be setup with:
   export DOCKER_TLS_VERIFY=1
   export DOCKER_HOST=tcp://192.168.59.103:2376
   export DOCKER_CERT_PATH=/Users/jgasper/.boot2docker/certs/boot2docker-vm

gradle runDockerContainer: starts the container for direct testing.
gradle removeDockerContainer: stops container and removes the instance.
gradle clean: cleans up the `build` directory.


## Author

  * John Gasper (<jgasper@unicon.net>)

## LICENSE

Copyright 2015 John Gasper

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
