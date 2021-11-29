# provider

`disk-symbol` - `provider` - `data-storage`

* `provide` provide a set of standard interfaces for `cmdlets` to access different types of data storage
* `all` data storage will serve like a `disk`

# get all providers

```=
get-psprovider
```
* list all providers avaialable in the os

# capablilities of provider
each capablity represent a set of commands you can use to interact with the storage
* `should process`
* `filter`
* `credentials`
* `transactions`

# mapped drives
these are the `virtual` drives `connects` to one `ps-provider`, it then connects to some `data storage`

```=
get-psdrive
```
* get all mapped drives

# `cmdlets` interacts with `psdrive`

```=
get-command -noun *item*
```

# typical `psprovider` : `filesystem`
## windows filesystem components
all of them are refered as `item` in `psprovider`
* drives
* folders
* files

## file system commands

```=
new-item -type directory folder01
```
* this is the generic form of `mkdir folder01`

```=
set-location folder01
```
* this is the generic form of `cd folder01`

```=
get-childitem folder01
```
* this is the generic form of `ls folder01`

```=
get-childitem *.exe
```
* use `wildcards` to filter the path 

```=
get-childitem -literalpath *folder01
```
* ignore `wildcards`, list the `*folder01` `item`
* this is useful in certain scenarios like `database`

# typical `psprovider` : `registry`

# go to registery of current user

```=
set-location -path hkcu:
```
# modify a value of the registry

```=
cd software/microsoft/windows
```
* you will find `dwm`, this is a `leaf` of the `registry` data structure

```=
set-itemproperty -path dwm -psproperty enableaeropeek -value 0
```
* now we have disabled the `aeropeek` feature of windows system

