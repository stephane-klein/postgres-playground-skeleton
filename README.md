# PostgreSQL playground skeleton

## Prerequisites

- [Docker Engine](https://docs.docker.com/engine/) (tested with `24.0.6`)
- [pgcli](https://www.pgcli.com/)
- `psql` (More info about `psql` [brew package](https://stackoverflow.com/a/49689589/261061))

Run this command to check that everything is installed correctly:

```
$ ./scripts/doctor.sh
docker 24.0.6 >= 24.0.6 installed ✅
psql installed ✅
pgcli installed ✅
```

See [`prerequisites.md`](prerequisites.md) to get more information on how to install this software.

## Note about psql and pgcli

I install both *psql* and *pgcli* for the following reasons:

- I like *pgcli* for autocompletion and multiline vim editor features
- However, *pgcli* don't support ["pipe" feature](https://github.com/dbcli/pgcli/issues/307). That's why I also install *psql*, I use psql to inject files into *PostgreSQL*.

## Getting start

```sh
$ docker compose up -d --wait
$ ./scripts/seed.sh
$ ./scripts/fixtures.sh
$ ./scripts/enter-in-pg.sh
postgres@127:postgres> select * from public.users;
+----+----------+
| id | username |
|----+----------|
| 1  | user1    |
| 2  | user2    |
| 3  | user3    |
+----+----------+
SELECT 3
Time: 0.012s
```
