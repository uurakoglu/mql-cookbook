# Reading objects: `print bus` and `list`

Looking at an object without opening a client. Sometimes you want everything about one object, sometimes only two or three fields.

```mql
print bus Drawing DRW-0000001 A.1;
```

Prints everything for the object with that type, name and revision. This is the one to use when you do not yet know which fields you need.

```mql
print bus Drawing DRW-0000001 A.1 select owner created;
```

Prints only the owner and the creation date and time. It is a quick way to see who made an object and when.

```mql
list person select name username email;
```

Returns one line per person of that type, with just those three fields.

## Notes

- Every command ends with a semicolon.
- `print` and `list` only read data. They change nothing.
- Start with the full `print bus` while exploring, then switch to `select` once you know the field names.
- Add fields to `select` as new questions come up, for example `owner created modified`. The same idea works with `expand bus` ([recipe 2](02-walking-structures.md)).
- A `list` over a large type can return thousands of lines. [Recipe 3](03-output-to-text-and-excel.md) shows how to send them to a file.
