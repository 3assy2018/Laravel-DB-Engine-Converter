# Laravel-DB-Engine-Converter

This problem faced me before so I want to publish an efficient solution to solve this problem.

Some times you clone a database from a server that uses MyISAM for example as MySQL default engine, and after start developing locally, you have been shocked with some unexpected errors that has this solution behind the scene.
An example for this is the dealing with relations between MyISAM and InnoDB, this can cause some collisions that could make a headache for you.

So all what you need is to clone the migration files that I have coded into new migration file and excute your migration.

Note: this solution was published before but with static table names wrapped inside array so all what you need to convert specific tables not all tables is to replace this line:

```
        $dbTables= DB::connection()->getDoctrineSchemaManager()->listTableNames();
```

with array of tables you want like so:

```
        $dbTables= [...list_your_tables_here];
```
