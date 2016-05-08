[![view on npm](http://img.shields.io/npm/v/command-line-commands.svg)](https://www.npmjs.org/package/command-line-commands)
[![npm module downloads](http://img.shields.io/npm/dt/command-line-commands.svg)](https://www.npmjs.org/package/command-line-commands)
[![Build Status](https://travis-ci.org/75lb/command-line-commands.svg?branch=master)](https://travis-ci.org/75lb/command-line-commands)
[![Dependency Status](https://david-dm.org/75lb/command-line-commands.svg)](https://david-dm.org/75lb/command-line-commands)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](https://github.com/feross/standard)

***documentation in progress***

<a name="module_command-line-commands"></a>

## command-line-commands
Add a git-like command interface to your app. Wraps [command-line-args](https://github.com/75lb/command-line-args).

**Example**  
```js
const commandLineCommands = require('command-line-commands')

// define your commands
const cli = commandLineCommands([
  { name: 'help' },
  { name: 'run', definitions: [ { name: 'why', type: String } ] }
])

// parse the command line
const command = cli.parse()

// respond
switch (command.name) {
  case 'help':
    console.log("I can't help you.")
    break
  case 'run':
    console.log(`${command.options.why}: this is not a good reason.`)
    break
  default:
    console.log(command.error + ':' + command.command);

}
```

Output (assumes your app name is `example`):
```
$ example help
I can't help you.

$ example run --why terror
terror: this is not a good reason.

$ example hide
Unknown command: hide
```

* [command-line-commands](#module_command-line-commands)
    * [CommandLineCommands](#exp_module_command-line-commands--CommandLineCommands) ⏏
        * [new CommandLineCommands(commands)](#new_module_command-line-commands--CommandLineCommands_new)
        * [.parse([argv])](#module_command-line-commands--CommandLineCommands+parse) ⇒ <code>Object</code>
        * [.getUsage([commandName], [options])](#module_command-line-commands--CommandLineCommands+getUsage) ⇒ <code>string</code>

<a name="exp_module_command-line-commands--CommandLineCommands"></a>

### CommandLineCommands ⏏
**Kind**: Exported class  
<a name="new_module_command-line-commands--CommandLineCommands_new"></a>

#### new CommandLineCommands(commands)

| Param | Type |
| --- | --- |
| commands | <code>array</code> | 

<a name="module_command-line-commands--CommandLineCommands+parse"></a>

#### cli.parse([argv]) ⇒ <code>Object</code>
**Kind**: instance method of <code>[CommandLineCommands](#exp_module_command-line-commands--CommandLineCommands)</code>  

| Param | Type |
| --- | --- |
| [argv] | <code>array</code> | 

<a name="module_command-line-commands--CommandLineCommands+getUsage"></a>

#### cli.getUsage([commandName], [options]) ⇒ <code>string</code>
Generates a usage guide for the specified command. Please see [command-line-usage](https://github.com/75lb/command-line-usage) for full instructions of how to use.

**Kind**: instance method of <code>[CommandLineCommands](#exp_module_command-line-commands--CommandLineCommands)</code>  

| Param | Type | Description |
| --- | --- | --- |
| [commandName] | <code>string</code> | the command to load the command line option definitions from |
| [options] | <code>object</code> | the options to pass to [command-line-usage](https://github.com/75lb/command-line-usage) |


* * *

&copy; 2015-16 Lloyd Brookes \<75pound@gmail.com\>. Documented by [jsdoc-to-markdown](https://github.com/jsdoc2md/jsdoc-to-markdown).
