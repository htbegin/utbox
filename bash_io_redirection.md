# bash I/O redirection

## input redirection

```bash
grep SYSCALL_DEFINE[0-9] < fs/read_write.c
```

```bash
# The - option is used to supresses leading tabs (but not spaces) in the output.
cat <<-END
	Usage: bmetrics.sh [-n] [-v] [-a $act] -f file
	-n: no summary
	-v: be verbose
    -a $act: the start action, the default is $default_act
	-f file: the output of perf
END
```

```bash
# disable paramter substitution by quoting the magic string
cat <<'EOF'
#!/bin/sh
for i in $(seq 1 10)
do
    echo $i
done
EOF
```

```bash
bc <<< "1 + 2 * 3"
```

## block comment

```bash
: <<COMMENT
This can be used to characterize the distribution of block device I/O
sizes. To study I/O in more detail, see iosnoop(8).
COMMENT
```

