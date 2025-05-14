# Important Notice: npm-recursive-install is Deprecated

## Please Migrate to npm-recursive-runner

We've created a new and more powerful package called **npm-recursive-runner** that replaces npm-recursive-install with improved functionality.

### Why Migrate?
- **More Capabilities**: Not just limited to installation - run any npm command recursively
- **Parallel Execution**: Significantly faster with support for concurrent execution across multiple directories
- **Better Performance**: Optimized for large monorepo projects
- **Advanced Filtering**: More control over which directories to process

### How to Migrate:
1. Uninstall the old package:
   ```
   npm uninstall npm-recursive-install
   ```

2. Install the new package:
   ```
   npm install npm-recursive-runner
   ```

3. Update your scripts - the new command format is similar but more powerful:
   ```
   npm-recursive-runner [command] [options]
   ```

### Documentation & Source:
Please check out the repository for full documentation and examples:
[https://github.com/avi747av/npm-recursive-runner](https://github.com/avi747av/npm-recursive-runner)

---

Thank you for using npm-recursive-install!

Feel free to open issues or contribute on GitHub if you have any suggestions or encounter any problems.



# npm-recursive-install
===

A small utility to recursively run `npm install` in any child directory that has a `package.json` file excluding sub directories of `node_modules`.

### Installation
---
`$ npm i npm-recursive-install --save-dev`


### Options
- `--production`:  Install dependencies with the `--production` option - skip dev dependencies.
- `--rootDir <directory>`:  Specify the root directory to start searching for `package.json` files.
- `--skipRoot`: Skip installation for the root `package.json`.
- `--skip <directories>`: Skip installation for specific directories.
- `--addDirectories <directories>`: Add specific directories to install dependencies even they in the skip.


Usage
---
`$ npm-recursive-install` - will install dependencies recursively except from node_modules directories.

`$ npm-recursive-install --skipRoot` - Will not install in `process.cwd()`.

`$ npm-recursive-install --rootDir=lib` - strat installing dependencies recuresively from the lib directory.

`$ npm-recursive-install --production` - Will not install dev dependencies

`$ npm-recursive-install --skip dist build` - Will skip installing dependencies from the dist and build folders

`$ npm-recursive-install --skip dist build --add dist/test` - Will skip installing dependencies from the dist and build folders but will install on dist/test folder.


License
---
MIT
