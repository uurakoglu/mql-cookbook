# mql-cookbook

Small, generic MQL patterns for administering a 3DEXPERIENCE / ENOVIA platform.

MQL is the command language of ENOVIA, and public examples are hard to find. These notes are the patterns I use most, written up so that someone new to the platform can adapt them. Each recipe is short and explains when to use it and what to watch out for.

## Ground rules

- Every example uses standard types and made-up names and data. Nothing here comes from a real system, and nothing is specific to any employer.
- Run everything on a test environment first.
- Scripts that change data start in dry-run mode, write a log, and stay safe to run twice.
- Tested on 3DEXPERIENCE R2024x. Syntax can differ between releases, so check yours.
- Not affiliated with or endorsed by Dassault Systèmes.

## Recipes

| # | Recipe | Commands | What it covers |
|---|--------|----------|----------------|
| 1 | [Reading objects](recipes/01-reading-objects.md) | `print bus`, `list` | Look up objects and choose what to print |
| 2 | [Walking structures](recipes/02-walking-structures.md) | `expand bus` | See what an object is connected to, with selectable output |
| 3 | [Output to a text file, then Excel](recipes/03-output-to-text-and-excel.md) | `output` | Send long results to a file and review them in Excel |
| 4 | Reading relationships _(planned)_ | `print connection`, `expand connection` | Inspect connections and their attributes |
| 5 | Changing objects _(planned)_ | `mod bus` | Change attributes and states on one object or many |
| 6 | Changing relationships _(planned)_ | `mod connection` | Change connection attributes in bulk |
| 7 | Users and permissions _(planned)_ | `mod person` | Update person records and assignments |
| 8 | Commands and menus _(planned)_ | `mod command` | Adjust command settings |
| 9 | Dry-run first _(planned)_ | | See what a bulk change would do before it runs |
| 10 | Transactions, logging and re-runs _(planned)_ | `start transaction` | Make scripts safe to stop, resume and run twice |

## Recipe format

Each file in `recipes/` follows the same layout:

1. **Problem**: what you are trying to do, in one or two sentences.
2. **Pattern**: the commands, with comments.
3. **Why it works**: the idea behind it.
4. **Watch out for**: mistakes that cost time or data.
5. **Variations**: when to change it.

## Contributing

Corrections and tested additions are welcome. Please use synthetic data only.
