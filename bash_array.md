# bash array

## sequence

### define

```bash
# it's optional
declare -a all_good_code
all_good_code=( "redis" "lua" "protocol-buf" )

all_tracer=( $(cat available_tracers) )

all_dbg_tool[0]="kprobe"
all_dbg_tool[1]="uprobe"
all_dbg_tool[2]="ftrace"

tools=([0]="awk" [1]="sed" [2]="grep")
```

### travel

```bash
# it's similar with the notation of positional parameters: $#, $@, $*
# the difference between $@ and $*: "$*" is treated as a single word,
# but "$@" is treated as a sequence of separated words
echo "tracer cnt is ${#all_tracer[@]}"
echo "first tracer is ${all_tracer[0]}"
for entry in "${all_tracer[@]}"
do
    echo $entry
done
```

### operation

```bash
tools[3]="git"
tools[4]="python"

# delete an element
unset tools[3]

# delete an array
unset tools

# copy an array
more=( "${tools[@]}" )
```

## associative array

### define

```bash
declare -A act2func
act2func[A]="block_bio_queue"
act2func[D]="block_rq_issue"
```

### iterate

```bash
echo "the number of act: ${#act2func[@]}"
for act in "${!act2func[@]}"
do
    echo "$act -> ${act2func[$act]}"
done

for func in "${act2func[@]}"
do
    echo "func $func"
done
```

### operations

```bash
act="C"
if test -z "${act2func[$act]}"
then
    echo "no act $act"
fi
```

