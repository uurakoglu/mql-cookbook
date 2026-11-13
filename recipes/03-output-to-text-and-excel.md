# Sending output to a text file, then to Excel

A query that returns hundreds or thousands of lines is slow to read in the MQL console, easy to lose, and you usually want to sort or filter it anyway.

Add `output` and a file path to the end of the command:

```mql
list person select name username email output c:/temp/personlist.txt;
```

The result goes to the file instead of the console. Open the file, or import it into Excel, to filter and review it. The console stays readable, you keep a record of what came back, and Excel does the sorting that MQL does not.

## Notes

- The folder in the path has to exist before you run the command.
- Use a new file name for each run, or put the date in it, so results from different runs do not get mixed up.
- When you import into Excel, choose the import option that lets you set how the text is split into columns, and check a few rows before trusting the result.
- Files with personal data, like the person list above, should not stay in shared folders.
- The same `output` ending works with `print bus ... select ...` and `expand bus ... select ...`. Keeping the command next to the exported file makes it easy to repeat the report later.
