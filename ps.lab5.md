# change registery key values

```=
cd hkcu:software/microsoft/windows/currentversion/exploer
```

```=
ls
```

```=
set-itemproperty -path advanced -psproperty dontprettypath -value 1
```

# create a zero length file `c:\test.txt`

```=
new-item -itemtype file -name newfile.txt
```

# use `set-item` to change the file content of c:\test.txt
we get a error msg when runnign the following command

```=
set-item test.txt -value testing
```

```=
set-item : Provider operation stopped because the provider does not
support this operation.
```

in file system, the `set-item` cmdlets is not implemented, this `cmdlet` is designed for `psprovider` : `variable` and `registry`


# difference of `-fileter` `-include` `-exclude` of `get-chiditem`

## `-filter`
* `-filer` is only implemented by `filesystem`
* `objects` -> `filter` -> `cmdlets`
* it is very efficient
* it only support `*` and `?`

```=
get-childitem -filter .*

```
* get all hidden file starting with `.`
* this is the same but more efficient than

```=
get-childitem -path .*
```

## `-include`
* specify more patterns to be matched

```=
get-childitem -include '*.txt','*.md'
```
* list all `.txt` file or '.md' file in the current `item`

## `-exclude`

* specify more patterns to be matched
* remove patterned path from output set
