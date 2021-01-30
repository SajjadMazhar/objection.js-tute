# Objection.js Tutorial with Postgres and Express

This tutorial demonstrates how to connect to a [Postgres](https://www.postgresql.org) database with [Objection.js](https://vincit.github.io/objection.js/).

It also demonstrates how to create the database schema and how to create seed data with the [knex.js](http://knexjs.org) migration tool.

<h3 align="center">Please help this repo with a ⭐️ if you find it useful! 😁</h3>

This repository is contains the code for the [Objection.js tutorial on Youtube](https://www.youtube.com/watch?v=wfrn21E2NaU)

[![Objection.js tutorial](images/node-knex-js-tutorial.png)](https://www.youtube.com/watch?v=wfrn21E2NaU)

Please also check out my website at [jangoebel.com](https://jangoebel.com)

# How to run this application

This application needs a local [Postgres](https://www.postgresql.org) instance.

## Installing Postgres

On macOS you can install [Postgres](https://www.postgresql.org) with [Homebrew](https://brew.sh/).

```
brew install postgresql
```

and start it with

```
brew services start postgres
```

For other operating systems, please check the [Postgres website](https://www.postgresql.org/download/).

### Database setup

Make sure to update the configuration app with your database credentials in the `../db/knexfile.js` file.
There you need to specify the `user`, `password` (per default no password required) and the `database` you want to connect to.

The default database we try to connect to is called `objection_tutorial`. Please make sure it exists in your local Postgres instance. You can either use a UI like [PgAdmin](https://www.pgadmin.org) to create the database or you can do so with `psql`

```
psql -h localhost -U <your-username> postgres
```

When installing locally, [Postgres](https://www.postgresql.org) creates a database user with your operation system's username.
You can run

```
whoami
```

on any Unix-like operating system to find out your user

Then you can create a new database with:

```
create database objection_tutorial;
```

## Execute database migration

Once you have installed Postgres and updated the credentials in the `./db/knexfile.js`, you can run the initial migration
to create the database schema with.

```
npm run migrate
```

## Starting the application

```
npm run dev
```
