# update-help
`update-help -force -erroraction silentlycontinue`
* igonre errors that may stop the update

# output -> html
`ConvertTo-Html`

# output -> file / printer
`out-file`
`out-printer`

# cmdlets handling processes
* cmdlets use singluar noun
`get-command -noun process | measure -Line`
* all commands
```

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Debug-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-Process                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Start-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Stop-Process                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Wait-Process                                       3.1.0.0    Microsoft.PowerShell.Management
```
# cmdlet write to event log
`write-eventlog`

# create, modify, export or import alias
## create
* `new-alias`
* `set-alias`
## modify 
* `set-alias`
## export 
* `export-alias`
## import 
* `import-alias`

# keep transcript/history of the shell session
```
Out-File -FilePath ./shell_history.txt -InputObject (Get-History)
```

# get the top 100 entries of security event log
```
 Get-EventLog -LogName security -Newest 100
```

# get services of a remote computer
```
Get-Service -ComputerName "Server02"
```

# get process of a remote computer
```
Get-Process -ComputerName "Server02"
```

# out-file width defaults.
out-file defaults wrap 80 characters
```
out-file -width <int>
```
* this will change the wrap of the chracters

# out-file with preventing overwrite
```
out-file -noclobber
```
# see a list of alias

```=
get-alias
```

# shortest form to get running process in a computer `server1`

```=
ps -cn server1
```
* `-cn` is an alias to `-computername`

# how many cmdlets dealing with generic objects

```=
get-command -noun object | measure -line
```

# topics about array

```=
help about_arrays
```

