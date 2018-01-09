# hello-awk

Where I learn AWK.

## Tips

### Extract the first line

These are all same.

```shell-session
$ awk 'NR==1'
$ awk 'NR==1{print}'
$ awk 'NR==1{print $0}'
```

### Extract N-th line

`NR` is the line number of current line.

```shell-session
$ awk 'NR==N'
```

### Remove empty lines

`NF` is the count of fields in current line.

```shell-session
$ awk 'NF'
$ awk '$0'
$ awk '/./'
```

### Count the characters

```shell-session
$ wc -c
$ awk '{n+=length($0)} END{print n}'
```

### Count the words

```shell-session
$ wc -w
$ awk '{n+=NF} END{print n}'
```

### Count the lines

```shell-session
$ wc -l
$ awk 'END{print NR}'
```

### Remove duplicated lines

```shell-session
$ uniq
$ awk '!a[$0]++'
```

### Extract the lines by regular expression

```shell-session
$ grep -e '/hogehoge/'
$ awk '/hogehoge/'

$ grep -ve '/hogehoge/'
$ awk '! /hogehoge/'
```

### Extract the lines from N-th to M-th

```shell-session
$ # May be able to replace with head and tail
$ awk 'NR==N,NR==M'
```

### Extract even/odd lines

```shell-session
$ awk 'NR%2==0'
$ awk 'NR%2'
```

## References

* [実用 awk ワンライナー](https://qiita.com/b4b4r07/items/45d34a434f05aa896d69)
