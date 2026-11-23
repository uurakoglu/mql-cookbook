# Reading relationships: `print connection` and `expand bus`

Looking at the connections between objects: what type a connection is, who created it, when it changed, and which connections hang off an object.

```mql
print connection <connection_id>;
```

Prints everything the platform stores about that one connection to the MQL console. The most useful part is the connection type: the connection between a 3D Data object and a Drawing is one type, and the connection between a 3D Data object and another 3D Data object is a different one. The output also shows when the connection was created and by whom, when it was last modified, its history, any other attributes defined on it, and the project and organization it belongs to.

```mql
expand bus VPMReference prd-xxx A.1 select bus type name revision select rel id type;
```

Expands the object and lists the objects connected to it. For each one you get its type, name and revision, plus the `id` and `type` of the connection that links them. The `id` is the value to pass to `print connection`, so the two commands work as a pair: expand to find the connection ids, then print the ones you want to inspect.

## Notes

- `expand bus` is the way to get at the connections of an object. The word `bus` has to be there, or the command returns an error.
- There is no `expand connection` command. To see what a connection links, start from one of the objects with `expand bus`, or run `print connection` on its id.
- A connection links two objects, so it is easier to start from the object and expand than to look for the connection directly.
- `print connection` and `expand bus` only read data.
- The `select` part of the syntax can differ between releases, so try it on yours before reusing it.
