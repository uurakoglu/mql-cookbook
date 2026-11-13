# mql-cookbook
Small, generic MQL patterns for administering 3DEXPERIENCE / ENOVIA (R2024x)

MQL is the command language of ENOVIA, and public examples are hard to find. These notes are the patterns I use most, written up so that someone new to the platform can adapt them. Each recipe is short and explains when to use it and what to watch out for.

Ground rules
Every example uses standard types and made-up names and data. Nothing here comes from a real system, and nothing is specific to any employer.
Run everything on a test environment first.
Scripts that change data start in dry-run mode, write a log, and stay safe to run twice.
Tested on 3DEXPERIENCE R2024x. Syntax can differ between releases, so check yours.
Not affiliated with or endorsed by Dassault Systèmes.
