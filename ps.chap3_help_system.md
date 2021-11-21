# `cmdlet` and `function`

* `cmdlet` is the basic executable unit
* `function` is wapper of one or more `cmdlet`

## example
* `Get-Help` is a cmdlet
* `Help` is a function
* `Man` is an alias

# common work flow to find help
1. `help *wildcards*`
2. `help command`

* the first command find all command names based on a keyword
* the last command locate the help file for the command

## update the help documents from internet
```
Update-Help
Update-Help -Verbose -Force -ErrorAction SilentlyContinue
```

## save the local help and use it in another pc
```
save-help -destinationpath <string>
update-help -source <string>
```

# understanding the help
## parameter set
* parameter set are exclusive. they provide different behavior
* use unique parameter in one set will select the set automatically.
* use commom parameter only will select the first parameter set.

## parameter type
### mandatory parameter
`-parameter-name <parameter-value>`
* in help system, all parameter name start with `-`
* parameter value is ecloused in `<` and `>`

### optional parameter
`[-parameter-name <parameter-value>]`
* the entire pair is enclosed with square brackets

### positional paramter
`[-parameter-name]` <parameter-value>
* parameter name can be omitted.
* the value must be placed in certain positions

### optional positional parameter
`[[-parameter-name] <parameter-value>]`
* it is optional
* the parameter name can be omitted
* if the parameter name is omitted, it must follow its position sequence

### switches
switches are parameters that does not have a parameter value
* switches are always optional
* they have a default value when `omitted`
* they have a alternative value when `present`

## parameter values
### single value
	* `<string>`
### multiple values
	* `<string[]>`
	* powershell accepts csv as array

## use output of a command as parameter
```
command_01 -param (command_02 -params)
```
* the `()` is used to evaluate the command first and use the output as parameter.


# search the commands directly
* `get-command <wildcard>` : search all commands and functions ( a lot of rubbish )
* `get-command -noun <wildcard>` : search all cmdlets that has wildcard in their noun section
* `get-command -verb <wildcard>` : search all cmdlets that has wildcard in their verb section

only `cmdlets` have `noun` and `verb` section, so it will only show powershell `cmdlets`

