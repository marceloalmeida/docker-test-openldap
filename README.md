# OpenLDAP Docker Image for testing

![Docker Build Status](https://img.shields.io/docker/build/marceloalmeida/docker-test-openldap.svg) ![Docker Stars](https://img.shields.io/docker/stars/marceloalmeida/docker-test-openldap.svg) ![Docker Pulls](https://img.shields.io/docker/pulls/marceloalmeida/docker-test-openldap.svg)

This image provides an OpenLDAP Server for testing LDAP applications, i.e. unit tests. The server is initialized with the example domain `thesimpsons.com` with data from the [The Simpsons Wiki][thesimpsonswiki].

Parts of the image are based on the work from Nick Stenning [docker-slapd][slapd] and Bertrand Gouny [docker-openldap][openldap].

The Flask extension [flask-ldapconn][flaskldapconn] use this image for unit tests.

[slapd]: https://github.com/nickstenning/docker-slapd
[openldap]: https://github.com/osixia/docker-openldap
[flaskldapconn]: https://github.com/rroemhild/flask-ldapconn
[thesimpsonswiki]: https://simpsons.fandom.com/wiki/Simpson_family


## Features

* Support for TLS (snake oil cert on build)
* Initialized with data from Futurama
* ~124MB images size (~40MB compressed)


## Usage

```
docker pull marceloalmeida/docker-test-openldap
docker run --privileged -d -p 389:389 marceloalmeida/docker-test-openldap
```

## Exposed ports

* 389
* 636

## Exposed volumes

* /etc/ldap/slapd.d
* /etc/ldap/ssl
* /var/lib/ldap
* /run/slapd
