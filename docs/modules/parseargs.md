---
description: Modern alternatives to packages for CLI argument parsing
---

# Replacements for argument parsers

## `util.parseArgs` (native, since Node.js 16.17.0)

[`util.parseArgs`](https://nodejs.org/api/util.html#utilparseargsconfig) can replace many common CLI parsing libraries such as `arg`, `minimist`, `mri`, `yargs-parser`.

Example:

```ts
import { parseArgs } from 'node:util'

const { values, positionals } = parseArgs({
  args: process.argv.slice(2),
  options: {
    force: { type: 'boolean', short: 'f' },
    output: { type: 'string', short: 'o' }
  },
  allowPositionals: true
})
```
