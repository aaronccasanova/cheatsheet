# CHTSHT

Display or execute your own custom cheat sheet

https://user-images.githubusercontent.com/32409546/153776785-f24cbf70-9834-4b38-a617-81f699925caf.mov

## Install

```sh
npm i -g chtsht
```

## Config

Add `.chtsht` file to your home directory. e.g. `~/.chtsht`

```ts
// Config structure
type Config = {
  [cheatsheet: string]: Array<{
    description: string;
    command: string;
  }>;
};
```

Example:

```json
{
  "npm": [
    {
      "description": "Show global packages",
      "command": "npm ls -g --depth=0"
    },
    {
      "description": "Show outdated global packages",
      "command": "npm outdated -g --depth=0"
    }
  ],
  "yarn": [
    {
      "description": "List caches",
      "command": "yarn cache list"
    },
    {
      "description": "Clean cache(s)",
      "command": "yarn cache clean <name>"
    }
  ]
}
```

> Note: `"command"` values with `<>` brackets will prompt you to input the enclosed value if the `--exec | -e` flag is used.

## CLI

Alternatively, you can use `npx` to use this CLI.

```
  $ chtsht --help

  Usage
    $ chtsht <name>

  Options
    --exec, -e  Execute the command

  Examples
    # Show select list of all cheat sheets
    $ chtsht

    # Show the docker cheat sheet
    $ chtsht docker

    # Execute the command
    $ chtsht -e docker
```
