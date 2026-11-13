# Sending output to a text file, then to Excel

## Problem
A query returns hundreds or thousands of lines. Reading them in the MQL console is slow, hard to follow and easy to lose, and you often want to sort or filter the result anyway.

## Pattern
Add `output` and a file path at the end of the command:

```mql
list person select name username email output c:/temp/personlist.txt;
```

The result is written to the text file instead of the console. Open the file, or import it into Excel, to filter and review it.

## Why it works
The command runs exactly as before, but the result goes to a file. The console stays readable, you keep a record of what you asked and what came back, and Excel does the sorting and filtering that MQL does not.

## Watch out for
- Make sure the folder in the path exists before you run the command.
- Use a new file name for each run, or put the date in the name, so results from different runs do not get mixed up.
- When you import into Excel, use the import option that lets you choose how the text is split into columns, and check a few rows before trusting the result.
- Do not leave exported files with personal data in shared folders.

## Variations
- Use the same `output` ending with `print bus ... select ...` and `expand bus ... select ...`.
- Keep the command next to the exported file, for example in the same folder, so you can repeat the same report later.
