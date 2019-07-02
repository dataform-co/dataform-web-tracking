# Introducing SQLX

We’d like to introduce Dataform’s new 'SQLX’ file format.

SQLX is a cleaned up version of Dataform’s existing syntax. We’ve designed it to make your Dataform files more readable for you and your team.

Significant changes:

## A single file extension

All Dataform SQL files, regardless of whether you’re publishing a dataset, running an assertion, or executing operations, use a single `.sqlx` file extension.

You’re still able to create pure JavaScript files (`.js`) for [defining includes](https://docs.dataform.co/guides/includes/) and [defining multiple actions in one file](https://docs.dataform.co/guides/js-api/).

## Configuring is simpler

Query configuration is now broken out into a `config { … }` block. Examples of usage are [here](https://docs.dataform.co/guides/datasets/). Most notably, a query’s ‘type’ may now be one of ‘view’, ‘table’, ‘incremental’, ‘assertion’, or ‘operations’.

Note that the default type of a new file is ‘operations’.

## JS blocks

Defining inline JavaScript in your SQLX files is cleaner. You now define inline JavaScript using a `js { … }` block (see [docs](https://docs.dataform.co/guides/includes/)).

## Incremental where 

Defining ‘incremental’ WHERE clauses is cleaner: these are now defined inside `incremental_where { … }’ blocks (see [docs](https://docs.dataform.co/guides/incremental-datasets/#daily-snapshots-with-incremental-datasets)).

## Migration
For now, Dataform projects are still fully backwards compatible with your old .sql files, and we’ve made sure that your files can be migrated to the new syntax individually - there’s no need to do a single massive change to all of your code.

Examples of all of the new syntax are available on docs.dataform.co. If you would like our help migrating to SQLX, please email team@dataform.co or get in touch through Intercom and we'd be happy to help.
