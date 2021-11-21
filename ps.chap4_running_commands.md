# running commands

# scripts vs commands
* scripts consists of multiple commands
* scripts has a `ps1` extension

# command format

```=
verb-noun
```
* get all recommended verb using `get-verb`
* power shell is case insensitive

# `get-alias`
* find the nick name of a command

```=
get-alias -definition <command>
```

# `alias` of a parameter
## what command returns ? 
* command returns an `object`
* `object` may print something on the `console`
* `the printed msg` is not the same with the `object`
* `more` info is stored in the `object` than what is `shown` on screen
* `object` can be further processed

## access raw data of object using `.` notation

```=
(get-command -defintion get-eventlog).parameters.computername
```

* `get-command -defintion get-eventlog` returns an `command object`
* `object.parameters` gets a `parameters object`
* `object.computername` returns the `parameter object``
```

* what you get is `object` inside `object`

# `show-command``
* pop the command in graphical form
* good for best practice


# envocation character
* save the name of the cmdlet to a string variable
* run the string as you type them on console

```=
$test = echo
& $test hello world
```

* `&` will run `$test` as a command instead of a `string`
