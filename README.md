# GoHipster - Work in progress
[![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency Status][daviddm-image]][daviddm-url]
> JHipster blueprint, A JHipster blueprint that will provide Golang as the server side language

# Introduction

This is a [JHipster](https://www.jhipster.tech/) blueprint, that is meant to be used in a JHipster application.

# Prerequisites

As this is a [JHipster](https://www.jhipster.tech/) blueprint, we expect you have JHipster and its related tools already installed:

- [Installing JHipster](https://www.jhipster.tech/installation/)

# Installation

## With NPM

To install this blueprint:

```bash
npm install -g generator-jhipster-go
```

To update this blueprint:

```bash
npm update -g generator-jhipster-go
```

## With Yarn

To install this blueprint:

```bash
yarn global add generator-jhipster-go
```

To update this blueprint:

```bash
yarn global upgrade generator-jhipster-go
```

# Usage

To use this blueprint, run the below command

```bash
jhipster --blueprints go
```

## Using Docker

Download the Dockerfile:

```bash
mkdir docker
cd docker
wget https://github.com/jhipster/jhipster-go/raw/master/docker/Dockerfile
```

Build the Docker images:

```bash
docker build -t jhipster-generator-go:latest .
```

Make a folder where you want to generate the Service:

```bash
mkdir service
cd service
```

Run the generator from image to generate service:

```bash
docker run -it --rm -v $PWD:/home/jhipster/app jhipster-generator-go
```

Run and attach interactive shell to the generator docker container to work from inside the running container:

```bash
docker run -it --rm -v $PWD:/home/jhipster/app jhipster-generator-go /bin/bash
```

## Running local Blueprint version for development

During development of blueprint, please note the below steps. They are very important.

1. Link your blueprint globally 

Note: If you do not want to link the blueprint(step 3) to each project being created, use NPM instead of Yarn as yeoman doesn't seem to fetch globally linked Yarn modules. On the other hand, this means you have to use NPM in all the below steps as well.

```bash
cd go
npm link
```

2. Link a development version of JHipster to your blueprint (optional: required only if you want to use a non-released JHipster version, like the master branch or your own custom fork)

You could also use Yarn for this if you prefer

```bash
cd generator-jhipster
npm link

cd go
npm link generator-jhipster
```

3. Create a new folder for the app to be generated and link JHipster and your blueprint there

```bash
mkdir my-app && cd my-app

npm link generator-jhipster-go
npm link generator-jhipster (Optional: Needed only if you are using a non-released JHipster version)

jhipster -d --blueprint go

```

# License

Apache-2.0 © [Deepu K Sasidharan](https://deepu.tech)


[npm-image]: https://img.shields.io/npm/v/generator-jhipster-go.svg
[npm-url]: https://npmjs.org/package/generator-jhipster-go
[travis-image]: https://travis-ci.org/deepu105/generator-jhipster-go.svg?branch=master
[travis-url]: https://travis-ci.org/deepu105/generator-jhipster-go
[daviddm-image]: https://david-dm.org/deepu105/generator-jhipster-go.svg?theme=shields.io
[daviddm-url]: https://david-dm.org/deepu105/generator-jhipster-go
