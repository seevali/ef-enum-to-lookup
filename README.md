Entity Framework 6.1 Enum Lookup Table Generator
================================================

* License: MIT - http://opensource.org/licenses/MIT
* Source code: https://github.com/timabell/ef-enum-to-lookup
* Bug tracker: https://github.com/timabell/ef-enum-to-lookup/issues
* Nuget package https://www.nuget.org/packages/ef-enum-to-lookup

About
-----

Creates lookup tables and foreign key constraints based on the enums
used in your model.

This makes up for a feature that's missing in Entity Framework 6.1.

Usage
-----

Run `EnumToLookup.Apply()` from your Seed method in either your database initializer
or your EF Migrations.

Use the properties exposed to control behaviour.

It is safe to run repeatedly (Idempotent), and will ensure enum values are kept in line
with your current code if run regularly (e.g. in the migration seed method). 

For example usage see [ExampleUsage/EnumExample.cs](ExampleUsage/EnumExample.cs), which
can be run in the test project project "[ExampleUsage](ExampleUsage)" if you want to see it in action.

	var enumToLookup = new EnumToLookup();
	enumToLookup.NameFieldLength = 42; // optional, example of how to override default values
	enumToLookup.Apply(context);

Contributing
------------

Feedback, bug reports, pull requests all welcome, head over to github.

Repository
----------

Files stored as LF, converted on checkout to windows, configure locally with

    git config core.autocrlf true


I've looked into the .gitattributes approach to this and it doesn't seem to have
the desired effect on a windows checkout.
