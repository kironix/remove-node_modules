# Removing `node_modules` from any project or any directory on Windows

If you're facing issues with removing deeply nested `node_modules` folders on Windows due to path length limitations, here are several methods to help you resolve the issue.

## Method 1: Using `rimraf`

The `rimraf` package is a widely used solution to remove directories with long path names on any platform.

Update, if you have npm v5, use [nxp](https://stackoverflow.com/a/62917293/1822977):

### How to use:
```bash
npx rimraf --glob **/node_modules
```

Otherwise install RimRaf:
   ```bash
   npm install -g rimraf
   ```

```bash
rimraf --glob node_modules
```
And in the project folder delete the node_modules folder with:

If you want to recursively delete:

```bash
rimraf --glob .\**\node_modules
```

Please save yourself the need to read most of these answers and just use npx rather than trying to install rimraf globally. You can run a single command and always have the most recent version with none of the issues seen here.

```bash
npx rimraf ./**/node_modules
```

[For More](http://www.nikola-breznjak.com/blog/nodejs/how-to-delete-node_modules-folder-on-windows-machine/)

## Method 2: Using `GitBash`

```bash
rm -r node_modules
```

## Method 3: Using `npkill`

I think this was not mentioned before. but the best way to delete unwanted node_modules is to install an utility called `npmkill`.

### How to use:

You can install as globally
```bash
npm i -g npkill
```

Then simply call it on a folder directly from your terminal
```bash
npkill
```

or alternatively, you can directly use it without installation by writing:
```bash
npx npkill
```

You will then be presented with a list of projects, and by hitting space bar you can delete their `node_modules`.

## Method 4: Using `remove-node-modules`

### How to use:

1. Install the `remove-node-modules` globally
```bash
npm install -g remove-node-modules
```
2. cd to root and `remove-node-modules`
3. or `remove-node-modules path/to/folder`

[Source](https://github.com/j-quelly/node-cleanup)
