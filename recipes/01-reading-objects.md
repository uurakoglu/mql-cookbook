# Reading objects: `print bus` and `list`

## Problem
You need to look at an object or a set of objects without opening a client. Sometimes you want everything about one object, sometimes only two or three fields.

## Pattern
Print everything about one object (type, name, revision):

```mql
print bus Drawing DRW-0000001 A.1;
```

Print only the fields you need:

```mql
print bus Drawing DRW-0000001 A.1 select owner created;
```

List records of a type and choose the columns:

```mql
list person select name username email;
```

## Why it works
`print bus` identifies one object by type, name and revision. Without `select` it prints every field it has, which is useful when you do not yet know what you are looking for. Adding `select` and a list of field names narrows the output to exactly those fields, so the answer is short and easy to read. `list` works the same way for a whole type: it returns one entry per record, and `select` decides which fields appear.

## Watch out for
- Start with the full `print bus` when exploring, then switch to `select` once you know the field names you need.
- Finish each command with a semicolon.
- `created` returns the date and time, so it is a quick way to answer "who made this and when".
- `print` and `list` only read data. They do not change anything.
- A `list` over a large type can return thousands of lines. See [recipe 3](03-output-to-text-and-excel.md) for sending long results to a file.

## Variations
- Add more fields to `select` as questions come up, for example `owner created modified`.
- Use the same `select` idea with `expand bus` ([recipe 2](02-walking-structures.md)).
