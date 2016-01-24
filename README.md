# tapf

TAP producer for shell scripts

- 1 file 1 test
- exit code is test result

# Usage

```
$ echo "[ 0 != 1 ]" > test_1.sh
$ echo "[ 0 != 0 ]" > test_2.sh
$ echo "diff -u test_1.sh test_2.sh" > test_3.sh
$ tapf ./test_*.sh
TAP version 13
1..3
ok 1 - ./test_1.sh
not ok 2 - ./test_2.sh
not ok 3 - ./test_3.sh
  ---
  stdout: |
    --- test_1.sh       2016-01-24 23:34:58.000000000 +0900
    +++ test_2.sh       2016-01-24 23:34:58.000000000 +0900
    @@ -1 +1 @@
    -[ 0 != 1 ]
    +[ 0 != 0 ]
```
