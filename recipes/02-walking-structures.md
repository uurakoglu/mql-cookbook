# Walking structures: `expand bus`

Finding out what an object is connected to: what sits below it in a structure, what sits above it, and what else it is attached to (a release, for example).

```mql
expand bus VPMReference PRD-000001 A.1;
```

Expands every connection of that object and prints one line per connected object.

```mql
expand bus VPMReference PRD-000001 A.1 select type name revision owner project organization;
```

Same command, but the output is limited to the fields you list, so it reads like a small report.

## Notes

- The result covers connections in both directions, not only the structure below the object. Expect extra lines for things like releases.
- Large structures produce a lot of lines. Send the output to a file ([recipe 3](03-output-to-text-and-excel.md)) instead of scrolling through the console.
- `expand` only reads data.
- The `select` part of the syntax can differ between releases, so try it on yours before reusing it.
- Change the fields in `select` to fit the question. Ownership and organization are useful when you are tracking down who is responsible for an object.
