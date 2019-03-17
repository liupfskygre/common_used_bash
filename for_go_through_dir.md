## this is a markdown file

**for, dir**

```console
for D in `find . -type d`
do
    //Do whatever you need with D
done
```
**or**

```console
for D in *; do
    if [ -d "${D}" ]; then
        echo "${D}"   # your processing here
    fi
done
```

**or**
```console
for D in *; do [ -d "${D}" ] && my_command; done
```

**or**
```console
for D in */; do my_command; done
```

**The simplest non recursive way is:**
```console
for d in */; do
    echo "$d"
done
```
