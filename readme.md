# What?
This script prints all its arguments, in various forms of expansion.
All output is printed to stdout, not stderr.


# Why?
1. Serve to aid in {debugging, education}.
2. I am tired of seeing various systems printing their arguments but failing to take spacing and quotes into consideration.


# Usage example
```bash
$ ./argv foo "hello       world" "bar"
Called with 3 arguments, here quoted:
  Argument $1: 'foo'
  Argument $2: 'hello       world'
  Argument $3: 'bar'
------
echo "$0 ${argv[@]@Q}"
++ echo './argv '\''foo'\''' ''\''hello       world'\''' ''\''bar'\'''
./argv 'foo' 'hello       world' 'bar'
------
echo "$0 $@"
++ echo './argv foo' 'hello       world' bar
./argv foo hello       world bar
------
echo "$0 $*"
++ echo './argv foo hello       world bar'
./argv foo hello       world bar
```

