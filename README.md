# Regex

## French city code

A complete regex to check french city code.

From 01001 to 19999, 2A001 to 2B999, 21001 to 96999, 97101 to 97899, 98401 to 98499, 98601 to 98999.

```
^(((([0,2][1-9])|([1,3-8][0-9])|(9[0-6])|(2A)|(2B))[0-9]{2})|((97[1-8]|98([4,6-9]))[0-9]{1}))[1-9]$
```
[The online demo on https://regex101.com](https://regex101.com/r/6B361X/1/)

The postgres domain to check data directly in Postgres.

```sql
CREATE DOMAIN fr_city_code AS character varying(5)
CHECK(
  VALUE ~ '^(((([0,2][1-9])|([1,3-8][0-9])|(9[0-6])|(2A)|(2B))[0-9]{2})|((97[1-8]|98([4,6-9]))[0-9]{1}))[1-9]$'
);
```
