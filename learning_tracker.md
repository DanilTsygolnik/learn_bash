<a name="top"></a>
## Progress reports

Total hours &ndash; X (clean hours &ndash; x, n %)

<details>
<summary>Milestones</summary>

...

</details>

<a name="23-Jul-2023"></a>
### Sun, 23 Jul 2023 (+1.49h; r+1.71h)

Recently, I've been using division with real numbers quite frequently from the terminal. Yesterday, I added a couple of functions to my `~/.bashrc` configuration to speed up my workflow. &mdash; 0.66h
```bash
# Given a b, echo result of "a / b"
# Example: 'r/ 3 2' should return '1.50'
r/ () {
    echo $(bc <<< "scale=2; ${1} / ${2}")
}

# Given arbitrary arguments, echo their sum.
# Example: 'r+ 1.3. 2.2 3.1' should return '6.6'
r+ () {
    local total
    total=0
    for i in $@; do
        total=$(bc <<< "scale=2; $total + $i")
    done
    echo $total
}
```

I had to review my previous notes on the `bc` command while coding. Today, I created this git repository for organizing and sharing my Bash expertise. The [reference guide](./commands/bc.md) for the `bc` command is the first one in here. &mdash; 0.83h ([commit](https://github.com/DanilTsygolnik/learn_bash/commit/5681dbbce04c5075be06fdb2aa1e67ea7ead1215))

[back](#top)

---

<!-- day's note template

Paste the following command to @= register to create a link for the day's title
"<a name=\"".trim(system('date +"%d-%b-%Y"'))."\"><\/a>"
Paste the following command to @= register to create a title for the day
"### ".trim(system('date +"%a, %d %b %Y"'))

...

[back](#top)

---

-->
