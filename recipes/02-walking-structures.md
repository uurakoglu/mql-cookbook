# Walking structures: `expand bus`

## Problem
You want to see what an object is connected to: what sits below it in a structure, what sits above it, and what else it is attached to (a release, for example).

## Pattern
Expand all connections of one object:

```mql
expand bus VPMReference PRD-000001 A.1;
```

Narrow the output to the fields you care about:

```mql
expand bus VPMReference PRD-000001 A.1 select type name revision owner project organization;
```

## Why it works
`expand bus` starts from one object and follows its connections. The result is one line per connected object, so a single command gives you the surroundings of that object. Without `select` you see the default information. Adding `select` turns the output into a small report with the exact fields you listed.

## Watch out for
- The result includes everything connected in both directions, not only the structure below the object. Expect extra lines for things like releases.
- Large structures produce a lot of lines. Send the output to a file ([recipe 3](03-output-to-text-and-excel.md)) instead of reading it in the console.
- Like `print` and `list`, `expand` only reads data.
- Check the exact `select` syntax on your own release before reusing a command. It is the part that tends to vary.

## Variations
- Pick different fields in `select` depending on the question, for example ownership and organization when you are tracking down who is responsible for an object.
- Compare the output with a `print bus` of one of the connected objects to see all of its fields.
