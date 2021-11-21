# display a list of running process

```=
ps
```

# display top 100 entiries of running process

```=
get-eventlog -logname application -newest 100
```

# display all `cmdlet` command

```=
get-command -commandtype cmdlet | measure -line
```
* there are `624` cmdlets in windows os

# display a list of all alias

```=
get-alias
```

# new alias to use `d` for `dir`

```=
new-alias -name d -value dir
```

# get services begin with `M`

```=
get-service -name M*
```

# get a list of windows firewall rules

```=
get-netfirewallrule
```

# get a list of inbound firewall rules

```=
get-netfirewallrule -direction inbound
```
