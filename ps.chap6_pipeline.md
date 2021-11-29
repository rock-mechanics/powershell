# pipeline

```=
command1 | command2 | command3
```

# export to csv file 

```=
ps | export-csv ps.csv
```

# display the csv file to powershell

```=
import-csv ps.csv
```

# export to xml file
* powershell supports a native `clixml` format, which is `xml` file with a little bit customization
* it can be read with normal browser

```=
ps | export-clixml ps.xml
```

# display xml in powershell

```=
import-clixml ps.xml
```


# compare files

```=
compare-object 
```
* is has alias called `diff`
