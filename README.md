# greeter

This is a fork of the [wildfly greeter example](https://github.com/wildfly/quickstart/tree/master/greeter) which demonstrates CDI, JPA, JTA, EJB, and JSF.

In addition it contains functionality to make use of a PostGresql Database instead of a in-memory H2 and make it deployable to heroku using [Heroku Buildpack](https://devcenter.heroku.com/articles/buildpacks).

## Usage

Build locally
```console
$ git clone https://github.com/mwiede/greeter.git
$ cd greeter
$ mvn clean install
```
Setup an heroku app to use wildfly and postgresql database driver.

```console
$ heroku create
$ heroku addons:create heroku-postgresql:hobby-dev
$ heroku buildpacks:clear
$ heroku buildpacks:add heroku/java
$ heroku buildpacks:add https://github.com/mwiede/heroku-buildpack-wildfly
$ heroku buildpacks:add https://github.com/mwiede/heroku-buildpack-wildfly-postgresql
```

Deploy
```console
$ git push heroku master
```
