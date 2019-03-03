# brf-energi-env

> A dockerized version of the production server environment.

## Setup
The project is made up of submodules which are hosted as seperate repositories.

```bash
$ git clone git@github.com:CIVIS-project/brf-env.git
$ cd brf-env
$ git submodule init
```

Copy `example.env` to `.env` in the project root and fill in all the blanks with
the correct credentials.
Secondly, copy `example.config.json` to `NodeBB/config.json` and fill in the
blanks (values in ALL_CAPS). The values should match those in `.env`.

To proceed, you'll need to have docker installed and running.

```bash
$ docker-compose build
```

NodeBB requires some extra setup and dependencies installed.

```bash
$ docker-compose run forum bash
$ npm install nodebb-plugin-brf-energi nodebb-plugin-sso-metry
$ ./nodebb upgrade
$ exit
```

You're now all set!

```bash
$ docker-compose up
```

## Development

When working on one of the two submodules, you commit, push and pull just like
you normally would. When finished, go to the project root folder and commit.
This will ensure that everyone else will be working off of the same commit of
the submodule that you just created.

When changes have been made to the submodules by another party, update them.
```bash
$ git submodule update
```
