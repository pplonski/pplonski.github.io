---
layout: post
title: SQLAlchemy vs psycopg2
---

I've compared the speed of reading form postgresql database in python using SQLAlchemy and psycopg2.

I was reading from table hosted in AWS RDS, the table has ~500 rows. The code used for measuring the speed:

{% gist 5671d1ff0335db0479e2352d8a556774 %}

The code output:

```
select * from projects_project
alchemy , select * from projects_project , 2.5992019891738893
pg , select * from projects_project , 1.1509313106536865
select count(*) from projects_project
alchemy , select count(*) from projects_project , 2.2600314140319826
pg , select count(*) from projects_project , 0.9214831829071045
```

The psycopg2 is over 2x faster than SQLAlchemy on small table. This behavior is expected as psycopg2 is a database driver for postgresql while SQLAlchemy is general ORM library.

{% include newsletter.html %}
